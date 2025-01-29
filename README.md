# Evolve

## Play

https://pmotschmann.github.io/Evolve/

## About

An incremental game about evolving a civilization from primordial ooze into a space faring empire.
Evolve combines elements of a clicker with an idler and has lots of micromanagement.

What will you evolve into?

## Submitting Issues

If you think you have discovered a bug or have some other issue with the game then you can open an issue here on Github.
Please do not open Github issues to ask gameplay questions, use Reddit or Discord for that.
Links for both can be found in the footer of the game.

## Contributing a Language file

If you are interested in a contributing a new language for Evolve the process is fairly straight forward (although a bit tedious).

Make a copy of strings/strings.json and name the copy as strings/strings.\<locale\>.json (EX: strings.es_US.json). The locale format is the language alpha-2 code joined with the country alpha-2 code.

The strings are stored in a json format and will look like this:

```
"job_farmer_desc": "Farmers create food to feed your population. Each farmer generates %0 food per second.",
```

If you are unfamiliar with json the first part is a **key** and cannot be altered, **do not translate or modify the key in any way**. The second part is the string to be translated. Many game strings use **tokens** (**%0**, **%1**, **%2**, etc) to represent game values, as such these tokens must remain in the final translated string. Their position can be moved accordingly, the number represents a specific value and not its position in the string.

To enable your language translation in the game you must add it to the locales constant in locale.js (bottom of the file).

Once you feel your translation file is ready send a pull request with it to the Evolve main branch.

## Contributing to the game

Bug fixes, additional translations, themes, or UI improvements can simply be submitted as pull requests; once reviewed and accepted they will be merged into the main game branch. If you want to contribute a new feature it can not arbitrarily make something easier without making something else harder. If your new feature idea simply makes the game easier it will not be accepted.

All pull requests should be based off current dev branch.
The dev branch is either master or named after its version number.
Please check the current game version and what branches are available before contributing.
Pull requests should not contain the JS/CSS files generated by the build.

## CSS Changes

Evolve uses LESS to build its CSS, you can not just edit the minified CSS file. You must instead edit src/evolve.less then use the less compiler to rebuild the CSS file.

## Build Commands

Assuming you configured your build environment correctly the game can be built, deployed to GitHub Pages or launched using

```
# Builds everything on Linux
npm run build
# Builds everything on Windows
npm run build-win
# Builds the game bundle
npm run evolve
# Builds the CSS file for the game on Linux
npm run evolve-less
# Builds the CSS file for the game on Windows
npm run evolve-less-win
# Builds the wiki bundle
npm run wiki
# Builds the Wiki CSS file on Linux
npm run wiki-less
# Builds the Wiki CSS file on Windows
npm run wiki-less-win
# Launches the game server locally on localhost:4400
npm run serve
# Deploys the game to GitHub Pages on Linux (requires forking)
npm run deploy
# Deploys the game to GitHub Pages on Windows (requires forking)
npm run deploy-win
```

## Docker

If you already have a Docker environment set up and want to run an evolve server using Docker, you can execute the following command to build a Docker image for the evolve server.

```
# Build evolve server image
docker build . -t evolve

# Run evolve server. Default address: http://localhost:8080/
docker run --name evolve -p 8080:80 -d evolve
```
