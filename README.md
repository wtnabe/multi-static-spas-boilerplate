## Multi Static SPAs' boilerplate with Vite

and yarn v1 workspace

### Goal / 目的

Define each directory as a single site that is ‘closed’ within the directory and build the whole as a collection of those sites.

各ディレクトリをディレクトリ内で「閉じる」一つのサイトとして定義し、全体をそれらのサイトの集合体として構築する

### Requirement / 要件

 * Node.js 20+
 * Yarn v1
 * Vite 5+

### How to Use / 使い方

 * Mkdir the sites/ directory.
 * Prepare index.html and package.json in it, and for package.json
     * Set name to the name of the directory.
     * Set the version to an appropriate one.
     * Ensure that vite can be invoked in scripts.

 * sites/ ディレクトリを掘る
 * その中に index.html と package.json を用意、package.json については
     * name をディレクトリ名に
     * version を適当に
     * scripts で vite を起動できるように

#### develop / 制作

Use Vite's HMR in the normal way

普通に Vite の HMR を利用する

#### build / ビルド

run `./bin/build`. Then.

 * Prepare vite.config.js in each site
 * Run vite build.
 * Collect the finished dist/ directories.

The final dist/ will be collected

`${ROOT}/dist`

will be the final result.

`./bin/build` を実行する。すると

 * 各 site の中に vite.config.js を用意
 * vite build を実行
 * できあがった dist/ ディレクトリを収集

してくれる。

最終的にできあがった

`${ROOT}/dist`

が成果物になる。

### example / 例

tree

```
sites/
├── counter/
│   ├── index.html
│   └── package.json
├── index.html
├── bookstand/
│   ├── index.html
│   └── package.json
└── package.json
```

package.json

```json
{
  "name": "counter",
  "version": "0.1.0",
  "scripts": {
    "dev": "vite"
  }
}
```
