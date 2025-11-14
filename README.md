# TreePlan - Modern Excel Add-in for Decision Trees

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Office Version](https://img.shields.io/badge/Office-2007%2B-blue.svg)](https://www.microsoft.com/en-us/microsoft-365)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-lightgrey.svg)](https://github.com/smrinalsingh/treeplan)

A modern, free, and user-friendly Excel add-in for creating and managing decision trees. Perfect for decision analysis, project management, and risk assessment.

![TreePlan Screenshot](docs/screenshot-1.jpg)

## Features

✨ **Modern User Interface**
- Clean, intuitive ribbon-based interface
- Context-aware commands
- Multiple tree creation options (2-5 branches)

🎨 **Three Built-in Themes**
- Professional visual styles
- Customizable appearance
- Publication-ready output

🖥️ **Cross-Platform Support**
- Works on Windows Excel 2007 and later
- Fully compatible with macOS Excel
- Supports Office 2019, 2021, and Microsoft 365

💰 **Free Forever**
- MIT License
- No subscription required
- Open source and community-driven

## Installation

### Method 1: Download and Install

1. Download the latest `BYTreePlan.xlam` file from the [Releases](../../releases) page

2. **On macOS:**
   - Open Excel
   - Go to **Tools** → **Excel Add-ins**
   - Click **Browse** and select the downloaded file
   - Check the box next to "BYTreePlan" to enable it

3. **On Windows:**
   - Open Excel
   - Click **File** → **Options** → **Add-Ins**
   - At the bottom, select "Excel Add-ins" and click **Go**
   - Click **Browse** and select the downloaded file
   - Check the box next to "BYTreePlan" to enable it

4. The "Tree Plan" tab will appear in your Excel ribbon

### Method 2: Clone and Build

```bash
git clone https://github.com/smrinalsingh/treeplan.git
cd treeplan
```

Then follow the installation steps above using the `BYTreePlan.xlam` file from the repository.

## Quick Start

New to TreePlan? See the **[Quick Start Guide](docs/QUICKSTART.md)** for a 5-minute tutorial!

## Usage

### Creating a New Tree

1. Click the **Tree Plan** tab in Excel ribbon
2. Select **New** and choose the number of branches (2-5)
3. A new decision tree will be created in your worksheet

### Working with Nodes

**Decision Nodes** (squares):
- Represent choices you control
- Change using **Change To Decision** button
- Can have multiple branches

**Event Nodes** (circles):
- Represent chance events
- Change using **Change To Event** button
- Assign probabilities to branches

**Terminal Nodes** (triangles):
- End points of the tree
- Change using **Change To Terminal** button
- Display final outcomes

### Managing Branches

- **Add Branch**: Add a new branch to a decision or event node
- **Remove Branch**: Remove a branch from the current node
- **Insert Decision**: Insert a decision node in the middle of a branch
- **Insert Event**: Insert an event node in the middle of a branch

### Copy and Paste

- **Copy Subtree**: Copy an entire subtree starting from the selected node
- **Paste Subtree**: Paste a previously copied subtree

### Configuration

- Click **Options** to customize:
  - Visual theme
  - Default branch counts
  - Cell sizing and spacing

## System Requirements

- **Windows**: Excel 2007, 2010, 2013, 2016, 2019, 2021, or Microsoft 365
- **macOS**: Excel 2016, 2019, 2021, or Microsoft 365
- Macros must be enabled

## Project Background

This project was created as homework for the "Data, Modeling and Analysis" course at SJTU Antai MBA. The original TreePlan add-in was created in the last decade and had several limitations:

- Not user-friendly
- Didn't work on macOS
- Outdated interface

This modern rewrite addresses all these issues while being completely free and open source.

## Documentation

- **[Quick Start Guide](docs/QUICKSTART.md)** - Get started in 5 minutes!
- **[Installation & Usage](README.md)** - This file
- **[Office Compatibility Guide](docs/COMPATIBILITY.md)** - Detailed compatibility information
- **[Developer Guide](docs/DEVELOPER_GUIDE.md)** - For contributors and developers
- **[Release Notes](docs/RELEASE_NOTES.md)** - Detailed version history
- **[Contributing Guidelines](CONTRIBUTING.md)** - How to contribute
- **[Changelog](CHANGELOG.md)** - Version history

## Contributing

Contributions are welcome! This project is maintained on a best-effort basis. 

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines and [docs/DEVELOPER_GUIDE.md](docs/DEVELOPER_GUIDE.md) for detailed development information.

### Quick Start for Developers

The add-in is built using:
- VBA (Visual Basic for Applications)
- Office Ribbon XML customization (2009/2010 schema)
- Excel 2007+ Open XML format

To modify the add-in:
1. Open `BYTreePlan.xlsm` in Excel
2. Press `Alt+F11` (Windows) or `Option+F11` (macOS) to open VBA Editor
3. Make your changes
4. Save and test
5. Export as `.xlam` for distribution

For more details, see the [Developer Guide](docs/DEVELOPER_GUIDE.md).

## Support

While this was created as a homework project, issues and feature requests are welcome:

- [Report a Bug](../../issues/new?labels=bug)
- [Request a Feature](../../issues/new?labels=enhancement)
- [Ask a Question](../../issues/new?labels=question)

Please note that support is provided on a best-effort basis.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Copyright (c) 2019 Bian Ying

## Acknowledgments

- Original TreePlan concept and methodology
- SJTU Antai MBA program
- Contributors and users who provide feedback

## Version History

See [CHANGELOG.md](CHANGELOG.md) for a detailed version history.

---

**Note**: TreePlan is a decision analysis tool. Always validate your analysis and consult with appropriate professionals for critical decisions.
