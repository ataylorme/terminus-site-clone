**Warning** this plugin is still in development. Use at your own risk.

# Terminus Site Clone
Site Clone - A [Terminus](http://github.com/pantheon-systems/terminus) plugin that adds the `site:clone` command to facilitate cloning sites on [Pantheon](https://pantheon.io/).

## Disclaimer
While this script has worked well for us your mileage may vary due to local machine configuration.

This repository is provided without warranty or direct support. Issues and questions may be filed in GitHub but their resolution is not guaranteed.

## Installation
Clone this project into your Terminus plugins directory found at `$HOME/.terminus/plugins`. If the `$HOME/.terminus/plugins` directory does not exists you can safely create it. See [installing Terminus plugin](https://pantheon.io/docs/terminus/plugins/#install-plugins) for details.

## Requirements
* [Terminus](https://github.com/pantheon-systems/terminus) `1.1.1` or greater
* [git command line](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Usage
`terminus site:clone <source>.<env> <destination>.<env>` where `<source>` and `<destination>` are site UUID or machine name and `<env>` is a valid environment (dev or multidev).

Code cannot be cloned to or from test and live environments as work must go through [the Pantheon workflow](https://pantheon.io/docs/pantheon-workflow/). You can, however, use `--no-code` to clone the files and database to or from a test or live environment.

You can also pass the argument(s) `--no-database`, `--no-files` and/or `--no-code` to skip cloning one or more items. You cannot, however, skip all three as there would be nothing left to clone.

**Note files and database backups over 500MBs will not work** due to Pantheon import file size limits. If your files or database are over 500MB they will need to be [manually migrated](https://pantheon.io/docs/migrate-manual/).

## License
MIT