---
title: Installation and set up
description: Installing and Using the AEM Guides Extension Package
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
---
# Installing and Using the AEM Guides Extension Package

Extensions give you the opportunity to customize your AEM Guides app to better suit your needs. This extension framework is supported with AEM Guides v4.3 onwards (on-prem) and 2310 (cloud).

## Requirements

This package requires [git bash](https://github.com/git-guides/install-git) and npm

## Installation

The easiest way to bootstrap AEM Guides framework installation is through cli

```bash
npx @adobe/create-guides-extension
```

## Adding customization code

1. Add code files for each component you want to extend in the `src/` directory. Some sample files have already been added for you.
2. Now in the `index.ts` file located in the `src/` directory :
    - Import the `.ts` files with the customizations you want to add in your build.
    - Add the imports to `window.extension`
    - Register the customized component's `id` and corresponding import to `tcx extensions`
    - Refer to the sample `/src/index.ts`

## Building the customized code

- Run `npm run build` in the root directory. You will get 3 files in the directory, `dist/`:
  - `build.css`
  - `guides-extension.js`
  - `guides-extension.umd.cjs`

![Build Output](./../imgs/build_output.png)

## Adding the customization to AEM

- Go to `CRXDE` `crx/de/index.jsp#/`
- Under the `apps` folder, make a new node of the type `cq:ClientLibraryFolder`

![Folder structure](./../imgs/crxde_folder_structure.png)

- In the `properties` of the node, select `Multi` add the following property
    Name: `categories`
    Type: `String []`
    Value: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

>[!NOTE]
>
> For penultimate UI, the values would be: `apps.fmdita.penultimate.xml_editor.page_overrides` and `apps.fmdita.review_overrides`


![Folder properties](./../imgs/crxde_folder_properties.png)

- To add the built js, create a new file, say, `tcx1.js` in the above created node. Here, add the code from `dist/guides-extension.umd.cjs` or `dist/guides-extension.js`. Now create a new file `js.txt`, here we add the name of our js file, which in this case would be:

```t
#base=.
tcx1.js
```

- To add the built css, create a new file, say, `tcx1.css` in the above created node. Here, add the code from `dist/build.css`. Now create a new file `css.txt`, here we add the name of our css file, which in this case would be:

```t
#base=.
tcx1.css
```

- Do a `shift + refresh` to load the app with the customizations!

## Troubleshooting

Check that all the above steps were performed correctly.
After adding your code to tcx.js, make sure to do a hard refresh (shift+refresh).
Now open AEM, do a right click and click `Inspect`
Go to Sources and search for your `[node_name].js` (for eg: extensions.js) file. Do a Control / Cmd + D to search for your file. If the `.js` file exists with the JS code you pasted from `dist/guides-extension.umd.cjs` or `dist/guides-extension.js`, your setup is complete
