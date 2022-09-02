# emap-actions
Reusable GitHub actions for EMAP projects


## Examples

To tag a list of repositories. Useful if an action in one repository requires 
delayed actions to happen in other repositories. 
```yaml
jobs:
  example-job:
    uses: inform-health-informatics/emap-actions/reusable_workflows/tag_repos.yaml@main
    with:
      repos: "Inform-DB"    # Required, space seperated list
      branch: "develop"     # Optional
      tag_name: "test_me"   # Optional
    secrets:
      token: ${{ github-access-token }}  # Required
```

***

Run tests if a tag exists on a repository. If it does run a workflow (`test.yaml`) in
the current repository and remove the tag. This can be combined with the `tag_repos` 
workflow to allow delayed testing of a set of repos when there is e.g. a push on one 
of them.
```yaml
jobs:
  example-job:
    uses: inform-health-informatics/emap-actions/reusable_workflows/test_if_tagged.yaml@main
    with:
      repo: "Inform-DB"     # Required
      tag_name: "test_me"   # Optional
    secrets:
      token: ${{ your-github-token }}  # Required
```

