# Contributing to TreePlan

Thank you for your interest in contributing to TreePlan! This document provides guidelines and instructions for contributing.

## Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards other contributors

## How to Contribute

### Reporting Bugs

Before creating a bug report, please check existing issues to avoid duplicates.

**Good bug reports include:**
- Clear, descriptive title
- Steps to reproduce the issue
- Expected behavior vs. actual behavior
- Screenshots if applicable
- Excel version and operating system
- Add-in version

### Suggesting Features

Feature requests are welcome! Please:
- Use a clear, descriptive title
- Provide detailed explanation of the feature
- Explain why this feature would be useful
- Include examples or mockups if possible

### Pull Requests

1. **Fork the repository**
   ```bash
   git clone https://github.com/smrinalsingh/treeplan.git
   cd treeplan
   ```

2. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow the existing code style
   - Test your changes thoroughly
   - Update documentation as needed

4. **Commit your changes**
   ```bash
   git commit -m "Add feature: description"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**
   - Provide a clear description of changes
   - Reference any related issues
   - Include screenshots for UI changes

## Development Setup

### Prerequisites

- Microsoft Excel (2007 or later)
- Basic knowledge of VBA
- Text editor for XML editing (optional)

### File Structure

```
treeplan/
├── BYTreePlan.xlam       # Main add-in file (production)
├── BYTreePlan.xlsm       # Development workbook
├── docs/                 # Documentation and screenshots
├── README.md            # Main documentation
├── CONTRIBUTING.md      # This file
├── LICENSE              # MIT License
└── CHANGELOG.md         # Version history
```

### Working with VBA

The add-in consists of several VBA modules:

1. **ThisWorkbook**
   - Application event handlers
   - Ribbon initialization

2. **Macros**
   - Main functionality
   - Tree operations
   - UI callbacks

3. **ConfigForm**
   - Options dialog
   - Theme selection

4. **Other modules**
   - Helper functions
   - Utility code

### Modifying the Ribbon

The ribbon UI is defined in `customUI/customUI.xml` within the `.xlam` file:

1. Extract the file (rename to `.zip` and unzip)
2. Edit `customUI/customUI.xml`
3. Re-package (zip and rename to `.xlam`)

**Note**: Be careful with XML syntax. Invalid XML will prevent the add-in from loading.

### Testing

Test your changes with:
- Multiple Excel versions if possible
- Both Windows and macOS if available
- Different tree sizes and configurations
- Edge cases (empty trees, maximum branches, etc.)

### Building for Release

1. Make changes in `BYTreePlan.xlsm`
2. Test thoroughly
3. Save as `BYTreePlan.xlam` (Excel Add-in format)
4. Update version information
5. Update CHANGELOG.md

## Coding Guidelines

### VBA Style

```vba
' Use clear, descriptive names
Sub CreateDecisionNode()
    ' Add comments for complex logic
    Dim nodeType As String
    
    ' Use error handling
    On Error GoTo ErrorHandler
    
    ' Your code here
    
    Exit Sub
    
ErrorHandler:
    MsgBox "Error: " & Err.Description
End Sub
```

### Best Practices

- **Error Handling**: Always include error handling in public subs
- **Variable Naming**: Use descriptive names (camelCase for VBA)
- **Comments**: Comment complex logic, not obvious code
- **Modularity**: Keep functions focused on single tasks
- **Testing**: Test all code paths

### XML/Ribbon Guidelines

- Use proper indentation
- Validate XML syntax
- Follow Office Fluent UI naming conventions
- Include `imageMso` for built-in icons

## Documentation

Update documentation when you:
- Add new features
- Change existing behavior
- Fix bugs that affect usage
- Modify installation process

## Questions?

If you have questions:
- Open an issue with the `question` label
- Provide context about what you're trying to do
- Include relevant code or screenshots

## Recognition

Contributors will be acknowledged in:
- Release notes
- Project README (for significant contributions)

Thank you for contributing to TreePlan! 🎉
