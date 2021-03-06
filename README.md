# :warning: DISCONTINUATION NOTICE

[HipChat itself is discontinued by Atlassian due to their partnership with Slack](https://www.atlassian.com/partnerships/slack).

This Swagger specification file is therefore no longer maintained, and goes archive. Thanks for your interest, though! :heart:

# hipchat_swagger

HipChat API specifications written in [Swagger](http://swagger.io/) YAML.

Using [Swagger (currently OpenAPI) specification 2.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md).

# Status

Currently in development. Gradually hand-exported from [official HipChat API documentations](https://www.hipchat.com/docs/apiv2).

APIs other than extension related ones are mostly included already.

My intention is to use this Swagger interpreted API specs to generate HipChat client library
for languages I am using (especially [Elixir](http://elixir-lang.org/)).

Mostly I am constructing API spec YAML using online [Swagger Editor](http://editor.swagger.io/#/).

# Policy

- Meant to be used in generating client libraries.
    - Some strings are slightly altered for easier programmatic manipulations, like camelize or underscore.
    - e.g. "OAuth" -> "Oauth"
- Cover APIs used in server side only.
- Not all of API aspects are covered. Especially, many schema information are purposefully omitted.
    - Simply lacking efforts on my side. HipChat API docs are large and fine-grained.
    - Some APIs are omitted for simplified code generation; e.g. APIs requiring specific content-types.
    - Intending to rely on HipChat cloud/server's request validations, so that always latest and accurate validations can be applied.
        - If we try to apply client-side validations, we have to be very accurate about it,
          and must actively catch up on HipChat's API updates, which we cannot easily afford to.
- Always welcoming helps.

# Usage

- As I mostly developing with online editor, files should be valid Swagger 2.0 specifications.
- You can just clone or submodule this repository, and import spec files for code generations, either using:
    - [Swagger Codegen](http://swagger.io/swagger-codegen/) for your favorite languages and/or frameworks
    - Your own parser/code generator
        - Example: [ymtszw/hipchat_elixir](https://github.com/ymtszw/hipchat_elixir)

# Coverage

- [x] [Capabilities API](https://www.hipchat.com/docs/apiv2/method/get_capabilities)
- [x] [Emoticons API](https://www.hipchat.com/docs/apiv2/method/get_emoticon)
- [ ] [Extensions API](https://www.hipchat.com/docs/apiv2/method/get_global_action)
- [x] [Groups API](https://www.hipchat.com/docs/apiv2/method/view_group)
- [x] [Integrations API](https://www.hipchat.com/docs/apiv2/method/get_integration_installable_data)
    - [Get integration installable data API](https://www.hipchat.com/docs/apiv2/method/get_integration_installable_data) is omitted,
      since it is only used in installation flow, and the whole URL is sent to Add-on server upon installation.
      Just use that URL as-is, seems easier than extracting `integration_id_or_key` and `token` from it and supplying them to library function.
    - [Invoke integration link API](https://www.hipchat.com/docs/apiv2/method/invoke_integration_link)
      is omitted, since it is for client side use.
- [x] [Invites API](https://www.hipchat.com/docs/apiv2/method/invite_user_to_group)
- [x] [Oauth Sessions API](https://www.hipchat.com/docs/apiv2/method/get_session)
- [x] ~~Prefs Public API~~ (Included under Users API)
- [ ] [Rooms API](https://www.hipchat.com/docs/apiv2/method/get_all_rooms)
    - [Share file with room API](https://www.hipchat.com/docs/apiv2/method/share_file_with_room) is omitted,
      since it requires requests with [`multipart/related`](https://tools.ietf.org/html/rfc2387) content-type.
    - [Set topic API](https://www.hipchat.com/docs/apiv2/method/set_topic) is omitted,
      since it requires (though undocumented,) `application/json` content-type.
- [x] [Users API](https://www.hipchat.com/docs/apiv2/method/get_all_users)
    - [Share file with user API](https://www.hipchat.com/docs/apiv2/method/share_file_with_user) is omitted,
      since it requires requests with [`multipart/related`](https://tools.ietf.org/html/rfc2387) content-type.

# License

MIT
