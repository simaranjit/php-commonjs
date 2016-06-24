#PHP CommonJS Compiler

##What is CommonJS:
CommonJS modules enables you to include javascript modules within the current scope and effectively keeps the global scope from being polluted.

This massively reduces the chance of naming collisions and keeps code organised.

##About this library
After cloning this repo, you will find three directories and one file
 - utils
 - source
 - compiled
 - compile.php
 
 ###Utils
 Utils directory contains all PHP related stuff, so it should not be touched.
 
 ###Source
 Source directory will contains all the CommonJS modules and different files. If you open directory, you will notice that there is already main.js and jquery modules for referrence.
 
 ###Compiled
 This directory stores default compiled file, named `script.js` in it.
 
##How to use this library
 Usage of this library is pretty simple and easy.
 
 It requires simply putting all the commonJS files under source directory and running compiile.php file from CLI, using somethign like this
 ```>php compile.php```
 
##Change Destination path
 There could be the case that custom destination path is needed. That is also pretty easy here. It requires minor tweak in `compile.php` file. Here are the steps.
 - Open `compile.php` file and look for code:
 ```
 (new \CommonJS\CommonJS())->save(true);
 ```
 Change this to:
 ```
 (new \CommonJS\CommonJS())->save(true, './custom/path/file.js');
 ```
 Changing source path is not possible since it doesn't make sense.
 
##Minify source code
 This library by default supports minified version and that can also be changed. To avoid creating minfied version of file, minor tweak is required. Here are the steps.
 Open `compile.php` file and look for code:
 ```
 (new \CommonJS\CommonJS())->save(true);
 ```
 Change this to:
 ```
 (new \CommonJS\CommonJS())->save(false);
 ```
 ##What are the libraries used internally
 This package uses two different PHP libraries MattCG and JShrink.

##Minimum PHP version requirement
PHP 5.3

##Things to take care during implementation
 - All new modules should come under `src/modules`
 - `Source` and `Compiled` directories should have proper permissions
 - If custom destination location is used, make sure that destination have proper exceptions.
 - compile.php must be executed after writing code.
