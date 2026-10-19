# Shelf

[中文](README.zh-CN.md)

A tessoa plugin in TypeScript: a shelf page that keeps files at hand.

It is one of the examples of the tessoa plugin SDK, made into a project of its
own so that it can be the start of your own plugin: create a repository from
it, change it, build it. The plugin template, with the other examples and an
empty starting point in TypeScript and in Rust, is at
<https://github.com/Tessoa/tessoa-plugin-template>.

## Test, package, install

```
powershell -ExecutionPolicy Bypass -File scripts/setup.ps1 -Lang ts   # Windows
bash scripts/setup.sh --lang ts                                    # macOS, Linux
tessoa-plugin test
tessoa-plugin package
tessoa-plugin install
```

The setup script installs what is missing: Node.js and the
`tessoa-plugin` command-line tool. `test` runs the scenarios in
`tests/scenarios` in the real sandbox against a simulated tessoa, so no tessoa
is needed for it. `package` writes `dist/com.example.shelf-0.1.0.zip`.
`install` hands the plugin to the tessoa running on this computer, which asks
you to confirm its permissions. Installing into tessoa needs a licence;
testing and packaging do not.

## Making it your own

1. Change `id` in `plugin.toml` before anything else. `com.example.shelf` belongs to
   the example, and tessoa tells plugins apart by their id. Use one of your
   own, such as `com.yourname.shelf`, and change `name` as well.
2. Change the code in `src/` and the scenarios in `tests/scenarios`, then run
   `tessoa-plugin test` again.

A coding assistant opened on this repository starts from `AGENTS.md`, which
sends it to the manual in `sdk/`. `tessoa-plugin upgrade` replaces `sdk/` with
the newest kit; never edit the files in it.

## Licence

The code of this plugin is released under the MIT licence in `LICENSE`. The
files under `sdk/` are the tessoa plugin SDK and are not covered by that
licence; they come with their own, in `sdk/LICENSE.md`.
