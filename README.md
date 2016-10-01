bower-collect
-------------
#### Easily integrate bower with backend frameworks like Django and Cloud hosting services like Heroku by adding a collect command to bower.

## Usage

`bower collect`

You use all other bower commands exactly as you did before.

## Why?

Backend frameworks like Django have complex project structures with modules located in various locations.  Each of these modules may incorporate frontend dependancies.  The `bower collect` command simplifies the process of linking all these local bower.json packages to the root project so that you can install all bower dependancies at the root project level.

## What does it do?

Running the collect command simply searches for any bower.json files in your project structure and adds the local bower package as a dependency to a root level bower.json file. Then creates a root level .bowerrc to designate an install directory of your choosing.  Finally, a node package.json file is crate to install bower and exicute bower install. 

## Instalation

Add the bowerc file to a directory available on your system path

```
curl -OLk https://raw.githubusercontent.com/arctelix/drag-resize-snap/v0.1.1/dist/drs.js
mv bowerc  /usr/local/bin/bowerc

```
Optionally create an alias in your shell's rc file, comonly .bashrc

`alias bower='bowerc'`
