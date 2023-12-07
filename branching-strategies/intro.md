## Branching Strategies

- Gitflow: A branching strategy that involves using two main branches, called "develop" and "master," as well as additional supporting branches for features, hotfixes, and releases. The develop branch is used for ongoing development, and the master branch represents the latest stable release.
- Trunk-Based Development: A branching strategy in which all development is done in a single "trunk" branch, and developers are expected to commit their code frequently and resolve conflicts as they arise.
- Feature Branching: A branching strategy in which a separate branch is created for each new feature that is being developed. When the feature is complete, the branch is merged back into the main development branch.
- Release Branching: A branching strategy in which a separate branch is created for each new release that is being prepared. The release branch is used to stabilize the code and fix any final bugs before the release is deployed.
- Branch by Abstraction: A branching strategy in which a new abstraction layer is introduced into the codebase, allowing the old and new implementations to coexist until the new implementation is ready to be fully deployed.