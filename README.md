# recent-activities

Recent activities data of Onsen UI Team, used in the website of Onsen UI.

## For maintainers

### How it works

The contents of this repository are loaded by the website via `raw.github.com`. The website requests a specific file based on the following rule.

|`location.hostname`|File|
|-|-|
|`onsen.io`|`recent-activities-en.json` (in `master` branch)|
|`s.onsen.io`|`recent-activities-en.json` (in `master` branch)|
|`ja.onsen.io`|`recent-activities-ja.json` (in `master` branch)|
|`s.ja.onsen.io`|`recent-activities-ja.json` (in `master` branch)|
|`localhost`|`recent-activities-en.json` (in `dev` branch)|
|`127.0.0.1`|`recent-activities-en.json` (in `dev` branch)|

Changes on the files will immediately reflect to the website.

### Structure of the files

Each of `recent-activities-en.json` and `recent-activities-ja.json` must be a valid JSON file.

You can use `date`, `title` and `description` properties for each item. `title` and `description` will be rendrered with `v-html` of Vue, so you can use any HTML syntax for these two properties.
