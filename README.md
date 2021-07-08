# This repo forks Roam Mosaic and adds a new theme: Cobalt 2.

This theme is inspired by [Wes Bos' Cobalt2 theme](https://github.com/wesbos?tab=repositories&q=cobalt2&type=&language=&sort=) with tweaks.

Fonts: 
 - Sans-serif: Montserrat
 - Monospace: Fira Code


To use:

1. Create a new page in Roam:
1. Add a bullet with `{{roam/css}}`.
1. Nest a bullet under `{{roam/css}}` and create a code block. Select CSS as the language and add:

```
@import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
@import url('https://gitcdn.link/repo/patleeman/roam-theme-cobalt2/master/build/css/themes/cobalt2.css');
```

Note that this theme is unsupported. I won't be taking contributions, but feel free to fork it.


---


<img src="img/logo_full.png?raw=true" width="400">

## What is Roam Mosaic?

A framework for developing all of your Roam Research CSS themes and UX enhancements with ease using modern development tools.

### Features

- Development tooling with live reload
- Modular SCSS scaffolding for styling Roam components
- A modular framework for creating CSS UX enhancements
- Best practise suggestions for theme creation

## Getting Started

- Install [Node.js](https://nodejs.org/) and [Yarn](https://classic.yarnpkg.com/en/docs/install/) if you haven't already.

- Setup [Chrome DevTools Local Override](https://developers.google.com/web/updates/2018/01/devtools#overrides)

  Click "Select folder for overrides" and point to the `theme-boilerplate\dev\` folder

  ![Screenshot of code tab](/screenshots/1_roam_nexus_chrome_overrides.png?raw=true)

  Click "Allow" on the popup in Chrome

  ![Screenshot of issues tab](/screenshots/2_roam_nexus_chrome_overrides_allow.png?raw=true)

  Your override should now look like this

  ![Screenshot issue page](/screenshots/3_roam_nexus_chrome_overrides_folder_linked.png?raw=true)

  If the `\roamresearch.com\assets\css` folder structure does not exist in your `dev` folder you can configure it by selecting "Save for overrides" on the site.css

  ![Screenshot of organization page](/screenshots/4_roam_nexus_chrome_overrides_folder_not_linked.png?raw=true)

- Fork this repository (clone from your repository)
- Run `cd roam-mosaic` to navigate into your forked repository
- Run `yarn` to install all dependencies
- Run `yarn dev` to build automatically when source files change.
- You are now ready to start building your own theme!

## How do I use Roam Mosaic?

### Folder Structure

Below is an overview of the important folders in this project you will need to build your own theme.

```js
├── build                       // built themes and features will be output here
├── dev                         // chrome devtools override location
├── scss                        // all scss goes here
│   ├── core                    // global selectors that apply to all themes 
│   │   ├── components          // scss files for core UI components 
│   │   │   ├── ...
│   │   │   ├── _block-embed.scss
│   │   │   ├── _block-reference.scss
│   │   │   └── ...    
│   │   ├── layout              // scss files for the main layout elements of Roam
│   │   │   ├── ...
│   │   │   ├── _left-sidebar.scss
│   │   │   ├── _right-sidebar.scss
│   │   │   └── ...
│   │   ├── pages               // scss files for predefined pages in Roam
│   │   ├── _mixins.scss        // useful mixins that can be used accross all themes
│   │   ├── _reset.scss         // global reset css for all themes
│   │   └── _variables.scss     // global variabls for all themes
│   ├── features                // non theme specific UX improvements
│   │   ├── ...
│   │   ├── right-sidebar       // UI Area used for grouping features together
│   │   │   ├── masonry         // all styles required for this feature
│   │   │   ├── ...
│   │   │   └── ...
│   ├── themes                  // folder containing all themes
│   │   ├── railscast           // a theme by Jeff Harris (https://github.com/jmharris903)
│   │   └── template            // a template to use as a base for new themes
│   │       ├── components      // scss files for UI components
│   │       ├── layout          // scss files for the main layout elements of Roam
│   │       ├── pages           // scss files for pages
│   │       ├── _variables.scss // variable overrides for this theme
│   │       └── main.scss       // main entry point for this theme and `yarn build`
│   ├── dev.scss                // entry point for development css `yarn dev`
│   └── roam.css                // latest css from Roam Research needed for override
└── updates                     // Roam Research css and scss used for change tracking
```



### Creating your own theme

The easiest way to create your own theme is to make a copy of the `template` folder and rename it.

Assuming you're in the root directory of `roam-mosaic` you can run the follwing command to do this:

```bash
cp -R scss/themes/template scss/themes/my-new-theme
```

You're now ready to start customizing your theme!

> We recommend starting with changing some variables in `scss/themes/my-new-theme/_variables.scss`.

You can [follow these steps](#getting-started) to get live reload up and running. Renember to [open Chrome DevTools](#i-have-yarn-watch-running-but-live-reload-isnt-working) for live reload to work.

When you're ready to *build your theme*, run `yarn build`. This will create a complied version of your theme into a new, single css file ready for distribution located in the 'build' folder.

## Troubleshooting

### Live reload isn't working

Make sure you have `yarn dev` running in your console

### I have `yarn dev` running but live reload isn't working

You need to have Chrome Dev Tools (`F12` on Windows and `cmd+opt+i` on Mac) open for the file override to work.

### My screen is flashing!

You might have an `@import url()` somewhere in your code. This is currently not supported.
If you want to import something from a url, like fonts for example, [we recommend using `roam/css` for this](https://youtu.be/UY-sAC2eGyI).

## Thanks

[WinHub-98](https://github.com/3lo1i/WinHub-98) for the base framework

### Contributors

- [Palash Karia](https://github.com/palashkaria)
- [Jeff Harris](https://github.com/jmharris903)
