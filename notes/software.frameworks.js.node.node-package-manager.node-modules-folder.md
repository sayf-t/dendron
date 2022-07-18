---
id: sa9wibujgik8sbzdurcl21h
title: Node Modules Folder
desc: ''
updated: 1658136291096
created: 1658135882301
---

IF we open node_modules folder, you can find the folder for what was installed eg `axios`, and `follow-redirects`
- The code and files should always be managed by npm, and not directly messed with
- `package.json` -> `dependencies` -> `follow-redirects` library/package (ie groups of modules) required by axios
- DEPENDENCIES OF OUR DEPENDENCIES - aka the dependency tree
- Need them to allow the application to run
![](./assets/images/node-modules-meme.png)

- Nowadays Node developers need not worry about npm package dependency bloat as it has improved 
- git ignore node modules bia `.gitignore` to save space!