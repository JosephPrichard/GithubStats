# GithubStats
A script to get repo metric from a github account such as lines of code or files per language.

Uses HTTP package and wait groups from Go to download zip archives in parallel for the lines of code metric.

Execute the program with `go run main.go`. Configurations should be in a `.env` file in the same directory.

Sample `.env` file:
```
token=<your-github-token>
name=JohnSmith
include=ts go rust cpp/hpp
exclude=cmake-build-debug target
```
The `token` requires "repo" privileges to run the script. Create a token at https://github.com/settings/tokens

The `include` variable specifies a space separated list of file extensions to include. You can `group`
extensions into one using slashes like so `cpp/hpp`. In that case, `cpp` and `hpp` files are added to the same metric
groupings. 

The `exclude` variable specifies directories to exclude. This is useful for dynamic languages where the
artefacts of a project use the same extensions as the source.

## Example
![image](https://github.com/JosephPrichard/GithubStats/assets/58538077/a985bfe4-3a74-4c51-a480-f36bced1e189)