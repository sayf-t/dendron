---
id: lgagl5axpere4l5eujk813p
title: package.lock Json Versioning
desc: ''
updated: 1658137048693
created: 1658136519709
---

Automatically generated when any `npm` commands modify the `node_modules` folder or `package.json`.
It is like a more specific description of the dependencies, version number, where the dependency is coming from, integrity checks to see dependency is not corrupt, dependency tree.
- The carat symbol `^` is used in semantic versioning to indicate versions equal to and above 
  - but patch versions for MAJORs less than 1 i.e. 0.8.0; treat MINOR version numbers as if they were major
  - https://semver.npmjs.com/ - use this to test out which versions a range will capture
- The tilde symbol `~` to match only versions in the same MINOR version (not above)
- If a package has a breaking change, this could lead to new bugs - so include package-lock.json to avoid versioning issues, differences in behaviour.

