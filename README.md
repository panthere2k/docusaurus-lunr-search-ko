Modification of [docusaurus-lunr-search](https://github.com/praveenn77/docusaurus-lunr-search)

Thanks to : [@eastuni/lunr-languages-ko](https://github.com/eastuni/lunr-languages)

Similar Plugin
<https://github.com/easyops-cn/docusaurus-search-local>

# docusaurus-lunr-search-ko

Offline Search for Docusaurus V2.1 Korean supported

[Demo Website](https://lelouch77.github.io/docusaurus-lunr-search-multilang/)

[![MIT Licence](https://img.shields.io/github/license/lelouch77/docusaurus-lunr-search)](#)

[![npm version](https://badge.fury.io/js/docusaurus-lunr-search.svg)](https://www.npmjs.com/package/docusaurus-lunr-search)

## Sample

<p align="center">
  <img width="460" height="300" src="https://raw.githubusercontent.com/panthere2k/docusaurus-lunr-search-ko/master/assets/search-offline.png">
</p>

## Prerequisites

`worker_thread` is needed, suggested node version > 12.X
For older version of node use `docusaurus-lunr-search` version `2.1.0`
(`npm i docusaurus-lunr-search@2.1.0`)

## How to Use ?

1. Install this package

```bash
npm i docusaurus-lunr-search-ko --save
```
2. Then run `npm install` to update, build, and link the packages
```bash
npm install
```
3. Add the docusaurus-lunr-search-ko plugin to your `docusaurus.config.js`
```bash
module.exports = {
  // ...
    plugins: [require.resolve('docusaurus-lunr-search-ko')],
}
```
4. Then run docusaurus swizzle
```bash
npm run swizzle docusaurus-lunr-search-ko SearchBar -- --eject --danger
```
5. Then build your Docusaurus project
```bash
npm run build
```
6. Serve your application
```bash
npx http-server ./build
```

Note: Docusaurus search information can only be generated from a production build. Local development is currently not supported.

## Language options

```JSX
module.exports = {
  // ...
    plugins: [[ require.resolve('docusaurus-lunr-search-ko'), {
      languages: ['en', 'ko'] // language codes
    }]],
}
```

Supports all the language listed here https://github.com/eastuni/lunr-languages

## Other options

### excludeRoutes

You can exclude certain routes from the search by using this option:

```JSX
module.exports = {
  // ...
    plugins: [
    [require.resolve('docusaurus-lunr-search-ko'), {
        excludeRoutes: [
            'docs/changelogs/**/*', // exclude changelogs from indexing
        ]
    }]
  ],
}
```

### indexBaseUrl

Base url will not indexed by default, if you want to index the base url set this option to `true`

```JSX
module.exports = {
  // ...
    plugins: [
        [require.resolve('docusaurus-lunr-search-ko'),
            {
                indexBaseUrl: true
            }
        ]
    ],
}
```

Thanks to [`algolia/docsearch.js`](https://github.com/algolia/docsearch), I modified it to create this search component 

And thanks [cmfcmf](https://github.com/cmfcmf), I used the code from his library [docusaurus-search-local](https://github.com/cmfcmf/docusaurus-search-local) for multi-language support.
