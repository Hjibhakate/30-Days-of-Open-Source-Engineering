# Day 22: Changelogs — Open Source Engineering
<p>
  <img src="./day22.png" width="100%" alt="Open">
</p>


## 1. What Is a Changelog?

A **changelog** is a file that records important changes made to a software project over time.

It helps developers, contributors, and users understand what has changed between versions of a project without reading every commit in the Git history.

A changelog commonly documents:
- **Added:** New features.
- **Changed:** Updates to existing functionality.
- **Deprecated:** Features that may be removed in the future.
- **Removed:** Features that have been deleted.
- **Fixed:** Bugs that have been corrected.
- **Security:** Security-related improvements or fixes.

The most common filename is `CHANGELOG.md`.

### Example

Imagine you maintain an open-source login application.

In version 1.0, users can log in using their email and password.

In version 1.1:
- You add Google login.
- You fix a password-reset bug.
- You improve login error messages.

A changelog records these updates so users know exactly what changed in version 1.1.

---

## 2. Why Is a Changelog Important?

### A. Helps Users Understand Updates
Users can quickly identify new features, bug fixes, and changes that might affect how they use the application.

### B. Improves Collaboration
Contributors can understand recent project changes without investigating every commit.

### C. Makes Debugging Easier
If a bug appears after an update, developers can review the changelog to identify potentially related changes.

### D. Improves Project Transparency
A clear changelog shows that a project communicates its changes openly and consistently.

### E. Supports Version Releases
When publishing a new release, maintainers can use the changelog to communicate what is included in that version.

---

## 3. Understanding Common Changelog Categories

