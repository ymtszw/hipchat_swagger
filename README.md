# HipChat Swagger

HipChat API specifications written in [Swagger](http://swagger.io/) YAML.

Using [Swagger (currently OpenAPI) specification 2.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md).

# Status

Currently in development. Gradually hand-exported from [official HipChat API documentations](https://www.hipchat.com/docs/apiv2).

My intention is to use this Swagger interpreted API specs to generate HipChat client library
for languages I am using (especially [Elixir](http://elixir-lang.org/)).

Mostly I am constructing API spec YAML using online [Swagger Editor](http://editor.swagger.io/#/).

# Policy

- Meant to be used in generating client libraries.
- Not all of API aspects are covered. Especially, many schema information are purposefully omitted.
    - Simply lacking efforts on my side. HipChat API docs are large and fine-grained.
    - Relying on HipChat cloud/server's request validations, so that always latest and accurate validations can be applied.
        - If we try to apply client-side validations, we have to be very accurate about it,
          and must actively catch up on HipChat's API updates, which we cannot easily afford to.
- Always welcoming helps.
    - And I actually hope HipChat developers generously provide this type of structured spec file.
    - From the looks of API docs, I believe they already have this kind of centralized spec file(s) internally.
      Publishing them for third parties would be really cool!

# Usage

- As I mostly developing with online editor, files should be valid Swagger 2.0 specifications.
- You can just clone or submodule this repository, and import spec files for code generations, either using:
    - [Swagger Codegen](http://swagger.io/swagger-codegen/) for your favorite languages and/or frameworks
    - You own parser/code generator

# License

MIT
