# EnvKit Homebrew tap

[EnvKit](https://envkit.net) is a local web-development stack for macOS and Windows:
nginx/Apache, several PHP versions, MySQL/MariaDB, PostgreSQL, Redis, MongoDB, Mailpit,
Node.js, Python, phpMyAdmin/pgAdmin and trusted HTTPS on `.test` domains.

```bash
brew install --cask env-kit/tap/envkit
```

or

```bash
brew tap env-kit/tap
brew install --cask envkit
```

Apple Silicon only (macOS 12 Monterey or newer).

## First launch

EnvKit is signed with a Developer ID but not yet notarized, so Gatekeeper may block the
first launch. Any one of these works:

```bash
xattr -dr com.apple.quarantine /Applications/EnvKit.app
```

or, after the first blocked launch, System Settings → Privacy & Security → **Open Anyway**
(macOS 15 removed the right-click → Open override).

## Updating

EnvKit updates itself in place, so the cask is marked `auto_updates`. `brew upgrade` skips
it by default; `brew upgrade --greedy --cask envkit` forces a reinstall from the latest
release.

## Uninstalling

```bash
brew uninstall --cask envkit          # removes the app, keeps your sites, databases and settings
brew uninstall --zap --cask envkit    # also deletes ~/Library/Application Support/EnvKit — your projects and data live there
```

Issues: https://github.com/Env-Kit/envkit-releases/issues
