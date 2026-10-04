# SleepGuard — Intel Mac automatic DMG build

This version builds a **native Intel x86_64** macOS application in GitHub Actions.

The workflow uses GitHub's `macos-15-intel` runner and installs the **official prebuilt Qt 6.8.3** packages with `aqtinstall`. It does not use Homebrew Qt, so it does not compile Qt or its Python dependencies from source.

## GitHub

1. Upload the entire project to your repository.
2. Make sure `.github/workflows/build-macos-dmg.yml` exists.
3. Open **Actions** → **Build SleepGuard macOS Intel DMG**.
4. Click **Run workflow**.
5. After a green run, download artifact **SleepGuard-macOS-Intel-x86_64**.
6. Inside it is `SleepGuard-Intel-x86_64.dmg`.

## Why official Qt is used

Homebrew's Qt is split across multiple formulae and is not a good release-packaging source for this workflow. The official Qt desktop package contains `macdeployqt`, which is needed to make a self-contained `.app`/`.dmg`.
