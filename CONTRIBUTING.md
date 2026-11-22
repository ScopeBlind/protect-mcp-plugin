# Contributing

This repository contains the guidance plugin published as protect-mcp in
Claude's directory. The gateway implementation is maintained in
[ScopeBlind/scopeblind-gateway](https://github.com/ScopeBlind/scopeblind-gateway).

Keep examples reproducible against pinned, published packages. A plugin update
must not silently install host hooks, start a service, grant authority or claim
enforcement without a tested route. Preserve existing workflow names when an
update is compatible.

This repository holds only the plugin's own files: the directory accepts other
files here only from Verified organizations, so the test scripts and CI that
1.1.0 added were removed in 1.1.2 (they remain in the history). Before opening a
pull request, validate the plugin with Claude Code:

```sh
claude plugin validate --strict .
```

Then check by hand that every `protect-mcp` and `@veritasacta/verify` command in
`skills/` names an exact published version, and that the examples still run.

Describe the behavior changed and the checks run in the pull request. Never
include private keys, credentials, customer transcripts or private repository
links in a report or fixture. Send security reports to security@scopeblind.com.

The plugin version is separate from the gateway npm version. Maintainers update
this repository's plugin version when shipping a plugin change, validate it,
and request review on the existing directory submission. Do not create a new
submission for an ordinary update. A passing local check does not imply
Anthropic approval or publication.
