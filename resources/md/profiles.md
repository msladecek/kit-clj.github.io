## Profiles

Running `clojure -X:new :template io.github.kit-clj :name yourname/app` will create an application using the default profile template.
However, if you would like to attach further functionality to your template you can append
profile hints for the extended functionality.

Default libs included with no profile specified:

- `kit-core`
- `kit-undertow`
- `kit-repl`

Additional profiles:

- `+bare` - Only includes the `kit-core` and `kit-undertow` libraries as the foundation
- `+xtdb` - Adds the `kit-xtdb` lib
- `+hato` - Adds the `kit-hato` lib
- `+metrics` - Adds the `kit-metrics` lib
- `+quartz` - Adds the `kit-quartz` lib
- `+redis` - Adds the `kit-redis` lib
- `+selmer` - Adds the `kit-selmer` lib
- `+sql` - Adds the `kit-sql` and `kit-postgres` libs
- `+full` - Adds the libs `kit-xtdb`, `kit-hato`, `kit-metrics`, `kit-quartz`, `kit-redis`, `kit-selmer`, and `kit-sql`

To add a profile simply pass it as an argument after your application name, eg:

```
clojure -X:new :template io.github.kit-clj :name yourname/app :args '[+selmer]'
```

You can also mix multiple profiles when creating the application, eg:

```
clojure -X:new :template io.github.kit-clj :name yourname/app :args '[+selmer +xtdb]'
```

### Libraries

- `kit-core` - basic utility functions used by some other libs
- `kit-xtdb` - Simple binding to connect to a [XTDB](https://xtdb.com/) database node
- `kit-hato` - HTTP client using [hato](https://github.com/gnarroway/hato)
- `kit-metrics` - Configurable metrics using [iapetos](https://github.com/clj-commons/iapetos)
- `kit-quartz` - Scheduler using [cronut](https://github.com/troy-west/cronut) as an integrant binding for [quartz](http://www.quartz-scheduler.org/). Exposes the `cronut` API, simply some extensions for `aero` and utilities
- `kit-redis` - An extension of [core.cache](https://github.com/clojure/core.cache) for Redis via [carmine](https://github.com/ptaoussanis/carmine)
- `kit-repl` - Socket REPL integrant binding
- `kit-selmer` - Templating configuration with [selmer](https://github.com/yogthos/Selmer)
- `kit-sql` - Generic SQL integrant binding. Uses [conman](https://github.com/luminus-framework/conman), [next.jdbc](https://github.com/seancorfield/next-jdbc), [hugsql](https://www.hugsql.org/), and [migratus](https://github.com/yogthos/migratus) directly, or implicitly. By default, imports `kit-postgres` lib which supports Postgresql
- `kit-postgres` - lib with data bindings and utilities for working with Postgres
- `kit-undertow` - Server binding via [luminus-undertow](https://github.com/luminus-framework/luminus-undertow)
