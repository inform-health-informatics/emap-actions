# emap-actions
Reusable GitHub actions for EMAP projects


## Examples

To tag a list of repositories
```yaml
jobs:
  example-job:
    uses: inform-health-informatics/emap-actions/reusable_workflows/tag_repos.yaml@main
    with:
      repos: "Inform-DB"    # Required, space seperated list
      branch: "develop"     # Optional
      tag_name: "test_me"   # Optional
    secrets:
      token: ${{ your-github-token }}  # Required
```

***

To test a repository if a tag exists
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

