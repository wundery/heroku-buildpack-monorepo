# Heroku Monorepo Buildpack

This buildpack helps with deploying multiple apps, having different heroku support files, from a monorepo.

Different from similar buildpacks which either move folders around or just copy the procfile to the root folder, this buildpack allows to just give a list of files (procfile, app.json or files required by other buildpacks) to move to the root.

## Usage

1. Create apps in different folders of the monorepo
2. Create apps on Heroku
3. Add `HOIST_APP_FILES=app_folder/Procfile,app_folder/app.json` (or any other list of files you want to copy to the root)
4. Add the build pack `heroku buildpacks:add -a <app name> https://github.com/branchbob/heroku-buildpack-monorepo`
5. Make sure the `Procfile`, `app.json` or (if you're running a node app) `package.json` direct the `web` process (or `start` script) to the app/folder you want to launch

## Authors

[Johannes Klose](https://github.com/extronics)
