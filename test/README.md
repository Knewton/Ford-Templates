# Unit test

## Running the test
Place this folder within a web-server, or simply run `start.sh` to begin a
simple Python Web Server on port 8080.

Due to a security restriction common to all browsers, the test must run within
a web server, and cannot be executed reliably off the `file://` protocol.

Once running in a web server, simply go to this `index.html` page to see the
results of the unit test.

## Adding new tests/fixing old tests
You can view which tests are run, add new tests, and fix up old ones in the
`test.js` file.

These unit tests are written in [ScrewUnit](https://github.com/nkallen/screw-unit).

**Notice**: Any HTML needed by the test should be placed in the `index.html`
file. Any elements referenced within `test.js` should either be created there
or exist within `index.html`.

# First time setup

## Compiling the test
First, you must edit `manifests/system_under_test.js` to reference the code you
will be testing. Ensure that within your manifest you specify the **relative
path** to the code. It should look something like:

    {
        "system_under_test": {
            "uri": "../jquery.my_plugin_name",
            "comp": ["js", "css"],
            "reqs": ["jquery"],
            "link": true
        }
    }

Once you have completed editing your system_under_test manifest, simply run
the `ford build` command. You should only need to run the build once in this
directory to fetch required files; after that simply make changes and refresh
in a browser.

## Writing an effective unit test
If you are unfamiliar with what a unit test is, check out this
[fantastic overview of unit testing](http://pragprog.com/magazines/2012-01/unit-tests-are-first).

