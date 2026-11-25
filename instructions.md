# Instruction

The following instructions show how the editor can be enabled. The steps below instruct how to mirror this minimal repo.

## Include Files

1. In the root of your GitHub repository, create the folders `editor`, `editor-dist` and `plugins` (the latter only if it doesn't exist yet).
2. Add the editor_local.mjs file to the plugins folder.
3. Add the myst-editor.tar.gz file to the editor-dist folder.
4. Add the options.js file to the editor folder.

Your repository should now contain the following files and folders:
```markdown
repository/
├── editor/
│   └── options.js
├── editor-dist/
│   └── myst-editor.tar.gz
└── plugins/
    └── editor_local.mjs
```

## Edit options.js
Open options.js and update line 15:
```js
githubRepo: "FreekPols/editor", // <user>/<repo>
```
Replace `FreekPols/editor` with your own GitHub username (or organization name) and repository name.

## Edit myst.yml

Open myst.yml and include the plugin:
```yml
  plugins:
    - plugins/editor_local.mjs
```



## Access token


## Note on updates