# Neonite Theme

A vibrant and modern dark theme for Visual Studio Code, featuring a sleek dark background with neon-inspired syntax highlighting. Designed for enhanced readability and visual appeal across all programming languages, with special optimizations for JavaScript, TypeScript, Python, Rust, Go, and web development.

## Installation

### From VS Code Marketplace

1. Open **VS Code**.
2. Go to the **Extensions** view (`Ctrl+Shift+X` or `Cmd+Shift+X` on Mac).
3. Search for **Neonite Theme**.
4. Click **Install**.
5. Once installed, go to **File > Preferences > Color Theme** (`Ctrl+K Ctrl+T`) and select **Neonite**.

### Testing Offline (Development/Preview)

X

1. Clone or download this repository.
2. Copy the theme folder to your VS Code extensions directory:
   - **Windows**: `%USERPROFILE%\.vscode\extensions\`
   - **macOS**: `~/.vscode/extensions/`
   - **Linux**: `~/.vscode/extensions/`
3. Restart VS Code.
4. Go to **File > Preferences > Color Theme** and select **Neonite**.

### Alternative Installation Method

1. Open VS Code.
2. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac) to open the command palette.
3. Type "Install from VSIX" and select the command.
4. Browse to the `.vsix` file (if available) and install.

## Features

- **Modern Dark Aesthetic**: Deep dark background (`#0A0E14`) with vibrant neon accents for optimal contrast and readability
- **Neon Syntax Highlighting**: Beautiful color scheme with green functions, purple operators, cyan types, and orange parameters
- **Multi-Language Support**: Optimized for JavaScript, TypeScript, Python, Rust, Go, Java, C/C++, PHP, and more
- **Enhanced Markup Support**: Special styling for HTML, JSX/TSX, CSS, Markdown, and documentation
- **Semantic Token Support**: Advanced highlighting using VS Code's semantic tokenization
- **Custom Icon Integration**: Includes Neonite-themed file and product icons for a cohesive experience
- **Eye-Friendly**: Carefully chosen colors to reduce eye strain during long coding sessions
- **Highly Customizable**: Easy to modify colors and styles to match your preferences

## Screenshots

![Neonite Theme Preview](images/preview.png)

_Neonite theme showcasing JavaScript/TypeScript syntax highlighting_

## Color Palette

The Neonite theme uses a carefully curated color palette designed for optimal readability and visual appeal:

### Core Colors

- **Background**: `#0A0E14` (Deep Dark Blue)
- **Foreground**: `#F0F4FC` (Light Blue-White)
- **Comments**: `#4A4F5B` (Muted Gray)
- **Selection**: `#2D3546` (Dark Blue-Gray)

### Syntax Colors

- **Keywords**: `#FF6E6E` (Coral Red) - Bold
- **Strings**: `#FFE68A` (Warm Yellow)
- **Functions**: `#76FF8F` (Bright Green) - Bold
- **Variables**: `#F0F4FC` (Light Blue-White)
- **Constants**: `#B28CFF` (Purple)
- **Types**: `#6CF3FF` (Cyan)
- **Operators**: `#9D6CFF` (Purple) - Bold
- **Parameters**: `#FF9F43` (Orange) - Italic
- **Properties**: `#FF92DF` (Pink)
- **Numbers**: `#B28CFF` (Purple)
- **Decorators**: `#9D6CFF` (Purple) - Italic

### UI Colors

- **Activity Bar**: `#0A0E14` with `#9D6CFF` accents
- **Sidebar**: `#0A0E14` with subtle borders
- **Tabs**: Active tab `#1A1E24`, inactive `#0A0E14`
- **Status Bar**: `#1A1E24` with colorful indicators
- **Terminal**: Full 16-color ANSI support with neon variants

## Recommended Icon Themes

Neonite comes with custom-designed icon themes that perfectly complement the dark aesthetic:

- **Neonite Icons**: Custom file icons with vibrant colors matching the theme palette
- **Neonite Product Icons**: Cohesive UI icons for a consistent visual experience

These icon themes are automatically included with the theme installation and provide enhanced visual consistency across your VS Code interface.

## Language Support

Neonite provides specialized syntax highlighting for:

### Web Development

- **JavaScript/TypeScript**: Enhanced support for ES6+, JSX, and TypeScript features
- **HTML/CSS**: Beautiful tag and property highlighting
- **React/Vue/Svelte**: Framework-specific component styling
- **JSON/YAML**: Clear data structure visualization

### Systems Programming

- **Rust**: Lifetime annotations, macros, and ownership highlighting
- **Go**: Package imports, interfaces, and goroutine support
- **C/C++**: Preprocessor directives and memory management
- **Java**: Annotations, generics, and OOP features

