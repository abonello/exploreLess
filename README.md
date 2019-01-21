# Practicing LESS CSS preprocessor

Online [winless.org](http://winless.org/online-less-compiler). This Online LESS Compiler can help you to learn LESS.  

## Installing less on your system

You need [nodejs](https://nodejs.org) installed.  

Installing less using CLI
```
npm install -g less
```

We need a less compiler to translate less syntax to css. Example

```less
// Declaring variables
@border-width: 1px;
@red: #842210;

// Using variables
div#header {
    border: @border-width solid @red;
} 
```

will be translated to

```CSS
div#header {
  border: 1px solid #842210;
}
```

We need a file watcher that will automatically compile less code to css everytime that we make changes and save.

## Dead Simple Watch Compiler

Runs in CLI. Install from github page.  
After installing less, use:
```
npm install -g less-watch-compiler
```
To run:
```
less-watch-compiler FOLDER-TO-WATCH OUYPUT-FOLDER
```
Or:
```bash
$ less-watch-compiler FOLDER-TO-WATCH OUYPUT-FOLDER MAIN-FILE.less
```

Simply running `lessc` in the folder where you have the less files will compile themto css once.

```bash
$ lessc styles.less
```
will output to standard output which is the command line.

```bash
$ lessc styles.less styles.css
```
will compile the less file and output to the css file (overwriting/creating).

less-watch-compiler will by default output a minified css.

It can be configured using a json file, `less-watch-compiler.config.json`. Place this file in the root of your project.

All configurations options:
```json
{
    "allowedExtensions":[".less"],
    "watchFolder": "<input_folder>",   
    "outputFolder": "<output_folder>",
    "mainFile": "<main-file>",   
    "sourceMap": false,
    "plugins": "plugin1,plugin2",
    "less-args": "option1=1,option2=2",
    "runOnce": false,
    "enableJs": true,
    "minified":false
}
```
The advantage of the less-watch-compiler over the standard lessc is that once it is enabled to watch a file it will automatically recompile that less file to css whenever there is a change in the less file.

