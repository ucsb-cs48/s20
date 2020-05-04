# s20

https://ucsb-cs48.github.io/s20/

Jekyll based website for UCSB CS48, Spring 2020

Website: <https://ucsb-cs48.github.io/s20/>

The theme currently being used can be find in the jekyll-theme value
in `_config.yml`

The navigation is set by the values in `_data/navigation.yml`

Jekyll status on Travis-CI: [![Build Status](https://travis-ci.org/ucsb-cs48/w20.svg?branch=master)](https://travis-ci.org/ucsb-cs48/s20)

* Travis-ci: https://travis-ci.org/ucsb-cs48/s20
* To add a status image like this in your README.md, see [these instructions](https://docs.travis-ci.com/user/status-images/)

To test locally:
* One time setup:
    * `git clone` the repo
    * Install rvm (the Ruby version manager)
    * Run `./setup.sh` to install correct ruby version, bundler version, and bundle the gems
* From then on, to test the site locally:
    * Run `./jekyll.sh`
    * Point browser to <http://localhost:4000/s20/>


