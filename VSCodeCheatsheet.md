# VS Code Essential Features Cheatsheet

## Editor Basics & Navigation

### Command Palette
- **Shortcut**: `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
- **What it does**: Opens a command search bar that gives you access to virtually all VS Code functionality.
- **How to use it**: Type what you want to do in plain language (e.g., "format document" or "git commit"). This is the most powerful feature to learn in VS Code.

### Quick Open Files
- **Shortcut**: `Ctrl+P` (Windows/Linux) or `Cmd+P` (Mac)
- **What it does**: Quickly open files in your project without using the file explorer.
- **How to use it**: Type part of a filename to see matching results. Add `>` to access commands, `@` to navigate to symbols within a file, or `#` to search by text.

### Multi-cursor Editing
- **Methods**:
  - `Alt+Click` (Windows/Linux) or `Opt+Click` (Mac): Add cursors at clicked positions
  - `Ctrl+Alt+Up/Down` (Windows/Linux) or `Cmd+Opt+Up/Down` (Mac): Add cursors above/below
  - `Alt+Shift+I` (Windows/Linux) or `Opt+Shift+I` (Mac): Add cursors at the end of each line in a selection
- **What it does**: Edit multiple lines simultaneously.
- **How to use it**: Select text that appears multiple times, then use the shortcuts to add cursors at each occurrence. Perfect for renaming variables or making consistent edits.

### Split Editor
- **Shortcut**: `Ctrl+\` (Windows/Linux) or `Cmd+\` (Mac)
- **What it does**: Splits the editor to view multiple files side by side.
- **How to use it**: Use when comparing code, referencing documentation, or working on related files. Drag tabs between split panes to organize your workspace.

### Zen Mode
- **Shortcut**: `Ctrl+K Z` (Windows/Linux) or `Cmd+K Z` (Mac)
- **What it does**: Removes distractions by hiding all UI elements except the editor.
- **How to use it**: Perfect for focused coding sessions. Press `Esc` twice to exit.

## Code Editing & Manipulation

### IntelliSense
- **Activation**: Automatic or `Ctrl+Space` (Windows/Linux) or `Cmd+Space` (Mac)
- **What it does**: Provides code completion, parameter info, quick info, and member lists.
- **How to use it**: As you type, suggestions appear automatically. Use arrow keys to navigate the suggestions and `Tab` or `Enter` to accept. Hover over code for more information.

### Code Formatting
- **Shortcut**: `Shift+Alt+F` (Windows/Linux) or `Shift+Opt+F` (Mac)
- **What it does**: Automatically formats your document according to language-specific rules.
- **How to use it**: Run on messy code to clean up indentation, spacing, and syntax. For partial formatting, select code first then use the shortcut.

### Code Folding
- **Shortcuts**:
  - Fold: `Ctrl+Shift+[` (Windows/Linux) or `Cmd+Opt+[` (Mac)
  - Unfold: `Ctrl+Shift+]` (Windows/Linux) or `Cmd+Opt+]` (Mac)
  - Fold All: `Ctrl+K Ctrl+0` (Windows/Linux) or `Cmd+K Cmd+0` (Mac)
  - Unfold All: `Ctrl+K Ctrl+J` (Windows/Linux) or `Cmd+K Cmd+J` (Mac)
- **What it does**: Collapses code blocks (functions, loops, etc.) to improve readability.
- **How to use it**: Fold sections you're not currently working on to focus on active code. Click the `-` and `+` symbols in the gutter to fold/unfold manually.

### Code Navigation
- **Shortcuts**:
  - Go to Definition: `F12`
  - Peek Definition: `Alt+F12` (Windows/Linux) or `Opt+F12` (Mac)
  - Go to References: `Shift+F12`
  - Go to Symbol: `Ctrl+Shift+O` (Windows/Linux) or `Cmd+Shift+O` (Mac)
- **What it does**: Jump to definitions, implementations, and references within your codebase.
- **How to use it**: Place cursor on a variable, function, or class name, then use the appropriate shortcut to navigate to related code.

### Refactoring
- **Shortcuts**:
  - Rename Symbol: `F2`
  - Extract Method/Variable: `Ctrl+Shift+R` (Windows/Linux) or `Cmd+Shift+R` (Mac)
- **What it does**: Safely rename variables, functions, and classes across your project.
- **How to use it**: Place cursor on the symbol you want to rename, press `F2`, type the new name, and press `Enter`. VS Code automatically updates all references.

## Search & Replace

### Global Search
- **Shortcut**: `Ctrl+Shift+F` (Windows/Linux) or `Cmd+Shift+F` (Mac)
- **What it does**: Search across all files in your project.
- **How to use it**: Enter your search term, use regex if needed, and filter by files to include/exclude. Results appear in a panel with context, allowing you to navigate to specific instances.

### Global Replace
- **Shortcut**: `Ctrl+Shift+H` (Windows/Linux) or `Cmd+Shift+H` (Mac)
- **What it does**: Search and replace text across all files in your project.
- **How to use it**: Enter search term and replacement text. Use the preview to verify changes before applying them. Supports regex for complex replacements.

### Find in Current File
- **Shortcut**: `Ctrl+F` (Windows/Linux) or `Cmd+F` (Mac)
- **What it does**: Search within the current file.
- **How to use it**: Type search term, use `F3` (Windows/Linux) or `Cmd+G` (Mac) to cycle through matches. Enable regex for advanced searching.

## File Management

### Explorer View
- **Shortcut**: `Ctrl+Shift+E` (Windows/Linux) or `Cmd+Shift+E` (Mac)
- **What it does**: Shows the file explorer panel.
- **How to use it**: Navigate your project's file structure. Right-click for context menu options like creating new files, copying paths, etc.

### Quick File Operations
- **Operations**:
  - New File: `Ctrl+N` (Windows/Linux) or `Cmd+N` (Mac)
  - Save: `Ctrl+S` (Windows/Linux) or `Cmd+S` (Mac)
  - Save All: `Ctrl+K S` (Windows/Linux) or `Cmd+K S` (Mac)
  - Close Editor: `Ctrl+W` (Windows/Linux) or `Cmd+W` (Mac)
  - Reopen Closed Editor: `Ctrl+Shift+T` (Windows/Linux) or `Cmd+Shift+T` (Mac)
- **How to use it**: Learn these shortcuts to speed up common file operations without using the mouse.

## Terminal & Debugging

### Integrated Terminal
- **Shortcut**: `` Ctrl+` `` (Windows/Linux) or `` Cmd+` `` (Mac)
- **What it does**: Opens the built-in terminal.
- **How to use it**: Run commands without leaving VS Code. Create multiple terminals with the `+` button in the terminal panel. Split terminals with the split icon.

### Debugging
- **Shortcuts**:
  - Start/Continue: `F5`
  - Stop: `Shift+F5`
  - Step Over: `F10`
  - Step Into: `F11`
  - Step Out: `Shift+F11`
  - Toggle Breakpoint: `F9`
- **What it does**: Runs your application in debug mode, allowing you to step through code and inspect variables.
- **How to use it**: Set breakpoints by clicking in the gutter or using `F9`. Press `F5` to start debugging. Use the Debug panel to watch variables and evaluate expressions.

## Extensions & Customization

### Extension Marketplace
- **Shortcut**: `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac)
- **What it does**: Opens the Extensions panel to browse and install extensions.
- **How to use it**: Search for extensions by name or category. Read reviews and documentation before installing. Click the gear icon on installed extensions for configuration options.

