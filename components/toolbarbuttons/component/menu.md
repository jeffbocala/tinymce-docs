---
layout: default
title: Menu
title_nav: Menu
description: Toolbar Button - Menu
keywords: menu menu toolbarmenu
---

## Config Options

| Name | Value | Requirement | Description |
|------| ------| ------------| ----------- |
| text | string | optional | Text to display if no icon is found. |
| icon | string | optional | It displays the icon corresponding to the icon name that has been defined in the icon pack. |
| tooltip | string | optional | Text for button tooltip.  |
| fetch | (success: (menu) => void) => void  | required| default: false - Represents button state. Is toggled by the button's API. |
| onSetup | (api) => (api) => void | optional | default: () => () => {} - Function that's invoked when the button is rendered. |

> Note:  See below for details on return type for onSetup and onAction.

## API

| Name | Value | Description |
|------| ------| ------------|
| isDisabled | ( ) => boolean | Check if the button is disabled. |
| setDisabled | (state: boolean) => void | Set the button's disabled state. |


## Example and Explanation

The following is an example of a Simple Toolbar Button:

{% include codepen.html id="custom-toolbar-menu-button" tab="js" %}

The above is a simple example of a toolbar menu button. It adds a button to the toolbar with the text `My Button` which, when clicked, opens the specified menu. In this case, we've added two menu items. The first inserts content when clicked, and the second opens a submenu which has two children.

The most important part of the configuration for a menu button is the `fetch` option. This configuration option is a function that is passed a callback which is called whenever the menu button's menu is opened. This allows for asynchronous fetching of the menu items. Within this function, we need to create a list of menu items, and pass them to the callback.

We also have a demo of the Menu Toolbar button for you [here]({{site.baseurl}}/demo/custom-toolbar-menu-button/).