# advanced-checkout-orb

[![CircleCI Status](https://circleci.com/gh/vsco/advanced-checkout-orb.svg?style=shield)](https://app.circleci.com/pipelines/github/vsco/advanced-checkout-orb?branch=main)&nbsp;[![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/vsco/advanced-checkout)](https://circleci.com/orbs/registry/orb/vsco/advanced-checkout)

## Description

A CircleCI Orb to add advanced features to replace the default `checkout` step.
The main use-case is to enable `shallow-checkout` operations to reduce the
compute time and bandwidth related to a full repository clone.

This is accomplished by:

- limiting clone depth
- limiting fetch depth
- skipping submodule resolution (unless overridden)
- skipping LFS pointer resolution (unless overridden)

This orb is mainly ideal for repositories with large git histories as well as the execution of jobs that do not require git history or linked dependencies to peform their actions (build, and release scripts / CI operations).

## Releases

- All open pull requests will build/tag as: `vsco/advanced-checkout@dev:alpha` on each commit.
- All merged pull requests to `main` will build/tag as: `vsco/advanced-checkout@dev:beta`

Upon a successful build / CircleCI publish on `main`, a release may be promoted using the following naming patterns:

- patch release: patch-release-v1.0.z
- minor release: minor-release-v1.y.0
- major release: major-release-vx.0.0

Once a tag with the correspoding name is pushed up a release flow will trigger and publish to the CircleCI Orb registry. (Note, it's necessary to distinguish between a patch, minor or major release for CircleCI purposes.)

See: [config.yml#L100-L107](https://github.com/vsco/advanced-checkout-orb/blob/main/.circleci/config.yml#L100-L107) and [orb-tools/dev-promote-prod-from-git-tag](https://circleci.com/orbs/registry/orb/circleci/orb-tools?version=9.3.1#jobs-dev-promote-prod-from-git-tag) for details on how the release process works.

## Citations

This Orb has code influenced from the following sources.

- The default CircleCI checkout code _uncited_
- [guitarrapc/git-shallow-clone-orb](https://github.com/guitarrapc/git-shallow-clone-orb/) (Shallow logic, parameterization)

## License

See [LICENSE](LICENSE), extrapolated from our forking of [guitarrapc/git-shallow-clone-orb](https://github.com/guitarrapc/git-shallow-clone-orb/).