### Settings
- **Shortcut**: `Ctrl+,` (Windows/Linux) or `Cmd+,` (Mac)
- **What it does**: Opens the Settings editor.
- **How to use it**: Customize VS Code behavior. Search for settings using the search bar. Switch between UI and JSON views with the button in the top-right corner.

### User Snippets
- **Access**: Command Palette → "Preferences: Configure User Snippets"
- **What it does**: Creates reusable code templates.
- **How to use it**: Create snippets for frequently used code patterns. Define tab triggers, descriptions, and the code template with placeholders. Use `$1`, `$2`, etc. for tabstop positions.

## Git Integration

### Source Control Panel
- **Shortcut**: `Ctrl+Shift+G` (Windows/Linux) or `Cmd+Shift+G` (Mac)
- **What it does**: Opens the Git panel to manage version control.
- **How to use it**: View changes, stage files, commit, pull, push, and resolve conflicts—all without leaving VS Code.

### Git Commands
- **Operations**:
  - Stage Changes: Click `+` next to modified files
  - Commit: Type commit message and press `Ctrl+Enter`
  - View Diff: Click on modified files
  - Git History: Command Palette → "Git: View History"
- **How to use it**: Incorporate version control into your workflow. Use the Git panel for common operations and the Command Palette for more advanced tasks.

### Gutter Indicators
- **What they show**: Changes compared to the last commit (new, modified, deleted).
- **How to use them**: Quickly identify what's changed in your file. Green: new lines, blue: modified lines, red: deleted lines. Click indicators to see the diff.

## Keyboard Shortcuts (Most Essential)

### General
- Save: `Ctrl+S` (Windows/Linux) or `Cmd+S` (Mac)
- Cut/Copy/Paste: `Ctrl+X/C/V` (Windows/Linux) or `Cmd+X/C/V` (Mac)
- Undo/Redo: `Ctrl+Z` / `Ctrl+Y` (Windows/Linux) or `Cmd+Z` / `Cmd+Shift+Z` (Mac)
- Open Settings: `Ctrl+,` (Windows/Linux) or `Cmd+,` (Mac)

### Selection
- Select All: `Ctrl+A` (Windows/Linux) or `Cmd+A` (Mac)
- Select Word: `Ctrl+D` (Windows/Linux) or `Cmd+D` (Mac)
- Select Line: `Ctrl+L` (Windows/Linux) or `Cmd+L` (Mac)
- Select All Occurrences: `Ctrl+Shift+L` (Windows/Linux) or `Cmd+Shift+L` (Mac)

### Navigation
- Go to Line: `Ctrl+G` (Windows/Linux) or `Cmd+G` (Mac)
- Go to File: `Ctrl+P` (Windows/Linux) or `Cmd+P` (Mac)
- Go to Symbol: `Ctrl+Shift+O` (Windows/Linux) or `Cmd+Shift+O` (Mac)
- Go Back/Forward: `Alt+Left/Right` (Windows/Linux) or `Ctrl+- / Ctrl+Shift+-` (Mac)

### Pro Tips

1. **Customize Your Shortcuts**: The most efficient workflow comes from personalized shortcuts. Open the Keyboard Shortcuts editor (`Ctrl+K Ctrl+S` / `Cmd+K Cmd+S`) and modify shortcuts to match your preferences.

2. **Learn Incrementally**: Don't try to memorize all shortcuts at once. Focus on 3-5 new shortcuts per week and practice them until they become muscle memory.

3. **Use Workspaces**: For complex projects, create workspaces to save window layouts, open files, and project-specific settings.

4. **Extension Syncing**: Enable Settings Sync (`Ctrl+Shift+P` → "Settings Sync: Turn On") to keep your extensions and settings consistent across different machines.

5. **Keyboard Reference Sheet**: Press `Ctrl+K Ctrl+R` (Windows/Linux) or `Cmd+K Cmd+R` (Mac) to open a printable keyboard shortcut reference sheet.
