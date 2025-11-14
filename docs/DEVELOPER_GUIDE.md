# Developer Guide

This guide provides detailed information for developers who want to contribute to or modify TreePlan.

## Architecture Overview

TreePlan consists of three main components:

### 1. Excel Files
- **BYTreePlan.xlam**: Production add-in file
- **BYTreePlan.xlsm**: Development workbook with macros

### 2. VBA Code Modules
Located in the VBA project within the Excel files:

- **ThisWorkbook**: Application event handlers
- **Macros**: Main functionality and ribbon callbacks
- **ConfigForm**: User interface for options dialog
- **Helper modules**: Utility functions

### 3. Custom Ribbon UI
Defined in `customUI/customUI.xml` within the Excel package:
- Uses Office Fluent UI Ribbon XML
- Schema: Office 2009/2010
- Supports Office 2010, 2013, 2016, 2019, 2021, and Microsoft 365

## Development Setup

### Prerequisites
- Microsoft Excel (2010 or later recommended)
- Basic knowledge of VBA
- Text editor (for XML editing)
- Optional: Git for version control

### Opening the Project
1. Open `BYTreePlan.xlsm` in Excel
2. Press `Alt+F11` (Windows) or `Option+F11` (Mac) to open VBA Editor
3. Enable "Trust access to the VBA project object model" in Excel settings

### Project Structure in VBA Editor
```
VBA Project (BYTreePlan.xlsm)
├── Microsoft Excel Objects
│   └── ThisWorkbook
├── Forms
│   └── ConfigForm
└── Modules
    └── Macros
```

## Working with VBA Code

### Code Style Guide

```vba
' Use descriptive names
Sub CreateNewDecisionTree()
    ' Add comments for complex logic
    Dim branchCount As Integer
    Dim currentNode As Range
    
    ' Use error handling
    On Error GoTo ErrorHandler
    
    ' Implementation
    branchCount = 3
    Call InitializeTree(branchCount)
    
    Exit Sub
    
ErrorHandler:
    MsgBox "Error creating tree: " & Err.Description, vbCritical
End Sub
```

### Best Practices
1. **Error Handling**: Always include error handlers in public Subs
2. **Naming Conventions**: 
   - Variables: camelCase (e.g., `nodeCount`)
   - Procedures: PascalCase (e.g., `CreateDecisionNode`)
   - Constants: UPPER_CASE (e.g., `MAX_BRANCHES`)
3. **Comments**: Comment complex algorithms, not obvious code
4. **Modularity**: Keep functions focused on single tasks
5. **Testing**: Test all code paths before committing

### Key Functions

#### Tree Creation
```vba
' Creates a new tree with specified branches
Sub BY_NewTree_2(control As IRibbonControl)
    Call CreateTree(2)
End Sub
```

#### Node Operations
```vba
' Changes current node to a decision node
Sub BY_ChangeToDecision(control As IRibbonControl)
    Call ConvertNodeType("D")
End Sub
```

#### Ribbon Callbacks
```vba
' Determines if a button should be enabled
Sub ToolEnabled(control As IRibbonControl, ByRef enabled)
    enabled = IsValidState(control.ID)
End Sub
```

## Working with Ribbon UI

### Extracting the Ribbon XML

1. Rename `.xlam` to `.zip`
2. Extract the archive
3. Navigate to `customUI/customUI.xml`
4. Edit with text editor
5. Re-zip and rename back to `.xlam`

### Ribbon XML Structure

```xml
<customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui" 
          onLoad="BY_OnMainLoad">
  <ribbon>
    <tabs>
      <tab id="ByTreePlanCustomTab" label="Tree Plan">
        <group id="customGroup1" label="Main">
          <button id="newTreeBtn" 
                  label="New" 
                  onAction="BY_NewTree"
                  imageMso="FileNew"
                  screentip="Create New Tree"
                  supertip="Create a new decision tree"/>
        </group>
      </tab>
    </tabs>
  </ribbon>
</customUI>
```

### Ribbon Attributes

- **id**: Unique identifier
- **label**: Display text
- **onAction**: VBA callback procedure
- **getEnabled**: Dynamic enable/disable callback
- **getVisible**: Dynamic show/hide callback
- **imageMso**: Built-in Office icon
- **screentip**: Short tooltip
- **supertip**: Detailed tooltip
- **keytip**: Keyboard shortcut hint

### Adding New Ribbon Commands

1. Add button to `customUI.xml`
2. Create VBA callback:
```vba
Sub MY_NewCommand(control As IRibbonControl)
    ' Your code here
End Sub
```
3. Add enable logic to `ToolEnabled` if needed
4. Test thoroughly

## Building and Packaging

### Creating the Add-in File

