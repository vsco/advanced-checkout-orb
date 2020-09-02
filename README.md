# advanced-checkout-orb

## Description

A CircleCI Orb to add advanced features to the default `checkout` step. Main use-case is to enable `shallow-checkout` operations to reduce the compute time and bandwidth related to repository clone. This is accomplished by:

- limiting clone depth
- limiting fetch depth
- skipping submodule resolution (unless overridden)
- skipping LFS pointer resolution (unless overridden)

The main use-case for a checkout operation like this applies to repositories with large git histories as well as the execution of jobs that do not require git history or linked dependencies to peform their actions (build, and release scripts / CI operations).

## Citations

This Orb has code influenced from the following sources.

- The default CircleCI checkout code _uncited_
- [guitarrapc/git-shallow-clone-orb](https://github.com/guitarrapc/git-shallow-clone-orb/) (Shallow logic, parameterization)

## License

See [LICENSE](LICENSE), extrapolated from our forking of [guitarrapc/git-shallow-clone-orb](https://github.com/guitarrapc/git-shallow-clone-orb/).
