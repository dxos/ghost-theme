# DXOS Ghost Theme

A multi-column [Ghost](https://github.com/TryGhost/Ghost) theme based on the default Ruby theme.

**Blog: https://blog.dxos.org**

## Instructions

1. Install the ghost cli.

```bash
pnpm -g i ghost-cli
```

2. Install ghost locally.

```bash
mkdir ghost
cd ghost
ghost install local
```

3. Clone the theme.

```bash
cd content/themes
git clone git@github.com:dxos/ghost-theme.git
```

Add a symlink from the Ghost installation to the theme directory.

```bash
cd ghost
cd content/themes
ln -s ../../ghost-theme
```

4. Start Ghost and activate the theme.

```bash
ghost restart
```

Open [settings](http://localhost:2368/ghost/#/settings/design/edit).

Click "Change theme" (bottom right) and select "Installed" and "@dxos/ghost-theme".

## Development

NOTE: You must have Node 18.19.0 installed.

From the theme directory run the dev server:

```bash
yarn
yarn dev
```

Restart ghost for major changes via `ghost restart`.

## Configuring Prism

The theme uses a modified version of [Prism](https://prismjs.com) for syntax highlighting. 
It uses generated and customized code from [here](https://prismjs.com/download.html#themes=prism-tomorrow&languages=markup+css+clike+javascript+bash+diff+json+markdown+jsx+tsx+regex+typescript+typoscript&plugins=line-highlight+line-numbers+command-line+toolbar+copy-to-clipboard+diff-highlight+treeview).

Prism style are imported in the `assets/css/screen.css` file:

```css
@import "prism.css";
```

The Prims script is imported from `default.hbs`.

```html
<script src="{{asset "js/prism.js"}}"></script>
```

## Build and Deploy

Run the following command then upload the theme from `./dist`.

```bash
yarn zip
```

Configure the theme via settings: https://dxos.ghost.io/ghost/#/settings/design/edit

Upload the theme file: `dist/dxos-ruby-dark.zip`.
