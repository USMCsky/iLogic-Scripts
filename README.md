Inventor iLogic PDF Export on Save
Overview

This repository provides an Autodesk Inventor external iLogic rule that automatically exports a PDF copy of the active drawing when the drawing document is saved.

The rule is intended for teams that need a consistent, repeatable method to generate PDF deliverables from Inventor drawing files (.idw or .dwg) as part of the normal save workflow.

Important Vault Limitation
This rule runs locally in the Autodesk Inventor client. It exports a PDF file to a configured location, but it does not perform Autodesk Vault check-in, lifecycle state changes, revision updates, job processor actions, or server-side publishing. Any Vault-related file management must be handled separately through approved Vault workflows.

What It Does

When an Inventor drawing is saved, the external iLogic rule can:

Detect the currently active drawing document.

Generate a PDF copy of the drawing.

Save the PDF to a configured output folder.

Use predefined PDF export options.

Run automatically through the Inventor After Save Document event trigger.

This helps reduce manual PDF publishing steps and supports more consistent drawing release documentation.

Intended Use

This rule is designed for:

Autodesk Inventor drawing documents:

.idw

.dwg

Local or network-accessible PDF export locations.

Client-side automation using Inventor iLogic.

Standardized drawing-to-PDF output during save operations.

Requirements

RequirementDescriptionAutodesk InventorInstalled and licensed Inventor environment with iLogic supportiLogicExternal rule execution enabledDrawing DocumentActive document must be an Inventor drawingPDF Translator Add-InInventor PDF export translator must be availableFile AccessUser must have write permission to the configured PDF output locationOptional: Autodesk VaultSupported only as a client-side environment; the rule does not check files into Vault

Recommended Setup

The recommended implementation is to configure this as an External Rule and assign it to the After Save Document event trigger.

Why External Rule

Using an external rule provides:

Centralized maintenance.

Consistent behavior across multiple drawing files.

Easier deployment to multiple users.

Reduced need to embed rule code into individual Inventor documents.

Recommended Trigger

Configure the rule to run using:

text

This causes the PDF export process to run immediately after the drawing file is saved.

Configuration Notes

The rule should be reviewed and configured before deployment.

PDF Output Path

The PDF output path should be set to match the intended business process.

Common options include:

Output StrategyDescriptionSame folder as drawingSaves the PDF next to the .idw or .dwg fileDedicated PDF folderSaves all PDFs to a configured directoryProject-relative folderSaves PDFs to a folder such as .\PDF or .\Released PDFNetwork locationSaves PDFs to a shared location accessible by authorized users

Example output folder patterns:

text

Recommended File Naming

Typical PDF file naming uses the drawing file name without the Inventor extension:

text

Example:

text

If revision-specific output is required, the rule may be configured to include revision information in the exported PDF file name.

Example:

text

PDF Export Options

Typical PDF export options may include:

OptionRecommended SettingExport all sheetsEnabledOpen PDF after exportDisabledVector resolution400–600 DPISheet rangeAll sheetsLine weightsEnabled, unless business standards require otherwiseColor outputConfigurable by standardRemove line weightsDisabled, unless required

PDF export options should be aligned with internal drawing release, manufacturing, supplier, or customer documentation requirements.

Installation
1. Download or Clone the Repository

Clone the repository or download the rule files to a controlled local or network location.

2. Place the External Rule File

Copy the iLogic rule file to an Inventor external rules directory.

3. Configure Inventor External Rule Directory

In Autodesk Inventor:

Open Tools.

Select Options.

Open iLogic Configuration.

Add the folder containing the external rule.

Confirm the rule appears in the iLogic browser under External Rules.

4. Configure the After Save Trigger

In Autodesk Inventor:

Open a drawing document.

Go to Manage.

Select iLogic.

Open Event Triggers.

Locate After Save Document.

Add the external PDF export rule.

Save the trigger configuration.

5. Validate Output Path

Confirm that:

The configured PDF folder exists, or the rule creates it.

The user has write permissions.

The path is accessible when working online, offline, or through VPN as applicable.

Usage Workflow

The expected user workflow is:

Open an Inventor drawing file.

Make drawing updates as required.

Save the drawing.

The After Save Document trigger runs the external iLogic rule.

A PDF is exported to the configured location.

User verifies the PDF if required by the release process.

If using Vault, user manually follows the required Vault check-in or release workflow.

Vault Limitation

This rule is not a Vault automation tool.

It does not:

Check the PDF into Vault.

Attach the PDF to the drawing file.

Update Vault lifecycle states.

Update Vault revision data.

Submit a Vault job.

Publish files through Vault Job Processor.

Guarantee that the exported PDF is the official released document.

When Autodesk Vault is used, the generated PDF should be managed according to the applicable Vault and document control procedures.

Troubleshooting

IssuePossible CauseRecommended ActionPDF is not createdRule did not runConfirm the rule is assigned to the After Save Document triggerPDF is not createdActive document is not a drawingConfirm the active document is an .idw or Inventor .dwg drawingPDF export failsPDF Translator Add-In is unavailableConfirm Inventor PDF export functionality is installed and enabledAccess denied errorUser lacks write permissionVerify permissions to the configured output folderPDF saves to wrong locationOutput path is configured incorrectlyReview the path configuration in the ruleOld PDF is overwrittenRule is configured to use the same file nameConfirm overwrite behavior is acceptable or update naming logicPDF does not include all sheetsSheet range option is incorrectSet PDF export options to export all sheetsRule does not appear in InventorExternal rule directory is not configuredAdd the rule folder in iLogic ConfigurationRule works for one user but not anotherDifferent local Inventor or iLogic settingsStandardize external rule paths and trigger configurationVault file is not updatedRule is client-side onlyPerform Vault check-in or release actions through the approved Vault workflow

Best Practices

Store the rule in a controlled external rule directory.

Use a shared network location for multi-user deployments when appropriate.

Keep output paths consistent across users and projects.

Do not rely on this rule as the official Vault publishing process.

Confirm PDF output before releasing or distributing controlled drawings.

Use revision-aware file naming if PDFs are retained by revision.

Test the rule with single-sheet and multi-sheet drawings.

Confirm behavior for read-only, checked-out, and non-checked-out Vault files.

Document any local configuration changes required for deployment.

Maintain version history when rule logic or export settings change.

Suggested Repository Structure
Folder Descriptions

Folder/FilePurposeREADME.mdPrimary project documentationrules/External iLogic rule filesdocs/Supplemental setup and configuration documentationexamples/Example path and naming configurationsCHANGELOG.mdVersion history and release notes

Disclaimer

Use of this rule does not replace approved engineering release, document control, or Autodesk Vault procedures. Users are responsible for confirming that exported PDF files are accurate, current, and managed according to applicable business requirements.
