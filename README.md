# auro-swatch

`<auro-swatch>` is a UI component for the display of color information containing styling and behavior.

## Docs

All information regarding Project Setup, Technical Details, Tests and information regarding ODS Stateless Components can be found in the [./docs](https://github.com/AlaskaAirlines/OrionStatelessComponents__docs/tree/master/docs) repository.

## Install

[![Build Status](https://img.shields.io/github/workflow/status/AlaskaAirlines/auro-swatch/Test%20and%20publish?branch=master&style=for-the-badge)](https://github.com/AlaskaAirlines/auro-swatch/actions?query=workflow%3A%22test+and+publish%22)
[![See it on NPM!](https://img.shields.io/npm/v/@alaskaairux/auro-swatch.svg?style=for-the-badge&color=orange)](https://www.npmjs.com/package/@alaskaairux/auro-swatch)
[![License](https://img.shields.io/npm/l/@alaskaairux/auro-swatch.svg?color=blue&style=for-the-badge)](https://www.apache.org/licenses/LICENSE-2.0)

```shell
$ npm i @alaskaairux/auro-swatch
```

### Design Token CSS Custom Property dependency

The use of any Auro Component has a dependency on the [Auro Design Tokens (npm install)](https://www.npmjs.com/package/@alaskaairux/orion-design-tokens). See repository and API information [here](https://github.com/AlaskaAirlines/AuroDesignTokenss).

For additional details in regards to using Auro Design Tokens with components, please see [./docs/TECH_DETAILS.md](https://github.com/AlaskaAirlines/auro_docs/blob/master/src/TECH_DETAILS.md)

### CSS Custom Property fallbacks

CSS Custom Properties are not supported in older browsers. For this, fallback properties are pre-generated and included with the npm. Any update to the Auro Design Tokens will be immediately reflected with browsers that support CSS Custom Properties, legacy browsers will require updated components with pre-generated fallback properties.

### Define dependency in project component

Define the component dependency within each component that is using the `<auro-swatch>` component.

```javascript
import "@alaskaairux/auro-swatch";
```

## Element auro-token-list

```javascript
class AuroTokenList extends ComponentBase
```

### auro-token-list use cases

The `<auro-token-list>` element should be used in situations where users may:

* Display table of design token name and value
* Display alternate table of deprecated tokens with optional new reference token name

### Properties:

| Attribute | Value type | Description |
|----|----|----|
| componentData | array | pass in `tokenvalue`, `token` |
| deprecated | boolean | use deprecated display table |

### Code Examples

```html
<auro-tokens-list componentData='[
  { "tokenvalue": "480px", "token": "breakpoint-width-narrow" }
]'></auro-tokens-list>
```

```html
<auro-tokens-list deprecated componentData='[
  { "tokenvalue": "480px", "token": "breakpoint-width-narrow", "reference": "breakpoint-sm" }
]'></auro-tokens-list>
```

## Element auro-swatch-list

```javascript
class AuroSwatchList extends ComponentBase
```

### auro-swatch-list use cases

The `<auro-swatch-list>` element should be used in situations where users may:

* Need to illustrate a Design Token color and its related data
* Display data in table format
* Displays CSS custom property name
* Displays Sass variable name
* Describes color usage and WCAG rating
* Displays color in circular inkwell
* Displays color HEX or RGBA value

### Properties:

| Attribute | Value type | Description |
|----|----|----|
| componentData | array | pass in `backgroundcolor`, `colorname`, `wcag`, `usage` |
| ondark | boolean | defines if color state is to be on-dark |

### Code Examples

```html
<auro-swatch-list componentData='[
  { "backgroundcolor": "#0074c8", "colorname": "color-brand-atlas-100", "wcag": "AAA", "usage": "Notification color on light backgrounds" },
  { "backgroundcolor": "#0074c8", "colorname": "color-brand-atlas-200", "wcag": "AAA", "usage": "Notification color on light backgrounds" }
  ]'></auro-swatch-list>
```

```html
<auro-swatch-list ondark componentData='[
  { "backgroundcolor": "#0074c8", "colorname": "color-brand-atlas-100", "wcag": "AAA", "usage": "Notification color on light backgrounds" },
  { "backgroundcolor": "#0074c8", "colorname": "color-brand-atlas-200", "wcag": "AAA", "usage": "Notification color on light backgrounds" }
  ]'></auro-swatch-list>
```

## Element auro-color-avatar

```javascript
class AuroColorAvatar extends ComponentBase
```

### auro-color-avatar use cases

The `<auro-color-avatar>` element should be used in situations where users may:

* Need to illustrate a Design Token color and its related data
* Use illustrative avatar to display color listing
* Need to illustrate between text, border, alert, interactive or icon uses

### Properties:

| Attribute | Value type | Description |
|----|----|----|
| avatartype | string | pass in `font`, `border`, `alert`, `ui`, `icon` string to illustrate preferred avatar type |
| colorname | string | pass in `-` (dash) delimitated name of color token |
| ondark | boolean | defines if color state is to be on-dark |

### Code Examples

```html
<auro-color-avatar avatartype="font" colorname="color-text-primary-on-light"></auro-color-avatar>
<auro-color-avatar avatartype="font" ondark colorname="color-text-primary-on-dark"></auro-color-avatar>
```

```html
<auro-color-avatar avatartype="border" colorname="color-border-error-on-light"></auro-color-avatar>
<auro-color-avatar avatartype="border" ondark colorname="color-border-error-on-dark"></auro-color-avatar>
```

```html
<auro-color-avatar avatartype="alert" colorname="color-alert-success-on-light"></auro-color-avatar>
<auro-color-avatar avatartype="alert" ondark colorname="color-alert-success-on-dark"></auro-color-avatar>
```
