# Learning Elixir

- Use [Typespecs](https://hexdocs.pm/elixir/1.12/typespecs.html) for type checking & safety. [TypedStruct](https://hexdocs.pm/typedstruct/readme.html) for easier struct definitions. [typed_struct](https://hexdocs.pm/typed_struct_uberbrodt/TypedStruct.html)<sup><i>is not maintained</i></sup>
- Resources list - [Masters of Elixir](https://github.com/abreujp/masters-of-elixir)
- Master list for everything Elixir - [Awesome Elixir](https://github.com/h4cc/awesome-elixir) <sup><i>See the up-to-date libraries [here](https://awsm-elixir.rubybox.dev)</i></sup>
-  Security in Elixir list on [Reddit](https://www.reddit.com/r/elixir/comments/1hg26n0/comment/m2k7rce/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)
- [Erlang Ecosystem Foundation Security WG](https://erlef.github.io/security-wg/)
- [Handling env variables](https://www.sean-lawrence.com/handling-environment-variables-in-elixir-phoenix-applications)

## Setting up Phoenix Channels
- [Client Libraries List](https://hexdocs.pm/phoenix/channels.html#client-libraries)
- [Client in Rust](https://github.com/liveview-native/phoenix-channels-client)
- [Phoenix Channels with React Redux](https://github.com/trixtateam/phoenix-to-redux)
- [Phoenix Channels with React SPA](https://github.com/syamsulmj/elixir-and-react-spa-websocket/blob/master/react-phoenix-websocket/src/App.js)
- [Phoenix.js](https://github.com/phoenixframework/phoenix/blob/v1.3/assets/js/phoenix.js)<sup><i>Might be outdated</i></sup>

### Getting Phoenix.js
```bash
git clone https://github.com/phoenixframework/phoenix
cd phoenix/assets
npm i
```


## Important CLI commands
### Create a new project for API without LiveView & HTML
```bash
mix phx.new kayaan_chat --app kayaan_chat --database postgres --no-live --no-html --binary-id --no-esbuild --no-gettext --no-tailwind --no-mailer
```
> Remove `-—no-mailer` to have mailing setup.
> Dont use `--no-assets` flag. [Many things depend on it](https://community.fly.io/t/unable-to-deploy-phoenix-app-without-assets/3798/4).


### Create a new schema & migration.
```bash
mix phx.gen.schema User users name:string email:string \
bio:string number_of_pets:integer
```

### Create controller, context, schema, table migrations & tests
```bash
mix phx.gen.json Accounts Account accounts email:string hashed_password:string
```
> Best suitable for controllers which are straightforward crud operations. Customising the tests to work can be a pain.

### Create context, schema, table migrations & tests
```bash
mix phx.gen.context Accounts Account accounts email:string hashed_password:string
```

### Run the migration
```bash
mix ecto.migrate
```
> Mix assumes that we are in the development environment unless we tell it otherwise with `MIX_ENV=prod mix ecto.migrate`.


## Important Libraries
### CORS
- [Corsica](https://hexdocs.pm/corsica/Corsica.html)
- [Cors Plug](https://github.com/mschae/cors_plug) <sup><i>last updated in Apr '22</i></sup>

### Write Logs to file
- [LogFileBackend](https://github.com/onkel-dirtus/logger_file_backend)


### Linting & Code Hygiene
- [Credo](https://github.com/rrrene/credo) is a static code analysis tool for the Elixir language with a focus on teaching and code consistency.

- [Dialyxir](https://github.com/jeremyjh/dialyxir) makes working with [Dialyzer](https://www.erlang.org/doc/apps/dialyzer/dialyzer.html) easy.
 is a static analysis tool that identifies software discrepancies, such as definite type errors, code that is unreachable because of programming errors, and unnecessary tests in single Erlang modules or an entire codebase.

 ### LiveView Components
 - [Surface](https://hexdocs.pm/surface/Surface.html)

### ORM
- [Ecto](https://hexdocs.pm/ecto)
> Use [embedded schemas](https://hexdocs.pm/ecto/embedded-schemas.html) for nested data to be stored as json/jsonb/array.

#### Multi Tenancy 
- [Multi Tenancy With Multiple Schemas](https://github.com/ateliware/triplex)

### Security
- [Cloak Ecto](https://hexdocs.pm/cloak_ecto/readme.html) helps to encrypt values when storing in database.

### Telemetry
- [Telemetry](https://hexdocs.pm/telemetry/readme.html)

### Validation
- [Validate](https://hexdocs.pm/validate/readme.html)
- [Vex](https://github.com/CargoSense/vex)
- [ChannelSpec](https://github.com/felt/channel_spec) - Validate Socket Input Params
- [ExValidator](https://github.com/costaraphael/ex_validator)<sup><i>Last update Apr '17</i></sup>


## Important Tools
### RBAC
- https://github.com/casbin/casbin-ex
- https://github.com/schrockwell/bodyguard

### Admin Console
- [Kaffy](https://github.com/kaffeins/kaffy)
- [Backpex](https://github.com/naymspace/backpex)
- [ExAdmin](https://github.com/smpallen99/ex_admin) <sup><i>Last updated Apr '18</i></sup>

### Email templating
- [Premailex](https://www.hex.pm/packages/premailex)

### Profiling & Monitoring
- [Recon](https://ferd.github.io/recon/overview.html)
- [Enforcing Code Quality in Elixir](https://leandrocp.com.br/2019/06/enforcing-code-quality-in-elixir/)
- [Track Phoenix Channels](https://hexdocs.pm/phoenix_pubsub/Phoenix.Tracker.html)
- [Tsung](http://tsung.erlang-projects.org/) Is a benchmarking tool for sockets. Gary Rennie shows how to [benchmark WebSockets using Tsung tool](http://www.archive.elixirconf.eu/elixirconf2016/gary-rennie)

### Observability & Monitoring
- [Alternatives](https://signoz.io/comparisons/sentry-alternatives/)
- [AppSignal](https://docs.appsignal.com/elixir)
- [Appsignal tracking errors](https://blog.appsignal.com/2024/07/09/track-errors-in-phoenix-for-elixir-with-appsignal.html)
- [Sentry Docs](https://docs.sentry.io/platforms/elixir/)
- [Event Filters in Sentry](https://medium.com/wttj-tech/observability-reducing-noise-in-elixir-applications-5bd39d494101)
- [Sentry & Open Telemetry](https://ananthakumaran.in/2022/06/11/sentry-performance-monitoring-for-elixir.html)
- [Erroro tracker in Elixir](https://www.youtube.com/watch?v=TNmSVjGyZx0)
- [Grafana & Promotheus Observability in Elixir](https://www.youtube.com/watch?v=98kYFy6nGXs)

### Soft Delete
- [Ecto Soft Delete](https://github.com/revelrylabs/ecto_soft_delete)

## Learning Resources
- [Handling amount with custom Ecto Types](https://fullstackphoenix.com/tutorials/handling-amount-fields-in-a-phoenix-application-with-ecto-custom-types)
- [API versioning strategies in Phoenix](https://web.archive.org/web/20210309052043/https://elviovicosa.com/freebies/versioned-apis-with-phoenix-by-elvio-vicosa.pdf)
  
### Email sending
- [Swoosh with Premailex](https://fullstackphoenix.com/tutorials/implementing-html-emails-in-phoenix-with-swoosh-and-premailex)
- [Tailwind styled emails](https://fullstackphoenix.com/tutorials/tailwind-emails-phoenix-swoosh)

### Multi Tenancy
- [Multi Tenancy with Multiple schemas](https://www.reddit.com/r/elixir/comments/1ep1uhu/multi_tenancy_with_elixir_and_phoenix/)
- [Multi Tenancy with Foreign Keys](https://hexdocs.pm/ecto/multi-tenancy-with-foreign-keys.html)
### Phoenix Guides
- [Phoenix from hexdocs](https://hexdocs.pm/phoenix)

### Profiling & Monitoring
- [Profiling in Elixir Blog](https://pulkitgoyal.in/profiling-in-elixir)

### Soft deletes
- [Soft Deletes by Ecto](https://dashbit.co/blog/soft-deletes-with-ecto)
- [Soft deltes at PostgreSQL](https://evilmartians.com/chronicles/soft-deletion-with-postgresql-but-with-logic-on-the-database#cascade-deletes)

### Swagger
- [Foundational setup of swagger](https://swagger.io/blog/api-development/generate-api-documentation-effortlessly-from-your/)

### PETAL stack with Typescript
- [setup](https://disusered.com/blog/phoenix-with-typescript/)
- [Video](https://elixirforum.com/t/getting-started-with-typescript-in-your-phoenix-projects/61122)

### Deployment
- [Debugging prod server locally](https://stackoverflow.com/a/47417932/13305008)

### Testing
- [Testing WebSocket Clients with Mock Server](https://pulkitgoyal.in/testing-websocket-clients-in-elixir-with-a-mock-server)
- [Testing Phoenix Channels](http://graemehill.ca/testing-phoenix-channels/)

### Hosting
- [On Digital Ocean](https://bjornbr.is/deploying-elixir-and-phoenix/)
