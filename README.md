# Show-CheckBoxPrompt Function

## Synopsis
Displays a custom installation prompt with toolkit branding, optional buttons, and dynamically created checkboxes.

## Description
This function creates a custom checkbox popup along with any combination of Left, Middle, or Right buttons. The return value of the button clicked by the user is the button text specified, and the return value of the checkboxes is the text specified.

## Parameters

- **Title**: Title of the prompt. Default: the application installation name.
- **Message**: Message text to be included in the prompt.
- **MessageAlignment**: Alignment of the message text. Options: `Left`, `Center`, `Right`. Default: `Center`.
- **ButtonLeftText**: Show a button on the left of the prompt with the specified text.
- **ButtonRightText**: Show a button on the right of the prompt with the specified text.
- **ButtonMiddleText**: Show a button in the middle of the prompt with the specified text.
- **Icon**: Show a system icon in the prompt. Options: `Application`, `Asterisk`, `Error`, `Exclamation`, `Hand`, `Information`, `None`, `Question`, `Shield`, `Warning`, `WinLogo`. Default: `None`.
- **NoWait**: Specifies whether to show the prompt asynchronously (i.e., allow the script to continue without waiting for a response). Default: `$false`.
- **PersistPrompt**: Specify whether to make the prompt persist in the center of the screen every couple of seconds, specified in the `AppDeployToolkitConfig.xml`. The user will have no option but to respond to the prompt.
- **MinimizeWindows**: Specifies whether to minimize other windows when displaying the prompt. Default: `$false`.
- **Timeout**: Specifies the time period in seconds after which the prompt should timeout. Default: UI timeout value set in the config XML file.
- **ExitOnTimeout**: Specifies whether to exit the script if the UI times out. Default: `$true`.
- **TopMost**: Specifies whether the progress window should be topmost. Default: `$true`.
- **CheckBoxOptions**: Specifies an array of strings to be displayed as checkboxes in the prompt.

## Inputs
None. You cannot pipe objects to this function.

## Outputs
None. This function does not generate any output.

## Examples

```powershell
# Example 1: Simple Installation Prompt
Show-CheckBoxPrompt -Title "Software Installation" -Message "Please select the components you want to install:" -CheckBoxOptions @("Component 1", "Component 2", "Component 3") -ButtonRightText "Install" -ButtonLeftText "Cancel"
```
```powershell
# Example 2: Feature Survey
Show-CheckBoxPrompt -Title "Survey" -Message "Which features do you find most useful?" -CheckBoxOptions @("Feature A", "Feature B", "Feature C", "Feature D") -ButtonRightText "Submit" -ButtonLeftText "Skip"
```
```powershell
# Example 3: User Preferences
Show-CheckBoxPrompt -Title "Preferences" -Message "Select your preferences:" -CheckBoxOptions @("Preference 1", "Preference 2", "Preference 3") -ButtonRightText "Save" -ButtonLeftText "Discard" -Icon Information -NoWait
```

## Notes
This function is a custom extension made specifically for PSAppDeployToolkit.
Copy and paste code into the main section of the AppDeployToolkitExtensions.ps1 file
