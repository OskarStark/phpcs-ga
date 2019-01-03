# GithubAction for PHPCS

## Usage

You can use it as a Github Action like this:

_.github/main.workflow_
```
workflow "Main" {
  on = "push"
  resolves = ["PHPCS"]
}

action "PHPCS" {
  uses = "docker://oskarstark/phpcs-ga"
  secrets = ["GITHUB_TOKEN"]
}
```

_to ignore annotations:_
```diff
workflow "Main" {
  on = "push"
  resolves = ["PHPCS"]
}

action "PHPCS" {
  uses = "docker://oskarstark/phpcs-ga"
  secrets = ["GITHUB_TOKEN"]
+  args = "--ignore-annotations"
}
```

**You can copy/paste the .github folder (under examples/) to your project and thats all!**

## Docker

A Docker-Image is built automatically and located here:
https://cloud.docker.com/u/oskarstark/repository/docker/oskarstark/phpcs-ga

You can run it in any given directory like this:

`docker run --rm -it -w=/app -v ${PWD}:/app oskarstark/phpcs-ga:latest`

