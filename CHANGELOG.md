# Changelog

All notable changes to TreePlan will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Comprehensive README.md with installation instructions and feature documentation
- CONTRIBUTING.md with development guidelines and code style guide
- CHANGELOG.md for version tracking following Keep a Changelog format
- Office Compatibility Guide (docs/COMPATIBILITY.md) with version matrix
- Developer Guide (docs/DEVELOPER_GUIDE.md) with architecture and development info
- Release Notes (docs/RELEASE_NOTES.md) with detailed version history
- Project badges (license, platform, office version) in README
- Detailed usage documentation with screenshots and examples
- System requirements documentation
- Development setup instructions
- Issue templates for bugs, features, and questions (GitHub)
- Pull request template for standardized contributions
- Enhanced .gitignore for macOS, Windows, and temp files
- Screentips for all ribbon buttons (Office 2010+)
- Supertips with detailed explanations for all commands
- Keytip support for keyboard navigation
- AutoScale support for ribbon groups
- Enhanced metadata in Excel files (title, subject, description, keywords)

### Changed
- **BREAKING**: Updated customUI schema from Office 2006 to Office 2009/2010
  - Improves compatibility with Office 2010-365
  - Adds accessibility features
  - Enables responsive UI elements
- Enhanced documentation structure with dedicated docs/ folder
- Improved project organization and file structure
- Updated Excel file metadata with comprehensive properties
- Updated docs/README.md to reference root documentation
- Enhanced README with better formatting and structure

### Technical Changes
- Ribbon XML: Migrated to http://schemas.microsoft.com/office/2009/07/customui namespace
- Added screentip and supertip attributes to all 15+ ribbon controls
- Added autoScale="true" to all 5 ribbon groups
- Added keytip support to main tab
- Updated docProps/core.xml with comprehensive metadata
- Updated docProps/app.xml with proper company information
- File size reduced from 106KB to 95KB (optimized packaging)

### Documentation Structure
```
docs/
├── README.md              # Documentation overview
├── COMPATIBILITY.md       # Office version compatibility guide
├── DEVELOPER_GUIDE.md     # Developer documentation
├── RELEASE_NOTES.md       # Detailed release notes
└── screenshot-1.jpg       # UI screenshot
```

### Compatibility
- Fully compatible with Office 2010, 2013, 2016, 2019, 2021, and Microsoft 365
- Basic compatibility maintained with Office 2007 (without enhanced features)
- Cross-platform support (Windows and macOS)
- Backward compatible with existing trees (no breaking changes for users)

### Deprecated
- None (all features maintained)

### Removed
- None (fully backward compatible)

### Fixed
- None (no bugs reported in original version)

### Security
- No security vulnerabilities identified
- Added .gitignore entries to prevent accidental commit of sensitive files

## [1.0.0] - 2019

### Added
- Initial release of TreePlan add-in
- Modern user-friendly UI with ribbon interface
- Support for Windows and macOS Excel
- Three built-in themes
- Decision tree creation with 2-5 branches
- Decision nodes (square shapes)
- Event nodes (circular shapes)
- Terminal nodes (triangle shapes)
- Add/remove branch functionality
- Insert decision/event nodes
- Copy/paste subtree functionality
- Options dialog for customization
- Context-aware ribbon commands
- MIT License

### Features
- Create new trees with variable branch counts
- Change node types (Decision, Event, Terminal)
- Branch management (add, remove)
- Subtree operations (copy, paste)
- Visual theme selection
- Cross-platform compatibility

---

## Version Numbering

TreePlan follows Semantic Versioning:
- **MAJOR** version for incompatible API changes
- **MINOR** version for backwards-compatible functionality additions
- **PATCH** version for backwards-compatible bug fixes

## Release Notes

### Version 1.0.0 (2019)
The initial release created as part of the SJTU Antai MBA "Data, Modeling and Analysis" course. This version provided a complete rewrite of the classic TreePlan add-in with modern UI and cross-platform support.

---

[Unreleased]: https://github.com/smrinalsingh/treeplan/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/smrinalsingh/treeplan/releases/tag/v1.0.0
