

# Settings File

## Settings File Locations
Depending on your platform, the user settings file is located here:

- Windows %APPDATA%\Code\User\settings.json
- Mac $HOME/Library/Application Support/Code/User/settings.json
- Linux $HOME/.config/Code/User/settings.json


## Link Settings File

    $ mklink /H /J %APPDATA%\Code\User X:\Your\Sync\Dir

example from work computer

    $ mklink /H %APPDATA%\Code\User\settings.json C:\Users\mbw\Desktop\vscode\settings.json


# Command Line Extension Management

[reference](https://code.visualstudio.com/docs/editor/extension-gallery)

    code --list-extensions
    code --install-extension ms-vscode.cpptools
    code --uninstall-extension ms-vscode.csharp
    code --disable-extensions



## Save Extensions

When ever i make changes to the extensions i have to save them using this command

    $ code --list-extensions > extensions.txt


## Install Extensions

When i then want to install the extensions on a new enviorment
i copy paste the below script in to the build in powershell (terminal) in vscode.


    $a = Get-Content extensions.txt;
    For($i=0; $i -lt  $a.Length; $i++) { code --install-extension $a[$i]}