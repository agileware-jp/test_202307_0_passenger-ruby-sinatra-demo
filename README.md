## Passenger: Sinatra example app

This is a [Sinatra](http://www.sinatrarb.com/) hello world example app for [the Passenger application server](https://www.phusionpassenger.com/).

The `main` branch contains the code without Passenger installed.

The `end_result` branch contains the code with Passenger installed.

Run `git diff origin/main..origin/end_result` to see what's different.

### Running the app

Install dependencies locally:

```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

Run the application:

```bash
bundle exec passenger start
```

You can then view the application by pointing your browser to localhost:port where port is the number given when starting the application.

### Running the app with custom Nginx template

```console
bundle exec passenger start --nginx-config-template nginx.conf.erb
```

Open http://localhost:3000/ to see `"foobarbaz"`.

Open http://localhost:3000/files to see https://www.ruby-lang.org/ja/ (only HTML).

More information: https://www.phusionpassenger.com/library/config/standalone/intro.html#nginx-configuration-template
