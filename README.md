# Importable NPM Packages Demo

## Setup

1. Configure npm to use AWS CodeArtifact repository using `aws codeartifact login`. Relevant documentation [here](https://docs.aws.amazon.com/codeartifact/latest/ug/npm-auth.html).
2. Set up importing and dependent packages in same directory.
3. Publish imported package to AWS CodeArtifact repository by running `npm publish`.
4. Update importing package's package.json to include the dependent package as a dependency. Include both local path and CodeArtifact dependency. The latter is what will be used when you run `npm install`.
5. Run `npm install` in the importing package.

## Usage - npm install

1. Download importing and dependent packages in same directory. Download importing package only if you just want to use version from CodeArtifact.
2. Put the local path url later if you have downloaded the dependent package locally. Put the CodeArtifact dependency later otherwise.
3. Run `npm install` in the importing package.


## Usage - adding new versions

1. On commit you want to use as a new version, run `npm version [patch | minor | major] -m "<Commit message>"`.
2. Push the commit and the new tag to the remote repo.