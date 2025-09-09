# mediawiki-repos

## Repository Configuration

### Example Repository Entry

```yaml
example_repo:
  branch: REL1_X
  path: extensions/example
  repo_url: https://github.com/example/example-repo
  alpha_branch: main
  commit: 1234abc
  composer: true
  latest: true
  removed: true
  recurse_submodules: false
  shallow_submodules: true
  versions: '1.44, 1.45'
```

### Parameters

01. branch:
    - Required. The Git branch to be cloned. If `_branch_` is used, it adapts based on the main MediaWiki branch.

02. path:
    - Required. The path where the repository will be cloned.

03. repo_url:
    - Required. The URL of the Git repository.

04. alpha_branch:
    - Optional. The alpha branch to be used if the MediaWiki core branch is `master`. This is only needed if the repo's main branch is not also `master`.

05. commit:
    - Optional. The Git commit to checkout. This pins the repo to this commit, which will make `git pull` only be able to pull this commit. Requires branch to be set to a real branch that the commit exists on.

06. composer:
    - Optional. If set to true, runs Composer install for the repository.

07. latest:
    - Optional. If set to true, ensures the repository is the latest version. This means it would automatically be updated whenever puppet runs.

08. removed:
    - Optional. If set to true, ensures the repository is absent.

09. recurse_submodules:
    - Optional. If set to false, will not clone any existing submodules.

10. shallow_submodules:
    - Optional. If set to true, clones submodules with only the latest commit.

11. versions:
    - Optional. A comma-separated list of versions for which the repository should be installed. If undefined, the repository will be installed for all versions.

**NOTE**: top-level keys in [mediawiki-repos.yaml](mediawiki-repos.yaml) **MUST** be sorted alphabetically.
