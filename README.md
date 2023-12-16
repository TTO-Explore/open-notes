# Unstuck
A UI/UX Demo of the Unstuck feature for solving 2-step equations.

## Project Organization
This is a rapid prototype thrown together by Sam Saarinen, and reflects his technology stack preferences, which were never intended to be permanent choices for the eventual long-term home of this project.

This project uses React (with Typescript), Tailwind CSS, and is compiled using Nx (with Vite). Sam isn't even sure what all of those words mean. Anyway, the public-viewable distribution code is in the frontend/dist/frontend subfolder.

Note that this version doesn't have a backend, and the user currently has to enter an OpenAI API key in order to run the demo.

## Setup Instructions
1. (pre-step:) Check npm version (install if not present) `npm -v`, `npm install -g npm@latest` to upgrade
1. (pre-step:) Check node version `node -v` (install if not present with `npm install n -g`, then `n latest` -- only if not on Windows. On windows, use https://nodejs.dev/en/about/releases/.)
1. `npx create-nx-workspace frontend --preset=react-standalone` (makes Nx/Vite/React project inside frontend folder. Should choose regular CSS.)
1. Add Tailwind CSS Support (from frontend subdirectory): `npx nx g @nrwl/react:setup-tailwind` (per https://blog.nrwl.io/setup-react-and-tailwind-the-easy-way-15592eebf4bc)
  1. The alternate process (manual) is documented here: https://tailwindcss.com/docs/guides/vite
  1. Note that Nx uses css modules, so styles for elements should be imported and included in the class name. (See "React CSS Modules" for some example usages.)
  1. ~~Add './index.html' to tailwind content sources.~~
1. Add Tailwind UI support: `npm install @headlessui/react @heroicons/react`
1. `npm i react-router-dom`
1. Create test build from frontend folder by running `npx nx build`

1. `npm i rimraf ncp` to provide functionality used in the next step.
1. Modify package.json to use the following script on build: `npx nx build && ncp ./dist/frontend ../docs`
1. Add a `prebuild` command that runs `rimraf ../docs`

1. Update Site Favicon.
1. Update Site Title (can programmatically update on each page).

## Cloning to a new workstation
Just clone the repo and then run `npm i` from inside the frontend directory, assuming you already have node and npm installed.


## Testing + Deploy Instructions

- Run a local server by running (from frontend folder) `npm serve`
- Build with `npm run build`
- Deploy with commit and push (using git)

