# Github Packages Release Cleaner Action

This action will remove all releases of a package (i.e. package versions) that
contain a specific pattern.

userOrg:
  description: "The Github user or organization that owns the package in question"
  required: true
package:
  description: 'The name of the package for which to clean releases'
  required: true
token:
  description: 'The authorization token to use to access Github Packages for the specified package. Must have access to delete:packages for the specified package owned by the organization or user specified.'
  required: true
pattern:
    description: 'The pattern to search for'
    required: true
    default: 'dev'
outputs:
numDeleted:
  description: 'The number of package versions that were deleted'

## Inputs

## `userOrg`

**Required** The name of the Github user or organization for which the Github
package is registered.

## `package`

**Required** The name of the package

## `token`

**Required** The authorization token to use to access Github packages for the
specified package. Must have access to `delete:packages` for the specified
package owned by the organization or user specified.

## `pattern`

**Required** The pattern to search for

## Outputs

## `numDeleted`

The number of package versions that were deleted.

## Example usage

uses: foamfactory/gh-release-cleaner@v1.0.0
with:
  userOrg: 'jwir3'
  package: 'somepackage'
  token: ${GITHUB_TOKEN}
  pattern: 'dev'
