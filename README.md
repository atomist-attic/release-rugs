# release-rugs

[![Build Status](https://travis-ci.org/atomist-rugs/release-rugs.svg?branch=master)](https://travis-ci.org/atomist-rugs/release-rugs)
[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

[rug]: http://docs.atomist.com/

This [Rug][rug] project contains handlers and editors for cutting a release

## Rugs

### UpdateChangeLogForRelease

The UpdateChangeLogForRelease editor moves unreleased entries in a
change log under a new release header.  See [Keep a CHANGELOG][keep]
for information on the format of a change log file.

[keep]: http://keepachangelog.com/

#### Prerequisites

A source code project with a change log.

#### Parameters

This Rug takes following parameters.

Name | Required | Default | Description
-----|----------|---------|------------
`version` | Yes | | New version to create header for, e.g., "1.2.3"
`name` | Yes | | Short name for new release, e.g., "New stuff"

#### Running

Run this Rug as follows:

```
$ cd project/directory
$ rug edit atomist-rugs:release-rugs:UpdateChangeLogForRelease \
    version=7.5.3 \
    description='Feature widget'
```

This will insert a new release header in the `CHANGELOG.md` file,
putting all unreleased entries under the new release header.

## Support

General support questions should be discussed in the `#support`
channel on our community Slack team
at [atomist-community.slack.com][slack].

If you find a problem, please create an [issue][].

[issue]: https://github.com/atomist-rugs/release-rugs/issues

## Development

You can build, test, and install the project locally with
the [Rug CLI][cli].

[cli]: https://github.com/atomist/rug-cli

```
$ rug test
$ rug install
```

To create a new release of the project, simply push a tag of the form
`M.N.P` where `M`, `N`, and `P` are integers that form the next
appropriate [semantic version][semver] for release.  For example:

[semver]: http://semver.org

```
$ git tag -a 1.2.3
```

The Travis CI build (see badge at the top of this page) will
automatically create a GitHub release using the tag name for the
release and the comment provided on the annotated tag as the contents
of the release notes.  It will also automatically upload the needed
artifacts.

---
Created by [Atomist][atomist].
Need Help?  [Join our Slack team][slack].

[atomist]: https://www.atomist.com/
[slack]: https://join.atomist.com/
