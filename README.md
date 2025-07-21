# Directory Colorizer

A simple VS Code extension that colors your title bar based on workspace directory patterns.

## Features

- **🎨 Simple Path → Color Mapping**: Just map directory patterns to hex colors
- **📁 Automatic Detection**: Colors applied automatically when workspace opens
- **⚙️ Flexible Matching**: Contains, exact match, or ends-with patterns

## Configuration

### Settings UI
Open VS Code Settings and search for "Directory Colorizer":

- **Path Color Mappings**: Simple object mapping path patterns to colors
- **Path Matching Method**: How to match patterns (contains/exact/endsWith) 
- **Case Sensitive Matching**: Enable/disable case sensitivity
- **Auto Apply Colors**: Automatic color application on workspace open

### Example Configuration

```json
{
    "directoryColorizer.pathColors": {
        "my-project": "#33cc33",
        "work": "#3333cc", 
        "client-abc": "#cc3333",
        "frontend": "#cc8800"
    },
    "directoryColorizer.matchType": "contains",
    "directoryColorizer.caseSensitive": false,
    "directoryColorizer.autoApply": true
}
```

This will color your title bar:
- **Green** when path contains "my-project"
- **Blue** when path contains "work"
- **Red** when path contains "client-abc"
- **Orange** when path contains "frontend"

## Commands

Access via Command Palette (`Ctrl/Cmd+Shift+P`):

- **Directory Colorizer: Update Colors** - Force apply colors to current workspace
- **Directory Colorizer: Reset Colors** - Remove color customizations
- **Directory Colorizer: Add Current Path** - Quick setup for current workspace

## Usage

### Automatic Mode (Default)
1. Configure your path patterns in settings
2. Open any workspace that matches your patterns
3. Title bar colors applied automatically!

### Quick Setup
1. Open a workspace you want to colorize
2. Run **Directory Colorizer: Add Current Path** command
3. Enter a path pattern and hex color
4. Colors applied immediately!

## Path Matching

**Contains** (default): Path contains pattern anywhere
- Pattern `"react"` matches `/home/user/my-react-app/`

**Exact**: Path exactly matches pattern  
- Pattern `"/home/user/work"` matches only that exact path

**Ends With**: Path ends with pattern
- Pattern `"-dev"` matches `/projects/my-app-dev/`


## Installation

### From Marketplace
1. Open VS Code Extensions (`Ctrl+Shift+X`)
2. Search for "Directory Colorizer"
3. Install and reload

### From VSIX
```bash
code --install-extension directory-colorizer-1.2.0.vsix
```

## Requirements

- VS Code 1.74.0 or higher

## What's Colored

This extension only colors the **title bar** (`titleBar.activeBackground`). It won't interfere with your editor theme, sidebar, or other UI elements - just provides a subtle visual indicator of which project you're working on.