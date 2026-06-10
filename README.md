# iLogic Scripts

A collection of Autodesk Inventor iLogic scripts for automation, vault integration, and workflow enhancements.

## Contents

- **External Rules** - Rules triggered by vault events
- **Utility Scripts** - General automation and helper functions
- **Drawing Export** - PDF and document export automation
- **Vault Integration** - Vault lifecycle and state management

## Scripts

### Drawing Export

#### [ExportPDFOnVault.ivb](./ExternalRules/ExportPDFOnVault.ivb)
Exports a PDF copy of the drawing to the vault when saved. Useful for automated documentation workflows.

**Features:**
- Automatically triggered on vault save
- Exports to same directory as drawing
- Configurable PDF export options
- Error handling and user feedback
- All sheets export support
- Color and line weight control

**Usage:**
1. Copy to your Inventor project as an iLogic External Rule
2. Configure vault event trigger for "File Save"
3. Customize PDF path and export options as needed (see inline comments)

## Setup

1. Clone or download this repository
2. Copy desired `.ivb` files to your Inventor project folder
3. Add rules in Inventor: `Tools > iLogic > Edit Module` or create External Rules
4. Configure event triggers in vault (if applicable)

## Requirements

- Autodesk Inventor 2020 or later
- iLogic module enabled
- Appropriate vault permissions (if using vault integration)

## Documentation

Each script includes inline comments explaining:
- Purpose and use case
- Required parameters
- Expected behavior
- Error handling
- Configuration options

## Contributing

Feel free to add new scripts or improvements. Follow the naming convention:
- `DescriptiveNameOfFunction.ivb` for script files

## Resources

- [Autodesk iLogic Documentation](https://help.autodesk.com/view/INVPRO/latest/)
- [Vault Integration Guide](https://help.autodesk.com/view/VLT/latest/)
- [iLogic API Reference](https://help.autodesk.com/view/INVPRO/latest/en/Options/ContentOptions/iLogicAPIGuide.html)

## License

These scripts are provided as-is for personal and professional use.