### Scripting & Data

- **Python**: Decorators, f-strings, and data science libraries
- **PHP**: Modern PHP features and web development
- **Shell/Bash**: Command highlighting and variable expansion
- **SQL**: Query syntax and database operations

### Markup & Documentation

- **Markdown**: Headers, links, code blocks, and formatting
- **Git**: Commit messages and diff highlighting
- **Docker**: Dockerfile instructions and container syntax
- **GraphQL**: Schema definitions and query operations

## Development & Testing

### Testing the Theme Locally

1. **Clone the repository**:

   ```bash
   git clone https://github.com/MoElsherbiny/vscode-neonite-theme.git
   cd vscode-neonite-theme
   ```

2. **Install dependencies** (if any):

   ```bash
   npm install
   ```

3. **Build the theme** (if needed):

   ```bash
   npm run build
   ```

4. **Install locally**:
   - Copy the entire theme folder to your VS Code extensions directory
   - Or use the VS Code extension development host by pressing `F5` in the theme project

### Creating a VSIX Package

1. **Install vsce** (Visual Studio Code Extension):

   ```bash
   npm install -g vsce
   ```

2. **Package the extension**:

   ```bash
   vsce package
   ```

3. **Install the VSIX**:
   - Open VS Code
   - Run `code --install-extension neonite-theme-x.x.x.vsix`

### Contributing

We welcome contributions! To contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes to the theme files
4. Test thoroughly with different languages
5. Commit your changes: `git commit -m 'Add amazing feature'`
6. Push to the branch: `git push origin feature/amazing-feature`
7. Open a Pull Request

## Customization

### Modifying Colors

You can customize the theme by editing the `themes/dark-color-theme.json` file:

```json
{
  "colors": {
    "editor.background": "#0A0E14",
    "editor.foreground": "#F0F4FC"
  },
  "tokenColors": [
    {
      "scope": ["keyword"],
      "settings": {
        "foreground": "#FF6E6E",
        "fontStyle": "bold"
      }
    }
  ]
}
```

### Adding New Language Support

To add support for a new language:

1. Identify the TextMate scopes for the language
2. Add corresponding entries to the `tokenColors` array
3. Test with sample code files
4. Update the README with the new language support

## Recommended Settings

To get the most out of the Neonite theme, add these settings to your VS Code `settings.json` file:

```json
{
  "editor.fontFamily": "'JetBrains Mono', 'Fira Code', 'Cascadia Code', 'SF Mono', Consolas, monospace",
  "editor.fontSize": 14,
  "editor.fontLigatures": true,
  "editor.lineHeight": 1.6,
  "editor.cursorBlinking": "smooth",
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.smoothScrolling": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": "active",
  "editor.guides.highlightActiveIndentation": true,
  "editor.semanticHighlighting.enabled": true,
  "editor.tokenColorCustomizations": {
    "[Neonite]": {
      "textMateRules": []
    }
  },
  "workbench.colorTheme": "Neonite",
  "workbench.iconTheme": "neonite-icons",
  "workbench.productIconTheme": "neonite-product-icons",
  "terminal.integrated.fontFamily": "'JetBrains Mono', 'Fira Code', Consolas, monospace",
  "terminal.integrated.fontSize": 13,
  "terminal.integrated.cursorBlinking": true,
  "terminal.integrated.cursorStyle": "line"
}
```

## Troubleshooting

### Theme Not Appearing

- Ensure the theme is properly installed in your extensions folder
- Restart VS Code completely
- Check if there are any conflicting themes installed

### Colors Not Displaying Correctly

- Verify that semantic highlighting is enabled: `"editor.semanticHighlighting.enabled": true`
- Some languages may require specific extensions for full syntax support
- Check if your file has the correct language mode selected

### Performance Issues

- The theme uses semantic tokens which may impact performance on very large files
- Consider adjusting `editor.semanticHighlighting.enabled` if needed
- Large files may benefit from `"editor.largeFileOptimizations": true`

## License

MIT License - feel free to use, modify, and distribute this theme.

## Credits

Created with ❤️ by **Mohamed Elsherbiny**

Special thanks to the VS Code team for the excellent theming API and the community for inspiration and feedback.

## Support

- **Issues**: [GitHub Issues](https://github.com/MoElsherbiny/vscode-neonite-theme/issues)
- **Discussions**: [GitHub Discussions](https://github.com/MoElsherbiny/vscode-neonite-theme/discussions)
- **Rating**: If you enjoy this theme, please leave a rating on the VS Code Marketplace!

---

**Enjoy coding with Neonite! 🚀**
