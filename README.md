# Just an early prototype, move along.

# Building & Running Locally

The blog is a simple Jekyll-powered site hosted by GitHub Pages. To run it locally, see [the Jekyll docs](https://jekyllrb.com/docs/installation/).

In case you're on an Linux-based environment, you can follow these instructions (replace apt with your distro's package manager if needed):

```shell
# First, install Jekyll's dependencies:
sudo apt install ruby-full build-essential zlib1g-dev

# Second, let's set an environment variable just so that we don't install Jekyll as root user:
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Third, install Jekyll:
gem install jekyll bundler

# Finally, we need to install the rest of the gems for the project.
# In the project folder, run:
bundle install
```

### Serve

```shell
bundle exec jekyll serve --host 0.0.0.0
```

The site should now be available at http://0.0.0.0:4000/ on your local machine, and your local machine's IP address on your network—great for testing on mobile OSes.

### Publish to demo site

First, commit your changes to the master branch or whatever branch you're currently on.

Then, make Jekyll build the site:
```shell
bundle exec jekyll build
```

Then, push just the _site folder to gh-pages branch:
```shell
git subtree push --prefix _site origin gh-pages
```