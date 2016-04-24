## GitPython

GitPython is a python library used to interact with git repositories, high-level like git-porcelain, or low-level like git-plumbing.

It provides abstractions of git objects for easy access of repository data, and additionally allows you to access the git repository more directly using either a pure python implementation, or the faster, but more resource intensive git command implementation.

The object database implementation is optimized for handling large quantities of objects and large datasets, which is achieved by using low-level structures and data streaming.

### REQUIREMENTS

GitPython needs the `git` executable to be installed on the system and available in your `PATH` for most operations. If it is not in your `PATH`, you can help GitPython find it by setting the `GIT_PYTHON_GIT_EXECUTABLE=<path/to/git>` environment variable.

* Git (1.7.x or newer)

The list of dependencies are listed in `./requirements.txt` and `./test-requirements.txt`. The installer takes care of installing them for you.

### INSTALL

[![Latest Version](https://pypip.in/version/GitPython/badge.svg)](https://pypi.python.org/pypi/GitPython/)
[![Supported Python Versions](https://pypip.in/py_versions/GitPython/badge.svg)](https://pypi.python.org/pypi/GitPython/)

If you have downloaded the source code:

    python setup.py install

or if you want to obtain a copy from the Pypi repository:

    pip install gitpython

Both commands will install the required package dependencies.

A distribution package can be obtained for manual installation at:

    http://pypi.python.org/pypi/GitPython

### RUNNING TESTS

The easiest way to run test is by using [tox](https://pypi.python.org/pypi/tox) a wrapper around virtualenv. It will take care of setting up environnements with the proper dependencies installed and execute test commands. To install it simply:

    pip install tox

Then run:

    tox

### SOURCE

GitPython's git repo is available on GitHub, which can be browsed at [github](https://github.com/gitpython-developers/GitPython) and cloned like that:

    git clone https://github.com/gitpython-developers/GitPython

### Live Coding

You can watch me fix issues or implement new features [live on Twitch][twitch-channel], or have a look at [past recordings on youtube][youtube-playlist]

* [Live on Twitch][twitch-channel] (just follow the channel to be notified when a session starts)
* [Archive on Youtube][youtube-playlist]

### INFRASTRUCTURE

* [User Documentation](http://gitpython.readthedocs.org)
* [Questions and Answers](http://stackexchange.com/filters/167317/gitpython)
 * Please post on stackoverflow and use the `gitpython` tag
* [Issue Tracker](https://github.com/gitpython-developers/GitPython/issues)
  * Post reproducible bugs and feature requests as a new issue. Please be sure to provide the following information if posting bugs:
    * GitPython version (e.g. `import git; git.__version__`)
    * Python version (e.g. `python --version`)
    * The encountered stack-trace, if applicable
    * Enough information to allow reproducing the issue

### How to make a new release

* assure `changes.rst` is up-to-date
* put new version into `VERSION` file
* run `./setup.py sdist`
* On https://pypi.python.org
 - Click `GitPython` (and pray it will not timeout)
 - Lucky ? Click `edit` on the last version, and copy the main description text
   to your clipboard - it's needed later.
 - On top of that page, click the `PKG file` button or drag & drop the one from
   `./GitPython.egg-info/PKG-INFO` on it. Then click the `add ...` button to 
   create a new version.
 - Paste the previously copied description text into the description field, and click the `add information` button on the very bottom of the page.
 - Click `GitPython` again and then click `files` of the newly created version.
 - Select `source package` in the dropdown, then choose or drag & drop 
   `./dist/GitPython-<version>.tar.gz` onto the file path.
 - Click the `upload` button.
* Run `git tag <version>` to mark the version you just uploaded to pypi.
* Run `git push --tags origin master` to publish the changes.
* finally, set the upcoming version in the `VERSION` file, usually be incrementing
  the patch level, and possibly by appending `-dev`. Probably you want to `git push` once more.
  
*NOTE:* At the time of writing, pypi wouldn't hear my prayers and did timeout on 
me, which is why button names are just *guesses*. It's advised to update this text
next time someone manages to publish a new release to a system so firmly rooted in
the past.

### LICENSE

New BSD License.  See the LICENSE file.

### DEVELOPMENT STATUS

[![Build Status](https://travis-ci.org/gitpython-developers/GitPython.svg)](https://travis-ci.org/gitpython-developers/GitPython)
[![Code Climate](https://codeclimate.com/github/gitpython-developers/GitPython/badges/gpa.svg)](https://codeclimate.com/github/gitpython-developers/GitPython)
[![Documentation Status](https://readthedocs.org/projects/gitpython/badge/?version=stable)](https://readthedocs.org/projects/gitpython/?badge=stable)
[![Issue Stats](http://www.issuestats.com/github/gitpython-developers/GitPython/badge/pr)](http://www.issuestats.com/github/gitpython-developers/GitPython)
[![Issue Stats](http://www.issuestats.com/github/gitpython-developers/GitPython/badge/issue)](http://www.issuestats.com/github/gitpython-developers/GitPython)

Now that there seems to be a massive user base, this should be motivation enough to let git-python return to a proper state, which means

* no open pull requests
* no open issues describing bugs

[twitch-channel]: http://www.twitch.tv/byronimo/profile
[youtube-playlist]: https://www.youtube.com/playlist?list=PLMHbQxe1e9MnoEcLhn6Yhv5KAvpWkJbL0
