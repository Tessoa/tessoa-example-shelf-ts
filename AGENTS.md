# tessoa plugin project

This repository is a plugin for tessoa, the file manager. The manual for working
on it is `sdk/AGENTS.md`: read it in full before changing anything. It covers the
steps, the sandbox rules, where the reference pages are and when the work counts
as done. It ships with the SDK kit in `sdk/` and is replaced when the kit is
upgraded, which is why this file does not repeat it.

If `tessoa-plugin` is not found, run the setup script first (step 2 of the manual).

The three commands that finish a change, run from the repository root:

```
tessoa-plugin test       run the scenarios in tests/scenarios
tessoa-plugin package    write dist/<id>-<version>.zip
tessoa-plugin install    hand the plugin to the tessoa running on this computer
```

Never edit anything under `sdk/`. This file is not touched by upgrades; notes
about this particular plugin can go below.

## This project

This project is the example `shelf-ts` of the tessoa plugin SDK, made into a
repository of its own. The steps of `sdk/AGENTS.md` that set a project up are
already done: there is no `skeleton/` and no `init` to run. The `examples/`
folder that the manual mentions is not here; the other examples are in the
plugin template, https://github.com/Tessoa/tessoa-plugin-template, under `examples/`.

The id in `plugin.toml`, `com.example.shelf`, belongs to the example. When the user
makes this plugin their own, change it to an id of theirs before anything else.
