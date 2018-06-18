# ejsrun 🏃🏻‍♂️

A command line runner for [EJS](http://ejs.co/) - similar to [ejs-cli](https://github.com/fnobi/ejs-cli)

I wrote this (quickly) because I needed to create templates for a project that merged various options before sending to EJS for processing.

Also, I prefer to keep my options in an [HJSON](http://hjson.org/) file. 

## Features

- Allows multiple `-O` options with parameters and merges them to pass to the **ejs** processor. This allows you to have various levels of providing values (think default values and overrides, and/or configuration values and override on command line, etc.)
- Can use with [HJSON](http://hjson.org/) files (my preferred configuration file format)
- Specify multiple **ejs** files on the command line (or even a glob) and output files are created with same name (and `.html` extension).

## Example

```bash
ejsrun pages/*.ejs -O defaults.json -O config.hjson -O "{\"develop\":true}"
```

The above example processes all `.ejs` pages within the `pages` directory and creates files with the same names and `.html` extension after processing with **EJS**. The *data* used in the template substitutions is a combination of the JSON from `defaults.json`, with overrides from the `config.hjson` and a final override of `develop: true`.