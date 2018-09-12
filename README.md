# env-path
Loads environment variables from a chosen `.env` file into [`process.env`](https://nodejs.org/docs/latest/api/process.html#process_process_env), using  [dotenv](https://www.npmjs.com/package/dotenv) and [dotenv-expand](https://github.com/motdotla/dotenv-expand)

> Adds  `.env` variables to `process.env`

[![NPM version](https://img.shields.io/badge/env--path-v1.0.4-green.svg)](https://www.npmjs.com/package/env-path)
## Installation

```sh
$ npm install env-path
```

## Usage

Thanks to [dotenv-expand](https://github.com/motdotla/dotenv-expand), we can use variables inside our `.env` file.

See simple `.env` file under


```
API_KEY=key
PORT=3000
MONGO_DB=myDB
MONGO_URL=mongodb://localhost:27017/${MONGO_DB}
REACT_APP_VERSION=$npm_package_version
```


### Run
Preloads dotenv and dotenv-expand. By doing this, you do not need to require and load dotenv and dotenv-expand in your application code.
#### Path
Specify a path using the `-p` flag:

>$ env-path -p path/.env-file node app.js


```sh
package.json
"scripts": {
  "build"   : "env-path -p path/.env.production, react-scripts build"
  "start"   : "env-path -p path/.env-file react-script start",
  "start2"  : "env-path -p path/.env.development node app.js",
  "start3"  : "env-path -p path/otherFileName.env node app.js",
}
```

#### Without path

Works similar to dotenv's Preload<br>
See [dotenv docs](https://github.com/motdotla/dotenv)

>$ env-path node app.js

```sh
package.json
"scripts": {
  "start"   : "env-path node app.js",
  "build"   : "env-path react-scripts build"
}
```

## License

  [MIT](LICENSE)
