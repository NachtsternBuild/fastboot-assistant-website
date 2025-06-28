# fastboot-assistant-website
Website for the Fastboot-Assistant using [Jekyll](https://jekyllrb.com/).


### How to build and run website locally
#### How to install Ruby and Jekyll
> [!WARNING]
> **Easier Snap setup is blocked by [snap.ruby#14](https://github.com/ruby/snap.ruby/issues/14)**
> **Please use native packages for now.**

<!--
```bash
$ sudo snap install ruby --classic
$ bundle env
$ bundle install
$ bundle exec jekyll serve --livereload
```
Browse to http://127.0.0.1:4000/
Jekyll will automatically refresh the page with each change you make to the source files.
For more information check https://jekyllrb.com/docs/
-->

1. Add `export GEM_HOME=${HOME}/.gem` to _~/.profile_ or _~/.bashrc_
2. Add `export PATH=${PATH}:$(ruby -r rubygems -e 'puts Gem.user_dir')/bin` to _$PATH_
3. `sudo apt-get install ruby-full build-essential zlib1g-dev` to install Ruby and its dependencies
4. Reload Linux or terminal session for changes to take effect
5. Verify enviroment configuration:
  ```bash
  $ ruby -r rubygems -e 'puts Gem.dir'
  /home/<user>/.gem
  $ ruby -r rubygems -e 'puts Gem.user_dir'
  /home/<user>/.gem/ruby/3.0.0
  ```
6. `gem install --user-install bundler` to install Ruby package manager
7. Execute `bundle env` in the project root directory to check environment configuration briefly.
  Bundler _path_, _Gemfile_ depepdencies, _Gemfile.lock_ should be correctly identified, i.e.
  ```bash
  ...
  ## Bundler settings
  path
    Set for your local app (/path/to/fastboot-assistant-website/.bundle/config): "vendor/bundle"
  
  ## Gemfile
  ### Gemfile
    ruby
  source "https://rubygems.org"
  
  ### Gemfile.lock
  GEM
    remote: https://rubygems.org/
  ...
  ```
8. Execute `bundle install` to install dependencies listed in _Gemfile_. Installation should successfully complete, i.e.
  ```bash
  Bundle complete! 8 Gemfile dependencies, 99 gems now installed.
  Bundled gems are installed into `./vendor/bundle`
  ```
9. Execute `bundle exec jekyll build` to build the website for the first time.
10. Now you can serve the website locally as per instruction below.

#### How to run Jekyll
Execute `bundle exec jekyll serve --livereload` to build and serve the website at http://127.0.0.1:4000/
Jekyll will automatically refresh the page with each change you make to the source files.
