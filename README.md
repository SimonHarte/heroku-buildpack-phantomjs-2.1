Heroku buildpack: PhantomJS 2.1.1
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) of [PhantomJS 2.1.1](http://phantomjs.org).

Usage
-----

Requires a [Cedar-14](https://devcenter.heroku.com/articles/cedar-14-migration) stack.
Migrate to this stack prior to running.

Also required is the [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi)
and the [heroku-buildpack-apt](https://github.com/ddollar/heroku-buildpack-apt)


Example usage - note the listed packages are required:

```shell
$ heroku create --stack cedar-14 --buildpack https://github.com/ddollar/heroku-buildpack-multi
$ echo "https://github.com/ddollar/heroku-buildpack-apt" >> .buildpacks
$ echo "https://github.com/SimonHarte/heroku-buildpack-phantomjs-2.1.git" >> .buildpacks
$ cat <<EOT >> Aptfile
libicu52
libjpeg8
libfontconfig
libwebp5
EOT

$ git push heroku master
```

You might need to force using the multi buildpack by following steps described in their [readme](https://github.com/ddollar/heroku-buildpack-multi).