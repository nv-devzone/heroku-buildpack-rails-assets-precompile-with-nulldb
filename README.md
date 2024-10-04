# rails assets:precompile with nulldb

This is a [Heroku Buildpack](http://devcenter.heroku.com/articles/buildpacks) for running `rails assets:precompile` with the [nulldb](https://github.com/nulldb/nulldb) adapter.

This buildpack is intended for use after [heroku-buildpack-ruby](https://github.com/heroku/heroku-buildpack-ruby). 

When precompiling assets, Rails attempts to connect to the database. If this is not possible, the Heroku `build` phase will fail. A workaround is to use [nulldb](https://github.com/nulldb/nulldb) as the database adapter during asset precompilation:

```sh
$ DATABASE_URL='nulldb://nulldb' bundle exec rails assets:precompile
```

## Usage

```
$ heroku buildpacks:add https://github.com/nv-devzone/heroku-buildpack-rails-assets-precompile-with-nulldb.git
```
