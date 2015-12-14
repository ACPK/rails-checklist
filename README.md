# Rails Checklist

A checklist of things to look at to ensure that your Rails setup is pitch perfect.

## APIs

- [ ] The app is using [Active Model Serializers](https://github.com/rails-api/active_model_serializers) instead of [jBuilder](https://github.com/rails/jbuilder) or [Rabl](https://github.com/nesquena/rabl).
- [ ] The app is following the [JSON API](http://jsonapi.org/) format.

## Assets

- [ ] Assets are gzip'd.
- [ ] Ensure Javscript is async unless you're in `assets.debug` mode.
  ```ruby
  javascript_include_tag 'application', 'data-turbolinks-track' => true, async: !Rails.application.config.assets.debug
  ```

- [ ] Assets are cached through a CDN such as [Cloudfront](http://aws.amazon.com/cloudfront/) or [Cloudinary](http://cloudinary.com/).
- [ ] If using [Bootstrap](http://getbootstrap.com/) or [Foundation](http://foundation.zurb.com/), ensure that you're only using the components that you require.
- [ ] Images and videos are stored on an asset server such as [AWS S3](https://aws.amazon.com/s3/).
- [ ] You're using [Turbolinks](https://github.com/rails/turbolinks) to improve page loading.

## Caching

- [ ] You're using [Redis](http://redis.io/) or [Memcached](http://memcached.org/).

## Continious Integration

- [ ] A CI is running tests per push and merge such as [TravisCI](https://travis-ci.org/) or [CircleCI](https://circleci.com/).
- [ ] A CI is reporting test coverage changes such as [Coveralls](https://coveralls.io/) or [CodeClimate](https://codeclimate.com/).
- [ ] A CI is ensuring that the app's dependencies are up to date such as [Gemnasium](https://gemnasium.com/).
- [ ] After a PR merge, a CI will deploy the application.

## Database

- [ ] The database exists on its own server.
- [ ] [PostgreSQL](http://www.postgresql.org/) is being used.

## Development

- [ ] Bullet is being used to catch n+1s.
- [ ] Better Errors is being used to provide better error pages.
- [ ] [Spring](https://github.com/rails/spring) or [Zeus](https://github.com/burke/zeus) are being used to improve the application load time.

## Production

- [ ] [Skylight](http://www.skylight.io/) is monitoring the application.
- [ ] The app is being monitored with [TuneMyGC](https://tunemygc.com/) to improve the application's GC performance.
- [ ] Errors are caught by a service such as [Airbrake](https://airbrake.io/).
- [ ] Errors are automatically opening new issues on Github via an integration service such as [Zapier](https://zapier.com/).
- [ ] You're using SSL and all requests are going to the https protocol.