1. Make changes in `BYTreePlan.xlsm`
2. Test all functionality
3. Save as `BYTreePlan.xlam`:
   - File → Save As
   - File Type: Excel Add-in (*.xlam)
4. Verify the add-in loads correctly

### Automation Script

You can use this approach to automate updates:

```bash
# Extract XLAM
unzip BYTreePlan.xlam -d temp/

# Make changes to temp/customUI/customUI.xml
# (Use your text editor)

# Repackage
cd temp
zip -r ../BYTreePlan.xlam *
cd ..
rm -rf temp/
```

### Version Control

The project uses Git, but VBA code isn't easily diffable:

**Recommended approach:**
1. Make changes in VBA Editor
2. Export modules: Right-click → Export File
3. Save exported `.bas` and `.cls` files to a `src/` directory
4. Commit exported files along with Excel files

**Note**: The current project doesn't use this approach yet, but it's recommended for future development.

## Testing

### Manual Testing Checklist

- [ ] Create new tree (2, 3, 4, 5 branches)
- [ ] Add branches to decision node
- [ ] Add branches to event node
- [ ] Remove branches
- [ ] Change node types (D → E, E → T, T → D, etc.)
- [ ] Insert decision node mid-branch
- [ ] Insert event node mid-branch
- [ ] Copy subtree
- [ ] Paste subtree
- [ ] Reset tree
- [ ] Configure options
- [ ] Test on different Office versions
- [ ] Test on Windows and macOS

### Testing Different Scenarios

1. **Edge Cases**
   - Empty workbook
   - Very large trees (100+ nodes)
   - Maximum branches (5 per node)
   - Deeply nested trees

2. **Error Conditions**
   - Invalid cell selection
   - Copy without paste
   - Paste without copy
   - Remove last branch

3. **Performance**
   - Large tree creation
   - Multiple copy/paste operations
   - Frequent node type changes

## Debugging

### VBA Debugging Tools

1. **Breakpoints**: Click in margin to set breakpoints
2. **Step Through**: F8 to step through code
3. **Watch Window**: Add expressions to watch
4. **Immediate Window**: Test code snippets (Ctrl+G)
5. **Locals Window**: View all local variables

### Common Issues

**Ribbon doesn't load:**
- Check XML syntax in customUI.xml
- Verify namespace is correct
- Check callback names match VBA procedures

**VBA errors:**
- Use error handler to capture details
- Check `Err.Number` and `Err.Description`
- Use Debug.Print for diagnostic output

**Performance issues:**
- Disable screen updating: `Application.ScreenUpdating = False`
- Disable calculation: `Application.Calculation = xlCalculationManual`
- Remember to re-enable after operation

## Advanced Topics

### Custom Icons

To use custom icons instead of built-in imageMso:

1. Add PNG files to `customUI/images/`
2. Create `customUI/_rels/customUI.xml.rels`
3. Reference in ribbon XML:
```xml
<button id="myBtn" image="myIcon.png"/>
```

### Multi-language Support

To add localization:

1. Create language-specific string tables
2. Use VBA to detect user language:
```vba
Dim userLang As String
userLang = Application.LanguageSettings.LanguageID(msoLanguageIDUI)
```
3. Load appropriate strings based on language

### Extending Functionality

Ideas for new features:
- Export tree as image
- Import/export tree structure
- Undo/redo functionality
- More visual themes
- Probability calculations
- Expected value computations
- Sensitivity analysis

## Documentation

When adding features, update:
- README.md (if user-facing)
- CHANGELOG.md (all changes)
- COMPATIBILITY.md (if affects compatibility)
- This guide (if affects development)
- Code comments (always)

## Release Process

1. Update version number in code comments
2. Update CHANGELOG.md
3. Test on multiple Office versions
4. Build both .xlam and .xlsm files
5. Create Git tag
6. Create GitHub release
7. Attach .xlam file to release

## Getting Help

- Review existing VBA code for patterns
- Check Office Fluent UI documentation
- Search VBA reference documentation
- Ask questions in GitHub issues
- Review Microsoft Excel VBA documentation

## Useful Resources

### Microsoft Documentation
- [Office Fluent UI](https://docs.microsoft.com/en-us/office/vba/library-reference/concepts/office-fluent-user-interface-extensibility)
- [Excel VBA Reference](https://docs.microsoft.com/en-us/office/vba/api/overview/excel)
- [Ribbon XML Reference](https://docs.microsoft.com/en-us/openspecs/office_standards/ms-customui/1b02d160-aa9c-47ca-8c35-dc1f5ff38f22)

### Tools
- [Office RibbonX Editor](https://github.com/fernandreu/office-ribbonx-editor)
- [VBA Code Cleaner](http://www.oaltd.co.uk/indenter/)
- [Excel Add-in Installer](https://github.com/VBA-tools)

---

Happy coding! 🎉
