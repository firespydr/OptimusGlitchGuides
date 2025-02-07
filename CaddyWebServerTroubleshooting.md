# Troubleshooting Guide for Caddy with Podman

## 1. Configuration File (Caddyfile)

### File Mounting & Location
- **Ensure Proper Mounting:**  
  Verify that your host’s Caddyfile (for example, stored at `~/caddy/config/Caddyfile`) is correctly mounted into the container at `/etc/caddy/Caddyfile`.
  
- **Check the File Content:**  
  Run the following command to inspect the file’s content inside the container:
  ```bash
  podman exec -it <container_id> cat /etc/caddy/Caddyfile
  ```

### Formatting & Line Endings
- **Format Your Caddyfile:**  
  Use the Caddy formatting command to automatically fix any inconsistencies:
  ```bash
  caddy fmt --overwrite /etc/caddy/Caddyfile
  ```
  You can run this either inside the container or on your host before mounting.

- **Ensure Correct Line Endings:**  
  If you’re editing on Windows, make sure the file uses LF (not CRLF). Tools like `dos2unix` can help you convert the file if necessary.

### Site Block and SNI
- **Domain Matching:**  
  If your Caddyfile defines a block for a specific domain (e.g., `techpro.com { … }`), ensure that your requests include that exact Host header.  
  For testing purposes, consider using a catch‑all block:
  ```caddy
  :443 {
      # Your configuration here
  }
  ```
  Alternatively, add an entry in your hosts file mapping the domain to your server’s public IP.

- **TLS Testing Note:**  
  Remember, when testing TLS, Caddy’s internal CA issues certificates based on the domain in the Caddyfile. Connecting by IP or “localhost” might cause TLS handshake failures due to certificate mismatches.

---

## 2. TLS and Certificate Issues

### TLS Configuration
- **Certificate Generation:**  
  If you’re using `tls internal`, check that Caddy is indeed generating a certificate for the intended domain. Look in the logs for messages about certificate installation.

- **Verify SNI Usage:**  
  Errors such as “TLS alert, internal error” or certificate verification failures may indicate that the correct SNI (e.g., `techpro.com`) isn’t being used. Double-check your request headers accordingly.

- **Production Considerations:**  
  In production, decide whether you want to trust Caddy’s internal CA (by installing its root certificate on client devices) or use Let’s Encrypt—which requires your domain to be publicly resolvable.

### Testing with SNI Overrides
- **Force SNI with Curl:**  
  You can force the proper SNI using the `--resolve` flag in curl:
  ```bash
  curl -4vk --resolve techpro.com:8443:<public_ip> https://techpro.com:8443
  ```
  If this command succeeds but connections by IP or “localhost” fail, the issue is likely related to SNI/certificate matching.

---

## 3. Network, Port Mapping, and Firewall

### Port Mapping
- **Verify Container Ports:**  
  Ensure your container’s port mapping is correct (e.g., container port `443` → host port `8443`). You can check this by running:
  ```bash
  podman ps
  ```

- **Check Host Port Bindings:**  
  Confirm on the host that the mapped port is open:
  ```bash
  sudo ss -tulpn | grep 8443
  ```

### Firewall/NAT
- **Update Firewall Rules:**  
  Make sure your host firewall (for example, using `ufw`) allows traffic on the necessary ports:
  ```bash
  sudo ufw allow 8443/tcp
  sudo ufw allow 8080/tcp
  sudo ufw reload
  ```
- **Cloud/Router Settings:**  
  In cloud environments or behind NAT, verify that no additional rules are blocking these ports.

---

## 4. DNS and Client Resolution

### DNS Records vs. Hosts File
- **Check Your DNS Settings:**  
  Tools like `nslookup` will use authoritative DNS settings (ignoring local hosts file entries), so verify that your domain’s A record correctly points to your public IP.

- **Temporary Hosts File Entry:**  
  For testing, you might add an entry in your hosts file on the client machine:
  ```plaintext
  <public_ip>   techpro.com
  ```

### Browser Cache and HSTS
- **Clear Cache and HSTS:**  
  If previous failed attempts might be cached, clear your browser cache and HSTS settings. Alternatively, test your setup using incognito mode or a different browser.

---

## 5. Log and Diagnostic Checks

### Examine Caddy Logs
- **Review Logs for Clues:**  
  Look at the container logs for warnings related to formatting, TLS handshake issues, or certificate errors:
  ```bash
  podman logs <container_id>
  ```

### Local vs. External Testing
- **Test Locally:**  
  Run a local test on your host:
  ```bash
  curl -4vk https://localhost:8443
  ```
- **Test Externally:**  
  Also test using the public IP and domain (with SNI forced via `--resolve`) to confirm consistent behavior across environments.
