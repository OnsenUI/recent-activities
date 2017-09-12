# recent-activities

Recent activities data of Onsen UI Team, used in the website of Onsen UI.

## For maintainers

### How it works

The contents of this repository are loaded by the website via `raw.github.com`. The website requests a specific file based on the following rule.

|`location.hostname`|File|
|-|-|
|`onsen.io`|`recent-activities-en.hjson` (in `master` branch)|
|`s.onsen.io`|`recent-activities-en.hjson` (in `master` branch)|
|`ja.onsen.io`|`recent-activities-ja.hjson` (in `master` branch)|
|`s.ja.onsen.io`|`recent-activities-ja.hjson` (in `master` branch)|
|`localhost`|`recent-activities-en.hjson` (in `dev` branch)|
|`127.0.0.1`|`recent-activities-en.hjson` (in `dev` branch)|

Changes on the files will immediately reflect to the website.

### Structure of the files

Each of `recent-activities-en.hjson` and `recent-activities-ja.hjson` must be a valid [Hjson](https://hjson.org/) file.

You can use `date`, `title` and `description` properties for each item.

- `date` property will be parsed with [`moment(String)`](https://momentjs.com/docs/#/parsing/string/). Please do not forget adding an offset string. Otherwise, `date` will be parsed based on user's timezone and cause an error of ± 24 hours.
- `title` and `description` properties will be rendrered with `v-html` of Vue, so you can use any HTML syntax for these two properties.

### Example

```js
[
  {
    date: 2017-09-10T00:00:00+09:00
    title: Onsen UI 9.9.9 Released
    description:
      '''
      Lorem ipsum
      '''
  },
  {
    date: 2017-09-01T00:00:00+09:00
    title:
      '''
      <a href="#" style="color: #444;">hoge-onsenui</a> 1.7.0 Released
      '''
    description:
      '''
      <p>
        Supported Hoge 2.0.
        <a href="#">Release Note</a>
        <br>
        <code>npm install hoge-onsenui --save</code>
      </p>
      '''
  },
]
```
