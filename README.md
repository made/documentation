# made/documentation

Generate static documentation from markdown files.

## Installation

```bash
composer create-project made/documentation documentation
cd documentation
npm install
gulp
```

## Usage

This project should be used as a starting point to hold multiple documentation templates or just one, that's up to you.
It only contains a bare symfony project with the [`made/documentation-bundle`](https://github.com/made/documentation-bundle)
already installed.

Use the usual `yaml` configuration to add multiple namespace folders for twig as needed.

For further reference on the usage of the bundle see the *README* file of the `made/documentation` bundle. It can be 
found [here](https://github.com/made/documentation-bundle/blob/master/README.md).

An example of how to use the `documentation:build` command provided by the bundle:

```bash
# optional, but recommended
gulp

# this will use the example data, change the paths to your liking
php bin/console documentation:build ./content ./public/documentation -l documentation

# serve the document root
php -S localhost:80 -t ./public

# now browse to http://localhost:80/documentation to view the result
```

The gulpfile provided can be used to process any asset inside the `asset/` directory. By default, the assets are
compiled to `public/asset/`. The default template does also assume that location.

For some scenarios, the assets should probably reside in the same sub-folder as the documentation html files. To achieve
that, change the path inside of the `gulpfile.js` and make sure the root page link is prepended to the style/script
source.

## License

It's GPLv3.
