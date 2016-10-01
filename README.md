bower-collect
-------------
#### Easily integrate Bower with backend frameworks like Django and cloud hosting services like Heroku by adding a collect command to bower.

## Usage

`bowerc collect` or with alias `bower collect` 

Use all other bower commands exactly as you did before.

OPTIONS:

    -a | --app       Specify root directory to install dependancies
                     default: A directory with the same name as pwd
    
    -d | --directory Specify the sub-directory to install dependancies
                     default: static/bower_components
    
    -e | --exclude   A comma seperated list of additional directories 
                     to exclude from the package serach.
                     default: static,components,bower_components
## Why?

Backend frameworks like Django have complex project structures with modules located in various locations.  Each of these modules may incorporate frontend dependancies.  The `bower collect` command simplifies the process of linking all these local bower.json packages to the root project so that you can install all bower dependancies at the root project level.

## What exactly does it do?

Running the collect command simply searches for local bower packages in your project structure and adds it as a dependency to a root level bower.json file. Then it creates a root level .bowerrc to designate an install directory of your choosing.  Finally, a node package.json file is crated to install bower and exicute bower install. 

## Why is this better then running a grunt task or using things like django-bower?

This is a local command that adds noting to your apps server footprint, it siply sets up your project to work the way it's suposed to.  If your utilizing grunt for many other things then it's no big deal, but Why install grunt and run an extra set of commands when bower is quite capeable of getting the job done.  Apps like django-bower just get in the way of using bower properly and are simply not necessary. 

## Ok fine, how do I get my project to work with heroku?
    
Check your buildpack list:

    heroku buildpack --app your-app-name

Add the nodejs buildpack to your herku app at index 1, if it's not there already

    herou buildpack:add heroku/nodejs --index 1 --app your-app-name

Remove any muti buildpacks or other special build pacs for getting bower to work with your project
and make sure you have the heroku buildpack for you app's platform installed. heroku/python, heroku/python3, heroku/ruby, etc..

## Instalation

Add the bowerc file to a directory available on your system path

```
curl -OLk https://raw.githubusercontent.com/arctelix/bower-collect/master/bowerc
chomd 755 bowerc
mv bowerc  /usr/local/bin/bowerc
```
Optionally create an alias in your shell's rc file, comonly .bashrc

`alias bower='bowerc'`
