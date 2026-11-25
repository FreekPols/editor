# Instruction

The following instructions show how the editor can be enabled. The steps below instruct how to mirror this minimal repo.

## Include Files

1. In the root of your GitHub repository, create the folders `editor`, `editor-dist` and `plugins` (the latter only if it doesn't exist yet).
2. Add the [editor_local.mjs](https://github.com/FreekPols/editor/blob/main/plugins/editor_local.mjs) file to the plugins folder.
3. Add the [myst-editor.tar.gz](https://github.com/FreekPols/editor/raw/main/editor-dist/myst-editor.tar.gz) file to the editor-dist folder.
4. Add the [options.js](https://github.com/FreekPols/editor/blob/main/editor/options.js) file to the editor folder.

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

Commit and push the changes to your GitHub repository.

## Creating a fine-grained access token

To allow the online editor to access your repository, you need to create a personal access token.

1. On GitHub, click your profile picture in the top-right corner and select **Settings**.

   ```{figure} figures/settings.png
   ```

2. Scroll down and select **Developer settings**  in the left sidebar.
3. Expand **Personal access tokens** and select **Fine-grained tokens**.
4. Click **Generate new token**.
5. Configure your token:
   - **Token name:** Choose a descriptive name, e.g. `MyST Editor`.
   - **Expiration:** Choose an appropriate expiration date.
   - **Resource owner:** Select your account or organization.
   - **Repository access:** Choose **Only select repositories** and select the repository you want to edit.
   - **Repository permissions:** Set **Contents** to **Read and write**.
   ```{figure} figures/rights.png
   ```
6. Click **Generate token**.
7. Copy the generated token and store it securely. You will need it to access your repository through the online editor.

**Important:** The token is displayed only once. Do not share it or include it in your repository, as it grants access to your repository.

You are now ready, go to your GH page and include /editor at the end of the URL

## Login 
You can login the editor by pasting /editor behind your url, in this case: https://freekpols.github.io/editor/editor/

This leads to a login page:
```{figure} figures/login.png
```
To enter, paste your _personal access token_. If all went well, you are logged in and you can edit your markdown files online.


## Note on updates

The above method has a fixed editor - we are still working on updates, fix bugs etc. These will not be included in your version as it depends entirely on the .tar file in which the editor is included. Do visit [combine](https://combine.tudelft.nl) for updates on the editor/
