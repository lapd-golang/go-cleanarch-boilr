# {{Name}}

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://{{GitServer}}/{{Organization}}/{{Name}}/blob/master/LICENSE)

## Install and Hooks

Make sure you installed [dep](https://github.com/golang/dep) and 
[golangci-lint](https://github.com/golangci/golangci-lint). Then install the
dependencies using the `dep` command:

```
$ go get -u github.com/golang/dep/cmd/dep
$ go get -u github.com/golangci/golangci-lint/cmd/golangci-lint
$ dep ensure
```

Then generate the mock to pass tests:

```
$ make mock
```

To enable the pre-commit hook:

```
$ git config core.hooksPath .githooks
```

## Configuration

## Make Targets

The version is either `0.1.0` if no tag has ever been defined or the latest
tag defined. The build number is the SHA1 of the latest commit.

- **make**: Builds and injects version/build in binary
- **make init**: Sets the pre-commit hook in the repository
- **make docker**: Build docker image and tag it with both `latest` and version
- **make latest**: Build docker image and tag it only with `latest`
- **make test**: Executes the test suite
- **make mock**: Generate the necessary mocks
- **make clean**: Removes the built binary if present