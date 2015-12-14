# Rails Checklist

A checklist of things to look at to ensure that your Rails setup is pitch perfect.

## APIs

- [ ] The app is using Active Model Serializers instead of jBuilder or Rabl.
- [ ] The app is following the JSON API format.

## Assets

- [ ] Assets are gzip'd.
- [ ] Ensure Javscript is async unless you're in `assets.debug` mode.
  ```ruby
  javascript_include_tag 'application', 'data-turbolinks-track' => true, async: !Rails.application.config.assets.debug
  ```
- [ ] Assets are cached through a CDN
- [ ] If using Bootstrap or Foundation, ensure that you're only using the components that you require.
- [ ] Images and videos are stored on an asset server such as AWS S3.
- [ ] You're using Turbolinks to improve page loading.

## Caching

- [ ] You're using Redis and not Memcache.

## Continious Integration

- [ ] A CI is running tests per push and merge such as TravisCI or CircleCI.
- [ ] A CI is reporting test coverage changes such as Coveralls or CodeClimate.
- [ ] A CI is ensuring that the app's dependencies are up to date such as Gemnasium.
- [ ] After a PR merge, a CI will deploy the application.

## Database

- [ ] The database exists on its own server.
- [ ] PostgreSQL is being used.

## Development

- [ ] Bullet is being used to catch n+1s.
- [ ] Better Errors is being used to provide better error pages.
- [ ] Spring or Zeus are being used to improve the application load time.

## Production

- [ ] Skylight is monitoring the application.
- [ ] The app is being monitored with TuneMyGC to improve the application's GC performance.
- [ ] Errors are caught by a service such as Airbrake.
- [ ] Errors are automatically opening new issues on Github via an integration service such as Zapier.

