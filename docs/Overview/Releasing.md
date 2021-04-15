# Releases from Deranged Senators
We will be adopting Semantic Versioning for the majority of our projects. Release tags will be detailed as follows:

` <MAJOR>.<MINOR>.<PATCH>.[TAG].[HHMMDDMMYY]`

## Tags
Each release will come with a tag. The current allowed tags are:

| Tag | Definition | Pre-Release | Description |
| - | - | - | - |
| `R` | Release | :x: | Used to Mark a release
| `RC` | Release Candidate | :heavy_check_mark: | An internal release to check for critical problems before releasing
| `OB` | Open Beta | :x: | Public Beta Program
| `CB` | Closed Beta | :x:  | Private Beta Program
| `A` | Alpha | :heavy_check_mark: | Alpha Builds are used for userend products which have not yet attained beta level
| `DP` | Developer Preview | :heavy_check_mark: | Developer Previews give the public access to unreleased APIs to allow developers to test and begin integrating them into their products

### Tag Formatting
A tag will be formatted as follows:
` {TAG}{CUMULATIVE_VALUE} `
The Cumulative value is a number which increments each time with a particular tag release. The cumulative value resets to 1 whenever the major value increases. RC values also reset to 1 when the corresponding `R` tag is published.
# Changelogs
Changelogs are files which contain a list of changes on the current relase.In our case, Changelogs must be kept in a `CHANGELOG.md` in the root of the repository. The GitHub Release action will automatically take this file and use it for the body of the release. It will also automatically wipe the file once the release has been published
## Principles
- They must be _human_ readable
- They must be present with every release
- They must be categorised to make it easier to understand
## Types of changes
- `Added` : New Features
- `Changed` : For changes in existing functionality
- `Deprecated`: To mark soon-to-be removed features
- `Removed`: Removed features
- `Fixed`: Bug fixes
- `Security`: Security Vulnerability Fixes
- `Issues`: Known problems regarding the release
