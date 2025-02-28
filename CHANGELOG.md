# Changelog

## 0.16.1 - 2023-01-20
[0.16.0...0.16.1](https://github.com/rust-lang/git2-rs/compare/0.16.0...0.16.1)

### Changed
- Updated to [libgit2-sys 0.14.2+1.5.1](libgit2-sys/CHANGELOG.md#0142151---2023-01-20)

## 0.16.0 - 2023-01-10
[0.15.0...0.16.0](https://github.com/rust-lang/git2-rs/compare/0.15.0...0.16.0)

### Changed
- Added ability to get the SSH host key and its type.
  This includes an API breaking change to the `certificate_check` callback.
  [#909](https://github.com/rust-lang/git2-rs/pull/909)
- Updated to [libgit2-sys 0.14.1+1.5.0](libgit2-sys/CHANGELOG.md#0141150---2023-01-10)

## 0.15.0 - 2022-07-28
[0.14.4...0.15.0](https://github.com/rust-lang/git2-rs/compare/0.14.4...0.15.0)

### Added
- Added `Repository::tag_annotation_create` binding `git_tag_annotation_create`.
  [#845](https://github.com/rust-lang/git2-rs/pull/845)
- Added the `Email` type which represents a patch in mbox format for sending via email.
  Added the `EmailCreateOptions` struct to control formatting of the email.
  Deprecates `Diff::format_email`, use `Email::from_diff` instead.
  [#847](https://github.com/rust-lang/git2-rs/pull/847)
- Added `ErrorCode::Owner` to map to the new `GIT_EOWNER` errors.
  [#839](https://github.com/rust-lang/git2-rs/pull/839)
- Added `opts::set_verify_owner_validation` to set whether or not ownership validation is performed.
  [#839](https://github.com/rust-lang/git2-rs/pull/839)

### Changed
- Updated to [libgit2-sys 0.14.0+1.5.0](libgit2-sys/CHANGELOG.md#0140150---2022-07-28)
- Removed the `Iterator` implementation for `ConfigEntries` due to the unsound usage of the API which allowed values to be used after free.
  Added `ConfigEntries::next` and `ConfigEntries::for_each` for iterating over all entries in a safe manor.
  [#854](https://github.com/rust-lang/git2-rs/pull/854)

## 0.14.4 - 2022-05-19
[0.14.3...0.14.4](https://github.com/rust-lang/git2-rs/compare/0.14.3...0.14.4)

### Added
- Added `Commit::body` and `Commit::body_bytes` for retrieving the commit message body.
  [#835](https://github.com/rust-lang/git2-rs/pull/835)
- Added `Tree::get_name_bytes` to handle non-UTF-8 entry names.
  [#841](https://github.com/rust-lang/git2-rs/pull/841)

### Changed
- Updated to [libgit2-sys 0.13.4+1.4.2](libgit2-sys/CHANGELOG.md#0134142---2022-05-10)

## 0.14.3 - 2022-04-27
[0.14.2...0.14.3](https://github.com/rust-lang/git2-rs/compare/0.14.2...0.14.3)

### Changed
- Updated to [libgit2-sys 0.13.3+1.4.2](libgit2-sys/CHANGELOG.md#0133142---2022-04-27)

### Fixed
- Fixed the lifetime of `Remote::create_detached`.
  [#825](https://github.com/rust-lang/git2-rs/pull/825)

## 0.14.2 - 2022-03-10
[0.14.1...0.14.2](https://github.com/rust-lang/git2-rs/compare/0.14.1...0.14.2)

### Added
- Added `Odb::exists_ext` to checks if an object database has an object, with extended flags.
  [#818](https://github.com/rust-lang/git2-rs/pull/818)

### Changed
- Updated to [libgit2-sys 0.13.2+1.4.2](libgit2-sys/CHANGELOG.md#0132142---2022-03-10)

## 0.14.1 - 2022-02-28
[0.14.0...0.14.1](https://github.com/rust-lang/git2-rs/compare/0.14.0...0.14.1)

### Changed
- Updated to [libgit2-sys 0.13.1+1.4.2](libgit2-sys/CHANGELOG.md#0131142---2022-02-28)

## 0.14.0 - 2022-02-24
[0.13.25...0.14.0](https://github.com/rust-lang/git2-rs/compare/0.13.25...0.14.0)

### Added
- Added `opts::get_extensions` and `opts::set_extensions` to support git extensions.
  [#791](https://github.com/rust-lang/git2-rs/pull/791)
- Added `PackBuilder::name` and `PackBuilder::name_bytes`.
  [#806](https://github.com/rust-lang/git2-rs/pull/806)
    - Deprecated `PackBuilder::hash`, use `PackBuilder::name` instead.
- Added `FetchOptions::follow_redirects` and `PushOptions::follow_redirects`.
  [#806](https://github.com/rust-lang/git2-rs/pull/806)
- Added `StatusOptions::rename_threshold`.
  [#806](https://github.com/rust-lang/git2-rs/pull/806)

### Changed
- Updated to [libgit2-sys 0.13.0+1.4.1](libgit2-sys/CHANGELOG.md#0130141---2022-02-24)
  [#806](https://github.com/rust-lang/git2-rs/pull/806)
  [#811](https://github.com/rust-lang/git2-rs/pull/811)