A widely used convention is the format recommended by [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

| Category | Meaning | Example |
|---|---|---|
| Added | New functionality | Added Google login |
| Changed | Existing behavior updated | Improved login validation |
| Deprecated | Functionality will be removed in a future release | Marked the old authentication API for removal |
| Removed | Functionality deleted | Removed an unsupported endpoint |
| Fixed | A bug was corrected | Fixed password-reset failure |
| Security | A security issue was addressed | Fixed an authorization vulnerability |

**Important:** Use only the categories that apply to your release. Do not add empty sections just to fill the file.

---

## 4. How to Create a CHANGELOG.md File

### Step 1: Open Your Repository

Open your project on GitHub or in your preferred code editor.

### Step 2: Create the File

Create a new file in the project's root directory:

```text
CHANGELOG.md
```

### Step 3: Add a Heading

```markdown
# Changelog

All notable changes to this project are documented in this file.
```

### Step 4: Record the Release

Add a version number and release date, followed by categorized changes.

For example:

```markdown
## [1.1.0] - 2026-10-10

### Added
- Added Google login support.

### Fixed
- Fixed the password-reset validation bug.

### Changed
- Improved login error messages.
```

The date above is an illustrative example. Use the actual release date for your project.

### Step 5: Save and Commit

After reviewing the changes, commit the file:

```bash
git add CHANGELOG.md
git commit -m "docs: add changelog for version 1.1.0"
```

You can then include it in a pull request or publish it with the corresponding release.

---

## 5. A Complete CHANGELOG.md Example

Copy and paste this example into a file named `CHANGELOG.md`.

```markdown
# Changelog

All notable changes to this project are documented in this file.

This project follows the principles of Keep a Changelog.

## [Unreleased]

### Added
- Planned support for additional login methods.

### Changed
- No changes recorded yet.

## [1.1.0] - 2026-10-10

### Added
- Added Google login support.
- Added input validation for the registration form.

### Changed
- Improved login error messages.
- Updated the user dashboard layout.

### Fixed
- Fixed the password-reset validation bug.
- Fixed an issue that prevented some users from logging out.

## [1.0.0] - 2026-09-15

### Added
- Added email and password authentication.
- Added user registration.
- Added password-reset functionality.
- Created the initial user dashboard.
```

**Note:** The release dates, features, and version numbers are fictional examples. Replace them with changes that actually exist in your project. The `Unreleased` section can contain changes that have not yet been published.

---

## 6. Changelog vs. Git Commit History

These two things are related, but they serve different purposes.

| Git Commit History | Changelog |
|---|---|
| Records individual commits | Summarizes important changes |
| Often includes technical implementation details | Focuses on changes relevant to users and contributors |
| Can contain many small or internal updates | Highlights notable changes by release |
| Mainly useful for investigating development history | Useful for understanding what changed between releases |

### Example

Git commit messages:

```text
fix login validation
update login component
add google oauth
change error text
```

A more useful changelog entry could be:

```markdown
### Added
- Added Google login support.

### Changed
- Improved login validation and error messages.
```

The changelog summarizes the meaningful result instead of repeating every commit.

---

## 7. Unique Practical Trick: The User-Impact Test

Before adding a change to your changelog, ask these three questions:

1. **What changed?** Identify the actual feature, behavior, or fix.
2. **Who is affected?** Consider users, developers, API consumers, or maintainers.
3. **Why does it matter?** Explain the practical result.

### Weak Entry

```markdown
- Updated authentication code.
```

This does not explain what changed or why it matters.

### Better Entry

```markdown
- Fixed an authentication issue that prevented users from logging in after resetting their passwords.
```

This communicates the problem and the outcome.

### The Trick

**Describe the impact, not just the implementation.**

For example, instead of writing:

```markdown
- Modified the API response handler.
```

Write:

```markdown
- Fixed an API error-handling issue that caused failed login requests to display misleading messages.
```

Only use the second description if it accurately represents the change.

This technique makes changelog entries more useful to readers, although the underlying idea is a practical writing technique rather than a guaranteed new or previously unpublished discovery.

---

## 8. How to Write a Good Changelog Entry

Follow these best practices:

- Use clear and simple language.
- Keep each entry focused on one meaningful change.
- Start with an action word such as Added, Fixed, Improved, or Removed.
- Mention user-visible effects where relevant.
- Group changes under suitable categories.
- Keep release dates and version numbers accurate.
- Avoid copying every commit message into the changelog.
- Include links to relevant issues or pull requests when useful.
- Do not claim that a bug is fixed unless the fix has been verified.
- Mention breaking changes clearly when they affect existing users or integrations.

### Example with a Pull Request Reference

```markdown
### Fixed
- Fixed an issue where expired sessions were not handled correctly
  ([#42](https://github.com/OWNER/REPOSITORY/pull/42)).
```

Replace `OWNER`, `REPOSITORY`, and `42` with the real repository details.

---

## 9. Changelog and Semantic Versioning

Changelogs often work alongside [Semantic Versioning](https://semver.org/).

A version commonly follows this pattern:

```text
MAJOR.MINOR.PATCH
```

For example:

```text
2.4.1
```

- **MAJOR:** Introduces incompatible changes.
- **MINOR:** Adds functionality in a backward-compatible manner.
- **PATCH:** Makes backward-compatible bug fixes.

For a public API, removing or changing an existing endpoint incompatibly may require a major version increase. The appropriate version depends on the project's compatibility rules and release policy.

A changelog explains the changes; semantic versioning communicates the type of release.

---

## 10. Common Changelog Mistakes

### Mistake 1: Listing Every Commit
A changelog is not intended to duplicate the entire Git history.

**Better approach:** Include notable changes that help users or contributors understand the release.

### Mistake 2: Using Vague Descriptions
Entries such as `updated code` or `fixed things` provide little value.

**Better approach:** Explain the behavior that changed.

### Mistake 3: Using Incorrect Dates
An incorrect release date can confuse users investigating when a feature became available.

**Better approach:** Use the actual release date and follow one consistent date format.

### Mistake 4: Forgetting Breaking Changes
A change that affects existing integrations should not be hidden among minor improvements.

**Better approach:** Clearly identify the incompatibility and explain what users need to do.

### Mistake 5: Documenting Unverified Fixes
A changelog should accurately describe what the release contains.

**Better approach:** Verify the change and ensure the description matches the released code.

---

## 11. Hands-On Challenge for Day 22

Choose any open-source repository that you are allowed to contribute to.

### Your Task

1. Read its README and recent release notes.
2. Identify one recent feature, bug fix, or improvement.
3. Check the associated commit, issue, or pull request to understand the actual change.
4. Find out whether the repository maintains a changelog.
5. If appropriate, draft a clear changelog entry.
6. Follow the repository's contribution guidelines before opening a pull request.

If the project does not maintain a changelog, do not automatically create one. First check whether the maintainers want release notes or changelog contributions.

### Practice Template

```markdown
## [Unreleased]

### Added
- [Describe a new feature, if applicable.]

### Changed
- [Describe a meaningful behavior change, if applicable.]

### Fixed
- [Describe a verified bug fix, if applicable.]
```

Remove categories that do not apply. Replace the placeholders with real information before submitting your contribution.

---

## 12. Quick Revision

- A changelog records notable project changes.
- `CHANGELOG.md` is a common filename.
- Keep a Changelog provides a widely used structure for organizing entries.
- Categories include Added, Changed, Deprecated, Removed, Fixed, and Security.
- A changelog is different from Git commit history.
- Semantic Versioning communicates the nature of a release.
- Good entries explain the change and its impact.
- Accurate release notes improve communication between maintainers, contributors, and users.

## Final Takeaway

A good changelog does more than record what developers changed. It helps people understand what a software release means for them.

**Day 22 Goal:** Learn to document software changes clearly, accurately, and professionally.
