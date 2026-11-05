# Contributing to WonderWoW

Thanks for your interest in WonderWoW. This project is a collection of six
educational mini-games for children, packaged as a single Android application
with Apache Cordova. Contributions of all kinds are welcome: bug reports, game
ideas, artwork, documentation fixes, accessibility improvements and code.

You do not need to be a member of the project to contribute. Opening an issue or
a pull request is enough.

## Ways to contribute

- **Report a bug** using the [bug report template](.github/ISSUE_TEMPLATE/bug_report.md).
- **Suggest a feature or a new game** using the
  [feature request template](.github/ISSUE_TEMPLATE/feature_request.md).
- **Improve the documentation** in `README.md` or `docs/`.
- **Send a pull request** for a fix, a new game or a new language.
- **Test a build** on a real device and report what you see, especially on
  older Android versions.

## Getting started

Prerequisites:

- Node.js 16 or newer
- Java JDK 11 or newer
- Android SDK (installed through Android Studio)
- A device or emulator running Android 5.1 (API level 22) or newer

Set up the project:

```
npm install -g cordova
npm install
cordova platform add android
cordova build android
```

The debug APK is written to `platforms/android/app/build/outputs/apk/debug/`.

The games are plain HTML, CSS and JavaScript, so you can also iterate quickly by
opening `www/index.html` in a desktop browser. Features that rely on Cordova
plugins (status bar, screen orientation) only behave correctly on a device.

## Project layout

| Path | Purpose |
| --- | --- |
| `www/index.html` | Game dashboard |
| `www/js/dashboard.js` | Dashboard navigation |
| `www/css/dashboard.css` | Dashboard styles |
| `www/games/<name>/` | One self-contained game per folder |
| `docs/` | Project report, user manual, testing notes |
| `apk/` | Prebuilt release APK |

Each game folder is self-contained: keep its HTML, CSS, JavaScript and assets
inside that folder so games stay independent of each other.

## Coding guidelines

- Match the style of the file you are editing: two-space indentation, `const`
  and `let` instead of `var`, clear function and variable names.
- Keep every game working offline where it already does. Do not add a
  dependency on a CDN unless the game genuinely needs it.
- Avoid new build dependencies. The project intentionally has a very small
  dependency tree.
- Test on at least one real device or emulator before opening a pull request.
- Do not commit generated files: `node_modules/`, `platforms/`, `plugins/`,
  `.cordova/`, `www/cordova.js` and `www/cordova_plugins.js` are ignored on
  purpose.
- Keep the prebuilt APK in `apk/` only when a release build is part of the
  change; a source-only change does not need a new APK.

## Pull request checklist

1. Fork the repository and create a branch with a descriptive name, for example
   `fix/puzzle-victory-animation`.
2. Make the change in small, focused commits with clear messages.
3. Describe what changed, why it changed and how you tested it.
4. Reference any related issue, for example `Closes #12`.
5. Confirm that the dashboard still opens and that the games you touched still
   load, play and return to the dashboard with the back button.

A maintainer will review the pull request, may ask for changes, and will merge
it when it is ready. Reviews can take a few days because this is a
volunteer-maintained project.

## Reporting security issues

Please do not open a public issue for a security problem. Describe the problem
privately to the maintainer through GitHub so a fix can be prepared before the
details are published.

## License of contributions

WonderWoW is released under the [MIT License](LICENSE). By submitting a pull
request you agree that your contribution is licensed under the same terms.
