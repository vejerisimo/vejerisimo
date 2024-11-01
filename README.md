vejerisimo

[![pages-build-deployment](https://github.com/vejerisimo/vejerisimo.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/vejerisimo/vejerisimo.github.io/actions/workflows/pages/pages-build-deployment)

website readme

    npm install -g bower
    bower install

    bundle exec middleman
    bundle exec middleman build

    git add . --all
    git commit -m "update"
    (save)
    git push origin master

    cd build
    git add . --all
    git commit -m "update"
    (publish)
    git push origin gh-pages
