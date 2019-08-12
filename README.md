# Whyzer
{
  "application": {
    "id": 609906130964971538,
    "manifests": [
      {
        "label": "my-awesome-game/windows",
        "platforms": ["win32", "win64"],
        "locales": [],
        "local_root": "./",
        "file_rules": {
          "mappings": [
            {
              "local_path": ".",
              "install_path": "."
            }
          ],
          "properties": [
            {
              "install_path": "save/*",
              "attributes": ["user_data"]
            }
          ],
          "exclusions": [
            {
              "local_path": "**/*.pdb"
            },
            {
              "local_path": "**/*.verycoolfile"
            }
          ]
        },
        "storage": {
          "sync": true,
          "roots": [
            {
              "id": "my-save-files",
              "paths": [
                {
                  "platform": "windows",
                  "path": "${DOCUMENTS}/My Games/My Awesome Game/Saves"
                },
                {
                  "platform": "macos",
                  "path": "${DOCUMENTS}/Games/My Awesome Game/Saves"
                }
              ],
              "patterns": ["**/*"]
            }
          ]
        },
        "install_scripts": [
          {
            "name": "SDB Compatibility",
            "executable": "Install.bat",
            "arguments": ["/silent"],
            "requires_admin": true,
            "platforms": ["win32", "win64"],
            "completion_registry_key": {
              "key": "Software\\My Game Company\\InstallScripts\\SDB-win32",
              "value": 1
            }
          }
        ],
        "registry_keys": [
          {
            "key": "Software\\My Game Company\\My Awesome Game\\FixAspctRatio",
            "value": "1"
          }
        ],
        "launch_options": [
          {
            "name": "My Awesome Game",
            "executable": "my-awesome-game.exe",
            "arguments": [],
            "platforms": ["win32", "win64"],
            "working_dir": "important-files-in-here/"
          },
          {
            "name": "My Awesome Map Editor",
            "executable": "my-awesome-map-editor.exe",
            "arguments": [],
            "platforms": ["win32", "win64"],
            "working_dir": "important-files-in-here/"
          }
        ]
      }
    ]
  }
}
