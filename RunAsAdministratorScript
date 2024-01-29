$checkIfAdmin = [Security.Principal.WindowsIdentity]::GetCurrent().Groups -contains 'S-1-5-32-544'
$scriptPath = (Get-ChildItem C:\ -Recurse -Filter "GUI_Access_RemovalWithInheritanceDisableOption.ps1" -ErrorAction SilentlyContinue | Select-Object -First 1).FullName

# Check local path form where script is started
$LocalPath = if ($PSScriptRoot) { $PSScriptRoot }
elseif ($psise) { split-path $psise.CurrentFile.FullPath }
elseif ($psEditor) { split-path $psEditor.GetEditorContext().CurrentFile.Path }

if ($checkIfAdmin) {
    # Enter your code here
    Start-Process powershell -ArgumentList "-NoProfile -ExecutionPolicy Bypass -File `"$scriptPath`"" -Verb RunAs
}
else {
    # Change the file location
    Start-Process powershell -ArgumentList "-NoProfile -ExecutionPolicy Bypass -File `"$scriptPath`"" -Verb RunAs
}
