# wp-leadmanagement

<!-- TOC -->
## Table of Conents

- [wp-leadmanagement](#wp-leadmanagement)
  - [Todos](#todos)
  - [Setup and installation](#setup-and-installation)
  - [Folder Structure](#folder-structure)
  - [Usage](#usage)
  - [Deployment](#deployment)
  - [Credits](#credits)
<!-- /TOC -->

_wp-leadmanagement_ is a WordPress plugin that adds a Lead Management page in your WordPress dashboard. It allows you to monitor your contact submissions or leads in a convenient user interface. The plugin allows the user to create, update, and delete leads.

Only submissions that are created from the plugin is editable. Meaning that submissions from the website's contact form cannot be edited to prevent false data.

Currently, leads are read from the **wp-database-emails** table. There are future plans to create a settings page that will allow for multiple tables and also specify the table/columns. For now everything is currently static.

**Did you know?** wp-leadmanagement is built with React! Many thanks to [gopangolin/wp-reactivate](https://github.com/gopangolin/wp-reactivate) for the starter template that I used for this plugin.

## Todos

- [x] Prevent unauthorized access to leads endpoint with WordPress NONCE
- [ ] Create settings page (Add tables and configure columns).

## Setup and installation

- **Install [Node 8.12.0 LTS or greater](https://nodejs.org)**
- **Install [Yarn](https://yarnpkg.com/en/docs/install)** (Or use npm if you prefer)

## Usage

- Install required modules: `yarn` (or `npm install`)
- Build development version of app and watch for changes: `yarn build` (or `npm run build`)
- Build production version of app:`yarn prod` (or `npm run prod`)

**To learn about how to use wp-reactivate. Please visit [wpr-reactivate repository](https://github.com/gopangolin/wp-reactivate)**

## Folder Structure

```
wpr_leads               # → Root of wp-leadmanagement plugin
├── app/                # → React application
│   ├── actions/        # → Redux actions
│   ├── components/     # → React components
│   ├── config/         # → React application configuration
│   ├── containers/     # → React containers
│   ├── reducers/       # → Redux reducers
│   ├── utils/          # → Utility functions
│   ├── admin.js        # → Settings main react file. (points to Admin.php)
│   ├── leads.js        # → Lead Management main file. (points to Leads.php)
│   ├── shortcode.js    # → Shortcode main file. (points to Shortcode.php)
│   ├── store.js        # → Create redux store (global state)
│   └── widget.js       # → Widget main react file. (points to Widget.php)
├── assets/
│   ├── css/            # → Application CSS
│   └── js/             # → The compiled code for our react application goes here.
├── includes/
│   ├── /Endpoint       # → Create Rest API endpoints to be used by the plugin.
│   ├── Admin.php       # → "Lead Settings" page
│   ├── Leads.php       # → "Lead Management" page
│   ├── Plugin.php      # → Sets our plugin's slug and code that runs on activate goes here.
│   ├── Shortcode.php   # → Code for creating a shortcode.
│   └── Widget.php      # → Code for creating a custom widget
├── node_modules/       # → Folder generated by npm. Never edit this!
├── uninstall.php       # → Runs when you uninstall the plugin from the WordPress dashboard.
├── webpack.config.js   # → Webpack Bundler configuration file.
└── wpr-leads.php       # → Main WordPress PHP file.
```

## Deployment

To deploy, build the production ready assets with `yarn prod` (if using yarn) or `npm run prod`. The generated assets can be found inside the `assets/js` folder. The files that you need to upload are:

- /assets
- /includes
- uninstall.php
- wpr-leads.php

## Credits

_Made by [James Vibar](www.jamesvibar.com) for Redkite PH_
