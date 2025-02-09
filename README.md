![Add to Calendar Button](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/readme-header.png?raw=true)

[![Code Quality](https://img.shields.io/codacy/grade/572c0a102d7b4f39b792439dcd2e8aad/main?style=for-the-badge)](https://app.codacy.com/gh/add2cal/add-to-calendar-button/dashboard)
[![Build Status](https://img.shields.io/github/actions/workflow/status/add2cal/add-to-calendar-button/npm-publish.yml?style=for-the-badge)](https://github.com/add2cal/add-to-calendar-button/actions/workflows/npm-publish.yml)
[![npm Installations](https://img.shields.io/npm/dt/add-to-calendar-button?label=npm%20Installations&style=for-the-badge)](https://www.npmjs.com/package/add-to-calendar-button)
[![jsDelivr npm Hits](https://img.shields.io/jsdelivr/npm/hm/add-to-calendar-button?label=jsDelivr%20npm%20hits&style=for-the-badge)](https://www.jsdelivr.com/package/npm/add-to-calendar-button)

<br />

# Your next Add to Calendar Button

The convenient JavaScript snippet, which lets you reliably create beautiful buttons, where people can add events to their calendars.

[![#1 Product of the Day on ProductHunt](https://api.producthunt.com/widgets/embed-image/v1/top-post-badge.svg?post_id=319458&theme=dark&period=daily)](https://www.producthunt.com/products/add-to-calendar-button-generator)

<br /><br />

For everybody, who wants to include a button at their website or app, which enables users to easily add a specific event to their calendars.
It's main goal is to keep this process as easy as possible at maximum compatibility. Simply define your button configuration and everything else is automatically generated by the script.
Supporting calendars at Apple, Google, Microsoft (365, Outlook, Teams), Yahoo, and generic iCal.

![Supported Calendars: Apple (via iCal), Google, Microsoft (365, Outlook, Teams), Yahoo, generic iCal](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/badge-supported-calendars.svg)

The script integrates easily with any usual HTML webpage (**VanillaJS** way) as well as popular JavaScript frameworks and libraries like **Angular**, **React**, **Vue**, **Svelte**, and more.

![Supported Technology: Angular, React, Vue, Svelte, and every other project that can load JavaScript](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/badge-technology.svg)

In terms of system support, **all modern browsers** (Chrome, Edge, Firefox, Safari) on **Windows, Mac, Android, and iOS** as well as rather restricted webview environments like the **Instagram** in-app browser are supported.

<br /><br />

---

<br />

## ▶️ Demo

See [add-to-calendar-button.com](https://add-to-calendar-button.com/) for a live demo.

And remember to [⭐ **star** this repository](#) in order to stay up-to-date and save it for later! 🤗

[![Remember to star this repository!](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/starring.gif?raw=true)](#)

## ✨ Features

Simple and convenient integration of 1 or many buttons, configurable directly within the HTML code.

### Supported Calendars

- **Google** Calendar.
- **Yahoo** Calender.
- **Microsoft 365, Outlook, and Teams**.
- Automatically generated **iCal/ics** files (for all other calendars, like **Apple**).

### Event Types

- Timed and all-day events.
- One-time, multi-date, recurring, or fluid.
- Most robust time zone and daylight saving management (via our own [TimeZones iCal Library](https://github.com/add2cal/timezones-ical-library)).
- Dynamic dates (like "today + 3").

### Look

- Beautiful and adjustable UI.
- Light and dark mode.
- Multiple themes.

### Accessibility

- Optimized and adjustable UX (for desktop and mobile).
- Dynamic dropdown positioning.
- Taking care of all those edge cases, where some scenarios do not support specific setups (like WebView blocking downloads); utilizing beautiful user guidance workarounds.
- Auto-generated Schema.org rich (structured) data for better SEO.
- Full support for mouse, touch, or keyboard input (W3C WAI compliant).
- Supporting 20+ languages, incl. RTL text for Arabic; but also custom labels and text blocks.

### And much more

- Well documented code, to easily understand the processes and build on top of it.
- No external module or backend dependencies.
- Therefore, fully GDPR, CCPA, and LGPD compliant - without the need of signing some data processing agreement.
- FREE and easy.

![Demo Screenshot](https://github.com/add2cal/add-to-calendar-button/blob/main/assets/img/demo.gif?raw=true)

<br />

---

<br />

## 📦 Installation / Setup

### Option 1: simple (CDN)

You can use the jsDeliver CDN and load the respective ressources into your web project.

Put the css (use atcb-3d for an alternative style) into the `<head>`:

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/add-to-calendar-button@1/assets/css/atcb.min.css">
```

... and the javascript into the `<body>` footer:

```
<script src="https://cdn.jsdelivr.net/npm/add-to-calendar-button@1" async defer></script>
```

_Mind that this always pulls the latest release of v1! You can pin a more specific version by adding the exact version number after the "@" - see [jsDeliver.com](https://www.jsdelivr.com/features#npm) for details._
If you want to rather host it yourself, you could also download the source files or clone the repository (mind to take the original one at [github.com/add2cal/add-to-calendar-button](https://github.com/add2cal/add-to-calendar-button)) and maintain/update it manually.

<br />

### Option 2: npm

Import the package using the following npm command:

```
npm install add-to-calendar-button
```

Import the module into your project/component. For example with Angular/React:

```
import { atcb_action, atcb_init } from 'add-to-calendar-button';
```

Either use `atcb_action` with your own buttons/forms/etc, or run `atcb_init` after the DOM has been loaded. To determine the right moment to execute the `atcb_init`, ...

- with Angular, you would use `ngAfterViewInit()` with `atcb_init();` (mind that, depending on your app, other hooks might be better);
- with React, you might want to include an event listener for `DOMContentLoaded` or use a hook in a functional component like `useEffect(() => atcb_init());`.

Include the css. For example with Angular or React, add `@import 'add-to-calendar-button/assets/css/atcb.css'` to some other css file - or include it in other more direct ways (like adding `import 'add-to-calendar-button/assets/css/atcb.css';` to the respective component) (use atcb-3d for an alternative style).

<br /><br />

## 🎛️ Configuration

A button can be easily created by placing a respective placeholder, wherever you want the button to appear.
(The `style="display:none;"` theoretically is not necessary, but should be used for better compatibility.)

```html
<div class="atcb" style="display:none;">(...)</div>
```

Within this placeholder, you can easily configure the button, by placing a respective JSON structure.
Mind that with Angular, you might need to escape the { with `{{ '{' }}` and } with `{{ '}' }}`; with React it would be `{ '{' }` and `{ '}' }`.

<br />

### Minimal structure (required)

If there is no endDate set, the script assumes that it is the same as startDate.

Mind that for auto-generating rich snippets, a location would be mandatory as well. Even a timezone is not required, but recommended - if not given, the script will assume UTC.

```html
<div class="atcb" style="display:none;">
  {
    "name":"Add the title of your event",
    "startDate":"2022-02-21",
    "options":[
      "Google"
    ]
  }
</div>
```

<br />

### Typical structure

```html
<div class="atcb" style="display:none;">
  {
    "name":"Add the title of your event",
    "description":"A nice description does not hurt",
    "startDate":"2022-02-21",
    "endDate":"2022-03-24",
    "startTime":"10:13",
    "endTime":"17:57",
    "location":"Somewhere over the rainbow",
    "label":"Add to Calendar",
    "options":[
      "Apple",
      "Google",
      "iCal",
      "Microsoft365",
      "MicrosoftTeams",
      "Outlook.com",
      "Yahoo"
    ],
    "timeZone":"Europe/Berlin",
    "trigger":"click",
    "inline":true,
    "listStyle":"modal",
    "iCalFileName":"Reminder-Event"
  }
</div>
```

<br />

### React examples

#### atcb_action

If you can't or don't want to use `atcb_init`, you can use the `atcb_action` import with your own buttons or other elements/components.

This may work better with React and other frontend frameworks, but it misses the Schema.org and button specific functionalities.

```js
import React from 'react';
import { atcb_action } from 'add-to-calendar-button';

const MyComponent = () => {
  const [name, setName] = React.useState("Some event");
  const changeName = e => {
    setName(e.target.value);
  };
  return (
    <form onSubmit={e => {
      e.preventDefault();
      atcb_action({
        name: name,
        startDate: "2022-10-14",
        endDate: "2022-10-18",
        options: ['Apple', 'Google', 'iCal', 'Microsoft365', 'Outlook.com', 'Yahoo'],
        timeZone: "Europe/Berlin",
        iCalFileName: "Reminder-Event",
      });
    }}>
      <input value={name} onChange={changeName} />
      <input type="submit" value="save" />
    </form>
  );
}
```

#### atcb_init

Alternatively, you could use `atcb_init` with a `useEffect` hook:

```js
import React from "react";
import { atcb_init } from "add-to-calendar-button";
import 'add-to-calendar-button/assets/css/atcb.css';

const MyComponent = () => {
  React.useEffect( () => { atcb_init() }, []);
  return (
    <div className="atcb">
      { '{' }
        "name":"Add the title of your event",
        "description":"A nice description does not hurt",
        "startDate":"2022-02-21",
        "endDate":"2022-03-24",
        "startTime":"10:13",
        "endTime":"17:57",
        "location":"Somewhere over the rainbow",
        "label":"Add to Calendar",
        "options":[
          "Apple",
          "Google",
          "iCal",
          "Microsoft365",
          "Outlook.com",
          "Yahoo"
        ],
        "timeZone":"Europe/Berlin",
        "iCalFileName":"Reminder-Event"
      { '}' }
    </div>
  );
}
```

_By the way: Both functions return an array, holding the IDs of the generated buttons!_

<br /><br />

### All options and hidden features

Find all information about the available options and how to configure specific features at the [DOCS.md](DOCS.md).

<br />

---

<br />

## ⚡ Changelog

Find all changes in the dedicated file at [CHANGELOG.md](CHANGELOG.md).

<br />

## 🙌 Contributing

Anyone is welcome to contribute, but mind the [guidelines](.github/CONTRIBUTING.md):

- [Bug reports](.github/CONTRIBUTING.md#bugs)
- [Feature requests](.github/CONTRIBUTING.md#features)
- [Pull requests](.github/CONTRIBUTING.md#pull-requests)

**IMPORTANT NOTE:** Run `npm install`, `npm run format`, and `npm run build` to auto-lint and create the minified js, css, as well as its sourcemap files!

<br />

## 📃 Copyright and License

Copyright (c) [Jens Kuerschner](https://jenskuerschner.de).

Licensed under [Apache-2.0 (with “Commons Clause” License Condition v1.0)](LICENSE.txt).

<br />

---

<br />

## 💜 Kudos go to

[uxwing.com](https://uxwing.com) as well as all contributors:

<a href="https://github.com/jekuer"><img src="https://avatars.githubusercontent.com/u/8572883?v=4" title="jekuer" width="60" height="60"></a>
<a href="https://github.com/add-to-calendar"><img src="https://avatars.githubusercontent.com/u/110406429?s=96&v=4" title="add-to-calendar" width="60" height="60"></a>
<a href="https://github.com/chadoh"><img src="https://avatars.githubusercontent.com/u/221614?v=4" title="chadoh" width="60" height="60"></a>
<a href="https://github.com/turcuciprian"><img src="https://avatars.githubusercontent.com/u/3309840?v=4" title="turcuciprian" width="60" height="60"></a>
<a href="https://github.com/lizakorab"><img src="https://avatars.githubusercontent.com/u/72821189?v=4" title="lizakorab" width="60" height="60"></a>
<a href="https://github.com/bryan-brancotte"><img src="https://avatars.githubusercontent.com/u/11556772?v=4" title="bryan-brancotte" width="60" height="60"></a>
<a href="https://github.com/nticaric"><img src="https://avatars.githubusercontent.com/u/824840?v=4" title="nticaric" width="60" height="60"></a>
<a href="https://github.com/Ortovoxx"><img src="https://avatars.githubusercontent.com/u/56805259?v=4" title="Ortovoxx" width="60" height="60"></a>
<a href="https://github.com/emilebosch"><img src="https://avatars.githubusercontent.com/u/303135?v=4" title="emilebosch" width="60" height="60"></a>
<a href="https://github.com/killerrin"><img src="https://avatars.githubusercontent.com/u/3269687?v=4" title="killerrin" width="60" height="60"></a>
<a href="https://github.com/acm-will"><img src="https://avatars.githubusercontent.com/u/103984058?v=4" title="acm-will" width="60" height="60"></a>
<a href="https://github.com/ssaaiidd"><img src="https://avatars.githubusercontent.com/u/29234802?v=4" title="ssaaiidd" width="60" height="60"></a>
<a href="https://github.com/c0rychu"><img src="https://avatars.githubusercontent.com/u/55235141?v=4" title="Cory Chu" width="60" height="60"></a>
<a href="https://github.com/Denperidge"><img src="https://avatars.githubusercontent.com/u/27348469?v=4" title="Cat" width="60" height="60"></a>
<a href="https://github.com/apps/dependabot"><img src="https://avatars.githubusercontent.com/in/29110?v=4" title="dependabot[bot]" width="60" height="60"></a>

<br />
