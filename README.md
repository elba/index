# `elba/index`

This is the repository for elba's default package index.

## Adding a package to the index

At the moment, adding packages to this index is a completely manual process. In
the future, the package publishing process will be improved such that package
authors don't need to manually make pull requests on this repo and get their
package added (in fact at that point we'll most likely turn off pull requests
and issues entirely). This new solution will likely arrive with the
introduction of the online default index package listing and a new set of CLI
commands to interact with package repositories.

However, in order to get elba out the door as fast as possible, this is the
solution we're stuck with.

In general, it's a good idea to read through
[The elba Guide](https://elba.github.io/elba/) to familiarize yourself with how
elba works before attempting to add a package to its default index. However, it
is vitally necessary that you read on
[how elba handles package names](https://elba.github.io/elba/usage/manifest.html),
[package resolutions](https://elba.github.io/elba/reference/resolutions.html),
and [how package indices work](https://elba.github.io/elba/reference/indices.html)
before attempting to add a package.

Once you've read through the elba documentation, editing the package index
should be relatively straightforward: just fork this repo, add the packages you
want to add, and submit that as a pull request.

## Special index-specific rules

The default index has some restrictions which only apply to it and not all
elba indices as a whole:

  - Packages in the default index can only depend on other packages in the
    default index.

  - A person can only publish to namespaces they own. A person owns a namespace
    after publishing to it for the first time.

    At the moment, only one person (GitHub account) can own a namespace and
    namespace ownership cannot be transferred. Additionally, namespaces cannot
    be claimed before a package is published. These deficiencies will be
    rectified with "the new solution."

  - After a version of a package is published, the only modification that can
    happen on that version is yanking that package. That is to say, once you
    put a line in a metadata file in the official index, you **cannot** change
    that line unless you are yanking that package. This means you can't delete
    packages too.

  - The direct resolution of all packages must be a git repository with a
    specific commit specified.
