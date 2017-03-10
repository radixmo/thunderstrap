# Thunderstrap
This is a basic child theme for WordPress which depends on the [UnderStrap Theme Framework] (https://github.com/holger1411/understrap)

## How Thunderstrap Works
As a child theme, Thunderstrap offers a convenient way to override the functions and template files of Understap (it's parent theme).

However, unlike most child themes PLEASE NOTE: IT DOES NOT LOAD PARENT THEME CSS FILE(S)!

Instead, Thunderstrap uses UnderStrap as a dependency via the Bower package manager. After installing dependencies you can complile Sass files to modify and generate CSS files for ThunderStrap on the fly.

## Installation
1. Go to "Appearance -> Themes" in your WordPress admin backend.
2. Find and install UnderStrap (the parent theme). - 
3. Download [ThunderStrap from Github] (https://github.com/radixmo/thunderstrap/archive/child.zip).
4. Upload the ThunderStrap theme via WordPress admin backend.
5. Activate the ThunderStrap Child theme.

## Editing
Add your own CSS styles to `/sass/theme/_child_theme.scss`
or import your own Sass files into `/sass/theme/child-theme.scss`.

To overwrite base variables (for Bootstrap or UnderStrap) just add your own values to:
`/sass/theme/_child_theme_variables.scss`.

For example:
The "$brand-primary" variable is used by both, Bootstrap and UnderStrap.
You modify the color in `/sass/theme/_child_theme_variables.scss` to overwrite it:
$brand-primary: #ff6600;
Doing so will automatically change all elements who use this variable.
It will be outputted into:
`/css/child-theme.min.css`
and
`/css/child-theme.css`

This leaves you with just one clean CSS file for browsers to load.

## Developing With NPM, Gulp, SASS and Browser Sync

### Installing Dependencies
- Make sure you have installed Node.js, Bower, and [Browser-Sync] (1) on your computer globally
- Then open your terminal and browse to the location of your copy of ThunderStrap
- Run: 

`$ npm install`

- Then run: 

`$ gulp copy-assets`

### Running
- To work and compile your Sass files on the fly start, run:

`$ gulp watch`

Or, to run with Browser-Sync:

- First change the browser-sync options to reflect your environment in the file `/gulpfile.js` in the beginning of the file:
```javascript
var browserSyncOptions = {
    proxy: "localhost/theme_test/", // <----- CHANGE PATH TO WORDPRESS INSTALL HERE
    notify: false
};
```
- Then run: 

`$ gulp watch-bs`

[1] Visit [http://browsersync.io](http://browsersync.io) for more information on Browser Sync
