# DKT Renovate Presets

Heavy influenced by [Sanity's own renovate presets](https://github.com/sanity-io/renovate-presets)

## How to use

Create a `renovate.json` in your root folder and add the following to use the default dkt configuration:

```json
{
  "extends": ["github>code-obos/dkt-renovate-presets"]
}
```

You can import a specific amount of presets to your own renovate bot config by adding each file respectively:

```json
{
  "extends": [
    "github>code-obos/dkt-renovate-presets//ecosystem/branding",
    "github>code-obos/dkt-renovate-presets//ecosystem/npm-pkg-github"
    "github>code-obos/dkt-renovate-presets//ecosystem/group-by-pattern",
    "github>code-obos/dkt-renovate-presets//ecosystem/labels",
    "github>code-obos/dkt-renovate-presets//ecosystem/schedule",
    "github>code-obos/dkt-renovate-presets//ecosystem/security",
  ]
}
```

### Automerge

We have made a config to automerge path dependencies/devdependencies as well. Use this only if you want to automerge patches every week.

Renovate won't automerge if branch protection is on, and it needs at least 1 approval to merge. Give renovate access to automerge without approvals if you need automerge to work

## NPM Registry host rules

You will need to do one extra step to get access to our private modules. Ask one of the CODEOWNERS for the token

```json
"hostRules": [
    {
      "matchHost": "https://npm.pkg.github.com/",
      "hostType": "npm",
      "encrypted": {
        "token": "<TOKEN>"
      }
    }
  ]
```
