# Office Compatibility Guide

## Supported Versions

TreePlan is designed to work with a wide range of Microsoft Office versions:

### Windows
- ✅ Office 2007
- ✅ Office 2010
- ✅ Office 2013
- ✅ Office 2016
- ✅ Office 2019
- ✅ Office 2021
- ✅ Microsoft 365 (formerly Office 365)

### macOS
- ✅ Office 2016 for Mac
- ✅ Office 2019 for Mac
- ✅ Office 2021 for Mac
- ✅ Microsoft 365 for Mac

## Feature Compatibility

### Ribbon UI (All Versions)
The TreePlan ribbon interface uses the Office Fluent UI:
- **2006 Schema**: Office 2007 (basic support)
- **2009/2010 Schema**: Office 2010+ (enhanced features)

**Enhanced features in Office 2010+:**
- Screentips and supertips for better accessibility
- AutoScale for ribbon groups (better display on different screen sizes)
- Keytips for keyboard navigation
- Improved high DPI support

### VBA Compatibility
TreePlan uses VBA (Visual Basic for Applications) that is compatible with:
- Excel Object Model (2007+)
- Standard VBA functions
- No external dependencies

## Known Issues

### Office 2007
- Basic ribbon functionality only
- No screentips/supertips
- Manual ribbon scaling

### macOS Specific
- Some keyboard shortcuts may differ from Windows
- File paths use forward slashes instead of backslashes
- Font rendering may appear slightly different

### Microsoft 365 Web
⚠️ **Not Supported**: TreePlan requires the desktop version of Excel and cannot run in Excel Online due to VBA limitations.

## Security Settings

### Macro Security
TreePlan requires macros to be enabled. To enable macros:

**Windows:**
1. Go to File → Options → Trust Center → Trust Center Settings
2. Select Macro Settings
3. Choose "Disable all macros with notification" (recommended) or "Enable all macros"

**macOS:**
1. Go to Excel → Preferences → Security & Privacy
2. Under Macro Security, select "Disable all macros with notification" (recommended)

### Trusted Locations (Recommended)
For the best experience, add the add-in location to trusted locations:

**Windows:**
1. Go to File → Options → Trust Center → Trust Center Settings
2. Select Trusted Locations
3. Add the folder where BYTreePlan.xlam is stored

**macOS:**
1. Go to Excel → Preferences → Security & Privacy
2. Click "Trust access to the VBA project object model"

## Performance Notes

### Large Trees
- Trees with 100+ nodes: Good performance on all versions
- Trees with 500+ nodes: May experience slowdown on older machines
- Trees with 1000+ nodes: Recommended to use newer Excel versions (2016+)

### Memory Requirements
- Minimum: 4 GB RAM
- Recommended: 8 GB RAM or more for large trees
- Excel versions 2013+ have better memory management

## Office 365 Features

### Modern Features Available
When using Microsoft 365, TreePlan benefits from:
- Improved rendering engine
- Better high DPI display support
- Enhanced accessibility features
- Faster VBA execution on modern hardware

### Cloud Integration
While TreePlan doesn't directly integrate with cloud features, you can:
- Store workbooks with trees in OneDrive/SharePoint
- Collaborate on decision trees (add-in must be installed on all machines)
- Use AutoSave (ensure add-in is loaded before editing)

## Upgrading from Older Versions

### From Office 2007 to 2010+
TreePlan automatically uses enhanced features when running on Office 2010+:
- No changes needed to existing trees
- UI enhancements appear automatically
- All functionality remains compatible

### From Previous TreePlan Versions
The modernized TreePlan maintains full backward compatibility:
- Existing trees open without modification
- All features work as before
- Enhanced UI provides better experience

## Testing Matrix

| Feature | 2007 | 2010-2016 | 2019-2021 | 365 | Mac 2016+ |
|---------|------|-----------|-----------|-----|-----------|
| Basic ribbon | ✅ | ✅ | ✅ | ✅ | ✅ |
| Screentips | ❌ | ✅ | ✅ | ✅ | ✅ |
| AutoScale | ❌ | ✅ | ✅ | ✅ | ✅ |
| Keytips | ❌ | ✅ | ✅ | ✅ | ✅ |
| High DPI | ⚠️ | ✅ | ✅ | ✅ | ✅ |
| Touch mode | ❌ | ⚠️ | ✅ | ✅ | ✅ |
| Dark mode | ❌ | ❌ | ❌ | ⚠️ | ⚠️ |

Legend:
- ✅ Fully supported
- ⚠️ Partial support
- ❌ Not supported

## Troubleshooting

### Add-in Not Appearing
1. Check if macros are enabled
2. Verify add-in is checked in Excel Add-ins dialog
3. Restart Excel
4. Check macro security settings

### Compatibility Mode
If a workbook is in compatibility mode (97-2003 format):
- TreePlan will still work
- Save as .xlsx format for best compatibility
- Some visual features may be limited

### Mixed Environments
In organizations with mixed Office versions:
- TreePlan works across all versions (2007+)
- Newer features gracefully degrade on older versions
- Trees created on newer versions work on older versions

## Future Compatibility

TreePlan is designed for long-term compatibility:
- Uses standard VBA (no version-specific code)
- Office Ribbon XML is stable and supported
- No external dependencies to maintain
- Open source allows community updates

## Support

For version-specific issues:
1. Check your Office version: File → Account → About Excel
2. Report issues on GitHub with version information
3. Include operating system details
4. Provide steps to reproduce

---

**Note**: While TreePlan strives for broad compatibility, testing on all versions may not be comprehensive. Community feedback helps improve compatibility.
