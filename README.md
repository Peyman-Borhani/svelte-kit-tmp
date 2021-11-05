# An improved version of svelte-kit default template.

- updated: CSS stylesheets, units... to be fully resposive (dynamic).
- improved the design.
- fixed some design flaws.
- fixed few mistakes in css stylesheet.
- fixed: incomplete css instructions. (missed by developer).
- adding a nice transition when changing pages.

### How to setup:
* *After you installed svelte-kit, copy-paste/overwrite files to your project folder.*
---

## Creating a project

To install svelte-kit use either npm or pnpm instructions bellow:

```bash
# create a new project in the current directory
npm init svelte@next

# create a new project in my-app
npm init svelte@next my-app
```

> note 1- the `@next` is temporary. 

> note 2- pnpm is a better practice, * to use: replace npm with pnpm in all instructions. 

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

Before creating a production version of your app, install an [adapter](https://kit.svelte.dev/docs#adapters) for your target environment. Then:

```bash
npm run build
```

> You can preview the built app with `npm run preview`, regardless of whether you installed an adapter. This should _not_ be used to serve your app in production.
