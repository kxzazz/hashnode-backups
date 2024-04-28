---
title: "My Minimal Web Development Setup"
seoTitle: "Efficient Web Dev Setup"
seoDescription: "Discover a minimal web development setup guide for Windows and PowerShell, covering Node.js, pnpm, and essential VSCode settings and extensions"
datePublished: Sun Apr 28 2024 07:56:58 GMT+0000 (Coordinated Universal Time)
cuid: clvj8lze9000u09mje292gg0v
slug: my-minimal-web-development-setup
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714290549616/57cacbfe-08ab-4452-a298-9663774de8a7.png
tags: web-development, nodejs, webdev, windows, environment, vscode, setup, vscode-extensions

---

Hey! Some time ago, I started a new dev environment on a new temporary computer, so I needed to re-install all the dev things.

I took this opportunity to document the tech setup I use.

**This is a temporary computer, therefore***This isn't an exhaustive list,* only the bare minimum required for a Windows and PowerShell Web setup.

## Basics 🔩

### Node.js with nvm

The most convenient way to install Node is through its [official website](https://nodejs.org/), download Node and install, but since I am working on multiple projects, I am required to switch between different versions of Node, Therefore I need a **Version Manager** for Node.js. It is good practice to be able to change node versions even when you will only ever use just one.

I choose a **Node version manager** called - [nvm](https://github.com/coreybutler/nvm-windows).

Download `nvm-setup.exe` from [here](https://github.com/coreybutler/nvm-windows/releases) and install.

> **Note: nvm is installed per-user and invoked per-shell.**
> 
> It is not recommended, when there are more than one builder agent.

If you already installed Node.js, The nvm installer will prompt you to add the installed node version in nvm.

> If you just want to install and use the latest version of Node.
> 
> Just run `nvm use latest`
> 
> It will Install and switch to latest version of Node.

After installations, There are 3 commands in PowerShell to install a version of Node.js

* Run `nvm install latest` to install the Latest Node.js.
    
* Run `nvm install lts` to install the Latest Node.js(LTS) version.
    
* Run `nvm install <version>` to install a specific version of node.
    

To see all the installed node versions, run `nvm ls`

To switch to a specific version of node, run `nvm use <version>`

### pnpm - package manager

pnpm is a drop-in replacement for npm, the default package manager installed with Node.js.

pnpm is **3 times faster than npm** and is more memory efficient, as package versions are never saved more than once on a disk.

Run `iwr`[`https://get.pnpm.io/install.ps1`](https://get.pnpm.io/install.ps1)`-useb | iex` to install pnpm.

Also enable corepack using `corepack enable pnpm` which is used to manage package managers.

# VSCode Settings and Extensions.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714289086958/e6d4f16a-4888-4987-a09a-a6627907f822.png align="center")

> Tip: You can try out the vscode setups online at [vscode.dev](https://vscode.dev/)

**User Settings (JSON):** [settings.json](https://gist.github.com/kxzazz/4d0f2294d591c5020ba42c17a277e6c5)

**Theme:** [Head in the Clouds](https://marketplace.visualstudio.com/items?itemName=radiolevity.head-in-the-clouds)

**File Icon Theme:** [Monokai Pro](https://marketplace.visualstudio.com/items?itemName=monokai.theme-monokai-pro-vscode)

**Other Extensions:**

* [Prettier - Code Formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
    
* [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    
* [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
    
* [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
    
* [ES7+ React/Redux/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714291157853/68336312-15fc-4c79-a081-90025621230b.gif align="center")