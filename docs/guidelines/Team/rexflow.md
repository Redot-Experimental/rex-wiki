---
title: ReX Flow
summary: Github workflow for ReX
authors:
- ChocolatechipAussie
date: 2025-06-30
toc: false
---

# **ReX Flow**
<p><u>Last updated - June 30th 2025</u></p>
---

## **Introducing ReX Flow**
ReX Flow is a Git-based workflow developed by the Redot ReX team to facilitate organized collaboration across ReX’s open source projects. It combines a fork-based approach, feature branches, and two long-term non-release branches: `master` and `develop`. This document outlines the workflow in detail and explains the reasoning behind these choices.

---

## **A Fork Based Approach**
ReX Flow emphasizes community contribution, making the use of forks essential for both organization and access management. It's not feasible for an open-source project to grant direct write access to main repositories for all contributors. Instead, both internal and external contributors are required to fork the repository to implement their changes.

Pull Requests (PRs) are then used to propose those changes to the upstream repository.

!!! info ""
    Forks must also follow the ReX Flow process described here to prevent conflicts and maintain a consistent and organized structure with the parent repository.

---

## **Long Term Branches**
ReX Flow uses two long-term branches outside of its stable release branches:

### **The `develop` Branch**
The `develop` branch is the default branch across all ReX repositories. It is the primary integration branch for ongoing development work.

!!! info ""
    Forks of the repository **must not** use the `develop` branch directly for changes. Instead, all changes should be made in **feature branches**. See the Feature Branches section for more details.

Pull Requests should target `develop` when:
- Merging feature branches
- Submitting contributions from forks

This structure ensures that `develop` remains the hub of active progress while remaining testable.

---

### **The `master` Branch**
The `master` branch acts as a **relatively stable checkpoint** for the `develop` branch. Periodically, the `develop` branch is merged into `master` to provide **nightly** or **experimental builds**. These check-ins allow the community to try out new features, provide early feedback, and report bugs before they reach a full release.

The sync frequency may vary based on development activity—from once a week to once a quarter.

!!! info ""
    In some workflows, `master` represents the latest production version. In ReX Flow, however, this role is handled by **version branches**, allowing ReX to maintain and support multiple stable versions simultaneously.

!!! danger ""
    Direct commits or pull requests to `master` are not permitted. This branch is *only* updated via merges from `develop`.

---
### **Version Branches**

Version branches in ReX Flow represent **stable production releases** and are used to maintain and patch specific versions of the engine over time. These branches are created from the `master` branch when a version is nearing stability, and follow a naming convention such as `release/1.3`, `release/2.0`, etc.

Once a version branch is created, a **release candidate** is produced from it. This allows time for final testing and bugfixing before the version is officially published. During this phase, only critical fixes, documentation updates, and platform compatibility patches are accepted — **no new features** should be introduced.

Once the stable release is tagged (e.g., `v1.3.0`), any changes made during the release process must be integrated into `develop` to ensure they are preserved and carried forward in future work.

!!! info "Backporting"
    Backporting changes made during the release process relies on two seperate methods. If posible directly merging these changes back into `develop` is preferred. If merging is not an option maintainers will make use of cherrypicking to bring these changes back into the `develop` branch.

Each version branch is maintained independently, allowing the team to:

- Backport critical bug fixes
- Release hotfixes
- Apply security patches
- Maintain long-term support (LTS) versions

!!! warning ""
    Version branches are the only branches intended to be used by production users, package maintainers, and downstream projects relying on ReX for game or tool development.

---

### **Version Development Branches**

Version development branches such as `1.x`, and `2.x` are used to support ongoing development within a specific **major version** of ReX. These branches allow for continued work on older or stable versions of the engine even as new major versions are being developed in `develop`.

These branches act as **stable, long-running tracks** for a specific version family. They are intended to support:
- Backported features or improvements
- Long-term support (LTS) updates
- Preparation for future minor releases (e.g., `1.4`, `1.5`)
- Isolated work when `develop` has moved on to a newer version (e.g., `2.x` development)

???+ info "**Use in Minor Releases**"
    Version development branches are the **starting point** for all new minor release branches.

    When preparing a new minor version (e.g., `1.4`):

    1. Branch `release/1.4` from the version branch (`1.x`)
    2. All **release work**—final testing, polishing, and bugfixing—happens on `release/1.4`
    3. After the release is tagged (e.g., `v1.4.0`), any changes made during the release are **merged back into `1.x`**

---

### **Feature Branches**

Feature branches are temporary branches used to develop isolated units of work, such as new features, bug fixes, improvements, or refactors. In ReX Flow, all development work—whether internal or external—**must take place on a feature branch**. Once work on a feature branch is completed it will be merged into the appropriate branch, either `develop` or version dev branch such as `1.x`

This branching model ensures:

- Isolation of work-in-progress
- Easier review and testing
- Cleaner project history
- Safer collaboration across teams and contributors

---

#### **In the Parent Repository**

In the parent ReX repository, feature branches are typically created by core maintainers when:

- Working on major features in coordination with others
- Prototyping large refactors or cross-cutting changes
- Collaborating on longer-lived tasks that require visibility

Feature branches in the parent repo follow this naming convention:

- `feature/<short-description>`
- `bugfix/<short-description>`
- `refactor/<short-description>`

These branches:

- Must always branch off from develop or a version dev branch like 1.x
- Should target develop or the appropriate version dev branch in their pull requests
- Are usually short-lived, but may remain longer for large coordinated efforts

!!! note ""
    Feature branches in the parent repo are used to coordinate larger tasks that require visibility or collaboration between multiple contributors. Most external contributions should not directly interact with these unless requested.

---

#### **In Forks (External Contributions)**

All external contributors must use a **fork-based workflow**, and are required to create a **feature branch in their fork** when proposing new changes—**unless a corresponding feature branch already exists in the parent repository**.

There are two scenarios to follow:

---

**Scenario 1: No existing feature branch in the parent repo**

If maintainers have not created a feature branch for the work:

- Fork the ReX repository
- Create a new feature branch in your fork from the appropriate upstream base (usually `develop` or `1.x`)
- Push your changes to your fork
- Open a Pull Request (PR) targeting the upstream branch (e.g., `develop`, `1.x`)

!!! danger "Before you begin"
    Before beginning work on a new feature, it is strongly recommended to submit a proposal for review and discussion. Skipping this step may result in completed work being rejected during review.
    This requirement **only applies to new features**, not bugfixes or work related to **approved open issues**.

!!! tip ""
    Use descriptive branch names that briefly convey the scope of your work following the same naming convention as if it were the parent repo (i.e. `feature/<short-description>`)

---

**Scenario 2: Feature branch already exists in the upstream repo**

If maintainers have created a feature branch in the main ReX repository for a coordinated effort:

- Fork the repo (if you haven’t already)
- Do not create a separate feature branch in your fork
- Instead, base your work on the existing upstream feature branch
- Push your changes to your fork (using the same branch name)
- Open a PR targeting that upstream feature branch

!!! info ""
    Matching the branch name and targeting the shared upstream branch ensures your contributions are reviewed and integrated as part of the coordinated effort.

!!! warning ""
    Do not create a new branch on your fork with a different name if a shared upstream feature branch already exists.