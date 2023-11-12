# Importable NPM packages Demo

## Setup

1. Set up importing and dependent packages in same directory.
2. Update importing package's package.json to include the dependent package as a dependency. Include both local path and git repo url. The latter is what will be used when you run `npm install`.

```jsonc
{
  "dependencies": {
    // For local paths
    "@nguylinc/importable-package": "file:../ImportablePackage",
    // For git repo urls
    "@nguylinc/importable-package": "git+ssh://git@github.com:rinkaaan/ImportablePackage.git",
    // For github repo urls
    "@nguylinc/importable-package": "rinkaaan/ImportablePackage.git",
    // For github repo urls with version tag
    "@nguylinc/importable-package": "rinkaaan/ImportablePackage.git#v1.0.0"
  }
}
```

3. Run `npm install` in the importing package.

## Usage - npm install

1. Download importing and dependent packages in same directory. Download importing package only if you just want to use version from git repo url.
2. Put the local path url later if you have downloaded the dependent package locally. Put the git repo url later otherwise.
3. Run `npm install` in the importing package.


## Usage - adding new versions

1. On commit you want to use as a new version, run `npm version [patch | minor | major] -m "<Commit message>"`.
2. Push the commit and the new tag to the remote repo.