# workflow: Set Commit Status

####  A simple way to set _any_ status on the commit

GitHub supports [several approaches to reuse code and script among workflows](https://github.com/orgs/thetechcollective/discussions/43)

This repo offers two comparable approaches to acieve the same thing: Set the commit status on a commit, as simple as possible.

In both cases it's essentially some sugar coating of the [commit status REST API](https://docs.github.com/en/rest/commits/statuses?apiVersion=2022-11-28#create-a-commit-status).

- [Using a `gh` extension](docs/gh-set-status.md)
- [Using a callable workflow](docs/set_status_yml.md)

## Conslusion

The `gh` extension approach is way simpler to implemnet in a workflow `yml` file:

```
gh extension install thetechcollective/gh-set-status
gh set-status success "All tests are good"
```

It's imperative code as opposed to declarative code; easier to test and maintain.

The `gh` extension protocol provides an excellent package manager for small utilization scripts.

In the current setup the script fails if it's called outside a GitHub Workflow Runne context, but it could quite easiliy be alterd to run _anywhere_ allowing developers to set commit statuse from their development envioronmetns with a simple cli.

See the details on [how to use it in your flow:](docs/gh-set-status.md). 


