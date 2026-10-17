# haz_fn

**Status: WIP.** Read this at the start of a session. If a helper is listed, use that path. Do not scan the `fn_` folder for it, and do not write a second one.

This list is only the helpers added in the breakpoints lift, plus the walker they sit on. The rest of the folder is not cataloged yet. Full pass is [#149](https://github.com/hugo-agent-zero/hugo-agent-zero/issues/149). When a helper is added, add a row with its path.

Paths are from the org root.

| fn | Path | Job |
|---|---|---|
| `fn_get_nested` | `project-modules/hugo-agent-zero-core/layouts/_partials/haz/helpers/fn/fn_get_nested.html` | Walk any map by a path slice. The walker. Not settings-only. |
| `fn_get_sys_manifest_prop` | `project-modules/hugo-agent-zero-core/layouts/_partials/haz/helpers/fn/fn_get_sys_manifest_prop.html` | Load sysManifest (or use the one passed) and walk `path` via `fn_get_nested`. |
| `fn_get_haz_breakpoints` | `project-modules/hugo-agent-zero-core/layouts/_partials/haz/helpers/fn/fn_get_haz_breakpoints.html` | Get only. Path is `settings` / `breakpoints`. Returns `m`, `t`, `d`. Does not adjust. |
| `fn_get_haz_breakpoints_adjust_down` | `project-modules/hugo-agent-zero-core/layouts/_partials/haz/helpers/fn/fn_get_haz_breakpoints_adjust_down.html` | Takes that dict. Subtracts 1 from `m` and `t`. Copies `d`. Does not read settings. |
