# JustPark Engineering Blog
[![Build and Deploy](https://github.com/EngineeringEd/engineeringed/actions/workflows/pages-deploy.yml/badge.svg)](https://github.com/EngineeringEd/engineeringed/actions/workflows/pages-deploy.yml)

## Installation
The site uses Jekyll so requires that Ruby is installed as well as normal build utils for compiling C programs. This was built using MacOS (Darwin) so only the correct version of Ruby needs to be installed if this is what you are using also. The project was built using Ruby 3.1 and the CD uses this also. To install dependencies and Ruby, use a package manager or version manager such as Brew or rbenv respectively.

Once the system dependencies are installed, run `bundle install` to install all project dependencies.

## Usage
- `jekyll s` will serve the site on port 4000 locally
- `jekyll b` will build the site and place it in the `_site` directory

## Contributing
This repository is to be added to by JustPark engineers only. Any pull requests from outside sources will be ignored. If there are any amendments needed, please contact us via our website or any of the channels on our blog.

The syntax for blogposts is Markdown with some enhancements. For information on what is possible, please check the documentation for Chirpy, the theme used [here](https://chirpy.cotes.page/posts/write-a-new-post/)

## Troubleshooting
If `bundle install` is not working, try `exec bundle install`. This will force whatever bundler version is installed to run the install. You may get a warning. This can safely be ignored.

Bundler should be included with the Ruby installation if you installed this via package manager or version manager. If not, you can use `gem install bundler`. This may need to be run with elevated priviliges depending on your system.

If something is behaving oddly, and you are running on a platform that isn't Linux or Darwin, you may have to add the platform to the project. This can be done with the command `bundle lock --add-platform [PLATFORM]`.
Once done, you can run `bundle install` to install project dependencies

It's possible you could receive OpenSSL errors or something related to the RubyGem, eventmachine, when running the project on Darwin. If this happens, make sure OpenSSL is installed. If using Brew:

```bash
$ brew install openssl
```
Once done, run `bundle install` again. You may get errors when doing this. This confirms that the issue is with eventmachine. If you run:

```bash
$ gem install eventmachine -- --with-cppflags=-I/usr/local/opt/openssl/include
```

Then run `bundle install` to install all project dependencies.
