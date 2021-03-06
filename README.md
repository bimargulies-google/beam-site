# Apache Beam website

This is the website for [Apache Beam](https://beam.apache.org/), hosted at:

    https://beam.apache.org/

## About this site

The Beam website is built using [Jekyll](http://jekyllrb.com/). Additionally,
for additional formatting capabilities, this website uses
[Twitter Bootstrap](http://getbootstrap.com/).

### Repository Structure
    
This repository contains:

1. `src/`: the source of the site, including markdown files containing the bulk of the content
1. `content/`: html generated from the markdown (which is what is actually hosted on the website)

## Development Workflow

### Setup

Install [Ruby Gems](https://rubygems.org/pages/download), a package management framework for Ruby.

Install [Bundler](http://bundler.io/v1.3/rationale.html), which  we use to specify dependencies and ensure
a consistent environment for building the website, even across multiple developers on different machines:

	$ gem install bundler

Use Bundler to download the versions of each dependency specified in the website's `Gemfile.lock`, 
including [Jekyll](https://jekyllrb.com/):

	$ bundle install --deployment
	
This will install a number of gems in a local `./vendor` directory.

### Active development

Launch Jekyll via Bundler in order to guarantee that the appropriate versions of the dependencies are used:

	$ bundle exec jekyll serve

Jekyll will start a webserver on port `4000`. As you make changes to the
content, Jekyll will rebuild it automatically. This is helpful if you want to see
how your changes will render in realtime.

In addition, check for dead links and the like by running the tests via:

    $ bundle exec rake test

Both of these commands will cause the `content/` directory to be generated. Merging autogenerated content can
get tricky, so please leave this directory out of your commits and pull request by doing:

	$ git checkout -- content

The committer doing the final merge will generate the `content/` directory at that time.

## Additional Information

### Writing blog posts

Blog posts are created in the `_posts` directory.

If this is your first post, make sure to add yourself to `_data\authors.yml`.

While you a working on your post before the publishing time listed in its header,
add `--future` when running Jekyll in order to view your draft on your local copy of
the site.

### Adding Jekyll plugins

If you modify the site to use additional Jekyll plugins, add them in `Gemfile`
and then run `bundle update`, which will regenerate the complete `Gemfile.lock`.
Make sure that the updated `Gemfile.lock` is included in your pull request. For more information,
see the Bundler [documentation](http://bundler.io/v1.3/rationale.html).

## Apache License

Except as otherwise noted this software is licensed under the
[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
