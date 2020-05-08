# semantic-release

Example semantic-release implementation.

## Here's what we need to set up:

- [commitlint](https://commitlint.js.org/): enforce a commit-message format standard so commit messages can be analyzed to determine the correct version bump (fix? feature? refactor?), release notes, changelog updates, etc.
- [semantic-release](https://semantic-release.gitbook.io): automate the creation of releases, enforce the use of [semver spec](https://semver.org), and push releases to different places.
- [semantic-release commit-analyzer](https://github.com/semantic-release/commit-analyzer): semantic-release plugin that allows for commits to be analyzed (using [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog)) in order to inform versioning strategy and release notes.
- [semantic-release git](https://github.com/semantic-release/git): semantic-release plugin that allows for releases to be published as git tags. You can also use the GitHub, or GitLab plugin, which will do certain things like comment in issues/PRs when they get released.
- [semantic-release release-notes-generator](https://github.com/semantic-release/release-notes-generator): semantic-release plugin that allows for release notes to be generated from commit messages (using [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog)).
- [semantic-release changelog](https://github.com/semantic-release/changelog): semantic-release plugin that allows for a CHANGELOG file to be mantained automatically based on commit messages (using [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog)).
- CI system, such as travis or circleci.

## Steps to set up

- Make sure node and npm are installed (use nvm, see `.nvmrc`).
- Install the tools you need:
  ```bash
  npm install --save-dev @commitlint/cli @commitlint/config-conventional husky semantic-release @semantic-release/commit-analyzer @semantic-release/git @semantic-release/release-notes-generator @semantic-release/changelog
  ```
- Configure commitlint, husky, and semantic-release.
  - `commitlint.config.js`
  - `husky.config.js`
  - `release.config.js`
  - `.circlieci/config.yml`
- Make commits that follow the standard (don't worry, commit-msg hooks will enforce for you).
- Push commits to different branches.
- Make PRs.
- Merge PRs, watch semantic-release deploy new tags.
