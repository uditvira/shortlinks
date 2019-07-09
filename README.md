# Hypha Co-op: Shortlinks

For managing our `link.hypha.coop` shortlinks.

Configuration for these shortlinks are stored in
[`shortlinks.csv`](/shortlinks.csv).

## :hammer_and_wrench: Technologies Used

- [`hyphacoop/worker-coop-scripts` repo][scripts]
  - CircleCI
  - [`spreadsheet2shortlinks` CLI
    tool](https://github.com/hyphacoop/spreadsheet2shortlinks)

## Terminology

- **shortlink.** The shortened url. Example:
  https://link.hypha.coop/my-shortlink
- **base URL.** The base for the shortened urls. Example: `https://link.hypha.coop`
- **keyword.** The string (usually human-readable) that makes up the
  path of the shortlink, and is appended to the base URL. a.k.a.
**slashtag**, a term used by the underlying shortlink service.

## :muscle: Contributing

tl;dr - simply edit [`shortlinks.csv`](/shortlinks.csv)!

For example: Say you want to create a new shortlink pointing
https://link.hypha.coop/my-shortlink to
https://example.com/asfjaflnadsesljarmdkasdjasd. Just add a new line to
`shortlinks.csv` with `my-shortlink` as the `slashtag` and your complex
URL as the `destination_url`.

To keep things lightweight, all changes can be committed directly to
`master` branch, without pull request. (Feel free to use a pull request
if you'd like a gut-check and you're not in a rush.)

Without explicit action, shortlinks are updated nightly as part of the
[`update_shortlinks`
task](https://github.com/hyphacoop/worker-coop-scripts#update_shortlinks)
in the [`hyphacoop/worker-coop-scripts` repo][scripts].

   [scripts]: https://github.com/hyphacoop/worker-coop-scripts

- **Creating** a new shortlink? Add a new line.
- **Changing** an existing shortlink? Change the `resource_url`.
- **Removing** an existing shortlink? Clear the `resource_url` field, leaving the `slashtag` field as-is.
