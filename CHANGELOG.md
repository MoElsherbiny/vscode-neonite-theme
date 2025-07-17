# Changelog

All notable changes to this project will be documented in this file.

## [1.3.0] - 2025-07-16

### Updated for Latest VS Code

- **Updated engine requirements**: Now requires VS Code 1.74.0 or higher for optimal compatibility
- **Enhanced product icon support**: Added more icon mappings for latest VS Code UI elements
- **Improved icon coverage**: Added support for:
  - Git integration icons (branch, commit, pull request)
  - Modern toolbar and panel controls
  - Split view and layout management icons
  - View-specific icons for all panels
  - Zoom and navigation controls
- **Updated documentation**: Added clear VS Code update instructions
- **Better error messaging**: Clear warnings for users with outdated VS Code versions

### Technical Improvements

- Updated product icon definitions to use latest VS Code API
- Added comprehensive icon mappings for modern VS Code features
- Enhanced compatibility with VS Code 1.74.0+ features
- Improved theme packaging and distribution

### Migration Guide

**Important**: If you're using VS Code 1.1.6 or older, you must update to VS Code 1.74.0+ to use product icons:

1. Download latest VS Code from [code.visualstudio.com](https://code.visualstudio.com)
2. Install over existing version
3. Restart VS Code
4. Install Neonite theme v1.3.0
5. Enable product icons in preferences

## [1.2.1] - 2025-07-16

### Fixed

- **Fixed product icons not applying**: Updated icon definitions format
- **Simplified configuration**: Removed unnecessary mappings
- **Updated documentation**: Added version requirements

## [1.2.0] - 2025-07-16

### Fixed

- **Fixed product icons not applying**: Product icons were not being applied correctly due to incorrect icon definitions
- **Updated icon mappings**: Fixed all product icon identifiers to match VS Code's expected names
- **Removed invalid configuration**: Removed the unnecessary `fonts` section from product icons configuration
- **Improved icon coverage**: Added proper mappings for all VS Code UI elements including:
  - Activity bar icons (explorer, search, debug, extensions, source control, settings)
  - Debug controls (play, pause, stop, restart, step controls)
  - Editor actions (add, close, edit, save, trash)
  - Status indicators (error, warning, info, check)
  - Terminal and panel icons
  - File browser actions
- **Enhanced documentation**: Added detailed instructions for enabling product icons in README

### Technical Improvements

- Cleaned up package to remove large unnecessary files
- Added proper `.vscodeignore` file to exclude development files
- Reduced package size from 21MB to 2MB
- Fixed JSON structure for product icons configuration

## [1.1.0] - 2025-07-16

### Enhanced Product Icons

- **Complete redesign** of product icons with modern neon aesthetic
- **Improved visual consistency** across all VS Code interface elements
- **Added animated effects** including glowing, pulsing, and subtle animations
- **Enhanced icon coverage** with 25+ new/updated product icons:
  - Terminal, Problems, Output, Debug Console
  - Run, Stop, Pause, Restart controls
  - Debug step controls (Step Over, Step Into, Step Out)
  - Breakpoint with modern styling
  - File browser icons (Folder, File)
  - Utility icons (Refresh, Sync, Lightbulb)
  - User interface icons (Notifications, Accounts, Remote, Layout, Feedback)
- **Gradient and glow effects** for better visual hierarchy
- **Improved accessibility** with better contrast and visual cues
- **SVG-based icons** for crisp display at all zoom levels
- **Consistent color palette** matching the Neonite theme aesthetic

### Technical Improvements

- Migrated from font-based to SVG-based product icons
- Enhanced icon definitions with proper path references
- Improved animation timing and effects
- Better filter definitions for glow effects
