# haz_fn

**Status: WIP.** This list is only the helpers added in the breakpoints lift. The rest of `layouts/_partials/haz/helpers/fn/` is not cataloged yet. Full pass is [#149](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/149). Add a line when a helper is added. Do not invent a second one.

Home: `project-modules/hugo-agent-zero-core/layouts/_partials/haz/helpers/fn/`

| fn | Job |
|---|---|
| `fn_get_sys_manifest_prop` | Load sysManifest (or use the one passed) and walk `path` via `fn_get_nested`. Not settings-only. |
| `fn_get_haz_breakpoints` | Get only. Path is `settings` / `breakpoints`. Returns `m`, `t`, `d`. Does not adjust. |
| `fn_get_haz_breakpoints_adjust_down` | Takes that dict. Subtracts 1 from `m` and `t`. Copies `d`. Does not read settings. |

`fn_get_nested` already walks any map by path. `fn_get_sys_manifest_prop` is the load in front of it. Do not write another walker.
