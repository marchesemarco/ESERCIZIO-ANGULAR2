# Editor configuration, see https://editorconfig.org
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
insert_final_newline = true
trim_trailing_whitespace = true

[*.md]

max_line_length = off
trim_trailing_whitespace = false
# See http://help.github.com/ignore-files/ for more about ignoring files.

# compiled output
/dist
/tmp
/out-tsc

# dependencies
/node_modules

# profiling files
chrome-profiler-events.json
speed-measure-plugin.json

# IDEs and editors
/.idea
.project
.classpath
.c9/
*.launch
.settings/
*.sublime-workspace

# IDE - VSCode
.vscode/*
!.vscode/settings.json
!.vscode/tasks.json
!.vscode/launch.json
!.vscode/extensions.json
.history/*

# misc
/.sass-cache
/connect.lock
/coverage
/libpeerconnection.log
npm-debug.log
yarn-error.log
testem.log
/typings

# System Files
.DS_Store
Thumbs.db






{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "version": 1,
  "newProjectRoot": "projects",
  "projects": {
    "angular-hello-world": {
      "root": "",
      "sourceRoot": "src",
      "projectType": "application",
      "prefix": "app",
      "schematics": {},
      "architect": {
        "build": {
          "builder": "@angular-devkit/build-angular:browser",
          "options": {
            "outputPath": "dist/angular-hello-world",
            "index": "src/index.html",
            "main": "src/main.ts",
            "polyfills": "src/polyfills.ts",
            "tsConfig": "src/tsconfig.app.json",
            "assets": [
              "src/favicon.ico",
              "src/assets"
            ],
            "styles": [
              "src/styles.css"
            ],
            "scripts": []
          },
          "configurations": {
            "production": {
              "fileReplacements": [
                {
                  "replace": "src/environments/environment.ts",
                  "with": "src/environments/environment.prod.ts"
                }
              ],
              "optimization": true,
              "outputHashing": "all",
              "sourceMap": false,
              "extractCss": true,
              "namedChunks": false,
              "aot": true,
              "extractLicenses": true,
              "vendorChunk": false,
              "buildOptimizer": true,
              "budgets": [
                {
                  "type": "initial",
                  "maximumWarning": "2mb",
                  "maximumError": "5mb"
                }
              ]
            }
          }
        },
        "serve": {
          "builder": "@angular-devkit/build-angular:dev-server",
          "options": {
            "browserTarget": "angular-hello-world:build"
          },
          "configurations": {
            "production": {
              "browserTarget": "angular-hello-world:build:production"
            }
          }
        },
        "extract-i18n": {
          "builder": "@angular-devkit/build-angular:extract-i18n",
          "options": {
            "browserTarget": "angular-hello-world:build"
          }
        },
        "test": {
          "builder": "@angular-devkit/build-angular:karma",
          "options": {
            "main": "src/test.ts",
            "polyfills": "src/polyfills.ts",
            "tsConfig": "src/tsconfig.spec.json",
            "karmaConfig": "src/karma.conf.js",
            "styles": [
              "src/styles.css"
            ],
            "scripts": [],
            "assets": [
              "src/favicon.ico",
              "src/assets"
            ]
          }
        },
        "lint": {
          "builder": "@angular-devkit/build-angular:tslint",
          "options": {
            "tsConfig": [
              "src/tsconfig.app.json",
              "src/tsconfig.spec.json"
            ],
            "exclude": [
              "**/node_modules/**"
            ]
          }
        }
      }
    },
    "angular-hello-world-e2e": {
      "root": "e2e/",
      "projectType": "application",
      "prefix": "",
      "architect": {
        "e2e": {
          "builder": "@angular-devkit/build-angular:protractor",
          "options": {
            "protractorConfig": "e2e/protractor.conf.js",
            "devServerTarget": "angular-hello-world:serve"
          },
          "configurations": {
            "production": {
              "devServerTarget": "angular-hello-world:serve:production"
            }
          }
        },
        "lint": {
          "builder": "@angular-devkit/build-angular:tslint",
          "options": {
            "tsConfig": "e2e/tsconfig.e2e.json",
            "exclude": [
              "**/node_modules/**"
            ]
          }
        }
      }
    }
  },
  "defaultProject": "angular-hello-world"
}


{
  "name": "angular-hello-world",
  "version": "0.0.0",
  "lockfileVersion": 1,
  "requires": true,
  "dependencies": {
    "@angular-devkit/architect": {
      "version": "0.12.3",
      "resolved": "https://registry.npmjs.org/@angular-devkit/architect/-/architect-0.12.3.tgz",
      "integrity": "sha512-nRZkuQkUMW0HS/YbVjsEA5zPMgsL4Icd0nFV2gM9vAK5X+Vzn9gZyCL1ogkOsJNlEP6Rc/Pc6Q1PPO2p5NxPsQ==",
      "dev": true,
      "requires": {
        "@angular-devkit/core": "7.2.3",
        "rxjs": "6.3.3"
      }
    },
    "@angular-devkit/build-angular": {
      "version": "0.12.3",
      "resolved": "https://registry.npmjs.org/@angular-devkit/build-angular/-/build-angular-0.12.3.tgz",
      "integrity": "sha512-YS/xwpJ23F4Cw/gWxJvVzQ3ghYqs8nOAYyV/+frZ/ZbOE3iYWnRjwoeWmKhmgBjvTjEnoDne9PYYkQRCxmVBaA==",
      "dev": true,
      "requires": {
        "@angular-devkit/architect": "0.12.3",
        "@angular-devkit/build-optimizer": "0.12.3",
        "@angular-devkit/build-webpack": "0.12.3",
        "@angular-devkit/core": "7.2.3",
        "@ngtools/webpack": "7.2.3",
        "ajv": "6.6.2",
        "autoprefixer": "9.4.3",
        "circular-dependency-plugin": "5.0.2",
        "clean-css": "4.2.1",
        "copy-webpack-plugin": "4.6.0",
        "file-loader": "2.0.0",
        "glob": "7.1.3",
        "istanbul": "0.4.5",
        "istanbul-instrumenter-loader": "3.0.1",
        "karma-source-map-support": "1.3.0",
        "less": "3.9.0",
        "less-loader": "4.1.0",
        "license-webpack-plugin": "2.0.4",
        "loader-utils": "1.1.0",
        "mini-css-extract-plugin": "0.4.4",
        "minimatch": "3.0.4",
        "node-sass": "4.10.0",
        "opn": "5.4.0",
        "parse5": "4.0.0",
        "portfinder": "1.0.17",
        "postcss": "7.0.13",
        "postcss-import": "12.0.1",
        "postcss-loader": "3.0.0",
        "raw-loader": "0.5.1",
        "rxjs": "6.3.3",
        "sass-loader": "7.1.0",
        "semver": "5.5.1",
        "source-map-loader": "0.2.4",
        "source-map-support": "0.5.9",
        "speed-measure-webpack-plugin": "1.2.5",
        "stats-webpack-plugin": "0.7.0",
        "style-loader": "0.23.1",
        "stylus": "0.54.5",
        "stylus-loader": "3.0.2",
        "terser-webpack-plugin": "1.2.1",
        "tree-kill": "1.2.0",
        "webpack": "4.28.4",
        "webpack-dev-middleware": "3.4.0",
        "webpack-dev-server": "3.1.14",
        "webpack-merge": "4.1.4",
        "webpack-sources": "1.3.0",
        "webpack-subresource-integrity": "1.1.0-rc.6"
      }
    },
    "@angular-devkit/build-optimizer": {
      "version": "0.12.3",
      "resolved": "https://registry.npmjs.org/@angular-devkit/build-optimizer/-/build-optimizer-0.12.3.tgz",
      "integrity": "sha512-wwukO6SDP/vPxXwiW7U58EeU1xwylrrEiNWS8JTwkBE/AGQNt0+c7ExNw2ViKL3oBgSpz/6YY2eGrv0aatzfIA==",
      "dev": true,
      "requires": {
        "loader-utils": "1.1.0",
        "source-map": "0.5.6",
        "typescript": "3.2.4",
        "webpack-sources": "1.2.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.5.6",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.5.6.tgz",
          "integrity": "sha1-dc449SvwczxafwwRjYEzSiu19BI=",
          "dev": true
        },
        "webpack-sources": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/webpack-sources/-/webpack-sources-1.2.0.tgz",
          "integrity": "sha512-9BZwxR85dNsjWz3blyxdOhTgtnQvv3OEs5xofI0wPYTwu5kaWxS08UuD1oI7WLBLpRO+ylf0ofnXLXWmGb2WMw==",
          "dev": true,
          "requires": {
            "source-list-map": "^2.0.0",
            "source-map": "~0.6.1"
          },
          "dependencies": {
            "source-map": {
              "version": "0.6.1",
              "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
              "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
              "dev": true
            }
          }
        }
      }
    },
    "@angular-devkit/build-webpack": {
      "version": "0.12.3",
      "resolved": "https://registry.npmjs.org/@angular-devkit/build-webpack/-/build-webpack-0.12.3.tgz",
      "integrity": "sha512-yzsluzemzmhVxiSdgP03D770lSpAvlJF+k/E5rSb0tS9yENWTgodxMJSP8gRcveZzVW0lVvRUGKucDWyt3vnPQ==",
      "dev": true,
      "requires": {
        "@angular-devkit/architect": "0.12.3",
        "@angular-devkit/core": "7.2.3",
        "rxjs": "6.3.3"
      }
    },
    "@angular-devkit/core": {
      "version": "7.2.3",
      "resolved": "https://registry.npmjs.org/@angular-devkit/core/-/core-7.2.3.tgz",
      "integrity": "sha512-NnN8O+97nJAxqD2zVTDlU8dSzrGCZmqYMDqDoRJJChYxAgmGwP4lhb+Jyi5D34tPxgKRTnjTOwC+G7D+WrXSDQ==",
      "dev": true,
      "requires": {
        "ajv": "6.6.2",
        "chokidar": "2.0.4",
        "fast-json-stable-stringify": "2.0.0",
        "rxjs": "6.3.3",
        "source-map": "0.7.3"
      }
    },
    "@angular-devkit/schematics": {
      "version": "7.2.3",
      "resolved": "https://registry.npmjs.org/@angular-devkit/schematics/-/schematics-7.2.3.tgz",
      "integrity": "sha512-zhnI1zxEcjx4OZ0yIzAAOujS8fzXE6nxjyC1viqliQbbjbikA6WIL7UT0jQXZKDsRBl8VXOyutBOaeOXuqktTQ==",
      "dev": true,
      "requires": {
        "@angular-devkit/core": "7.2.3",
        "rxjs": "6.3.3"
      }
    },
    "@angular/animations": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/animations/-/animations-7.2.2.tgz",
      "integrity": "sha512-St03YR3N4Rv0vLr0+3V0kmf/QNi9q0tOenAlHP+jG/YySPkkv8P3xRcGVU38ID4JQzRiShUD+k2r+oZGCQMNjw==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/cli": {
      "version": "7.2.3",
      "resolved": "https://registry.npmjs.org/@angular/cli/-/cli-7.2.3.tgz",
      "integrity": "sha512-qhzVL600CdSr4gJY8jGd3TpbMAqse+wo7Tf3n6B89Jk0ssVdlxvMJfpHoUekZ80CxqRpFPX6l6XjrYHkpNN/6g==",
      "dev": true,
      "requires": {
        "@angular-devkit/architect": "0.12.3",
        "@angular-devkit/core": "7.2.3",
        "@angular-devkit/schematics": "7.2.3",
        "@schematics/angular": "7.2.3",
        "@schematics/update": "0.12.3",
        "inquirer": "6.2.1",
        "opn": "5.3.0",
        "semver": "5.5.1",
        "symbol-observable": "1.2.0"
      },
      "dependencies": {
        "opn": {
          "version": "5.3.0",
          "resolved": "https://registry.npmjs.org/opn/-/opn-5.3.0.tgz",
          "integrity": "sha512-bYJHo/LOmoTd+pfiYhfZDnf9zekVJrY+cnS2a5F2x+w5ppvTqObojTP7WiFG+kVZs9Inw+qQ/lw7TroWwhdd2g==",
          "dev": true,
          "requires": {
            "is-wsl": "^1.1.0"
          }
        }
      }
    },
    "@angular/common": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/common/-/common-7.2.2.tgz",
      "integrity": "sha512-43EcR3mbM+dKH4VE1EYS1HxSuEToxxv5XPktKqdzY95g8PBOxe11ifcXoYHgImd7YOWzcKoy0k6yQbX3o0cZ8g==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/compiler": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/compiler/-/compiler-7.2.2.tgz",
      "integrity": "sha512-vjPreOVPca6HSuDmj7N1w5u8hwXdm98gEPo2wqQMVuJd6qvGEyLYE9FsHc0XCchyQEKSybAYl1dwsjZq2nNSvQ==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/compiler-cli": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/compiler-cli/-/compiler-cli-7.2.2.tgz",
      "integrity": "sha512-ac62YlDescAaf0qPguyRkpzWCMNlwtsKObq80GKADP33Sxm0BxGt4+Wz6rolvUuWzCX8aZwJ0FA7ehKxdmdQoA==",
      "dev": true,
      "requires": {
        "canonical-path": "1.0.0",
        "chokidar": "^1.4.2",
        "convert-source-map": "^1.5.1",
        "dependency-graph": "^0.7.2",
        "magic-string": "^0.25.0",
        "minimist": "^1.2.0",
        "reflect-metadata": "^0.1.2",
        "shelljs": "^0.8.1",
        "source-map": "^0.6.1",
        "tslib": "^1.9.0",
        "yargs": "9.0.1"
      },
      "dependencies": {
        "ansi-regex": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-3.0.0.tgz",
          "integrity": "sha1-7QMXwyIGT3lGbAKWa922Bas32Zg=",
          "dev": true
        },
        "anymatch": {
          "version": "1.3.2",
          "resolved": "https://registry.npmjs.org/anymatch/-/anymatch-1.3.2.tgz",
          "integrity": "sha512-0XNayC8lTHQ2OI8aljNCN3sSx6hsr/1+rlcDAotXJR7C1oZZHCNsfpbKwMjRA3Uqb5tF1Rae2oloTr4xpq+WjA==",
          "dev": true,
          "requires": {
            "micromatch": "^2.1.5",
            "normalize-path": "^2.0.0"
          }
        },
        "arr-diff": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/arr-diff/-/arr-diff-2.0.0.tgz",
          "integrity": "sha1-jzuCf5Vai9ZpaX5KQlasPOrjVs8=",
          "dev": true,
          "requires": {
            "arr-flatten": "^1.0.1"
          }
        },
        "array-unique": {
          "version": "0.2.1",
          "resolved": "https://registry.npmjs.org/array-unique/-/array-unique-0.2.1.tgz",
          "integrity": "sha1-odl8yvy8JiXMcPrc6zalDFiwGlM=",
          "dev": true
        },
        "braces": {
          "version": "1.8.5",
          "resolved": "https://registry.npmjs.org/braces/-/braces-1.8.5.tgz",
          "integrity": "sha1-uneWLhLf+WnWt2cR6RS3N4V79qc=",
          "dev": true,
          "requires": {
            "expand-range": "^1.8.1",
            "preserve": "^0.2.0",
            "repeat-element": "^1.1.2"
          }
        },
        "camelcase": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/camelcase/-/camelcase-4.1.0.tgz",
          "integrity": "sha1-1UVjW+HjPFQmScaRc+Xeas+uNN0=",
          "dev": true
        },
        "chokidar": {
          "version": "1.7.0",
          "resolved": "https://registry.npmjs.org/chokidar/-/chokidar-1.7.0.tgz",
          "integrity": "sha1-eY5ol3gVHIB2tLNg5e3SjNortGg=",
          "dev": true,
          "requires": {
            "anymatch": "^1.3.0",
            "async-each": "^1.0.0",
            "fsevents": "^1.0.0",
            "glob-parent": "^2.0.0",
            "inherits": "^2.0.1",
            "is-binary-path": "^1.0.0",
            "is-glob": "^2.0.0",
            "path-is-absolute": "^1.0.0",
            "readdirp": "^2.0.0"
          }
        },
        "cross-spawn": {
          "version": "5.1.0",
          "resolved": "https://registry.npmjs.org/cross-spawn/-/cross-spawn-5.1.0.tgz",
          "integrity": "sha1-6L0O/uWPz/b4+UUQoKVUu/ojVEk=",
          "dev": true,
          "requires": {
            "lru-cache": "^4.0.1",
            "shebang-command": "^1.2.0",
            "which": "^1.2.9"
          }
        },
        "execa": {
          "version": "0.7.0",
          "resolved": "https://registry.npmjs.org/execa/-/execa-0.7.0.tgz",
          "integrity": "sha1-lEvs00zEHuMqY6n68nrVpl/Fl3c=",
          "dev": true,
          "requires": {
            "cross-spawn": "^5.0.1",
            "get-stream": "^3.0.0",
            "is-stream": "^1.1.0",
            "npm-run-path": "^2.0.0",
            "p-finally": "^1.0.0",
            "signal-exit": "^3.0.0",
            "strip-eof": "^1.0.0"
          }
        },
        "expand-brackets": {
          "version": "0.1.5",
          "resolved": "https://registry.npmjs.org/expand-brackets/-/expand-brackets-0.1.5.tgz",
          "integrity": "sha1-3wcoTjQqgHzXM6xa9yQR5YHRF3s=",
          "dev": true,
          "requires": {
            "is-posix-bracket": "^0.1.0"
          }
        },
        "extglob": {
          "version": "0.3.2",
          "resolved": "https://registry.npmjs.org/extglob/-/extglob-0.3.2.tgz",
          "integrity": "sha1-Lhj/PS9JqydlzskCPwEdqo2DSaE=",
          "dev": true,
          "requires": {
            "is-extglob": "^1.0.0"
          }
        },
        "glob-parent": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/glob-parent/-/glob-parent-2.0.0.tgz",
          "integrity": "sha1-gTg9ctsFT8zPUzbaqQLxgvbtuyg=",
          "dev": true,
          "requires": {
            "is-glob": "^2.0.0"
          }
        },
        "is-extglob": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-extglob/-/is-extglob-1.0.0.tgz",
          "integrity": "sha1-rEaBd8SUNAWgkvyPKXYMb/xiBsA=",
          "dev": true
        },
        "is-fullwidth-code-point": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/is-fullwidth-code-point/-/is-fullwidth-code-point-2.0.0.tgz",
          "integrity": "sha1-o7MKXE8ZkYMWeqq5O+764937ZU8=",
          "dev": true
        },
        "is-glob": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/is-glob/-/is-glob-2.0.1.tgz",
          "integrity": "sha1-0Jb5JqPe1WAPP9/ZEZjLCIjC2GM=",
          "dev": true,
          "requires": {
            "is-extglob": "^1.0.0"
          }
        },
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        },
        "load-json-file": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/load-json-file/-/load-json-file-2.0.0.tgz",
          "integrity": "sha1-eUfkIUmvgNaWy/eXvKq8/h/inKg=",
          "dev": true,
          "requires": {
            "graceful-fs": "^4.1.2",
            "parse-json": "^2.2.0",
            "pify": "^2.0.0",
            "strip-bom": "^3.0.0"
          }
        },
        "mem": {
          "version": "1.1.0",
          "resolved": "https://registry.npmjs.org/mem/-/mem-1.1.0.tgz",
          "integrity": "sha1-Xt1StIXKHZAP5kiVUFOZoN+kX3Y=",
          "dev": true,
          "requires": {
            "mimic-fn": "^1.0.0"
          }
        },
        "micromatch": {
          "version": "2.3.11",
          "resolved": "https://registry.npmjs.org/micromatch/-/micromatch-2.3.11.tgz",
          "integrity": "sha1-hmd8l9FyCzY0MdBNDRUpO9OMFWU=",
          "dev": true,
          "requires": {
            "arr-diff": "^2.0.0",
            "array-unique": "^0.2.1",
            "braces": "^1.8.2",
            "expand-brackets": "^0.1.4",
            "extglob": "^0.3.1",
            "filename-regex": "^2.0.0",
            "is-extglob": "^1.0.0",
            "is-glob": "^2.0.1",
            "kind-of": "^3.0.2",
            "normalize-path": "^2.0.1",
            "object.omit": "^2.0.0",
            "parse-glob": "^3.0.4",
            "regex-cache": "^0.4.2"
          }
        },
        "minimist": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/minimist/-/minimist-1.2.0.tgz",
          "integrity": "sha1-o1AIsg9BOD7sH7kU9M1d95omQoQ=",
          "dev": true
        },
        "os-locale": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/os-locale/-/os-locale-2.1.0.tgz",
          "integrity": "sha512-3sslG3zJbEYcaC4YVAvDorjGxc7tv6KVATnLPZONiljsUncvihe9BQoVCEs0RZ1kmf4Hk9OBqlZfJZWI4GanKA==",
          "dev": true,
          "requires": {
            "execa": "^0.7.0",
            "lcid": "^1.0.0",
            "mem": "^1.1.0"
          }
        },
        "path-type": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/path-type/-/path-type-2.0.0.tgz",
          "integrity": "sha1-8BLMuEFbcJb8LaoQVMPXI4lZTHM=",
          "dev": true,
          "requires": {
            "pify": "^2.0.0"
          }
        },
        "pify": {
          "version": "2.3.0",
          "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
          "integrity": "sha1-7RQaasBDqEnqWISY59yosVMw6Qw=",
          "dev": true
        },
        "read-pkg": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/read-pkg/-/read-pkg-2.0.0.tgz",
          "integrity": "sha1-jvHAYjxqbbDcZxPEv6xGMysjaPg=",
          "dev": true,
          "requires": {
            "load-json-file": "^2.0.0",
            "normalize-package-data": "^2.3.2",
            "path-type": "^2.0.0"
          }
        },
        "read-pkg-up": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/read-pkg-up/-/read-pkg-up-2.0.0.tgz",
          "integrity": "sha1-a3KoBImE4MQeeVEP1en6mbO1Sb4=",
          "dev": true,
          "requires": {
            "find-up": "^2.0.0",
            "read-pkg": "^2.0.0"
          }
        },
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        },
        "string-width": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/string-width/-/string-width-2.1.1.tgz",
          "integrity": "sha512-nOqH59deCq9SRHlxq1Aw85Jnt4w6KvLKqWVik6oA9ZklXLNIOlqg4F2yrT1MVaTjAqvVwdfeZ7w7aCvJD7ugkw==",
          "dev": true,
          "requires": {
            "is-fullwidth-code-point": "^2.0.0",
            "strip-ansi": "^4.0.0"
          }
        },
        "strip-ansi": {
          "version": "4.0.0",
          "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-4.0.0.tgz",
          "integrity": "sha1-qEeQIusaw2iocTibY1JixQXuNo8=",
          "dev": true,
          "requires": {
            "ansi-regex": "^3.0.0"
          }
        },
        "strip-bom": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/strip-bom/-/strip-bom-3.0.0.tgz",
          "integrity": "sha1-IzTBjpx1n3vdVv3vfprj1YjmjtM=",
          "dev": true
        },
        "which-module": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/which-module/-/which-module-2.0.0.tgz",
          "integrity": "sha1-2e8H3Od7mQK4o6j6SzHD4/fm6Ho=",
          "dev": true
        },
        "y18n": {
          "version": "3.2.1",
          "resolved": "https://registry.npmjs.org/y18n/-/y18n-3.2.1.tgz",
          "integrity": "sha1-bRX7qITAhnnA136I53WegR4H+kE=",
          "dev": true
        },
        "yargs": {
          "version": "9.0.1",
          "resolved": "https://registry.npmjs.org/yargs/-/yargs-9.0.1.tgz",
          "integrity": "sha1-UqzCP+7Kw0BCB47njAwAf1CF20w=",
          "dev": true,
          "requires": {
            "camelcase": "^4.1.0",
            "cliui": "^3.2.0",
            "decamelize": "^1.1.1",
            "get-caller-file": "^1.0.1",
            "os-locale": "^2.0.0",
            "read-pkg-up": "^2.0.0",
            "require-directory": "^2.1.1",
            "require-main-filename": "^1.0.1",
            "set-blocking": "^2.0.0",
            "string-width": "^2.0.0",
            "which-module": "^2.0.0",
            "y18n": "^3.2.1",
            "yargs-parser": "^7.0.0"
          }
        },
        "yargs-parser": {
          "version": "7.0.0",
          "resolved": "https://registry.npmjs.org/yargs-parser/-/yargs-parser-7.0.0.tgz",
          "integrity": "sha1-jQrELxbqVd69MyyvTEA4s+P139k=",
          "dev": true,
          "requires": {
            "camelcase": "^4.1.0"
          }
        }
      }
    },
    "@angular/core": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/core/-/core-7.2.2.tgz",
      "integrity": "sha512-kQ0HxUYAPvly8b3aibTGbiodFnBBgo3asXAQuPgFjYYEqcKR1zZII7PQdaEF9kb9sfm/IKLKj4nd9fZ0gcgqZg==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/forms": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/forms/-/forms-7.2.2.tgz",
      "integrity": "sha512-IsvVuUnzIA2ryRmh7l42AANPZFSyNcwqZNtxbmRq2wm3Lfed64U0rsRWWNqipjz7QTxZ2SRdAlP+XDgzg8hvMQ==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/language-service": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/language-service/-/language-service-7.2.2.tgz",
      "integrity": "sha512-qkyY5nUT3J/vBvTTZCTFy3isijQseBFGd6gM08o4ycwbTuOOnnC0XUFuv7o8eeu0jd32MGbaK0gikF+OQOCGNQ==",
      "dev": true
    },
    "@angular/platform-browser": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/platform-browser/-/platform-browser-7.2.2.tgz",
      "integrity": "sha512-eiaqHq26PVASx1kTngBDkFkXhaJzEjoGtc5I+wQUef8CUjq6ZViWz8tUgiiDPOWdqUKUacRZG4q6VR/6uwQj0A==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/platform-browser-dynamic": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/platform-browser-dynamic/-/platform-browser-dynamic-7.2.2.tgz",
      "integrity": "sha512-bw5PuzMzjKMecB4slG/btmvxgn4qFWhNmJVpf2pbtZW7NtZz3HlrqipYzMk9XrCUDGjtwy7O2Z71C3ujI748iw==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@angular/router": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@angular/router/-/router-7.2.2.tgz",
      "integrity": "sha512-+cBC+JxbPdjk+Nyqq27PKkjfIdnc+H+xjMGrkO6dlAKhVMGxyNaYt5NUNugb8XJPsQ1XNXyzwTfZK6jcAGLw6w==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "@babel/code-frame": {
      "version": "7.0.0",
      "resolved": "https://registry.npmjs.org/@babel/code-frame/-/code-frame-7.0.0.tgz",
      "integrity": "sha512-OfC2uemaknXr87bdLUkWog7nYuliM9Ij5HUcajsVcMCpQrcLmtxRbVFTIqmcSkSeYRBFBRxs2FiUqFJDLdiebA==",
      "dev": true,
      "requires": {
        "@babel/highlight": "^7.0.0"
      }
    },
    "@babel/generator": {
      "version": "7.3.0",
      "resolved": "https://registry.npmjs.org/@babel/generator/-/generator-7.3.0.tgz",
      "integrity": "sha512-dZTwMvTgWfhmibq4V9X+LMf6Bgl7zAodRn9PvcPdhlzFMbvUutx74dbEv7Atz3ToeEpevYEJtAwfxq/bDCzHWg==",
      "dev": true,
      "requires": {
        "@babel/types": "^7.3.0",
        "jsesc": "^2.5.1",
        "lodash": "^4.17.10",
        "source-map": "^0.5.0",
        "trim-right": "^1.0.1"
      },
      "dependencies": {
        "jsesc": {
          "version": "2.5.2",
          "resolved": "https://registry.npmjs.org/jsesc/-/jsesc-2.5.2.tgz",
          "integrity": "sha512-OYu7XEzjkCQ3C5Ps3QIZsQfNpqoJyZZA99wd9aWd05NCtC5pWOkShK2mkL6HXQR6/Cy2lbNdPlZBpuQHXE63gA==",
          "dev": true
        },
        "source-map": {
          "version": "0.5.7",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.5.7.tgz",
          "integrity": "sha1-igOdLRAh0i0eoUyA2OpGi6LvP8w=",
          "dev": true
        }
      }
    },
    "@babel/helper-function-name": {
      "version": "7.1.0",
      "resolved": "https://registry.npmjs.org/@babel/helper-function-name/-/helper-function-name-7.1.0.tgz",
      "integrity": "sha512-A95XEoCpb3TO+KZzJ4S/5uW5fNe26DjBGqf1o9ucyLyCmi1dXq/B3c8iaWTfBk3VvetUxl16e8tIrd5teOCfGw==",
      "dev": true,
      "requires": {
        "@babel/helper-get-function-arity": "^7.0.0",
        "@babel/template": "^7.1.0",
        "@babel/types": "^7.0.0"
      }
    },
    "@babel/helper-get-function-arity": {
      "version": "7.0.0",
      "resolved": "https://registry.npmjs.org/@babel/helper-get-function-arity/-/helper-get-function-arity-7.0.0.tgz",
      "integrity": "sha512-r2DbJeg4svYvt3HOS74U4eWKsUAMRH01Z1ds1zx8KNTPtpTL5JAsdFv8BNyOpVqdFhHkkRDIg5B4AsxmkjAlmQ==",
      "dev": true,
      "requires": {
        "@babel/types": "^7.0.0"
      }
    },
    "@babel/helper-split-export-declaration": {
      "version": "7.0.0",
      "resolved": "https://registry.npmjs.org/@babel/helper-split-export-declaration/-/helper-split-export-declaration-7.0.0.tgz",
      "integrity": "sha512-MXkOJqva62dfC0w85mEf/LucPPS/1+04nmmRMPEBUB++hiiThQ2zPtX/mEWQ3mtzCEjIJvPY8nuwxXtQeQwUag==",
      "dev": true,
      "requires": {
        "@babel/types": "^7.0.0"
      }
    },
    "@babel/highlight": {
      "version": "7.0.0",
      "resolved": "https://registry.npmjs.org/@babel/highlight/-/highlight-7.0.0.tgz",
      "integrity": "sha512-UFMC4ZeFC48Tpvj7C8UgLvtkaUuovQX+5xNWrsIoMG8o2z+XFKjKaN9iVmS84dPwVN00W4wPmqvYoZF3EGAsfw==",
      "dev": true,
      "requires": {
        "chalk": "^2.0.0",
        "esutils": "^2.0.2",
        "js-tokens": "^4.0.0"
      },
      "dependencies": {
        "js-tokens": {
          "version": "4.0.0",
          "resolved": "https://registry.npmjs.org/js-tokens/-/js-tokens-4.0.0.tgz",
          "integrity": "sha512-RdJUflcE3cUzKiMqQgsCu06FPu9UdIJO0beYbPhHN4k6apgJtifcoCtT9bcxOpYBtpD2kCM6Sbzg4CausW/PKQ==",
          "dev": true
        }
      }
    },
    "@babel/parser": {
      "version": "7.3.1",
      "resolved": "https://registry.npmjs.org/@babel/parser/-/parser-7.3.1.tgz",
      "integrity": "sha512-ATz6yX/L8LEnC3dtLQnIx4ydcPxhLcoy9Vl6re00zb2w5lG6itY6Vhnr1KFRPq/FHNsgl/gh2mjNN20f9iJTTA==",
      "dev": true
    },
    "@babel/template": {
      "version": "7.2.2",
      "resolved": "https://registry.npmjs.org/@babel/template/-/template-7.2.2.tgz",
      "integrity": "sha512-zRL0IMM02AUDwghf5LMSSDEz7sBCO2YnNmpg3uWTZj/v1rcG2BmQUvaGU8GhU8BvfMh1k2KIAYZ7Ji9KXPUg7g==",
      "dev": true,
      "requires": {
        "@babel/code-frame": "^7.0.0",
        "@babel/parser": "^7.2.2",
        "@babel/types": "^7.2.2"
      }
    },
    "@babel/traverse": {
      "version": "7.2.3",
      "resolved": "https://registry.npmjs.org/@babel/traverse/-/traverse-7.2.3.tgz",
      "integrity": "sha512-Z31oUD/fJvEWVR0lNZtfgvVt512ForCTNKYcJBGbPb1QZfve4WGH8Wsy7+Mev33/45fhP/hwQtvgusNdcCMgSw==",
      "dev": true,
      "requires": {
        "@babel/code-frame": "^7.0.0",
        "@babel/generator": "^7.2.2",
        "@babel/helper-function-name": "^7.1.0",
        "@babel/helper-split-export-declaration": "^7.0.0",
        "@babel/parser": "^7.2.3",
        "@babel/types": "^7.2.2",
        "debug": "^4.1.0",
        "globals": "^11.1.0",
        "lodash": "^4.17.10"
      },
      "dependencies": {
        "debug": {
          "version": "4.1.1",
          "resolved": "https://registry.npmjs.org/debug/-/debug-4.1.1.tgz",
          "integrity": "sha512-pYAIzeRo8J6KPEaJ0VWOh5Pzkbw/RetuzehGM7QRRX5he4fPHx2rdKMB256ehJCkX+XRQm16eZLqLNS8RSZXZw==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "globals": {
          "version": "11.10.0",
          "resolved": "https://registry.npmjs.org/globals/-/globals-11.10.0.tgz",
          "integrity": "sha512-0GZF1RiPKU97IHUO5TORo9w1PwrH/NBPl+fS7oMLdaTRiYmYbwK4NWoZWrAdd0/abG9R2BU+OiwyQpTpE6pdfQ==",
          "dev": true
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        }
      }
    },
    "@babel/types": {
      "version": "7.3.0",
      "resolved": "https://registry.npmjs.org/@babel/types/-/types-7.3.0.tgz",
      "integrity": "sha512-QkFPw68QqWU1/RVPyBe8SO7lXbPfjtqAxRYQKpFpaB8yMq7X2qAqfwK5LKoQufEkSmO5NQ70O6Kc3Afk03RwXw==",
      "dev": true,
      "requires": {
        "esutils": "^2.0.2",
        "lodash": "^4.17.10",
        "to-fast-properties": "^2.0.0"
      },
      "dependencies": {
        "to-fast-properties": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/to-fast-properties/-/to-fast-properties-2.0.0.tgz",
          "integrity": "sha1-3F5pjL0HkmW8c+A3doGk5Og/YW4=",
          "dev": true
        }
      }
    },
    "@ngtools/webpack": {
      "version": "7.2.3",
      "resolved": "https://registry.npmjs.org/@ngtools/webpack/-/webpack-7.2.3.tgz",
      "integrity": "sha512-TbaCeE1mkruWzFGfAP1kSnwk4v5k0MQUxzy2reUvCfq80H8jYrqUuMZJa0VLPoEky5cYIy98Fe2Wz9xlEdx7sA==",
      "dev": true,
      "requires": {
        "@angular-devkit/core": "7.2.3",
        "enhanced-resolve": "4.1.0",
        "rxjs": "6.3.3",
        "tree-kill": "1.2.0",
        "webpack-sources": "1.2.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        },
        "webpack-sources": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/webpack-sources/-/webpack-sources-1.2.0.tgz",
          "integrity": "sha512-9BZwxR85dNsjWz3blyxdOhTgtnQvv3OEs5xofI0wPYTwu5kaWxS08UuD1oI7WLBLpRO+ylf0ofnXLXWmGb2WMw==",
          "dev": true,
          "requires": {
            "source-list-map": "^2.0.0",
            "source-map": "~0.6.1"
          }
        }
      }
    },
    "@schematics/angular": {
      "version": "7.2.3",
      "resolved": "https://registry.npmjs.org/@schematics/angular/-/angular-7.2.3.tgz",
      "integrity": "sha512-hKp+qaM8YU55+JukteXOVY2N5IQBDIIIXkyPcikbC2GBXUeNOMiPqw9au9sjHrgtFp+SVGoaFzzz9+MOCc1gig==",
      "dev": true,
      "requires": {
        "@angular-devkit/core": "7.2.3",
        "@angular-devkit/schematics": "7.2.3",
        "typescript": "3.2.2"
      },
      "dependencies": {
        "typescript": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/typescript/-/typescript-3.2.2.tgz",
          "integrity": "sha512-VCj5UiSyHBjwfYacmDuc/NOk4QQixbE+Wn7MFJuS0nRuPQbof132Pw4u53dm264O8LPc2MVsc7RJNml5szurkg==",
          "dev": true
        }
      }
    },
    "@schematics/update": {
      "version": "0.12.3",
      "resolved": "https://registry.npmjs.org/@schematics/update/-/update-0.12.3.tgz",
      "integrity": "sha512-larMMlYtHyc/ha2N63DtAsnCVVkCePbw9hoAJxVDglBZY7ahShBAQ4RERKYXuHXvmEudG79I+s8P89HjdWsV1w==",
      "dev": true,
      "requires": {
        "@angular-devkit/core": "7.2.3",
        "@angular-devkit/schematics": "7.2.3",
        "@yarnpkg/lockfile": "1.1.0",
        "ini": "1.3.5",
        "pacote": "9.1.1",
        "rxjs": "6.3.3",
        "semver": "5.5.1",
        "semver-intersect": "1.4.0"
      }
    },
    "@types/jasmine": {
      "version": "2.8.16",
      "resolved": "https://registry.npmjs.org/@types/jasmine/-/jasmine-2.8.16.tgz",
      "integrity": "sha512-056oRlBBp7MDzr+HoU5su099s/s7wjZ3KcHxLfv+Byqb9MwdLUvsfLgw1VS97hsh3ddxSPyQu+olHMnoVTUY6g==",
      "dev": true
    },
    "@types/jasminewd2": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/@types/jasminewd2/-/jasminewd2-2.0.6.tgz",
      "integrity": "sha512-2ZOKrxb8bKRmP/po5ObYnRDgFE4i+lQiEB27bAMmtMWLgJSqlIDqlLx6S0IRorpOmOPRQ6O80NujTmQAtBkeNw==",
      "dev": true,
      "requires": {
        "@types/jasmine": "*"
      }
    },
    "@types/node": {
      "version": "8.9.5",
      "resolved": "https://registry.npmjs.org/@types/node/-/node-8.9.5.tgz",
      "integrity": "sha512-jRHfWsvyMtXdbhnz5CVHxaBgnV6duZnPlQuRSo/dm/GnmikNcmZhxIES4E9OZjUmQ8C+HCl4KJux+cXN/ErGDQ==",
      "dev": true
    },
    "@types/q": {
      "version": "0.0.32",
      "resolved": "https://registry.npmjs.org/@types/q/-/q-0.0.32.tgz",
      "integrity": "sha1-vShOV8hPEyXacCur/IKlMoGQwMU=",
      "dev": true
    },
    "@types/selenium-webdriver": {
      "version": "3.0.14",
      "resolved": "https://registry.npmjs.org/@types/selenium-webdriver/-/selenium-webdriver-3.0.14.tgz",
      "integrity": "sha512-4GbNCDs98uHCT/OMv40qQC/OpoPbYn9XdXeTiFwHBBFO6eJhYEPUu2zDKirXSbHlvDV8oZ9l8EQ+HrEx/YS9DQ==",
      "dev": true
    },
    "@types/source-list-map": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/@types/source-list-map/-/source-list-map-0.1.2.tgz",
      "integrity": "sha512-K5K+yml8LTo9bWJI/rECfIPrGgxdpeNbj+d53lwN4QjW1MCwlkhUms+gtdzigTeUyBr09+u8BwOIY3MXvHdcsA==",
      "dev": true
    },
    "@types/webpack-sources": {
      "version": "0.1.5",
      "resolved": "https://registry.npmjs.org/@types/webpack-sources/-/webpack-sources-0.1.5.tgz",
      "integrity": "sha512-zfvjpp7jiafSmrzJ2/i3LqOyTYTuJ7u1KOXlKgDlvsj9Rr0x7ZiYu5lZbXwobL7lmsRNtPXlBfmaUD8eU2Hu8w==",
      "dev": true,
      "requires": {
        "@types/node": "*",
        "@types/source-list-map": "*",
        "source-map": "^0.6.1"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "@webassemblyjs/ast": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/ast/-/ast-1.7.11.tgz",
      "integrity": "sha512-ZEzy4vjvTzScC+SH8RBssQUawpaInUdMTYwYYLh54/s8TuT0gBLuyUnppKsVyZEi876VmmStKsUs28UxPgdvrA==",
      "dev": true,
      "requires": {
        "@webassemblyjs/helper-module-context": "1.7.11",
        "@webassemblyjs/helper-wasm-bytecode": "1.7.11",
        "@webassemblyjs/wast-parser": "1.7.11"
      }
    },
    "@webassemblyjs/floating-point-hex-parser": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/floating-point-hex-parser/-/floating-point-hex-parser-1.7.11.tgz",
      "integrity": "sha512-zY8dSNyYcgzNRNT666/zOoAyImshm3ycKdoLsyDw/Bwo6+/uktb7p4xyApuef1dwEBo/U/SYQzbGBvV+nru2Xg==",
      "dev": true
    },
    "@webassemblyjs/helper-api-error": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-api-error/-/helper-api-error-1.7.11.tgz",
      "integrity": "sha512-7r1qXLmiglC+wPNkGuXCvkmalyEstKVwcueZRP2GNC2PAvxbLYwLLPr14rcdJaE4UtHxQKfFkuDFuv91ipqvXg==",
      "dev": true
    },
    "@webassemblyjs/helper-buffer": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-buffer/-/helper-buffer-1.7.11.tgz",
      "integrity": "sha512-MynuervdylPPh3ix+mKZloTcL06P8tenNH3sx6s0qE8SLR6DdwnfgA7Hc9NSYeob2jrW5Vql6GVlsQzKQCa13w==",
      "dev": true
    },
    "@webassemblyjs/helper-code-frame": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-code-frame/-/helper-code-frame-1.7.11.tgz",
      "integrity": "sha512-T8ESC9KMXFTXA5urJcyor5cn6qWeZ4/zLPyWeEXZ03hj/x9weSokGNkVCdnhSabKGYWxElSdgJ+sFa9G/RdHNw==",
      "dev": true,
      "requires": {
        "@webassemblyjs/wast-printer": "1.7.11"
      }
    },
    "@webassemblyjs/helper-fsm": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-fsm/-/helper-fsm-1.7.11.tgz",
      "integrity": "sha512-nsAQWNP1+8Z6tkzdYlXT0kxfa2Z1tRTARd8wYnc/e3Zv3VydVVnaeePgqUzFrpkGUyhUUxOl5ML7f1NuT+gC0A==",
      "dev": true
    },
    "@webassemblyjs/helper-module-context": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-module-context/-/helper-module-context-1.7.11.tgz",
      "integrity": "sha512-JxfD5DX8Ygq4PvXDucq0M+sbUFA7BJAv/GGl9ITovqE+idGX+J3QSzJYz+LwQmL7fC3Rs+utvWoJxDb6pmC0qg==",
      "dev": true
    },
    "@webassemblyjs/helper-wasm-bytecode": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-wasm-bytecode/-/helper-wasm-bytecode-1.7.11.tgz",
      "integrity": "sha512-cMXeVS9rhoXsI9LLL4tJxBgVD/KMOKXuFqYb5oCJ/opScWpkCMEz9EJtkonaNcnLv2R3K5jIeS4TRj/drde1JQ==",
      "dev": true
    },
    "@webassemblyjs/helper-wasm-section": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/helper-wasm-section/-/helper-wasm-section-1.7.11.tgz",
      "integrity": "sha512-8ZRY5iZbZdtNFE5UFunB8mmBEAbSI3guwbrsCl4fWdfRiAcvqQpeqd5KHhSWLL5wuxo53zcaGZDBU64qgn4I4Q==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/helper-buffer": "1.7.11",
        "@webassemblyjs/helper-wasm-bytecode": "1.7.11",
        "@webassemblyjs/wasm-gen": "1.7.11"
      }
    },
    "@webassemblyjs/ieee754": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/ieee754/-/ieee754-1.7.11.tgz",
      "integrity": "sha512-Mmqx/cS68K1tSrvRLtaV/Lp3NZWzXtOHUW2IvDvl2sihAwJh4ACE0eL6A8FvMyDG9abes3saB6dMimLOs+HMoQ==",
      "dev": true,
      "requires": {
        "@xtuc/ieee754": "^1.2.0"
      }
    },
    "@webassemblyjs/leb128": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/leb128/-/leb128-1.7.11.tgz",
      "integrity": "sha512-vuGmgZjjp3zjcerQg+JA+tGOncOnJLWVkt8Aze5eWQLwTQGNgVLcyOTqgSCxWTR4J42ijHbBxnuRaL1Rv7XMdw==",
      "dev": true,
      "requires": {
        "@xtuc/long": "4.2.1"
      }
    },
    "@webassemblyjs/utf8": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/utf8/-/utf8-1.7.11.tgz",
      "integrity": "sha512-C6GFkc7aErQIAH+BMrIdVSmW+6HSe20wg57HEC1uqJP8E/xpMjXqQUxkQw07MhNDSDcGpxI9G5JSNOQCqJk4sA==",
      "dev": true
    },
    "@webassemblyjs/wasm-edit": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/wasm-edit/-/wasm-edit-1.7.11.tgz",
      "integrity": "sha512-FUd97guNGsCZQgeTPKdgxJhBXkUbMTY6hFPf2Y4OedXd48H97J+sOY2Ltaq6WGVpIH8o/TGOVNiVz/SbpEMJGg==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/helper-buffer": "1.7.11",
        "@webassemblyjs/helper-wasm-bytecode": "1.7.11",
        "@webassemblyjs/helper-wasm-section": "1.7.11",
        "@webassemblyjs/wasm-gen": "1.7.11",
        "@webassemblyjs/wasm-opt": "1.7.11",
        "@webassemblyjs/wasm-parser": "1.7.11",
        "@webassemblyjs/wast-printer": "1.7.11"
      }
    },
    "@webassemblyjs/wasm-gen": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/wasm-gen/-/wasm-gen-1.7.11.tgz",
      "integrity": "sha512-U/KDYp7fgAZX5KPfq4NOupK/BmhDc5Kjy2GIqstMhvvdJRcER/kUsMThpWeRP8BMn4LXaKhSTggIJPOeYHwISA==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/helper-wasm-bytecode": "1.7.11",
        "@webassemblyjs/ieee754": "1.7.11",
        "@webassemblyjs/leb128": "1.7.11",
        "@webassemblyjs/utf8": "1.7.11"
      }
    },
    "@webassemblyjs/wasm-opt": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/wasm-opt/-/wasm-opt-1.7.11.tgz",
      "integrity": "sha512-XynkOwQyiRidh0GLua7SkeHvAPXQV/RxsUeERILmAInZegApOUAIJfRuPYe2F7RcjOC9tW3Cb9juPvAC/sCqvg==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/helper-buffer": "1.7.11",
        "@webassemblyjs/wasm-gen": "1.7.11",
        "@webassemblyjs/wasm-parser": "1.7.11"
      }
    },
    "@webassemblyjs/wasm-parser": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/wasm-parser/-/wasm-parser-1.7.11.tgz",
      "integrity": "sha512-6lmXRTrrZjYD8Ng8xRyvyXQJYUQKYSXhJqXOBLw24rdiXsHAOlvw5PhesjdcaMadU/pyPQOJ5dHreMjBxwnQKg==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/helper-api-error": "1.7.11",
        "@webassemblyjs/helper-wasm-bytecode": "1.7.11",
        "@webassemblyjs/ieee754": "1.7.11",
        "@webassemblyjs/leb128": "1.7.11",
        "@webassemblyjs/utf8": "1.7.11"
      }
    },
    "@webassemblyjs/wast-parser": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/wast-parser/-/wast-parser-1.7.11.tgz",
      "integrity": "sha512-lEyVCg2np15tS+dm7+JJTNhNWq9yTZvi3qEhAIIOaofcYlUp0UR5/tVqOwa/gXYr3gjwSZqw+/lS9dscyLelbQ==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/floating-point-hex-parser": "1.7.11",
        "@webassemblyjs/helper-api-error": "1.7.11",
        "@webassemblyjs/helper-code-frame": "1.7.11",
        "@webassemblyjs/helper-fsm": "1.7.11",
        "@xtuc/long": "4.2.1"
      }
    },
    "@webassemblyjs/wast-printer": {
      "version": "1.7.11",
      "resolved": "https://registry.npmjs.org/@webassemblyjs/wast-printer/-/wast-printer-1.7.11.tgz",
      "integrity": "sha512-m5vkAsuJ32QpkdkDOUPGSltrg8Cuk3KBx4YrmAGQwCZPRdUHXxG4phIOuuycLemHFr74sWL9Wthqss4fzdzSwg==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/wast-parser": "1.7.11",
        "@xtuc/long": "4.2.1"
      }
    },
    "@xtuc/ieee754": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/@xtuc/ieee754/-/ieee754-1.2.0.tgz",
      "integrity": "sha512-DX8nKgqcGwsc0eJSqYt5lwP4DH5FlHnmuWWBRy7X0NcaGR0ZtuyeESgMwTYVEtxmsNGY+qit4QYT/MIYTOTPeA==",
      "dev": true
    },
    "@xtuc/long": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/@xtuc/long/-/long-4.2.1.tgz",
      "integrity": "sha512-FZdkNBDqBRHKQ2MEbSC17xnPFOhZxeJ2YGSfr2BKf3sujG49Qe3bB+rGCwQfIaA7WHnGeGkSijX4FuBCdrzW/g==",
      "dev": true
    },
    "@yarnpkg/lockfile": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/@yarnpkg/lockfile/-/lockfile-1.1.0.tgz",
      "integrity": "sha512-GpSwvyXOcOOlV70vbnzjj4fW5xW/FdUF6nQEt1ENy7m4ZCczi1+/buVUPAqmGfqznsORNFzUMjctTIp8a9tuCQ==",
      "dev": true
    },
    "JSONStream": {
      "version": "1.3.5",
      "resolved": "https://registry.npmjs.org/JSONStream/-/JSONStream-1.3.5.tgz",
      "integrity": "sha512-E+iruNOY8VV9s4JEbe1aNEm6MiszPRr/UfcHMz0TQh1BXSxHK+ASV1R6W4HpjBhSeS+54PIsAMCBmwD06LLsqQ==",
      "dev": true,
      "requires": {
        "jsonparse": "^1.2.0",
        "through": ">=2.2.7 <3"
      }
    },
    "abbrev": {
      "version": "1.0.9",
      "resolved": "https://registry.npmjs.org/abbrev/-/abbrev-1.0.9.tgz",
      "integrity": "sha1-kbR5JYinc4wl813W9jdSovh3YTU=",
      "dev": true
    },
    "accepts": {
      "version": "1.3.5",
      "resolved": "https://registry.npmjs.org/accepts/-/accepts-1.3.5.tgz",
      "integrity": "sha1-63d99gEXI6OxTopywIBcjoZ0a9I=",
      "dev": true,
      "requires": {
        "mime-types": "~2.1.18",
        "negotiator": "0.6.1"
      }
    },
    "acorn": {
      "version": "5.7.3",
      "resolved": "https://registry.npmjs.org/acorn/-/acorn-5.7.3.tgz",
      "integrity": "sha512-T/zvzYRfbVojPWahDsE5evJdHb3oJoQfFbsrKM7w5Zcs++Tr257tia3BmMP8XYVjp1S9RZXQMh7gao96BlqZOw==",
      "dev": true
    },
    "acorn-dynamic-import": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/acorn-dynamic-import/-/acorn-dynamic-import-3.0.0.tgz",
      "integrity": "sha512-zVWV8Z8lislJoOKKqdNMOB+s6+XV5WERty8MnKBeFgwA+19XJjJHs2RP5dzM57FftIs+jQnRToLiWazKr6sSWg==",
      "dev": true,
      "requires": {
        "acorn": "^5.0.0"
      }
    },
    "adm-zip": {
      "version": "0.4.13",
      "resolved": "https://registry.npmjs.org/adm-zip/-/adm-zip-0.4.13.tgz",
      "integrity": "sha512-fERNJX8sOXfel6qCBCMPvZLzENBEhZTzKqg6vrOW5pvoEaQuJhRU4ndTAh6lHOxn1I6jnz2NHra56ZODM751uw==",
      "dev": true
    },
    "after": {
      "version": "0.8.2",
      "resolved": "https://registry.npmjs.org/after/-/after-0.8.2.tgz",
      "integrity": "sha1-/ts5T58OAqqXaOcCvaI7UF+ufh8=",
      "dev": true
    },
    "agent-base": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/agent-base/-/agent-base-4.2.1.tgz",
      "integrity": "sha512-JVwXMr9nHYTUXsBFKUqhJwvlcYU/blreOEUkhNR2eXZIvwd+c+o5V4MgDPKWnMS/56awN3TRzIP+KoPn+roQtg==",
      "dev": true,
      "requires": {
        "es6-promisify": "^5.0.0"
      }
    },
    "agentkeepalive": {
      "version": "3.5.2",
      "resolved": "https://registry.npmjs.org/agentkeepalive/-/agentkeepalive-3.5.2.tgz",
      "integrity": "sha512-e0L/HNe6qkQ7H19kTlRRqUibEAwDK5AFk6y3PtMsuut2VAH6+Q4xZml1tNDJD7kSAyqmbG/K08K5WEJYtUrSlQ==",
      "dev": true,
      "requires": {
        "humanize-ms": "^1.2.1"
      }
    },
    "ajv": {
      "version": "6.6.2",
      "resolved": "https://registry.npmjs.org/ajv/-/ajv-6.6.2.tgz",
      "integrity": "sha512-FBHEW6Jf5TB9MGBgUUA9XHkTbjXYfAUjY43ACMfmdMRHniyoMHjHjzD50OK8LGDWQwp4rWEsIq5kEqq7rvIM1g==",
      "dev": true,
      "requires": {
        "fast-deep-equal": "^2.0.1",
        "fast-json-stable-stringify": "^2.0.0",
        "json-schema-traverse": "^0.4.1",
        "uri-js": "^4.2.2"
      }
    },
    "ajv-errors": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/ajv-errors/-/ajv-errors-1.0.1.tgz",
      "integrity": "sha512-DCRfO/4nQ+89p/RK43i8Ezd41EqdGIU4ld7nGF8OQ14oc/we5rEntLCUa7+jrn3nn83BosfwZA0wb4pon2o8iQ==",
      "dev": true
    },
    "ajv-keywords": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/ajv-keywords/-/ajv-keywords-3.2.0.tgz",
      "integrity": "sha1-6GuBnGAs+IIa1jdBNpjx3sAhhHo=",
      "dev": true
    },
    "amdefine": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/amdefine/-/amdefine-1.0.1.tgz",
      "integrity": "sha1-SlKCrBZHKek2Gbz9OtFR+BfOkfU=",
      "dev": true
    },
    "ansi-colors": {
      "version": "3.2.3",
      "resolved": "https://registry.npmjs.org/ansi-colors/-/ansi-colors-3.2.3.tgz",
      "integrity": "sha512-LEHHyuhlPY3TmuUYMh2oz89lTShfvgbmzaBcxve9t/9Wuy7Dwf4yoAKcND7KFT1HAQfqZ12qtc+DUrBMeKF9nw==",
      "dev": true
    },
    "ansi-escapes": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/ansi-escapes/-/ansi-escapes-3.1.0.tgz",
      "integrity": "sha512-UgAb8H9D41AQnu/PbWlCofQVcnV4Gs2bBJi9eZPxfU/hgglFh3SMDMENRIqdr7H6XFnXdoknctFByVsCOotTVw==",
      "dev": true
    },
    "ansi-html": {
      "version": "0.0.7",
      "resolved": "https://registry.npmjs.org/ansi-html/-/ansi-html-0.0.7.tgz",
      "integrity": "sha1-gTWEAhliqenm/QOflA0S9WynhZ4=",
      "dev": true
    },
    "ansi-regex": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-2.1.1.tgz",
      "integrity": "sha1-w7M6te42DYbg5ijwRorn7yfWVN8=",
      "dev": true
    },
    "ansi-styles": {
      "version": "3.2.1",
      "resolved": "https://registry.npmjs.org/ansi-styles/-/ansi-styles-3.2.1.tgz",
      "integrity": "sha512-VT0ZI6kZRdTh8YyJw3SMbYm/u+NqfsAxEpWO0Pf9sq8/e94WxxOpPKx9FR1FlyCtOVDNOQ+8ntlqFxiRc+r5qA==",
      "dev": true,
      "requires": {
        "color-convert": "^1.9.0"
      }
    },
    "anymatch": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/anymatch/-/anymatch-2.0.0.tgz",
      "integrity": "sha512-5teOsQWABXHHBFP9y3skS5P3d/WfWXpv3FUpy+LorMrNYaT9pI4oLMQX7jzQ2KklNpGpWHzdCXTDT2Y3XGlZBw==",
      "dev": true,
      "requires": {
        "micromatch": "^3.1.4",
        "normalize-path": "^2.1.1"
      }
    },
    "app-root-path": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/app-root-path/-/app-root-path-2.1.0.tgz",
      "integrity": "sha1-mL9lmTJ+zqGZMJhm6BQDaP0uZGo=",
      "dev": true
    },
    "append-transform": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/append-transform/-/append-transform-1.0.0.tgz",
      "integrity": "sha512-P009oYkeHyU742iSZJzZZywj4QRJdnTWffaKuJQLablCZ1uz6/cW4yaRgcDaoQ+uwOxxnt0gRUcwfsNP2ri0gw==",
      "dev": true,
      "requires": {
        "default-require-extensions": "^2.0.0"
      }
    },
    "aproba": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/aproba/-/aproba-1.2.0.tgz",
      "integrity": "sha512-Y9J6ZjXtoYh8RnXVCMOU/ttDmk1aBjunq9vO0ta5x85WDQiQfUF9sIPBITdbiiIVcBo03Hi3jMxigBtsddlXRw==",
      "dev": true
    },
    "are-we-there-yet": {
      "version": "1.1.5",
      "resolved": "https://registry.npmjs.org/are-we-there-yet/-/are-we-there-yet-1.1.5.tgz",
      "integrity": "sha512-5hYdAkZlcG8tOLujVDTgCT+uPX0VnpAH28gWsLfzpXYm7wP6mp5Q/gYyR7YQ0cKVJcXJnl3j2kpBan13PtQf6w==",
      "dev": true,
      "requires": {
        "delegates": "^1.0.0",
        "readable-stream": "^2.0.6"
      }
    },
    "argparse": {
      "version": "1.0.10",
      "resolved": "https://registry.npmjs.org/argparse/-/argparse-1.0.10.tgz",
      "integrity": "sha512-o5Roy6tNG4SL/FOkCAN6RzjiakZS25RLYFrcMttJqbdd8BWrnA+fGz57iN5Pb06pvBGvl5gQ0B48dJlslXvoTg==",
      "dev": true,
      "requires": {
        "sprintf-js": "~1.0.2"
      }
    },
    "arr-diff": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/arr-diff/-/arr-diff-4.0.0.tgz",
      "integrity": "sha1-1kYQdP6/7HHn4VI1dhoyml3HxSA=",
      "dev": true
    },
    "arr-flatten": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/arr-flatten/-/arr-flatten-1.1.0.tgz",
      "integrity": "sha512-L3hKV5R/p5o81R7O02IGnwpDmkp6E982XhtbuwSe3O4qOtMMMtodicASA1Cny2U+aCXcNpml+m4dPsvsJ3jatg==",
      "dev": true
    },
    "arr-union": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/arr-union/-/arr-union-3.1.0.tgz",
      "integrity": "sha1-45sJrqne+Gao8gbiiK9jkZuuOcQ=",
      "dev": true
    },
    "array-find-index": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/array-find-index/-/array-find-index-1.0.2.tgz",
      "integrity": "sha1-3wEKoSh+Fku9pvlyOwqWoexBh6E=",
      "dev": true,
      "optional": true
    },
    "array-flatten": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/array-flatten/-/array-flatten-2.1.2.tgz",
      "integrity": "sha512-hNfzcOV8W4NdualtqBFPyVO+54DSJuZGY9qT4pRroB6S9e3iiido2ISIC5h9R2sPJ8H3FHCIiEnsv1lPXO3KtQ==",
      "dev": true
    },
    "array-slice": {
      "version": "0.2.3",
      "resolved": "https://registry.npmjs.org/array-slice/-/array-slice-0.2.3.tgz",
      "integrity": "sha1-3Tz7gO15c6dRF82sabC5nshhhvU=",
      "dev": true
    },
    "array-union": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/array-union/-/array-union-1.0.2.tgz",
      "integrity": "sha1-mjRBDk9OPaI96jdb5b5w8kd47Dk=",
      "dev": true,
      "requires": {
        "array-uniq": "^1.0.1"
      }
    },
    "array-uniq": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/array-uniq/-/array-uniq-1.0.3.tgz",
      "integrity": "sha1-r2rId6Jcx/dOBYiUdThY39sk/bY=",
      "dev": true
    },
    "array-unique": {
      "version": "0.3.2",
      "resolved": "https://registry.npmjs.org/array-unique/-/array-unique-0.3.2.tgz",
      "integrity": "sha1-qJS3XUvE9s1nnvMkSp/Y9Gri1Cg=",
      "dev": true
    },
    "arraybuffer.slice": {
      "version": "0.0.7",
      "resolved": "https://registry.npmjs.org/arraybuffer.slice/-/arraybuffer.slice-0.0.7.tgz",
      "integrity": "sha512-wGUIVQXuehL5TCqQun8OW81jGzAWycqzFF8lFp+GOM5BXLYj3bKNsYC4daB7n6XjCqxQA/qgTJ+8ANR3acjrog==",
      "dev": true
    },
    "arrify": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/arrify/-/arrify-1.0.1.tgz",
      "integrity": "sha1-iYUI2iIm84DfkEcoRWhJwVAaSw0=",
      "dev": true
    },
    "asap": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/asap/-/asap-2.0.6.tgz",
      "integrity": "sha1-5QNHYR1+aQlDIIu9r+vLwvuGbUY=",
      "dev": true,
      "optional": true
    },
    "asn1": {
      "version": "0.2.4",
      "resolved": "https://registry.npmjs.org/asn1/-/asn1-0.2.4.tgz",
      "integrity": "sha512-jxwzQpLQjSmWXgwaCZE9Nz+glAG01yF1QnWgbhGwHI5A6FRIEY6IVqtHhIepHqI7/kyEyQEagBC5mBEFlIYvdg==",
      "dev": true,
      "requires": {
        "safer-buffer": "~2.1.0"
      }
    },
    "asn1.js": {
      "version": "4.10.1",
      "resolved": "https://registry.npmjs.org/asn1.js/-/asn1.js-4.10.1.tgz",
      "integrity": "sha512-p32cOF5q0Zqs9uBiONKYLm6BClCoBCM5O9JfeUSlnQLBTxYdTK+pW+nXflm8UkKd2UYlEbYz5qEi0JuZR9ckSw==",
      "dev": true,
      "requires": {
        "bn.js": "^4.0.0",
        "inherits": "^2.0.1",
        "minimalistic-assert": "^1.0.0"
      }
    },
    "assert": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/assert/-/assert-1.4.1.tgz",
      "integrity": "sha1-mZEtWRg2tab1s0XA8H7vwI/GXZE=",
      "dev": true,
      "requires": {
        "util": "0.10.3"
      },
      "dependencies": {
        "inherits": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/inherits/-/inherits-2.0.1.tgz",
          "integrity": "sha1-sX0I0ya0Qj5Wjv9xn5GwscvfafE=",
          "dev": true
        },
        "util": {
          "version": "0.10.3",
          "resolved": "https://registry.npmjs.org/util/-/util-0.10.3.tgz",
          "integrity": "sha1-evsa/lCAUkZInj23/g7TeTNqwPk=",
          "dev": true,
          "requires": {
            "inherits": "2.0.1"
          }
        }
      }
    },
    "assert-plus": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/assert-plus/-/assert-plus-1.0.0.tgz",
      "integrity": "sha1-8S4PPF13sLHN2RRpQuTpbB5N1SU=",
      "dev": true
    },
    "assign-symbols": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/assign-symbols/-/assign-symbols-1.0.0.tgz",
      "integrity": "sha1-WWZ/QfrdTyDMvCu5a41Pf3jsA2c=",
      "dev": true
    },
    "async": {
      "version": "1.5.2",
      "resolved": "https://registry.npmjs.org/async/-/async-1.5.2.tgz",
      "integrity": "sha1-7GphrlZIDAw8skHJVhjiCJL5Zyo=",
      "dev": true
    },
    "async-each": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/async-each/-/async-each-1.0.1.tgz",
      "integrity": "sha1-GdOGodntxufByF04iu28xW0zYC0=",
      "dev": true
    },
    "async-foreach": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/async-foreach/-/async-foreach-0.1.3.tgz",
      "integrity": "sha1-NhIfhFwFeBct5Bmpfb6x0W7DRUI=",
      "dev": true,
      "optional": true
    },
    "async-limiter": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/async-limiter/-/async-limiter-1.0.0.tgz",
      "integrity": "sha512-jp/uFnooOiO+L211eZOoSyzpOITMXx1rBITauYykG3BRYPu8h0UcxsPNB04RR5vo4Tyz3+ay17tR6JVf9qzYWg==",
      "dev": true
    },
    "asynckit": {
      "version": "0.4.0",
      "resolved": "https://registry.npmjs.org/asynckit/-/asynckit-0.4.0.tgz",
      "integrity": "sha1-x57Zf380y48robyXkLzDZkdLS3k=",
      "dev": true
    },
    "atob": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/atob/-/atob-2.1.2.tgz",
      "integrity": "sha512-Wm6ukoaOGJi/73p/cl2GvLjTI5JM1k/O14isD73YML8StrH/7/lRFgmg8nICZgD3bZZvjwCGxtMOD3wWNAu8cg==",
      "dev": true
    },
    "autoprefixer": {
      "version": "9.4.3",
      "resolved": "https://registry.npmjs.org/autoprefixer/-/autoprefixer-9.4.3.tgz",
      "integrity": "sha512-/XSnzDepRkAU//xLcXA/lUWxpsBuw0WiriAHOqnxkuCtzLhaz+fL4it4gp20BQ8n5SyLzK/FOc7A0+u/rti2FQ==",
      "dev": true,
      "requires": {
        "browserslist": "^4.3.6",
        "caniuse-lite": "^1.0.30000921",
        "normalize-range": "^0.1.2",
        "num2fraction": "^1.2.2",
        "postcss": "^7.0.6",
        "postcss-value-parser": "^3.3.1"
      }
    },
    "aws-sign2": {
      "version": "0.7.0",
      "resolved": "https://registry.npmjs.org/aws-sign2/-/aws-sign2-0.7.0.tgz",
      "integrity": "sha1-tG6JCTSpWR8tL2+G1+ap8bP+dqg=",
      "dev": true
    },
    "aws4": {
      "version": "1.8.0",
      "resolved": "https://registry.npmjs.org/aws4/-/aws4-1.8.0.tgz",
      "integrity": "sha512-ReZxvNHIOv88FlT7rxcXIIC0fPt4KZqZbOlivyWtXLt8ESx84zd3kMC6iK5jVeS2qt+g7ftS7ye4fi06X5rtRQ==",
      "dev": true
    },
    "babel-code-frame": {
      "version": "6.26.0",
      "resolved": "https://registry.npmjs.org/babel-code-frame/-/babel-code-frame-6.26.0.tgz",
      "integrity": "sha1-Y/1D99weO7fONZR9uP42mj9Yx0s=",
      "dev": true,
      "requires": {
        "chalk": "^1.1.3",
        "esutils": "^2.0.2",
        "js-tokens": "^3.0.2"
      },
      "dependencies": {
        "ansi-styles": {
          "version": "2.2.1",
          "resolved": "https://registry.npmjs.org/ansi-styles/-/ansi-styles-2.2.1.tgz",
          "integrity": "sha1-tDLdM1i2NM914eRmQ2gkBTPB3b4=",
          "dev": true
        },
        "chalk": {
          "version": "1.1.3",
          "resolved": "https://registry.npmjs.org/chalk/-/chalk-1.1.3.tgz",
          "integrity": "sha1-qBFcVeSnAv5NFQq9OHKCKn4J/Jg=",
          "dev": true,
          "requires": {
            "ansi-styles": "^2.2.1",
            "escape-string-regexp": "^1.0.2",
            "has-ansi": "^2.0.0",
            "strip-ansi": "^3.0.0",
            "supports-color": "^2.0.0"
          }
        },
        "supports-color": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-2.0.0.tgz",
          "integrity": "sha1-U10EXOa2Nj+kARcIRimZXp3zJMc=",
          "dev": true
        }
      }
    },
    "babel-generator": {
      "version": "6.26.1",
      "resolved": "https://registry.npmjs.org/babel-generator/-/babel-generator-6.26.1.tgz",
      "integrity": "sha512-HyfwY6ApZj7BYTcJURpM5tznulaBvyio7/0d4zFOeMPUmfxkCjHocCuoLa2SAGzBI8AREcH3eP3758F672DppA==",
      "dev": true,
      "requires": {
        "babel-messages": "^6.23.0",
        "babel-runtime": "^6.26.0",
        "babel-types": "^6.26.0",
        "detect-indent": "^4.0.0",
        "jsesc": "^1.3.0",
        "lodash": "^4.17.4",
        "source-map": "^0.5.7",
        "trim-right": "^1.0.1"
      },
      "dependencies": {
        "source-map": {
          "version": "0.5.7",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.5.7.tgz",
          "integrity": "sha1-igOdLRAh0i0eoUyA2OpGi6LvP8w=",
          "dev": true
        }
      }
    },
    "babel-messages": {
      "version": "6.23.0",
      "resolved": "https://registry.npmjs.org/babel-messages/-/babel-messages-6.23.0.tgz",
      "integrity": "sha1-8830cDhYA1sqKVHG7F7fbGLyYw4=",
      "dev": true,
      "requires": {
        "babel-runtime": "^6.22.0"
      }
    },
    "babel-runtime": {
      "version": "6.26.0",
      "resolved": "https://registry.npmjs.org/babel-runtime/-/babel-runtime-6.26.0.tgz",
      "integrity": "sha1-llxwWGaOgrVde/4E/yM3vItWR/4=",
      "dev": true,
      "requires": {
        "core-js": "^2.4.0",
        "regenerator-runtime": "^0.11.0"
      }
    },
    "babel-template": {
      "version": "6.26.0",
      "resolved": "https://registry.npmjs.org/babel-template/-/babel-template-6.26.0.tgz",
      "integrity": "sha1-3gPi0WOWsGn0bdn/+FIfsaDjXgI=",
      "dev": true,
      "requires": {
        "babel-runtime": "^6.26.0",
        "babel-traverse": "^6.26.0",
        "babel-types": "^6.26.0",
        "babylon": "^6.18.0",
        "lodash": "^4.17.4"
      }
    },
    "babel-traverse": {
      "version": "6.26.0",
      "resolved": "https://registry.npmjs.org/babel-traverse/-/babel-traverse-6.26.0.tgz",
      "integrity": "sha1-RqnL1+3MYsjlwGTi0tjQ9ANXZu4=",
      "dev": true,
      "requires": {
        "babel-code-frame": "^6.26.0",
        "babel-messages": "^6.23.0",
        "babel-runtime": "^6.26.0",
        "babel-types": "^6.26.0",
        "babylon": "^6.18.0",
        "debug": "^2.6.8",
        "globals": "^9.18.0",
        "invariant": "^2.2.2",
        "lodash": "^4.17.4"
      }
    },
    "babel-types": {
      "version": "6.26.0",
      "resolved": "https://registry.npmjs.org/babel-types/-/babel-types-6.26.0.tgz",
      "integrity": "sha1-o7Bz+Uq0nrb6Vc1lInozQ4BjJJc=",
      "dev": true,
      "requires": {
        "babel-runtime": "^6.26.0",
        "esutils": "^2.0.2",
        "lodash": "^4.17.4",
        "to-fast-properties": "^1.0.3"
      }
    },
    "babylon": {
      "version": "6.18.0",
      "resolved": "https://registry.npmjs.org/babylon/-/babylon-6.18.0.tgz",
      "integrity": "sha512-q/UEjfGJ2Cm3oKV71DJz9d25TPnq5rhBVL2Q4fA5wcC3jcrdn7+SssEybFIxwAvvP+YCsCYNKughoF33GxgycQ==",
      "dev": true
    },
    "backo2": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/backo2/-/backo2-1.0.2.tgz",
      "integrity": "sha1-MasayLEpNjRj41s+u2n038+6eUc=",
      "dev": true
    },
    "balanced-match": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/balanced-match/-/balanced-match-1.0.0.tgz",
      "integrity": "sha1-ibTRmasr7kneFk6gK4nORi1xt2c=",
      "dev": true
    },
    "base": {
      "version": "0.11.2",
      "resolved": "https://registry.npmjs.org/base/-/base-0.11.2.tgz",
      "integrity": "sha512-5T6P4xPgpp0YDFvSWwEZ4NoE3aM4QBQXDzmVbraCkFj8zHM+mba8SyqB5DbZWyR7mYHo6Y7BdQo3MoA4m0TeQg==",
      "dev": true,
      "requires": {
        "cache-base": "^1.0.1",
        "class-utils": "^0.3.5",
        "component-emitter": "^1.2.1",
        "define-property": "^1.0.0",
        "isobject": "^3.0.1",
        "mixin-deep": "^1.2.0",
        "pascalcase": "^0.1.1"
      },
      "dependencies": {
        "define-property": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-1.0.0.tgz",
          "integrity": "sha1-dp66rz9KY6rTr56NMEybvnm/sOY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^1.0.0"
          }
        },
        "is-accessor-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-accessor-descriptor/-/is-accessor-descriptor-1.0.0.tgz",
          "integrity": "sha512-m5hnHTkcVsPfqx3AKlyttIPb7J+XykHvJP2B9bZDjlhLIoEq4XoK64Vg7boZlVWYK6LUY94dYPEE7Lh0ZkZKcQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-data-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-data-descriptor/-/is-data-descriptor-1.0.0.tgz",
          "integrity": "sha512-jbRXy1FmtAoCjQkVmIVYwuuqDFUbaOeDjmed1tOGPrsMhtJA4rD9tkgA0F1qJ3gRFRXcHYVkdeaP50Q5rE/jLQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-descriptor": {
          "version": "1.0.2",
          "resolved": "https://registry.npmjs.org/is-descriptor/-/is-descriptor-1.0.2.tgz",
          "integrity": "sha512-2eis5WqQGV7peooDyLmNEPUrps9+SXX5c9pL3xEB+4e9HnGuDa7mB7kHxHw4CbqS9k1T2hOH3miL8n8WtiYVtg==",
          "dev": true,
          "requires": {
            "is-accessor-descriptor": "^1.0.0",
            "is-data-descriptor": "^1.0.0",
            "kind-of": "^6.0.2"
          }
        }
      }
    },
    "base64-arraybuffer": {
      "version": "0.1.5",
      "resolved": "https://registry.npmjs.org/base64-arraybuffer/-/base64-arraybuffer-0.1.5.tgz",
      "integrity": "sha1-c5JncZI7Whl0etZmqlzUv5xunOg=",
      "dev": true
    },
    "base64-js": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/base64-js/-/base64-js-1.3.0.tgz",
      "integrity": "sha512-ccav/yGvoa80BQDljCxsmmQ3Xvx60/UpBIij5QN21W3wBi/hhIC9OoO+KLpu9IJTS9j4DRVJ3aDDF9cMSoa2lw==",
      "dev": true
    },
    "base64id": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/base64id/-/base64id-1.0.0.tgz",
      "integrity": "sha1-R2iMuZu2gE8OBtPnY7HDLlfY5rY=",
      "dev": true
    },
    "batch": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/batch/-/batch-0.6.1.tgz",
      "integrity": "sha1-3DQxT05nkxgJP8dgJyUl+UvyXBY=",
      "dev": true
    },
    "bcrypt-pbkdf": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/bcrypt-pbkdf/-/bcrypt-pbkdf-1.0.2.tgz",
      "integrity": "sha1-pDAdOJtqQ/m2f/PKEaP2Y342Dp4=",
      "dev": true,
      "requires": {
        "tweetnacl": "^0.14.3"
      }
    },
    "better-assert": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/better-assert/-/better-assert-1.0.2.tgz",
      "integrity": "sha1-QIZrnhueC1W0gYlDEeaPr/rrxSI=",
      "dev": true,
      "requires": {
        "callsite": "1.0.0"
      }
    },
    "big.js": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/big.js/-/big.js-3.2.0.tgz",
      "integrity": "sha512-+hN/Zh2D08Mx65pZ/4g5bsmNiZUuChDiQfTUQ7qJr4/kuopCr88xZsAXv6mBoZEsUI4OuGHlX59qE94K2mMW8Q==",
      "dev": true
    },
    "binary-extensions": {
      "version": "1.12.0",
      "resolved": "https://registry.npmjs.org/binary-extensions/-/binary-extensions-1.12.0.tgz",
      "integrity": "sha512-DYWGk01lDcxeS/K9IHPGWfT8PsJmbXRtRd2Sx72Tnb8pcYZQFF1oSDb8hJtS1vhp212q1Rzi5dUf9+nq0o9UIg==",
      "dev": true
    },
    "blob": {
      "version": "0.0.5",
      "resolved": "https://registry.npmjs.org/blob/-/blob-0.0.5.tgz",
      "integrity": "sha512-gaqbzQPqOoamawKg0LGVd7SzLgXS+JH61oWprSLH+P+abTczqJbhTR8CmJ2u9/bUYNmHTGJx/UEmn6doAvvuig==",
      "dev": true
    },
    "block-stream": {
      "version": "0.0.9",
      "resolved": "https://registry.npmjs.org/block-stream/-/block-stream-0.0.9.tgz",
      "integrity": "sha1-E+v+d4oDIFz+A3UUgeu0szAMEmo=",
      "dev": true,
      "optional": true,
      "requires": {
        "inherits": "~2.0.0"
      }
    },
    "blocking-proxy": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/blocking-proxy/-/blocking-proxy-1.0.1.tgz",
      "integrity": "sha512-KE8NFMZr3mN2E0HcvCgRtX7DjhiIQrwle+nSVJVC/yqFb9+xznHl2ZcoBp2L9qzkI4t4cBFJ1efXF8Dwi132RA==",
      "dev": true,
      "requires": {
        "minimist": "^1.2.0"
      },
      "dependencies": {
        "minimist": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/minimist/-/minimist-1.2.0.tgz",
          "integrity": "sha1-o1AIsg9BOD7sH7kU9M1d95omQoQ=",
          "dev": true
        }
      }
    },
    "bluebird": {
      "version": "3.5.3",
      "resolved": "https://registry.npmjs.org/bluebird/-/bluebird-3.5.3.tgz",
      "integrity": "sha512-/qKPUQlaW1OyR51WeCPBvRnAlnZFUJkCSG5HzGnuIqhgyJtF+T94lFnn33eiazjRm2LAHVy2guNnaq48X9SJuw==",
      "dev": true
    },
    "bn.js": {
      "version": "4.11.8",
      "resolved": "https://registry.npmjs.org/bn.js/-/bn.js-4.11.8.tgz",
      "integrity": "sha512-ItfYfPLkWHUjckQCk8xC+LwxgK8NYcXywGigJgSwOP8Y2iyWT4f2vsZnoOXTTbo+o5yXmIUJ4gn5538SO5S3gA==",
      "dev": true
    },
    "body-parser": {
      "version": "1.18.3",
      "resolved": "https://registry.npmjs.org/body-parser/-/body-parser-1.18.3.tgz",
      "integrity": "sha1-WykhmP/dVTs6DyDe0FkrlWlVyLQ=",
      "dev": true,
      "requires": {
        "bytes": "3.0.0",
        "content-type": "~1.0.4",
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "http-errors": "~1.6.3",
        "iconv-lite": "0.4.23",
        "on-finished": "~2.3.0",
        "qs": "6.5.2",
        "raw-body": "2.3.3",
        "type-is": "~1.6.16"
      }
    },
    "bonjour": {
      "version": "3.5.0",
      "resolved": "https://registry.npmjs.org/bonjour/-/bonjour-3.5.0.tgz",
      "integrity": "sha1-jokKGD2O6aI5OzhExpGkK897yfU=",
      "dev": true,
      "requires": {
        "array-flatten": "^2.1.0",
        "deep-equal": "^1.0.1",
        "dns-equal": "^1.0.0",
        "dns-txt": "^2.0.2",
        "multicast-dns": "^6.0.1",
        "multicast-dns-service-types": "^1.1.0"
      }
    },
    "brace-expansion": {
      "version": "1.1.11",
      "resolved": "https://registry.npmjs.org/brace-expansion/-/brace-expansion-1.1.11.tgz",
      "integrity": "sha512-iCuPHDFgrHX7H2vEI/5xpz07zSHB00TpugqhmYtVmMO6518mCuRMoOYFldEBl0g187ufozdaHgWKcYFb61qGiA==",
      "dev": true,
      "requires": {
        "balanced-match": "^1.0.0",
        "concat-map": "0.0.1"
      }
    },
    "braces": {
      "version": "2.3.2",
      "resolved": "https://registry.npmjs.org/braces/-/braces-2.3.2.tgz",
      "integrity": "sha512-aNdbnj9P8PjdXU4ybaWLK2IF3jc/EoDYbC7AazW6to3TRsfXxscC9UXOB5iDiEQrkyIbWp2SLQda4+QAa7nc3w==",
      "dev": true,
      "requires": {
        "arr-flatten": "^1.1.0",
        "array-unique": "^0.3.2",
        "extend-shallow": "^2.0.1",
        "fill-range": "^4.0.0",
        "isobject": "^3.0.1",
        "repeat-element": "^1.1.2",
        "snapdragon": "^0.8.1",
        "snapdragon-node": "^2.0.1",
        "split-string": "^3.0.2",
        "to-regex": "^3.0.1"
      },
      "dependencies": {
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        }
      }
    },
    "brorand": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/brorand/-/brorand-1.1.0.tgz",
      "integrity": "sha1-EsJe/kCkXjwyPrhnWgoM5XsiNx8=",
      "dev": true
    },
    "browserify-aes": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/browserify-aes/-/browserify-aes-1.2.0.tgz",
      "integrity": "sha512-+7CHXqGuspUn/Sl5aO7Ea0xWGAtETPXNSAjHo48JfLdPWcMng33Xe4znFvQweqc/uzk5zSOI3H52CYnjCfb5hA==",
      "dev": true,
      "requires": {
        "buffer-xor": "^1.0.3",
        "cipher-base": "^1.0.0",
        "create-hash": "^1.1.0",
        "evp_bytestokey": "^1.0.3",
        "inherits": "^2.0.1",
        "safe-buffer": "^5.0.1"
      }
    },
    "browserify-cipher": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/browserify-cipher/-/browserify-cipher-1.0.1.tgz",
      "integrity": "sha512-sPhkz0ARKbf4rRQt2hTpAHqn47X3llLkUGn+xEJzLjwY8LRs2p0v7ljvI5EyoRO/mexrNunNECisZs+gw2zz1w==",
      "dev": true,
      "requires": {
        "browserify-aes": "^1.0.4",
        "browserify-des": "^1.0.0",
        "evp_bytestokey": "^1.0.0"
      }
    },
    "browserify-des": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/browserify-des/-/browserify-des-1.0.2.tgz",
      "integrity": "sha512-BioO1xf3hFwz4kc6iBhI3ieDFompMhrMlnDFC4/0/vd5MokpuAc3R+LYbwTA9A5Yc9pq9UYPqffKpW2ObuwX5A==",
      "dev": true,
      "requires": {
        "cipher-base": "^1.0.1",
        "des.js": "^1.0.0",
        "inherits": "^2.0.1",
        "safe-buffer": "^5.1.2"
      }
    },
    "browserify-rsa": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/browserify-rsa/-/browserify-rsa-4.0.1.tgz",
      "integrity": "sha1-IeCr+vbyApzy+vsTNWenAdQTVSQ=",
      "dev": true,
      "requires": {
        "bn.js": "^4.1.0",
        "randombytes": "^2.0.1"
      }
    },
    "browserify-sign": {
      "version": "4.0.4",
      "resolved": "https://registry.npmjs.org/browserify-sign/-/browserify-sign-4.0.4.tgz",
      "integrity": "sha1-qk62jl17ZYuqa/alfmMMvXqT0pg=",
      "dev": true,
      "requires": {
        "bn.js": "^4.1.1",
        "browserify-rsa": "^4.0.0",
        "create-hash": "^1.1.0",
        "create-hmac": "^1.1.2",
        "elliptic": "^6.0.0",
        "inherits": "^2.0.1",
        "parse-asn1": "^5.0.0"
      }
    },
    "browserify-zlib": {
      "version": "0.2.0",
      "resolved": "https://registry.npmjs.org/browserify-zlib/-/browserify-zlib-0.2.0.tgz",
      "integrity": "sha512-Z942RysHXmJrhqk88FmKBVq/v5tqmSkDz7p54G/MGyjMnCFFnC79XWNbg+Vta8W6Wb2qtSZTSxIGkJrRpCFEiA==",
      "dev": true,
      "requires": {
        "pako": "~1.0.5"
      }
    },
    "browserslist": {
      "version": "4.4.1",
      "resolved": "https://registry.npmjs.org/browserslist/-/browserslist-4.4.1.tgz",
      "integrity": "sha512-pEBxEXg7JwaakBXjATYw/D1YZh4QUSCX/Mnd/wnqSRPPSi1U39iDhDoKGoBUcraKdxDlrYqJxSI5nNvD+dWP2A==",
      "dev": true,
      "requires": {
        "caniuse-lite": "^1.0.30000929",
        "electron-to-chromium": "^1.3.103",
        "node-releases": "^1.1.3"
      }
    },
    "browserstack": {
      "version": "1.5.2",
      "resolved": "https://registry.npmjs.org/browserstack/-/browserstack-1.5.2.tgz",
      "integrity": "sha512-+6AFt9HzhKykcPF79W6yjEUJcdvZOV0lIXdkORXMJftGrDl0OKWqRF4GHqpDNkxiceDT/uB7Fb/aDwktvXX7dg==",
      "dev": true,
      "requires": {
        "https-proxy-agent": "^2.2.1"
      }
    },
    "buffer": {
      "version": "4.9.1",
      "resolved": "https://registry.npmjs.org/buffer/-/buffer-4.9.1.tgz",
      "integrity": "sha1-bRu2AbB6TvztlwlBMgkwJ8lbwpg=",
      "dev": true,
      "requires": {
        "base64-js": "^1.0.2",
        "ieee754": "^1.1.4",
        "isarray": "^1.0.0"
      }
    },
    "buffer-alloc": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/buffer-alloc/-/buffer-alloc-1.2.0.tgz",
      "integrity": "sha512-CFsHQgjtW1UChdXgbyJGtnm+O/uLQeZdtbDo8mfUgYXCHSM1wgrVxXm6bSyrUuErEb+4sYVGCzASBRot7zyrow==",
      "dev": true,
      "requires": {
        "buffer-alloc-unsafe": "^1.1.0",
        "buffer-fill": "^1.0.0"
      }
    },
    "buffer-alloc-unsafe": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/buffer-alloc-unsafe/-/buffer-alloc-unsafe-1.1.0.tgz",
      "integrity": "sha512-TEM2iMIEQdJ2yjPJoSIsldnleVaAk1oW3DBVUykyOLsEsFmEc9kn+SFFPz+gl54KQNxlDnAwCXosOS9Okx2xAg==",
      "dev": true
    },
    "buffer-fill": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/buffer-fill/-/buffer-fill-1.0.0.tgz",
      "integrity": "sha1-+PeLdniYiO858gXNY39o5wISKyw=",
      "dev": true
    },
    "buffer-from": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/buffer-from/-/buffer-from-1.1.1.tgz",
      "integrity": "sha512-MQcXEUbCKtEo7bhqEs6560Hyd4XaovZlO/k9V3hjVUF/zwW7KBVdSK4gIt/bzwS9MbR5qob+F5jusZsb0YQK2A==",
      "dev": true
    },
    "buffer-indexof": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/buffer-indexof/-/buffer-indexof-1.1.1.tgz",
      "integrity": "sha512-4/rOEg86jivtPTeOUUT61jJO1Ya1TrR/OkqCSZDyq84WJh3LuuiphBYJN+fm5xufIk4XAFcEwte/8WzC8If/1g==",
      "dev": true
    },
    "buffer-xor": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/buffer-xor/-/buffer-xor-1.0.3.tgz",
      "integrity": "sha1-JuYe0UIvtw3ULm42cp7VHYVf6Nk=",
      "dev": true
    },
    "builtin-modules": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/builtin-modules/-/builtin-modules-1.1.1.tgz",
      "integrity": "sha1-Jw8HbFpywC9bZaR9+Uxf46J4iS8=",
      "dev": true
    },
    "builtin-status-codes": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/builtin-status-codes/-/builtin-status-codes-3.0.0.tgz",
      "integrity": "sha1-hZgoeOIbmOHGZCXgPQF0eI9Wnug=",
      "dev": true
    },
    "builtins": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/builtins/-/builtins-1.0.3.tgz",
      "integrity": "sha1-y5T662HIaWRR2zZTThQi+U8K7og=",
      "dev": true
    },
    "bytes": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/bytes/-/bytes-3.0.0.tgz",
      "integrity": "sha1-0ygVQE1olpn4Wk6k+odV3ROpYEg=",
      "dev": true
    },
    "cacache": {
      "version": "10.0.4",
      "resolved": "https://registry.npmjs.org/cacache/-/cacache-10.0.4.tgz",
      "integrity": "sha512-Dph0MzuH+rTQzGPNT9fAnrPmMmjKfST6trxJeK7NQuHRaVw24VzPRWTmg9MpcwOVQZO0E1FBICUlFeNaKPIfHA==",
      "dev": true,
      "requires": {
        "bluebird": "^3.5.1",
        "chownr": "^1.0.1",
        "glob": "^7.1.2",
        "graceful-fs": "^4.1.11",
        "lru-cache": "^4.1.1",
        "mississippi": "^2.0.0",
        "mkdirp": "^0.5.1",
        "move-concurrently": "^1.0.1",
        "promise-inflight": "^1.0.1",
        "rimraf": "^2.6.2",
        "ssri": "^5.2.4",
        "unique-filename": "^1.1.0",
        "y18n": "^4.0.0"
      }
    },
    "cache-base": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/cache-base/-/cache-base-1.0.1.tgz",
      "integrity": "sha512-AKcdTnFSWATd5/GCPRxr2ChwIJ85CeyrEyjRHlKxQ56d4XJMGym0uAiKn0xbLOGOl3+yRpOTi484dVCEc5AUzQ==",
      "dev": true,
      "requires": {
        "collection-visit": "^1.0.0",
        "component-emitter": "^1.2.1",
        "get-value": "^2.0.6",
        "has-value": "^1.0.0",
        "isobject": "^3.0.1",
        "set-value": "^2.0.0",
        "to-object-path": "^0.3.0",
        "union-value": "^1.0.0",
        "unset-value": "^1.0.0"
      }
    },
    "callsite": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/callsite/-/callsite-1.0.0.tgz",
      "integrity": "sha1-KAOY5dZkvXQDi28JBRU+borxvCA=",
      "dev": true
    },
    "camelcase": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/camelcase/-/camelcase-2.1.1.tgz",
      "integrity": "sha1-fB0W1nmhu+WcoCys7PsBHiAfWh8=",
      "dev": true,
      "optional": true
    },
    "camelcase-keys": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/camelcase-keys/-/camelcase-keys-2.1.0.tgz",
      "integrity": "sha1-MIvur/3ygRkFHvodkyITyRuPkuc=",
      "dev": true,
      "optional": true,
      "requires": {
        "camelcase": "^2.0.0",
        "map-obj": "^1.0.0"
      }
    },
    "caniuse-lite": {
      "version": "1.0.30000932",
      "resolved": "https://registry.npmjs.org/caniuse-lite/-/caniuse-lite-1.0.30000932.tgz",
      "integrity": "sha512-4bghJFItvzz8m0T3lLZbacmEY9X1Z2AtIzTr7s7byqZIOumASfr4ynDx7rtm0J85nDmx8vsgR6vnaSoeU8Oh0A==",
      "dev": true
    },
    "canonical-path": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/canonical-path/-/canonical-path-1.0.0.tgz",
      "integrity": "sha512-feylzsbDxi1gPZ1IjystzIQZagYYLvfKrSuygUCgf7z6x790VEzze5QEkdSV1U58RA7Hi0+v6fv4K54atOzATg==",
      "dev": true
    },
    "caseless": {
      "version": "0.12.0",
      "resolved": "https://registry.npmjs.org/caseless/-/caseless-0.12.0.tgz",
      "integrity": "sha1-G2gcIf+EAzyCZUMJBolCDRhxUdw=",
      "dev": true
    },
    "chalk": {
      "version": "2.4.2",
      "resolved": "https://registry.npmjs.org/chalk/-/chalk-2.4.2.tgz",
      "integrity": "sha512-Mti+f9lpJNcwF4tWV8/OrTTtF1gZi+f8FqlyAdouralcFWFQWF2+NgCHShjkCb+IFBLq9buZwE1xckQU4peSuQ==",
      "dev": true,
      "requires": {
        "ansi-styles": "^3.2.1",
        "escape-string-regexp": "^1.0.5",
        "supports-color": "^5.3.0"
      },
      "dependencies": {
        "supports-color": {
          "version": "5.5.0",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-5.5.0.tgz",
          "integrity": "sha512-QjVjwdXIt408MIiAqCX4oUKsgU2EqAGzs2Ppkm4aQYbjm+ZEWEcW4SfFNTr4uMNZma0ey4f5lgLrkB0aX0QMow==",
          "dev": true,
          "requires": {
            "has-flag": "^3.0.0"
          }
        }
      }
    },
    "chardet": {
      "version": "0.7.0",
      "resolved": "https://registry.npmjs.org/chardet/-/chardet-0.7.0.tgz",
      "integrity": "sha512-mT8iDcrh03qDGRRmoA2hmBJnxpllMR+0/0qlzjqZES6NdiWDcZkCNAk4rPFZ9Q85r27unkiNNg8ZOiwZXBHwcA==",
      "dev": true
    },
    "chokidar": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/chokidar/-/chokidar-2.0.4.tgz",
      "integrity": "sha512-z9n7yt9rOvIJrMhvDtDictKrkFHeihkNl6uWMmZlmL6tJtX9Cs+87oK+teBx+JIgzvbX3yZHT3eF8vpbDxHJXQ==",
      "dev": true,
      "requires": {
        "anymatch": "^2.0.0",
        "async-each": "^1.0.0",
        "braces": "^2.3.0",
        "fsevents": "^1.2.2",
        "glob-parent": "^3.1.0",
        "inherits": "^2.0.1",
        "is-binary-path": "^1.0.0",
        "is-glob": "^4.0.0",
        "lodash.debounce": "^4.0.8",
        "normalize-path": "^2.1.1",
        "path-is-absolute": "^1.0.0",
        "readdirp": "^2.0.0",
        "upath": "^1.0.5"
      }
    },
    "chownr": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/chownr/-/chownr-1.1.1.tgz",
      "integrity": "sha512-j38EvO5+LHX84jlo6h4UzmOwi0UgW61WRyPtJz4qaadK5eY3BTS5TY/S1Stc3Uk2lIM6TPevAlULiEJwie860g==",
      "dev": true
    },
    "chrome-trace-event": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/chrome-trace-event/-/chrome-trace-event-1.0.0.tgz",
      "integrity": "sha512-xDbVgyfDTT2piup/h8dK/y4QZfJRSa73bw1WZ8b4XM1o7fsFubUVGYcE+1ANtOzJJELGpYoG2961z0Z6OAld9A==",
      "dev": true,
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "cipher-base": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/cipher-base/-/cipher-base-1.0.4.tgz",
      "integrity": "sha512-Kkht5ye6ZGmwv40uUDZztayT2ThLQGfnj/T71N/XzeZeo3nf8foyW7zGTsPYkEya3m5f3cAypH+qe7YOrM1U2Q==",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "safe-buffer": "^5.0.1"
      }
    },
    "circular-dependency-plugin": {
      "version": "5.0.2",
      "resolved": "https://registry.npmjs.org/circular-dependency-plugin/-/circular-dependency-plugin-5.0.2.tgz",
      "integrity": "sha512-oC7/DVAyfcY3UWKm0sN/oVoDedQDQiw/vIiAnuTWTpE5s0zWf7l3WY417Xw/Fbi/QbAjctAkxgMiS9P0s3zkmA==",
      "dev": true
    },
    "circular-json": {
      "version": "0.5.9",
      "resolved": "https://registry.npmjs.org/circular-json/-/circular-json-0.5.9.tgz",
      "integrity": "sha512-4ivwqHpIFJZBuhN3g/pEcdbnGUywkBblloGbkglyloVjjR3uT6tieI89MVOfbP2tHX5sgb01FuLgAOzebNlJNQ==",
      "dev": true
    },
    "class-utils": {
      "version": "0.3.6",
      "resolved": "https://registry.npmjs.org/class-utils/-/class-utils-0.3.6.tgz",
      "integrity": "sha512-qOhPa/Fj7s6TY8H8esGu5QNpMMQxz79h+urzrNYN6mn+9BnxlDGf5QZ+XeCDsxSjPqsSR56XOZOJmpeurnLMeg==",
      "dev": true,
      "requires": {
        "arr-union": "^3.1.0",
        "define-property": "^0.2.5",
        "isobject": "^3.0.0",
        "static-extend": "^0.1.1"
      },
      "dependencies": {
        "define-property": {
          "version": "0.2.5",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-0.2.5.tgz",
          "integrity": "sha1-w1se+RjsPJkPmlvFe+BKrOxcgRY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^0.1.0"
          }
        }
      }
    },
    "clean-css": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/clean-css/-/clean-css-4.2.1.tgz",
      "integrity": "sha512-4ZxI6dy4lrY6FHzfiy1aEOXgu4LIsW2MhwG0VBKdcoGoH/XLFgaHSdLTGr4O8Be6A8r3MOphEiI8Gc1n0ecf3g==",
      "dev": true,
      "requires": {
        "source-map": "~0.6.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "cli-cursor": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/cli-cursor/-/cli-cursor-2.1.0.tgz",
      "integrity": "sha1-s12sN2R5+sw+lHR9QdDQ9SOP/LU=",
      "dev": true,
      "requires": {
        "restore-cursor": "^2.0.0"
      }
    },
    "cli-width": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/cli-width/-/cli-width-2.2.0.tgz",
      "integrity": "sha1-/xnt6Kml5XkyQUewwR8PvLq+1jk=",
      "dev": true
    },
    "cliui": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/cliui/-/cliui-3.2.0.tgz",
      "integrity": "sha1-EgYBU3qRbSmUD5NNo7SNWFo5IT0=",
      "dev": true,
      "requires": {
        "string-width": "^1.0.1",
        "strip-ansi": "^3.0.1",
        "wrap-ansi": "^2.0.0"
      }
    },
    "clone": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/clone/-/clone-2.1.2.tgz",
      "integrity": "sha1-G39Ln1kfHo+DZwQBYANFoCiHQ18=",
      "dev": true
    },
    "clone-deep": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/clone-deep/-/clone-deep-2.0.2.tgz",
      "integrity": "sha512-SZegPTKjCgpQH63E+eN6mVEEPdQBOUzjyJm5Pora4lrwWRFS8I0QAxV/KD6vV/i0WuijHZWQC1fMsPEdxfdVCQ==",
      "dev": true,
      "requires": {
        "for-own": "^1.0.0",
        "is-plain-object": "^2.0.4",
        "kind-of": "^6.0.0",
        "shallow-clone": "^1.0.0"
      }
    },
    "co": {
      "version": "4.6.0",
      "resolved": "https://registry.npmjs.org/co/-/co-4.6.0.tgz",
      "integrity": "sha1-bqa989hTrlTMuOR7+gvz+QMfsYQ=",
      "dev": true
    },
    "code-point-at": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/code-point-at/-/code-point-at-1.1.0.tgz",
      "integrity": "sha1-DQcLTQQ6W+ozovGkDi7bPZpMz3c=",
      "dev": true
    },
    "codelyzer": {
      "version": "4.5.0",
      "resolved": "https://registry.npmjs.org/codelyzer/-/codelyzer-4.5.0.tgz",
      "integrity": "sha512-oO6vCkjqsVrEsmh58oNlnJkRXuA30hF8cdNAQV9DytEalDwyOFRvHMnlKFzmOStNerOmPGZU9GAHnBo4tGvtiQ==",
      "dev": true,
      "requires": {
        "app-root-path": "^2.1.0",
        "css-selector-tokenizer": "^0.7.0",
        "cssauron": "^1.4.0",
        "semver-dsl": "^1.0.1",
        "source-map": "^0.5.7",
        "sprintf-js": "^1.1.1"
      },
      "dependencies": {
        "source-map": {
          "version": "0.5.7",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.5.7.tgz",
          "integrity": "sha1-igOdLRAh0i0eoUyA2OpGi6LvP8w=",
          "dev": true
        },
        "sprintf-js": {
          "version": "1.1.2",
          "resolved": "https://registry.npmjs.org/sprintf-js/-/sprintf-js-1.1.2.tgz",
          "integrity": "sha512-VE0SOVEHCk7Qc8ulkWw3ntAzXuqf7S2lvwQaDLRnUeIEaKNQJzV6BwmLKhOqT61aGhfUMrXeaBk+oDGCzvhcug==",
          "dev": true
        }
      }
    },
    "collection-visit": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/collection-visit/-/collection-visit-1.0.0.tgz",
      "integrity": "sha1-S8A3PBZLwykbTTaMgpzxqApZ3KA=",
      "dev": true,
      "requires": {
        "map-visit": "^1.0.0",
        "object-visit": "^1.0.0"
      }
    },
    "color-convert": {
      "version": "1.9.3",
      "resolved": "https://registry.npmjs.org/color-convert/-/color-convert-1.9.3.tgz",
      "integrity": "sha512-QfAUtd+vFdAtFQcC8CCyYt1fYWxSqAiK2cSD6zDB8N3cpsEBAvRxp9zOGg6G/SHHJYAT88/az/IuDGALsNVbGg==",
      "dev": true,
      "requires": {
        "color-name": "1.1.3"
      }
    },
    "color-name": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/color-name/-/color-name-1.1.3.tgz",
      "integrity": "sha1-p9BVi9icQveV3UIyj3QIMcpTvCU=",
      "dev": true
    },
    "colors": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/colors/-/colors-1.1.2.tgz",
      "integrity": "sha1-FopHAXVran9RoSzgyXv6KMCE7WM=",
      "dev": true
    },
    "combine-lists": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/combine-lists/-/combine-lists-1.0.1.tgz",
      "integrity": "sha1-RYwH4J4NkA/Ci3Cj/sLazR0st/Y=",
      "dev": true,
      "requires": {
        "lodash": "^4.5.0"
      }
    },
    "combined-stream": {
      "version": "1.0.7",
      "resolved": "https://registry.npmjs.org/combined-stream/-/combined-stream-1.0.7.tgz",
      "integrity": "sha512-brWl9y6vOB1xYPZcpZde3N9zDByXTosAeMDo4p1wzo6UMOX4vumB+TP1RZ76sfE6Md68Q0NJSrE/gbezd4Ul+w==",
      "dev": true,
      "requires": {
        "delayed-stream": "~1.0.0"
      }
    },
    "commander": {
      "version": "2.17.1",
      "resolved": "https://registry.npmjs.org/commander/-/commander-2.17.1.tgz",
      "integrity": "sha512-wPMUt6FnH2yzG95SA6mzjQOEKUU3aLaDEmzs1ti+1E9h+CsrZghRlqEM/EJ4KscsQVG8uNN4uVreUeT8+drlgg==",
      "dev": true
    },
    "commondir": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/commondir/-/commondir-1.0.1.tgz",
      "integrity": "sha1-3dgA2gxmEnOTzKWVDqloo6rxJTs=",
      "dev": true
    },
    "compare-versions": {
      "version": "3.4.0",
      "resolved": "https://registry.npmjs.org/compare-versions/-/compare-versions-3.4.0.tgz",
      "integrity": "sha512-tK69D7oNXXqUW3ZNo/z7NXTEz22TCF0pTE+YF9cxvaAM9XnkLo1fV621xCLrRR6aevJlKxExkss0vWqUCUpqdg==",
      "dev": true
    },
    "component-bind": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/component-bind/-/component-bind-1.0.0.tgz",
      "integrity": "sha1-AMYIq33Nk4l8AAllGx06jh5zu9E=",
      "dev": true
    },
    "component-emitter": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/component-emitter/-/component-emitter-1.2.1.tgz",
      "integrity": "sha1-E3kY1teCg/ffemt8WmPhQOaUJeY=",
      "dev": true
    },
    "component-inherit": {
      "version": "0.0.3",
      "resolved": "https://registry.npmjs.org/component-inherit/-/component-inherit-0.0.3.tgz",
      "integrity": "sha1-ZF/ErfWLcrZJ1crmUTVhnbJv8UM=",
      "dev": true
    },
    "compressible": {
      "version": "2.0.15",
      "resolved": "https://registry.npmjs.org/compressible/-/compressible-2.0.15.tgz",
      "integrity": "sha512-4aE67DL33dSW9gw4CI2H/yTxqHLNcxp0yS6jB+4h+wr3e43+1z7vm0HU9qXOH8j+qjKuL8+UtkOxYQSMq60Ylw==",
      "dev": true,
      "requires": {
        "mime-db": ">= 1.36.0 < 2"
      }
    },
    "compression": {
      "version": "1.7.3",
      "resolved": "https://registry.npmjs.org/compression/-/compression-1.7.3.tgz",
      "integrity": "sha512-HSjyBG5N1Nnz7tF2+O7A9XUhyjru71/fwgNb7oIsEVHR0WShfs2tIS/EySLgiTe98aOK18YDlMXpzjCXY/n9mg==",
      "dev": true,
      "requires": {
        "accepts": "~1.3.5",
        "bytes": "3.0.0",
        "compressible": "~2.0.14",
        "debug": "2.6.9",
        "on-headers": "~1.0.1",
        "safe-buffer": "5.1.2",
        "vary": "~1.1.2"
      }
    },
    "concat-map": {
      "version": "0.0.1",
      "resolved": "https://registry.npmjs.org/concat-map/-/concat-map-0.0.1.tgz",
      "integrity": "sha1-2Klr13/Wjfd5OnMDajug1UBdR3s=",
      "dev": true
    },
    "concat-stream": {
      "version": "1.6.2",
      "resolved": "https://registry.npmjs.org/concat-stream/-/concat-stream-1.6.2.tgz",
      "integrity": "sha512-27HBghJxjiZtIk3Ycvn/4kbJk/1uZuJFfuPEns6LaEvpvG1f0hTea8lilrouyo9mVc2GWdcEZ8OLoGmSADlrCw==",
      "dev": true,
      "requires": {
        "buffer-from": "^1.0.0",
        "inherits": "^2.0.3",
        "readable-stream": "^2.2.2",
        "typedarray": "^0.0.6"
      }
    },
    "connect": {
      "version": "3.6.6",
      "resolved": "https://registry.npmjs.org/connect/-/connect-3.6.6.tgz",
      "integrity": "sha1-Ce/2xVr3I24TcTWnJXSFi2eG9SQ=",
      "dev": true,
      "requires": {
        "debug": "2.6.9",
        "finalhandler": "1.1.0",
        "parseurl": "~1.3.2",
        "utils-merge": "1.0.1"
      },
      "dependencies": {
        "finalhandler": {
          "version": "1.1.0",
          "resolved": "https://registry.npmjs.org/finalhandler/-/finalhandler-1.1.0.tgz",
          "integrity": "sha1-zgtoVbRYU+eRsvzGgARtiCU91/U=",
          "dev": true,
          "requires": {
            "debug": "2.6.9",
            "encodeurl": "~1.0.1",
            "escape-html": "~1.0.3",
            "on-finished": "~2.3.0",
            "parseurl": "~1.3.2",
            "statuses": "~1.3.1",
            "unpipe": "~1.0.0"
          }
        },
        "statuses": {
          "version": "1.3.1",
          "resolved": "https://registry.npmjs.org/statuses/-/statuses-1.3.1.tgz",
          "integrity": "sha1-+vUbnrdKrvOzrPStX2Gr8ky3uT4=",
          "dev": true
        }
      }
    },
    "connect-history-api-fallback": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/connect-history-api-fallback/-/connect-history-api-fallback-1.6.0.tgz",
      "integrity": "sha512-e54B99q/OUoH64zYYRf3HBP5z24G38h5D3qXu23JGRoigpX5Ss4r9ZnDk3g0Z8uQC2x2lPaJ+UlWBc1ZWBWdLg==",
      "dev": true
    },
    "console-browserify": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/console-browserify/-/console-browserify-1.1.0.tgz",
      "integrity": "sha1-8CQcRXMKn8YyOyBtvzjtx0HQuxA=",
      "dev": true,
      "requires": {
        "date-now": "^0.1.4"
      }
    },
    "console-control-strings": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/console-control-strings/-/console-control-strings-1.1.0.tgz",
      "integrity": "sha1-PXz0Rk22RG6mRL9LOVB/mFEAjo4=",
      "dev": true
    },
    "constants-browserify": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/constants-browserify/-/constants-browserify-1.0.0.tgz",
      "integrity": "sha1-wguW2MYXdIqvHBYCF2DNJ/y4y3U=",
      "dev": true
    },
    "content-disposition": {
      "version": "0.5.2",
      "resolved": "https://registry.npmjs.org/content-disposition/-/content-disposition-0.5.2.tgz",
      "integrity": "sha1-DPaLud318r55YcOoUXjLhdunjLQ=",
      "dev": true
    },
    "content-type": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/content-type/-/content-type-1.0.4.tgz",
      "integrity": "sha512-hIP3EEPs8tB9AT1L+NUqtwOAps4mk2Zob89MWXMHjHWg9milF/j4osnnQLXBCBFBk/tvIG/tUc9mOUJiPBhPXA==",
      "dev": true
    },
    "convert-source-map": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/convert-source-map/-/convert-source-map-1.6.0.tgz",
      "integrity": "sha512-eFu7XigvxdZ1ETfbgPBohgyQ/Z++C0eEhTor0qRwBw9unw+L0/6V8wkSuGgzdThkiS5lSpdptOQPD8Ak40a+7A==",
      "dev": true,
      "requires": {
        "safe-buffer": "~5.1.1"
      }
    },
    "cookie": {
      "version": "0.3.1",
      "resolved": "https://registry.npmjs.org/cookie/-/cookie-0.3.1.tgz",
      "integrity": "sha1-5+Ch+e9DtMi6klxcWpboBtFoc7s=",
      "dev": true
    },
    "cookie-signature": {
      "version": "1.0.6",
      "resolved": "https://registry.npmjs.org/cookie-signature/-/cookie-signature-1.0.6.tgz",
      "integrity": "sha1-4wOogrNCzD7oylE6eZmXNNqzriw=",
      "dev": true
    },
    "copy-concurrently": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/copy-concurrently/-/copy-concurrently-1.0.5.tgz",
      "integrity": "sha512-f2domd9fsVDFtaFcbaRZuYXwtdmnzqbADSwhSWYxYB/Q8zsdUUFMXVRwXGDMWmbEzAn1kdRrtI1T/KTFOL4X2A==",
      "dev": true,
      "requires": {
        "aproba": "^1.1.1",
        "fs-write-stream-atomic": "^1.0.8",
        "iferr": "^0.1.5",
        "mkdirp": "^0.5.1",
        "rimraf": "^2.5.4",
        "run-queue": "^1.0.0"
      }
    },
    "copy-descriptor": {
      "version": "0.1.1",
      "resolved": "https://registry.npmjs.org/copy-descriptor/-/copy-descriptor-0.1.1.tgz",
      "integrity": "sha1-Z29us8OZl8LuGsOpJP1hJHSPV40=",
      "dev": true
    },
    "copy-webpack-plugin": {
      "version": "4.6.0",
      "resolved": "https://registry.npmjs.org/copy-webpack-plugin/-/copy-webpack-plugin-4.6.0.tgz",
      "integrity": "sha512-Y+SQCF+0NoWQryez2zXn5J5knmr9z/9qSQt7fbL78u83rxmigOy8X5+BFn8CFSuX+nKT8gpYwJX68ekqtQt6ZA==",
      "dev": true,
      "requires": {
        "cacache": "^10.0.4",
        "find-cache-dir": "^1.0.0",
        "globby": "^7.1.1",
        "is-glob": "^4.0.0",
        "loader-utils": "^1.1.0",
        "minimatch": "^3.0.4",
        "p-limit": "^1.0.0",
        "serialize-javascript": "^1.4.0"
      }
    },
    "core-js": {
      "version": "2.6.3",
      "resolved": "https://registry.npmjs.org/core-js/-/core-js-2.6.3.tgz",
      "integrity": "sha512-l00tmFFZOBHtYhN4Cz7k32VM7vTn3rE2ANjQDxdEN6zmXZ/xq1jQuutnmHvMG1ZJ7xd72+TA5YpUK8wz3rWsfQ=="
    },
    "core-util-is": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/core-util-is/-/core-util-is-1.0.2.tgz",
      "integrity": "sha1-tf1UIgqivFq1eqtxQMlAdUUDwac=",
      "dev": true
    },
    "cosmiconfig": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/cosmiconfig/-/cosmiconfig-4.0.0.tgz",
      "integrity": "sha512-6e5vDdrXZD+t5v0L8CrurPeybg4Fmf+FCSYxXKYVAqLUtyCSbuyqE059d0kDthTNRzKVjL7QMgNpEUlsoYH3iQ==",
      "dev": true,
      "requires": {
        "is-directory": "^0.3.1",
        "js-yaml": "^3.9.0",
        "parse-json": "^4.0.0",
        "require-from-string": "^2.0.1"
      },
      "dependencies": {
        "parse-json": {
          "version": "4.0.0",
          "resolved": "https://registry.npmjs.org/parse-json/-/parse-json-4.0.0.tgz",
          "integrity": "sha1-vjX1Qlvh9/bHRxhPmKeIy5lHfuA=",
          "dev": true,
          "requires": {
            "error-ex": "^1.3.1",
            "json-parse-better-errors": "^1.0.1"
          }
        }
      }
    },
    "create-ecdh": {
      "version": "4.0.3",
      "resolved": "https://registry.npmjs.org/create-ecdh/-/create-ecdh-4.0.3.tgz",
      "integrity": "sha512-GbEHQPMOswGpKXM9kCWVrremUcBmjteUaQ01T9rkKCPDXfUHX0IoP9LpHYo2NPFampa4e+/pFDc3jQdxrxQLaw==",
      "dev": true,
      "requires": {
        "bn.js": "^4.1.0",
        "elliptic": "^6.0.0"
      }
    },
    "create-hash": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/create-hash/-/create-hash-1.2.0.tgz",
      "integrity": "sha512-z00bCGNHDG8mHAkP7CtT1qVu+bFQUPjYq/4Iv3C3kWjTFV10zIjfSoeqXo9Asws8gwSHDGj/hl2u4OGIjapeCg==",
      "dev": true,
      "requires": {
        "cipher-base": "^1.0.1",
        "inherits": "^2.0.1",
        "md5.js": "^1.3.4",
        "ripemd160": "^2.0.1",
        "sha.js": "^2.4.0"
      }
    },
    "create-hmac": {
      "version": "1.1.7",
      "resolved": "https://registry.npmjs.org/create-hmac/-/create-hmac-1.1.7.tgz",
      "integrity": "sha512-MJG9liiZ+ogc4TzUwuvbER1JRdgvUFSB5+VR/g5h82fGaIRWMWddtKBHi7/sVhfjQZ6SehlyhvQYrcYkaUIpLg==",
      "dev": true,
      "requires": {
        "cipher-base": "^1.0.3",
        "create-hash": "^1.1.0",
        "inherits": "^2.0.1",
        "ripemd160": "^2.0.0",
        "safe-buffer": "^5.0.1",
        "sha.js": "^2.4.8"
      }
    },
    "cross-spawn": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/cross-spawn/-/cross-spawn-3.0.1.tgz",
      "integrity": "sha1-ElYDfsufDF9549bvE14wdwGEuYI=",
      "dev": true,
      "optional": true,
      "requires": {
        "lru-cache": "^4.0.1",
        "which": "^1.2.9"
      }
    },
    "crypto-browserify": {
      "version": "3.12.0",
      "resolved": "https://registry.npmjs.org/crypto-browserify/-/crypto-browserify-3.12.0.tgz",
      "integrity": "sha512-fz4spIh+znjO2VjL+IdhEpRJ3YN6sMzITSBijk6FK2UvTqruSQW+/cCZTSNsMiZNvUeq0CqurF+dAbyiGOY6Wg==",
      "dev": true,
      "requires": {
        "browserify-cipher": "^1.0.0",
        "browserify-sign": "^4.0.0",
        "create-ecdh": "^4.0.0",
        "create-hash": "^1.1.0",
        "create-hmac": "^1.1.0",
        "diffie-hellman": "^5.0.0",
        "inherits": "^2.0.1",
        "pbkdf2": "^3.0.3",
        "public-encrypt": "^4.0.0",
        "randombytes": "^2.0.0",
        "randomfill": "^1.0.3"
      }
    },
    "css-parse": {
      "version": "1.7.0",
      "resolved": "https://registry.npmjs.org/css-parse/-/css-parse-1.7.0.tgz",
      "integrity": "sha1-Mh9s9zeCpv91ERE5D8BeLGV9jJs=",
      "dev": true
    },
    "css-selector-tokenizer": {
      "version": "0.7.1",
      "resolved": "https://registry.npmjs.org/css-selector-tokenizer/-/css-selector-tokenizer-0.7.1.tgz",
      "integrity": "sha512-xYL0AMZJ4gFzJQsHUKa5jiWWi2vH77WVNg7JYRyewwj6oPh4yb/y6Y9ZCw9dsj/9UauMhtuxR+ogQd//EdEVNA==",
      "dev": true,
      "requires": {
        "cssesc": "^0.1.0",
        "fastparse": "^1.1.1",
        "regexpu-core": "^1.0.0"
      }
    },
    "cssauron": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/cssauron/-/cssauron-1.4.0.tgz",
      "integrity": "sha1-pmAt/34EqDBtwNuaVR6S6LVmKtg=",
      "dev": true,
      "requires": {
        "through": "X.X.X"
      }
    },
    "cssesc": {
      "version": "0.1.0",
      "resolved": "https://registry.npmjs.org/cssesc/-/cssesc-0.1.0.tgz",
      "integrity": "sha1-yBSQPkViM3GgR3tAEJqq++6t27Q=",
      "dev": true
    },
    "currently-unhandled": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/currently-unhandled/-/currently-unhandled-0.4.1.tgz",
      "integrity": "sha1-mI3zP+qxke95mmE2nddsF635V+o=",
      "dev": true,
      "optional": true,
      "requires": {
        "array-find-index": "^1.0.1"
      }
    },
    "custom-event": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/custom-event/-/custom-event-1.0.1.tgz",
      "integrity": "sha1-XQKkaFCt8bSjF5RqOSj8y1v9BCU=",
      "dev": true
    },
    "cyclist": {
      "version": "0.2.2",
      "resolved": "https://registry.npmjs.org/cyclist/-/cyclist-0.2.2.tgz",
      "integrity": "sha1-GzN5LhHpFKL9bW7WRHRkRE5fpkA=",
      "dev": true
    },
    "dashdash": {
      "version": "1.14.1",
      "resolved": "https://registry.npmjs.org/dashdash/-/dashdash-1.14.1.tgz",
      "integrity": "sha1-hTz6D3y+L+1d4gMmuN1YEDX24vA=",
      "dev": true,
      "requires": {
        "assert-plus": "^1.0.0"
      }
    },
    "date-format": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/date-format/-/date-format-1.2.0.tgz",
      "integrity": "sha1-YV6CjiM90aubua4JUODOzPpuytg=",
      "dev": true
    },
    "date-now": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/date-now/-/date-now-0.1.4.tgz",
      "integrity": "sha1-6vQ5/U1ISK105cx9vvIAZyueNFs=",
      "dev": true
    },
    "debug": {
      "version": "2.6.9",
      "resolved": "https://registry.npmjs.org/debug/-/debug-2.6.9.tgz",
      "integrity": "sha512-bC7ElrdJaJnPbAP+1EotYvqZsb3ecl5wi6Bfi6BJTUcNowp6cvspg0jXznRTKDjm/E7AdgFBVeAPVMNcKGsHMA==",
      "dev": true,
      "requires": {
        "ms": "2.0.0"
      }
    },
    "decamelize": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/decamelize/-/decamelize-1.2.0.tgz",
      "integrity": "sha1-9lNNFRSCabIDUue+4m9QH5oZEpA=",
      "dev": true
    },
    "decode-uri-component": {
      "version": "0.2.0",
      "resolved": "https://registry.npmjs.org/decode-uri-component/-/decode-uri-component-0.2.0.tgz",
      "integrity": "sha1-6zkTMzRYd1y4TNGh+uBiEGu4dUU=",
      "dev": true
    },
    "deep-equal": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/deep-equal/-/deep-equal-1.0.1.tgz",
      "integrity": "sha1-9dJgKStmDghO/0zbyfCK0yR0SLU=",
      "dev": true
    },
    "deep-is": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/deep-is/-/deep-is-0.1.3.tgz",
      "integrity": "sha1-s2nW+128E+7PUk+RsHD+7cNXzzQ=",
      "dev": true
    },
    "default-gateway": {
      "version": "2.7.2",
      "resolved": "https://registry.npmjs.org/default-gateway/-/default-gateway-2.7.2.tgz",
      "integrity": "sha512-lAc4i9QJR0YHSDFdzeBQKfZ1SRDG3hsJNEkrpcZa8QhBfidLAilT60BDEIVUUGqosFp425KOgB3uYqcnQrWafQ==",
      "dev": true,
      "requires": {
        "execa": "^0.10.0",
        "ip-regex": "^2.1.0"
      }
    },
    "default-require-extensions": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/default-require-extensions/-/default-require-extensions-2.0.0.tgz",
      "integrity": "sha1-9fj7sYp9bVCyH2QfZJ67Uiz+JPc=",
      "dev": true,
      "requires": {
        "strip-bom": "^3.0.0"
      },
      "dependencies": {
        "strip-bom": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/strip-bom/-/strip-bom-3.0.0.tgz",
          "integrity": "sha1-IzTBjpx1n3vdVv3vfprj1YjmjtM=",
          "dev": true
        }
      }
    },
    "define-property": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/define-property/-/define-property-2.0.2.tgz",
      "integrity": "sha512-jwK2UV4cnPpbcG7+VRARKTZPUWowwXA8bzH5NP6ud0oeAxyYPuGZUAC7hMugpCdz4BeSZl2Dl9k66CHJ/46ZYQ==",
      "dev": true,
      "requires": {
        "is-descriptor": "^1.0.2",
        "isobject": "^3.0.1"
      },
      "dependencies": {
        "is-accessor-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-accessor-descriptor/-/is-accessor-descriptor-1.0.0.tgz",
          "integrity": "sha512-m5hnHTkcVsPfqx3AKlyttIPb7J+XykHvJP2B9bZDjlhLIoEq4XoK64Vg7boZlVWYK6LUY94dYPEE7Lh0ZkZKcQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-data-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-data-descriptor/-/is-data-descriptor-1.0.0.tgz",
          "integrity": "sha512-jbRXy1FmtAoCjQkVmIVYwuuqDFUbaOeDjmed1tOGPrsMhtJA4rD9tkgA0F1qJ3gRFRXcHYVkdeaP50Q5rE/jLQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-descriptor": {
          "version": "1.0.2",
          "resolved": "https://registry.npmjs.org/is-descriptor/-/is-descriptor-1.0.2.tgz",
          "integrity": "sha512-2eis5WqQGV7peooDyLmNEPUrps9+SXX5c9pL3xEB+4e9HnGuDa7mB7kHxHw4CbqS9k1T2hOH3miL8n8WtiYVtg==",
          "dev": true,
          "requires": {
            "is-accessor-descriptor": "^1.0.0",
            "is-data-descriptor": "^1.0.0",
            "kind-of": "^6.0.2"
          }
        }
      }
    },
    "del": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/del/-/del-3.0.0.tgz",
      "integrity": "sha1-U+z2mf/LyzljdpGrE7rxYIGXZuU=",
      "dev": true,
      "requires": {
        "globby": "^6.1.0",
        "is-path-cwd": "^1.0.0",
        "is-path-in-cwd": "^1.0.0",
        "p-map": "^1.1.1",
        "pify": "^3.0.0",
        "rimraf": "^2.2.8"
      },
      "dependencies": {
        "globby": {
          "version": "6.1.0",
          "resolved": "https://registry.npmjs.org/globby/-/globby-6.1.0.tgz",
          "integrity": "sha1-9abXDoOV4hyFj7BInWTfAkJNUGw=",
          "dev": true,
          "requires": {
            "array-union": "^1.0.1",
            "glob": "^7.0.3",
            "object-assign": "^4.0.1",
            "pify": "^2.0.0",
            "pinkie-promise": "^2.0.0"
          },
          "dependencies": {
            "pify": {
              "version": "2.3.0",
              "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
              "integrity": "sha1-7RQaasBDqEnqWISY59yosVMw6Qw=",
              "dev": true
            }
          }
        }
      }
    },
    "delayed-stream": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/delayed-stream/-/delayed-stream-1.0.0.tgz",
      "integrity": "sha1-3zrhmayt+31ECqrgsp4icrJOxhk=",
      "dev": true
    },
    "delegates": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/delegates/-/delegates-1.0.0.tgz",
      "integrity": "sha1-hMbhWbgZBP3KWaDvRM2HDTElD5o=",
      "dev": true
    },
    "depd": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/depd/-/depd-1.1.2.tgz",
      "integrity": "sha1-m81S4UwJd2PnSbJ0xDRu0uVgtak=",
      "dev": true
    },
    "dependency-graph": {
      "version": "0.7.2",
      "resolved": "https://registry.npmjs.org/dependency-graph/-/dependency-graph-0.7.2.tgz",
      "integrity": "sha512-KqtH4/EZdtdfWX0p6MGP9jljvxSY6msy/pRUD4jgNwVpv3v1QmNLlsB3LDSSUg79BRVSn7jI1QPRtArGABovAQ==",
      "dev": true
    },
    "des.js": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/des.js/-/des.js-1.0.0.tgz",
      "integrity": "sha1-wHTS4qpqipoH29YfmhXCzYPsjsw=",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "minimalistic-assert": "^1.0.0"
      }
    },
    "destroy": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/destroy/-/destroy-1.0.4.tgz",
      "integrity": "sha1-l4hXRCxEdJ5CBmE+N5RiBYJqvYA=",
      "dev": true
    },
    "detect-indent": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/detect-indent/-/detect-indent-4.0.0.tgz",
      "integrity": "sha1-920GQ1LN9Docts5hnE7jqUdd4gg=",
      "dev": true,
      "requires": {
        "repeating": "^2.0.0"
      }
    },
    "detect-node": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/detect-node/-/detect-node-2.0.4.tgz",
      "integrity": "sha512-ZIzRpLJrOj7jjP2miAtgqIfmzbxa4ZOr5jJc601zklsfEx9oTzmmj2nVpIPRpNlRTIh8lc1kyViIY7BWSGNmKw==",
      "dev": true
    },
    "di": {
      "version": "0.0.1",
      "resolved": "https://registry.npmjs.org/di/-/di-0.0.1.tgz",
      "integrity": "sha1-gGZJMmzqp8qjMG112YXqJ0i6kTw=",
      "dev": true
    },
    "diff": {
      "version": "3.5.0",
      "resolved": "https://registry.npmjs.org/diff/-/diff-3.5.0.tgz",
      "integrity": "sha512-A46qtFgd+g7pDZinpnwiRJtxbC1hpgf0uzP3iG89scHk0AUC7A1TGxf5OiiOUv/JMZR8GOt8hL900hV0bOy5xA==",
      "dev": true
    },
    "diffie-hellman": {
      "version": "5.0.3",
      "resolved": "https://registry.npmjs.org/diffie-hellman/-/diffie-hellman-5.0.3.tgz",
      "integrity": "sha512-kqag/Nl+f3GwyK25fhUMYj81BUOrZ9IuJsjIcDE5icNM9FJHAVm3VcUDxdLPoQtTuUylWm6ZIknYJwwaPxsUzg==",
      "dev": true,
      "requires": {
        "bn.js": "^4.1.0",
        "miller-rabin": "^4.0.0",
        "randombytes": "^2.0.0"
      }
    },
    "dir-glob": {
      "version": "2.2.2",
      "resolved": "https://registry.npmjs.org/dir-glob/-/dir-glob-2.2.2.tgz",
      "integrity": "sha512-f9LBi5QWzIW3I6e//uxZoLBlUt9kcp66qo0sSCxL6YZKc75R1c4MFCoe/LaZiBGmgujvQdxc5Bn3QhfyvK5Hsw==",
      "dev": true,
      "requires": {
        "path-type": "^3.0.0"
      }
    },
    "dns-equal": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/dns-equal/-/dns-equal-1.0.0.tgz",
      "integrity": "sha1-s55/HabrCnW6nBcySzR1PEfgZU0=",
      "dev": true
    },
    "dns-packet": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/dns-packet/-/dns-packet-1.3.1.tgz",
      "integrity": "sha512-0UxfQkMhYAUaZI+xrNZOz/as5KgDU0M/fQ9b6SpkyLbk3GEswDi6PADJVaYJradtRVsRIlF1zLyOodbcTCDzUg==",
      "dev": true,
      "requires": {
        "ip": "^1.1.0",
        "safe-buffer": "^5.0.1"
      }
    },
    "dns-txt": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/dns-txt/-/dns-txt-2.0.2.tgz",
      "integrity": "sha1-uR2Ab10nGI5Ks+fRB9iBocxGQrY=",
      "dev": true,
      "requires": {
        "buffer-indexof": "^1.0.0"
      }
    },
    "dom-serialize": {
      "version": "2.2.1",
      "resolved": "https://registry.npmjs.org/dom-serialize/-/dom-serialize-2.2.1.tgz",
      "integrity": "sha1-ViromZ9Evl6jB29UGdzVnrQ6yVs=",
      "dev": true,
      "requires": {
        "custom-event": "~1.0.0",
        "ent": "~2.2.0",
        "extend": "^3.0.0",
        "void-elements": "^2.0.0"
      }
    },
    "domain-browser": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/domain-browser/-/domain-browser-1.2.0.tgz",
      "integrity": "sha512-jnjyiM6eRyZl2H+W8Q/zLMA481hzi0eszAaBUzIVnmYVDBbnLxVNnfu1HgEBvCbL+71FrxMl3E6lpKH7Ge3OXA==",
      "dev": true
    },
    "duplexify": {
      "version": "3.6.1",
      "resolved": "https://registry.npmjs.org/duplexify/-/duplexify-3.6.1.tgz",
      "integrity": "sha512-vM58DwdnKmty+FSPzT14K9JXb90H+j5emaR4KYbr2KTIz00WHGbWOe5ghQTx233ZCLZtrGDALzKwcjEtSt35mA==",
      "dev": true,
      "requires": {
        "end-of-stream": "^1.0.0",
        "inherits": "^2.0.1",
        "readable-stream": "^2.0.0",
        "stream-shift": "^1.0.0"
      }
    },
    "ecc-jsbn": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/ecc-jsbn/-/ecc-jsbn-0.1.2.tgz",
      "integrity": "sha1-OoOpBOVDUyh4dMVkt1SThoSamMk=",
      "dev": true,
      "requires": {
        "jsbn": "~0.1.0",
        "safer-buffer": "^2.1.0"
      }
    },
    "ee-first": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/ee-first/-/ee-first-1.1.1.tgz",
      "integrity": "sha1-WQxhFWsK4vTwJVcyoViyZrxWsh0=",
      "dev": true
    },
    "electron-to-chromium": {
      "version": "1.3.108",
      "resolved": "https://registry.npmjs.org/electron-to-chromium/-/electron-to-chromium-1.3.108.tgz",
      "integrity": "sha512-/QI4hMpAh48a1Sea6PALGv+kuVne9A2EWGd8HrWHMdYhIzGtbhVVHh6heL5fAzGaDnZuPyrlWJRl8WPm4RyiQQ==",
      "dev": true
    },
    "elliptic": {
      "version": "6.4.1",
      "resolved": "https://registry.npmjs.org/elliptic/-/elliptic-6.4.1.tgz",
      "integrity": "sha512-BsXLz5sqX8OHcsh7CqBMztyXARmGQ3LWPtGjJi6DiJHq5C/qvi9P3OqgswKSDftbu8+IoI/QDTAm2fFnQ9SZSQ==",
      "dev": true,
      "requires": {
        "bn.js": "^4.4.0",
        "brorand": "^1.0.1",
        "hash.js": "^1.0.0",
        "hmac-drbg": "^1.0.0",
        "inherits": "^2.0.1",
        "minimalistic-assert": "^1.0.0",
        "minimalistic-crypto-utils": "^1.0.0"
      }
    },
    "emojis-list": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/emojis-list/-/emojis-list-2.1.0.tgz",
      "integrity": "sha1-TapNnbAPmBmIDHn6RXrlsJof04k=",
      "dev": true
    },
    "encodeurl": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/encodeurl/-/encodeurl-1.0.2.tgz",
      "integrity": "sha1-rT/0yG7C0CkyL1oCw6mmBslbP1k=",
      "dev": true
    },
    "encoding": {
      "version": "0.1.12",
      "resolved": "https://registry.npmjs.org/encoding/-/encoding-0.1.12.tgz",
      "integrity": "sha1-U4tm8+5izRq1HsMjgp0flIDHS+s=",
      "dev": true,
      "requires": {
        "iconv-lite": "~0.4.13"
      }
    },
    "end-of-stream": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/end-of-stream/-/end-of-stream-1.4.1.tgz",
      "integrity": "sha512-1MkrZNvWTKCaigbn+W15elq2BB/L22nqrSY5DKlo3X6+vclJm8Bb5djXJBmEX6fS3+zCh/F4VBK5Z2KxJt4s2Q==",
      "dev": true,
      "requires": {
        "once": "^1.4.0"
      }
    },
    "engine.io": {
      "version": "3.2.1",
      "resolved": "https://registry.npmjs.org/engine.io/-/engine.io-3.2.1.tgz",
      "integrity": "sha512-+VlKzHzMhaU+GsCIg4AoXF1UdDFjHHwMmMKqMJNDNLlUlejz58FCy4LBqB2YVJskHGYl06BatYWKP2TVdVXE5w==",
      "dev": true,
      "requires": {
        "accepts": "~1.3.4",
        "base64id": "1.0.0",
        "cookie": "0.3.1",
        "debug": "~3.1.0",
        "engine.io-parser": "~2.1.0",
        "ws": "~3.3.1"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        }
      }
    },
    "engine.io-client": {
      "version": "3.2.1",
      "resolved": "https://registry.npmjs.org/engine.io-client/-/engine.io-client-3.2.1.tgz",
      "integrity": "sha512-y5AbkytWeM4jQr7m/koQLc5AxpRKC1hEVUb/s1FUAWEJq5AzJJ4NLvzuKPuxtDi5Mq755WuDvZ6Iv2rXj4PTzw==",
      "dev": true,
      "requires": {
        "component-emitter": "1.2.1",
        "component-inherit": "0.0.3",
        "debug": "~3.1.0",
        "engine.io-parser": "~2.1.1",
        "has-cors": "1.1.0",
        "indexof": "0.0.1",
        "parseqs": "0.0.5",
        "parseuri": "0.0.5",
        "ws": "~3.3.1",
        "xmlhttprequest-ssl": "~1.5.4",
        "yeast": "0.1.2"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        }
      }
    },
    "engine.io-parser": {
      "version": "2.1.3",
      "resolved": "https://registry.npmjs.org/engine.io-parser/-/engine.io-parser-2.1.3.tgz",
      "integrity": "sha512-6HXPre2O4Houl7c4g7Ic/XzPnHBvaEmN90vtRO9uLmwtRqQmTOw0QMevL1TOfL2Cpu1VzsaTmMotQgMdkzGkVA==",
      "dev": true,
      "requires": {
        "after": "0.8.2",
        "arraybuffer.slice": "~0.0.7",
        "base64-arraybuffer": "0.1.5",
        "blob": "0.0.5",
        "has-binary2": "~1.0.2"
      }
    },
    "enhanced-resolve": {
      "version": "4.1.0",
      "resolved": "https://registry.npmjs.org/enhanced-resolve/-/enhanced-resolve-4.1.0.tgz",
      "integrity": "sha512-F/7vkyTtyc/llOIn8oWclcB25KdRaiPBpZYDgJHgh/UHtpgT2p2eldQgtQnLtUvfMKPKxbRaQM/hHkvLHt1Vng==",
      "dev": true,
      "requires": {
        "graceful-fs": "^4.1.2",
        "memory-fs": "^0.4.0",
        "tapable": "^1.0.0"
      }
    },
    "ent": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/ent/-/ent-2.2.0.tgz",
      "integrity": "sha1-6WQhkyWiHQX0RGai9obtbOX13R0=",
      "dev": true
    },
    "err-code": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/err-code/-/err-code-1.1.2.tgz",
      "integrity": "sha1-BuARbTAo9q70gGhJ6w6mp0iuaWA=",
      "dev": true
    },
    "errno": {
      "version": "0.1.7",
      "resolved": "https://registry.npmjs.org/errno/-/errno-0.1.7.tgz",
      "integrity": "sha512-MfrRBDWzIWifgq6tJj60gkAwtLNb6sQPlcFrSOflcP1aFmmruKQ2wRnze/8V6kgyz7H3FF8Npzv78mZ7XLLflg==",
      "dev": true,
      "requires": {
        "prr": "~1.0.1"
      }
    },
    "error-ex": {
      "version": "1.3.2",
      "resolved": "https://registry.npmjs.org/error-ex/-/error-ex-1.3.2.tgz",
      "integrity": "sha512-7dFHNmqeFSEt2ZBsCriorKnn3Z2pj+fd9kmI6QoWw4//DL+icEBfc0U7qJCisqrTsKTjw4fNFy2pW9OqStD84g==",
      "dev": true,
      "requires": {
        "is-arrayish": "^0.2.1"
      }
    },
    "es6-promise": {
      "version": "4.2.5",
      "resolved": "https://registry.npmjs.org/es6-promise/-/es6-promise-4.2.5.tgz",
      "integrity": "sha512-n6wvpdE43VFtJq+lUDYDBFUwV8TZbuGXLV4D6wKafg13ldznKsyEvatubnmUe31zcvelSzOHF+XbaT+Bl9ObDg==",
      "dev": true
    },
    "es6-promisify": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/es6-promisify/-/es6-promisify-5.0.0.tgz",
      "integrity": "sha1-UQnWLz5W6pZ8S2NQWu8IKRyKUgM=",
      "dev": true,
      "requires": {
        "es6-promise": "^4.0.3"
      }
    },
    "escape-html": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/escape-html/-/escape-html-1.0.3.tgz",
      "integrity": "sha1-Aljq5NPQwJdN4cFpGI7wBR0dGYg=",
      "dev": true
    },
    "escape-string-regexp": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/escape-string-regexp/-/escape-string-regexp-1.0.5.tgz",
      "integrity": "sha1-G2HAViGQqN/2rjuyzwIAyhMLhtQ=",
      "dev": true
    },
    "escodegen": {
      "version": "1.8.1",
      "resolved": "https://registry.npmjs.org/escodegen/-/escodegen-1.8.1.tgz",
      "integrity": "sha1-WltTr0aTEQvrsIZ6o0MN07cKEBg=",
      "dev": true,
      "requires": {
        "esprima": "^2.7.1",
        "estraverse": "^1.9.1",
        "esutils": "^2.0.2",
        "optionator": "^0.8.1",
        "source-map": "~0.2.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.2.0",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.2.0.tgz",
          "integrity": "sha1-2rc/vPwrqBm03gO9b26qSBZLP50=",
          "dev": true,
          "optional": true,
          "requires": {
            "amdefine": ">=0.0.4"
          }
        }
      }
    },
    "eslint-scope": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/eslint-scope/-/eslint-scope-4.0.0.tgz",
      "integrity": "sha512-1G6UTDi7Jc1ELFwnR58HV4fK9OQK4S6N985f166xqXxpjU6plxFISJa2Ba9KCQuFa8RCnj/lSFJbHo7UFDBnUA==",
      "dev": true,
      "requires": {
        "esrecurse": "^4.1.0",
        "estraverse": "^4.1.1"
      },
      "dependencies": {
        "estraverse": {
          "version": "4.2.0",
          "resolved": "https://registry.npmjs.org/estraverse/-/estraverse-4.2.0.tgz",
          "integrity": "sha1-De4/7TH81GlhjOc0IJn8GvoL2xM=",
          "dev": true
        }
      }
    },
    "esprima": {
      "version": "2.7.3",
      "resolved": "https://registry.npmjs.org/esprima/-/esprima-2.7.3.tgz",
      "integrity": "sha1-luO3DVd59q1JzQMmc9HDEnZ7pYE=",
      "dev": true
    },
    "esrecurse": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/esrecurse/-/esrecurse-4.2.1.tgz",
      "integrity": "sha512-64RBB++fIOAXPw3P9cy89qfMlvZEXZkqqJkjqqXIvzP5ezRZjW+lPWjw35UX/3EhUPFYbg5ER4JYgDw4007/DQ==",
      "dev": true,
      "requires": {
        "estraverse": "^4.1.0"
      },
      "dependencies": {
        "estraverse": {
          "version": "4.2.0",
          "resolved": "https://registry.npmjs.org/estraverse/-/estraverse-4.2.0.tgz",
          "integrity": "sha1-De4/7TH81GlhjOc0IJn8GvoL2xM=",
          "dev": true
        }
      }
    },
    "estraverse": {
      "version": "1.9.3",
      "resolved": "https://registry.npmjs.org/estraverse/-/estraverse-1.9.3.tgz",
      "integrity": "sha1-r2fy3JIlgkFZUJJgkaQAXSnJu0Q=",
      "dev": true
    },
    "esutils": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/esutils/-/esutils-2.0.2.tgz",
      "integrity": "sha1-Cr9PHKpbyx96nYrMbepPqqBLrJs=",
      "dev": true
    },
    "etag": {
      "version": "1.8.1",
      "resolved": "https://registry.npmjs.org/etag/-/etag-1.8.1.tgz",
      "integrity": "sha1-Qa4u62XvpiJorr/qg6x9eSmbCIc=",
      "dev": true
    },
    "eventemitter3": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/eventemitter3/-/eventemitter3-3.1.0.tgz",
      "integrity": "sha512-ivIvhpq/Y0uSjcHDcOIccjmYjGLcP09MFGE7ysAwkAvkXfpZlC985pH2/ui64DKazbTW/4kN3yqozUxlXzI6cA==",
      "dev": true
    },
    "events": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/events/-/events-3.0.0.tgz",
      "integrity": "sha512-Dc381HFWJzEOhQ+d8pkNon++bk9h6cdAoAj4iE6Q4y6xgTzySWXlKn05/TVNpjnfRqi/X0EpJEJohPjNI3zpVA==",
      "dev": true
    },
    "eventsource": {
      "version": "1.0.7",
      "resolved": "https://registry.npmjs.org/eventsource/-/eventsource-1.0.7.tgz",
      "integrity": "sha512-4Ln17+vVT0k8aWq+t/bF5arcS3EpT9gYtW66EPacdj/mAFevznsnyoHLPy2BA8gbIQeIHoPsvwmfBftfcG//BQ==",
      "dev": true,
      "requires": {
        "original": "^1.0.0"
      }
    },
    "evp_bytestokey": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/evp_bytestokey/-/evp_bytestokey-1.0.3.tgz",
      "integrity": "sha512-/f2Go4TognH/KvCISP7OUsHn85hT9nUkxxA9BEWxFn+Oj9o8ZNLm/40hdlgSLyuOimsrTKLUMEorQexp/aPQeA==",
      "dev": true,
      "requires": {
        "md5.js": "^1.3.4",
        "safe-buffer": "^5.1.1"
      }
    },
    "execa": {
      "version": "0.10.0",
      "resolved": "https://registry.npmjs.org/execa/-/execa-0.10.0.tgz",
      "integrity": "sha512-7XOMnz8Ynx1gGo/3hyV9loYNPWM94jG3+3T3Y8tsfSstFmETmENCMU/A/zj8Lyaj1lkgEepKepvd6240tBRvlw==",
      "dev": true,
      "requires": {
        "cross-spawn": "^6.0.0",
        "get-stream": "^3.0.0",
        "is-stream": "^1.1.0",
        "npm-run-path": "^2.0.0",
        "p-finally": "^1.0.0",
        "signal-exit": "^3.0.0",
        "strip-eof": "^1.0.0"
      },
      "dependencies": {
        "cross-spawn": {
          "version": "6.0.5",
          "resolved": "https://registry.npmjs.org/cross-spawn/-/cross-spawn-6.0.5.tgz",
          "integrity": "sha512-eTVLrBSt7fjbDygz805pMnstIs2VTBNkRm0qxZd+M7A5XDdxVRWO5MxGBXZhjY4cqLYLdtrGqRf8mBPmzwSpWQ==",
          "dev": true,
          "requires": {
            "nice-try": "^1.0.4",
            "path-key": "^2.0.1",
            "semver": "^5.5.0",
            "shebang-command": "^1.2.0",
            "which": "^1.2.9"
          }
        }
      }
    },
    "exit": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/exit/-/exit-0.1.2.tgz",
      "integrity": "sha1-BjJjj42HfMghB9MKD/8aF8uhzQw=",
      "dev": true
    },
    "expand-braces": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/expand-braces/-/expand-braces-0.1.2.tgz",
      "integrity": "sha1-SIsdHSRRyz06axks/AMPRMWFX+o=",
      "dev": true,
      "requires": {
        "array-slice": "^0.2.3",
        "array-unique": "^0.2.1",
        "braces": "^0.1.2"
      },
      "dependencies": {
        "array-unique": {
          "version": "0.2.1",
          "resolved": "https://registry.npmjs.org/array-unique/-/array-unique-0.2.1.tgz",
          "integrity": "sha1-odl8yvy8JiXMcPrc6zalDFiwGlM=",
          "dev": true
        },
        "braces": {
          "version": "0.1.5",
          "resolved": "https://registry.npmjs.org/braces/-/braces-0.1.5.tgz",
          "integrity": "sha1-wIVxEIUpHYt1/ddOqw+FlygHEeY=",
          "dev": true,
          "requires": {
            "expand-range": "^0.1.0"
          }
        },
        "expand-range": {
          "version": "0.1.1",
          "resolved": "https://registry.npmjs.org/expand-range/-/expand-range-0.1.1.tgz",
          "integrity": "sha1-TLjtoJk8pW+k9B/ELzy7TMrf8EQ=",
          "dev": true,
          "requires": {
            "is-number": "^0.1.1",
            "repeat-string": "^0.2.2"
          }
        },
        "is-number": {
          "version": "0.1.1",
          "resolved": "https://registry.npmjs.org/is-number/-/is-number-0.1.1.tgz",
          "integrity": "sha1-aaevEWlj1HIG7JvZtIoUIW8eOAY=",
          "dev": true
        },
        "repeat-string": {
          "version": "0.2.2",
          "resolved": "https://registry.npmjs.org/repeat-string/-/repeat-string-0.2.2.tgz",
          "integrity": "sha1-x6jTI2BoNiBZp+RlH8aITosftK4=",
          "dev": true
        }
      }
    },
    "expand-brackets": {
      "version": "2.1.4",
      "resolved": "https://registry.npmjs.org/expand-brackets/-/expand-brackets-2.1.4.tgz",
      "integrity": "sha1-t3c14xXOMPa27/D4OwQVGiJEliI=",
      "dev": true,
      "requires": {
        "debug": "^2.3.3",
        "define-property": "^0.2.5",
        "extend-shallow": "^2.0.1",
        "posix-character-classes": "^0.1.0",
        "regex-not": "^1.0.0",
        "snapdragon": "^0.8.1",
        "to-regex": "^3.0.1"
      },
      "dependencies": {
        "define-property": {
          "version": "0.2.5",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-0.2.5.tgz",
          "integrity": "sha1-w1se+RjsPJkPmlvFe+BKrOxcgRY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^0.1.0"
          }
        },
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        }
      }
    },
    "expand-range": {
      "version": "1.8.2",
      "resolved": "https://registry.npmjs.org/expand-range/-/expand-range-1.8.2.tgz",
      "integrity": "sha1-opnv/TNf4nIeuujiV+x5ZE/IUzc=",
      "dev": true,
      "requires": {
        "fill-range": "^2.1.0"
      },
      "dependencies": {
        "fill-range": {
          "version": "2.2.4",
          "resolved": "https://registry.npmjs.org/fill-range/-/fill-range-2.2.4.tgz",
          "integrity": "sha512-cnrcCbj01+j2gTG921VZPnHbjmdAf8oQV/iGeV2kZxGSyfYjjTyY79ErsK1WJWMpw6DaApEX72binqJE+/d+5Q==",
          "dev": true,
          "requires": {
            "is-number": "^2.1.0",
            "isobject": "^2.0.0",
            "randomatic": "^3.0.0",
            "repeat-element": "^1.1.2",
            "repeat-string": "^1.5.2"
          }
        },
        "is-number": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/is-number/-/is-number-2.1.0.tgz",
          "integrity": "sha1-Afy7s5NGOlSPL0ZszhbezknbkI8=",
          "dev": true,
          "requires": {
            "kind-of": "^3.0.2"
          }
        },
        "isobject": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/isobject/-/isobject-2.1.0.tgz",
          "integrity": "sha1-8GVWEJaj8dou9GJy+BXIQNh+DIk=",
          "dev": true,
          "requires": {
            "isarray": "1.0.0"
          }
        },
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "express": {
      "version": "4.16.4",
      "resolved": "https://registry.npmjs.org/express/-/express-4.16.4.tgz",
      "integrity": "sha512-j12Uuyb4FMrd/qQAm6uCHAkPtO8FDTRJZBDd5D2KOL2eLaz1yUNdUB/NOIyq0iU4q4cFarsUCrnFDPBcnksuOg==",
      "dev": true,
      "requires": {
        "accepts": "~1.3.5",
        "array-flatten": "1.1.1",
        "body-parser": "1.18.3",
        "content-disposition": "0.5.2",
        "content-type": "~1.0.4",
        "cookie": "0.3.1",
        "cookie-signature": "1.0.6",
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "etag": "~1.8.1",
        "finalhandler": "1.1.1",
        "fresh": "0.5.2",
        "merge-descriptors": "1.0.1",
        "methods": "~1.1.2",
        "on-finished": "~2.3.0",
        "parseurl": "~1.3.2",
        "path-to-regexp": "0.1.7",
        "proxy-addr": "~2.0.4",
        "qs": "6.5.2",
        "range-parser": "~1.2.0",
        "safe-buffer": "5.1.2",
        "send": "0.16.2",
        "serve-static": "1.13.2",
        "setprototypeof": "1.1.0",
        "statuses": "~1.4.0",
        "type-is": "~1.6.16",
        "utils-merge": "1.0.1",
        "vary": "~1.1.2"
      },
      "dependencies": {
        "array-flatten": {
          "version": "1.1.1",
          "resolved": "https://registry.npmjs.org/array-flatten/-/array-flatten-1.1.1.tgz",
          "integrity": "sha1-ml9pkFGx5wczKPKgCJaLZOopVdI=",
          "dev": true
        }
      }
    },
    "extend": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/extend/-/extend-3.0.2.tgz",
      "integrity": "sha512-fjquC59cD7CyW6urNXK0FBufkZcoiGG80wTuPujX590cB5Ttln20E2UB4S/WARVqhXffZl2LNgS+gQdPIIim/g==",
      "dev": true
    },
    "extend-shallow": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-3.0.2.tgz",
      "integrity": "sha1-Jqcarwc7OfshJxcnRhMcJwQCjbg=",
      "dev": true,
      "requires": {
        "assign-symbols": "^1.0.0",
        "is-extendable": "^1.0.1"
      },
      "dependencies": {
        "is-extendable": {
          "version": "1.0.1",
          "resolved": "https://registry.npmjs.org/is-extendable/-/is-extendable-1.0.1.tgz",
          "integrity": "sha512-arnXMxT1hhoKo9k1LZdmlNyJdDDfy2v0fXjFlmok4+i8ul/6WlbVge9bhM74OpNPQPMGUToDtz+KXa1PneJxOA==",
          "dev": true,
          "requires": {
            "is-plain-object": "^2.0.4"
          }
        }
      }
    },
    "external-editor": {
      "version": "3.0.3",
      "resolved": "https://registry.npmjs.org/external-editor/-/external-editor-3.0.3.tgz",
      "integrity": "sha512-bn71H9+qWoOQKyZDo25mOMVpSmXROAsTJVVVYzrrtol3d4y+AsKjf4Iwl2Q+IuT0kFSQ1qo166UuIwqYq7mGnA==",
      "dev": true,
      "requires": {
        "chardet": "^0.7.0",
        "iconv-lite": "^0.4.24",
        "tmp": "^0.0.33"
      },
      "dependencies": {
        "iconv-lite": {
          "version": "0.4.24",
          "resolved": "https://registry.npmjs.org/iconv-lite/-/iconv-lite-0.4.24.tgz",
          "integrity": "sha512-v3MXnZAcvnywkTUEZomIActle7RXXeedOR31wwl7VlyoXO4Qi9arvSenNQWne1TcRwhCL1HwLI21bEqdpj8/rA==",
          "dev": true,
          "requires": {
            "safer-buffer": ">= 2.1.2 < 3"
          }
        }
      }
    },
    "extglob": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/extglob/-/extglob-2.0.4.tgz",
      "integrity": "sha512-Nmb6QXkELsuBr24CJSkilo6UHHgbekK5UiZgfE6UHD3Eb27YC6oD+bhcT+tJ6cl8dmsgdQxnWlcry8ksBIBLpw==",
      "dev": true,
      "requires": {
        "array-unique": "^0.3.2",
        "define-property": "^1.0.0",
        "expand-brackets": "^2.1.4",
        "extend-shallow": "^2.0.1",
        "fragment-cache": "^0.2.1",
        "regex-not": "^1.0.0",
        "snapdragon": "^0.8.1",
        "to-regex": "^3.0.1"
      },
      "dependencies": {
        "define-property": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-1.0.0.tgz",
          "integrity": "sha1-dp66rz9KY6rTr56NMEybvnm/sOY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^1.0.0"
          }
        },
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        },
        "is-accessor-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-accessor-descriptor/-/is-accessor-descriptor-1.0.0.tgz",
          "integrity": "sha512-m5hnHTkcVsPfqx3AKlyttIPb7J+XykHvJP2B9bZDjlhLIoEq4XoK64Vg7boZlVWYK6LUY94dYPEE7Lh0ZkZKcQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-data-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-data-descriptor/-/is-data-descriptor-1.0.0.tgz",
          "integrity": "sha512-jbRXy1FmtAoCjQkVmIVYwuuqDFUbaOeDjmed1tOGPrsMhtJA4rD9tkgA0F1qJ3gRFRXcHYVkdeaP50Q5rE/jLQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-descriptor": {
          "version": "1.0.2",
          "resolved": "https://registry.npmjs.org/is-descriptor/-/is-descriptor-1.0.2.tgz",
          "integrity": "sha512-2eis5WqQGV7peooDyLmNEPUrps9+SXX5c9pL3xEB+4e9HnGuDa7mB7kHxHw4CbqS9k1T2hOH3miL8n8WtiYVtg==",
          "dev": true,
          "requires": {
            "is-accessor-descriptor": "^1.0.0",
            "is-data-descriptor": "^1.0.0",
            "kind-of": "^6.0.2"
          }
        }
      }
    },
    "extsprintf": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/extsprintf/-/extsprintf-1.3.0.tgz",
      "integrity": "sha1-lpGEQOMEGnpBT4xS48V06zw+HgU=",
      "dev": true
    },
    "fast-deep-equal": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/fast-deep-equal/-/fast-deep-equal-2.0.1.tgz",
      "integrity": "sha1-ewUhjd+WZ79/Nwv3/bLLFf3Qqkk=",
      "dev": true
    },
    "fast-json-stable-stringify": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/fast-json-stable-stringify/-/fast-json-stable-stringify-2.0.0.tgz",
      "integrity": "sha1-1RQsDK7msRifh9OnYREGT4bIu/I=",
      "dev": true
    },
    "fast-levenshtein": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/fast-levenshtein/-/fast-levenshtein-2.0.6.tgz",
      "integrity": "sha1-PYpcZog6FqMMqGQ+hR8Zuqd5eRc=",
      "dev": true
    },
    "fastparse": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/fastparse/-/fastparse-1.1.2.tgz",
      "integrity": "sha512-483XLLxTVIwWK3QTrMGRqUfUpoOs/0hbQrl2oz4J0pAcm3A3bu84wxTFqGqkJzewCLdME38xJLJAxBABfQT8sQ==",
      "dev": true
    },
    "faye-websocket": {
      "version": "0.10.0",
      "resolved": "https://registry.npmjs.org/faye-websocket/-/faye-websocket-0.10.0.tgz",
      "integrity": "sha1-TkkvjQTftviQA1B/btvy1QHnxvQ=",
      "dev": true,
      "requires": {
        "websocket-driver": ">=0.5.1"
      }
    },
    "figgy-pudding": {
      "version": "3.5.1",
      "resolved": "https://registry.npmjs.org/figgy-pudding/-/figgy-pudding-3.5.1.tgz",
      "integrity": "sha512-vNKxJHTEKNThjfrdJwHc7brvM6eVevuO5nTj6ez8ZQ1qbXTvGthucRF7S4vf2cr71QVnT70V34v0S1DyQsti0w==",
      "dev": true
    },
    "figures": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/figures/-/figures-2.0.0.tgz",
      "integrity": "sha1-OrGi0qYsi/tDGgyUy3l6L84nyWI=",
      "dev": true,
      "requires": {
        "escape-string-regexp": "^1.0.5"
      }
    },
    "file-loader": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/file-loader/-/file-loader-2.0.0.tgz",
      "integrity": "sha512-YCsBfd1ZGCyonOKLxPiKPdu+8ld9HAaMEvJewzz+b2eTF7uL5Zm/HdBF6FjCrpCMRq25Mi0U1gl4pwn2TlH7hQ==",
      "dev": true,
      "requires": {
        "loader-utils": "^1.0.2",
        "schema-utils": "^1.0.0"
      }
    },
    "filename-regex": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/filename-regex/-/filename-regex-2.0.1.tgz",
      "integrity": "sha1-wcS5vuPglyXdsQa3XB4wH+LxiyY=",
      "dev": true
    },
    "fileset": {
      "version": "2.0.3",
      "resolved": "https://registry.npmjs.org/fileset/-/fileset-2.0.3.tgz",
      "integrity": "sha1-jnVIqW08wjJ+5eZ0FocjozO7oqA=",
      "dev": true,
      "requires": {
        "glob": "^7.0.3",
        "minimatch": "^3.0.3"
      }
    },
    "fill-range": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/fill-range/-/fill-range-4.0.0.tgz",
      "integrity": "sha1-1USBHUKPmOsGpj3EAtJAPDKMOPc=",
      "dev": true,
      "requires": {
        "extend-shallow": "^2.0.1",
        "is-number": "^3.0.0",
        "repeat-string": "^1.6.1",
        "to-regex-range": "^2.1.0"
      },
      "dependencies": {
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        }
      }
    },
    "finalhandler": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/finalhandler/-/finalhandler-1.1.1.tgz",
      "integrity": "sha512-Y1GUDo39ez4aHAw7MysnUD5JzYX+WaIj8I57kO3aEPT1fFRL4sr7mjei97FgnwhAyyzRYmQZaTHb2+9uZ1dPtg==",
      "dev": true,
      "requires": {
        "debug": "2.6.9",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "on-finished": "~2.3.0",
        "parseurl": "~1.3.2",
        "statuses": "~1.4.0",
        "unpipe": "~1.0.0"
      }
    },
    "find-cache-dir": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/find-cache-dir/-/find-cache-dir-1.0.0.tgz",
      "integrity": "sha1-kojj6ePMN0hxfTnq3hfPcfww7m8=",
      "dev": true,
      "requires": {
        "commondir": "^1.0.1",
        "make-dir": "^1.0.0",
        "pkg-dir": "^2.0.0"
      }
    },
    "find-up": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/find-up/-/find-up-2.1.0.tgz",
      "integrity": "sha1-RdG35QbHF93UgndaK3eSCjwMV6c=",
      "dev": true,
      "requires": {
        "locate-path": "^2.0.0"
      }
    },
    "flatted": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/flatted/-/flatted-2.0.0.tgz",
      "integrity": "sha512-R+H8IZclI8AAkSBRQJLVOsxwAoHd6WC40b4QTNWIjzAa6BXOBfQcM587MXDTVPeYaopFNWHUFLx7eNmHDSxMWg==",
      "dev": true
    },
    "flush-write-stream": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/flush-write-stream/-/flush-write-stream-1.0.3.tgz",
      "integrity": "sha512-calZMC10u0FMUqoiunI2AiGIIUtUIvifNwkHhNupZH4cbNnW1Itkoh/Nf5HFYmDrwWPjrUxpkZT0KhuCq0jmGw==",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "readable-stream": "^2.0.4"
      }
    },
    "follow-redirects": {
      "version": "1.6.1",
      "resolved": "https://registry.npmjs.org/follow-redirects/-/follow-redirects-1.6.1.tgz",
      "integrity": "sha512-t2JCjbzxQpWvbhts3l6SH1DKzSrx8a+SsaVf4h6bG4kOXUuPYS/kg2Lr4gQSb7eemaHqJkOThF1BGyjlUkO1GQ==",
      "dev": true,
      "requires": {
        "debug": "=3.1.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        }
      }
    },
    "for-in": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/for-in/-/for-in-1.0.2.tgz",
      "integrity": "sha1-gQaNKVqBQuwKxybG4iAMMPttXoA=",
      "dev": true
    },
    "for-own": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/for-own/-/for-own-1.0.0.tgz",
      "integrity": "sha1-xjMy9BXO3EsE2/5wz4NklMU8tEs=",
      "dev": true,
      "requires": {
        "for-in": "^1.0.1"
      }
    },
    "forever-agent": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/forever-agent/-/forever-agent-0.6.1.tgz",
      "integrity": "sha1-+8cfDEGt6zf5bFd60e1C2P2sypE=",
      "dev": true
    },
    "form-data": {
      "version": "2.3.3",
      "resolved": "https://registry.npmjs.org/form-data/-/form-data-2.3.3.tgz",
      "integrity": "sha512-1lLKB2Mu3aGP1Q/2eCOx0fNbRMe7XdwktwOruhfqqd0rIJWwN4Dh+E3hrPSlDCXnSR7UtZ1N38rVXm+6+MEhJQ==",
      "dev": true,
      "requires": {
        "asynckit": "^0.4.0",
        "combined-stream": "^1.0.6",
        "mime-types": "^2.1.12"
      }
    },
    "forwarded": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/forwarded/-/forwarded-0.1.2.tgz",
      "integrity": "sha1-mMI9qxF1ZXuMBXPozszZGw/xjIQ=",
      "dev": true
    },
    "fragment-cache": {
      "version": "0.2.1",
      "resolved": "https://registry.npmjs.org/fragment-cache/-/fragment-cache-0.2.1.tgz",
      "integrity": "sha1-QpD60n8T6Jvn8zeZxrxaCr//DRk=",
      "dev": true,
      "requires": {
        "map-cache": "^0.2.2"
      }
    },
    "fresh": {
      "version": "0.5.2",
      "resolved": "https://registry.npmjs.org/fresh/-/fresh-0.5.2.tgz",
      "integrity": "sha1-PYyt2Q2XZWn6g1qx+OSyOhBWBac=",
      "dev": true
    },
    "from2": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/from2/-/from2-2.3.0.tgz",
      "integrity": "sha1-i/tVAr3kpNNs/e6gB/zKIdfjgq8=",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "readable-stream": "^2.0.0"
      }
    },
    "fs-access": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/fs-access/-/fs-access-1.0.1.tgz",
      "integrity": "sha1-1qh/JiJxzv6+wwxVNAf7mV2od3o=",
      "dev": true,
      "requires": {
        "null-check": "^1.0.0"
      }
    },
    "fs-minipass": {
      "version": "1.2.5",
      "resolved": "https://registry.npmjs.org/fs-minipass/-/fs-minipass-1.2.5.tgz",
      "integrity": "sha512-JhBl0skXjUPCFH7x6x61gQxrKyXsxB5gcgePLZCwfyCGGsTISMoIeObbrvVeP6Xmyaudw4TT43qV2Gz+iyd2oQ==",
      "dev": true,
      "requires": {
        "minipass": "^2.2.1"
      }
    },
    "fs-write-stream-atomic": {
      "version": "1.0.10",
      "resolved": "https://registry.npmjs.org/fs-write-stream-atomic/-/fs-write-stream-atomic-1.0.10.tgz",
      "integrity": "sha1-tH31NJPvkR33VzHnCp3tAYnbQMk=",
      "dev": true,
      "requires": {
        "graceful-fs": "^4.1.2",
        "iferr": "^0.1.5",
        "imurmurhash": "^0.1.4",
        "readable-stream": "1 || 2"
      }
    },
    "fs.realpath": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/fs.realpath/-/fs.realpath-1.0.0.tgz",
      "integrity": "sha1-FQStJSMVjKpA20onh8sBQRmU6k8=",
      "dev": true
    },
    "fsevents": {
      "version": "1.2.7",
      "resolved": "https://registry.npmjs.org/fsevents/-/fsevents-1.2.7.tgz",
      "integrity": "sha512-Pxm6sI2MeBD7RdD12RYsqaP0nMiwx8eZBXCa6z2L+mRHm2DYrOYwihmhjpkdjUHwQhslWQjRpEgNq4XvBmaAuw==",
      "dev": true,
      "optional": true,
      "requires": {
        "nan": "^2.9.2",
        "node-pre-gyp": "^0.10.0"
      },
      "dependencies": {
        "abbrev": {
          "version": "1.1.1",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "ansi-regex": {
          "version": "2.1.1",
          "bundled": true,
          "dev": true
        },
        "aproba": {
          "version": "1.2.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "are-we-there-yet": {
          "version": "1.1.5",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "delegates": "^1.0.0",
            "readable-stream": "^2.0.6"
          }
        },
        "balanced-match": {
          "version": "1.0.0",
          "bundled": true,
          "dev": true
        },
        "brace-expansion": {
          "version": "1.1.11",
          "bundled": true,
          "dev": true,
          "requires": {
            "balanced-match": "^1.0.0",
            "concat-map": "0.0.1"
          }
        },
        "chownr": {
          "version": "1.1.1",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "code-point-at": {
          "version": "1.1.0",
          "bundled": true,
          "dev": true
        },
        "concat-map": {
          "version": "0.0.1",
          "bundled": true,
          "dev": true
        },
        "console-control-strings": {
          "version": "1.1.0",
          "bundled": true,
          "dev": true
        },
        "core-util-is": {
          "version": "1.0.2",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "debug": {
          "version": "2.6.9",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "ms": "2.0.0"
          }
        },
        "deep-extend": {
          "version": "0.6.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "delegates": {
          "version": "1.0.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "detect-libc": {
          "version": "1.0.3",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "fs-minipass": {
          "version": "1.2.5",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "minipass": "^2.2.1"
          }
        },
        "fs.realpath": {
          "version": "1.0.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "gauge": {
          "version": "2.7.4",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "aproba": "^1.0.3",
            "console-control-strings": "^1.0.0",
            "has-unicode": "^2.0.0",
            "object-assign": "^4.1.0",
            "signal-exit": "^3.0.0",
            "string-width": "^1.0.1",
            "strip-ansi": "^3.0.1",
            "wide-align": "^1.1.0"
          }
        },
        "glob": {
          "version": "7.1.3",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "fs.realpath": "^1.0.0",
            "inflight": "^1.0.4",
            "inherits": "2",
            "minimatch": "^3.0.4",
            "once": "^1.3.0",
            "path-is-absolute": "^1.0.0"
          }
        },
        "has-unicode": {
          "version": "2.0.1",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "iconv-lite": {
          "version": "0.4.24",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "safer-buffer": ">= 2.1.2 < 3"
          }
        },
        "ignore-walk": {
          "version": "3.0.1",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "minimatch": "^3.0.4"
          }
        },
        "inflight": {
          "version": "1.0.6",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "once": "^1.3.0",
            "wrappy": "1"
          }
        },
        "inherits": {
          "version": "2.0.3",
          "bundled": true,
          "dev": true
        },
        "ini": {
          "version": "1.3.5",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "is-fullwidth-code-point": {
          "version": "1.0.0",
          "bundled": true,
          "dev": true,
          "requires": {
            "number-is-nan": "^1.0.0"
          }
        },
        "isarray": {
          "version": "1.0.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "minimatch": {
          "version": "3.0.4",
          "bundled": true,
          "dev": true,
          "requires": {
            "brace-expansion": "^1.1.7"
          }
        },
        "minimist": {
          "version": "0.0.8",
          "bundled": true,
          "dev": true
        },
        "minipass": {
          "version": "2.3.5",
          "bundled": true,
          "dev": true,
          "requires": {
            "safe-buffer": "^5.1.2",
            "yallist": "^3.0.0"
          }
        },
        "minizlib": {
          "version": "1.2.1",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "minipass": "^2.2.1"
          }
        },
        "mkdirp": {
          "version": "0.5.1",
          "bundled": true,
          "dev": true,
          "requires": {
            "minimist": "0.0.8"
          }
        },
        "ms": {
          "version": "2.0.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "needle": {
          "version": "2.2.4",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "debug": "^2.1.2",
            "iconv-lite": "^0.4.4",
            "sax": "^1.2.4"
          }
        },
        "node-pre-gyp": {
          "version": "0.10.3",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "detect-libc": "^1.0.2",
            "mkdirp": "^0.5.1",
            "needle": "^2.2.1",
            "nopt": "^4.0.1",
            "npm-packlist": "^1.1.6",
            "npmlog": "^4.0.2",
            "rc": "^1.2.7",
            "rimraf": "^2.6.1",
            "semver": "^5.3.0",
            "tar": "^4"
          }
        },
        "nopt": {
          "version": "4.0.1",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "abbrev": "1",
            "osenv": "^0.1.4"
          }
        },
        "npm-bundled": {
          "version": "1.0.5",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "npm-packlist": {
          "version": "1.2.0",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "ignore-walk": "^3.0.1",
            "npm-bundled": "^1.0.1"
          }
        },
        "npmlog": {
          "version": "4.1.2",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "are-we-there-yet": "~1.1.2",
            "console-control-strings": "~1.1.0",
            "gauge": "~2.7.3",
            "set-blocking": "~2.0.0"
          }
        },
        "number-is-nan": {
          "version": "1.0.1",
          "bundled": true,
          "dev": true
        },
        "object-assign": {
          "version": "4.1.1",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "once": {
          "version": "1.4.0",
          "bundled": true,
          "dev": true,
          "requires": {
            "wrappy": "1"
          }
        },
        "os-homedir": {
          "version": "1.0.2",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "os-tmpdir": {
          "version": "1.0.2",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "osenv": {
          "version": "0.1.5",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "os-homedir": "^1.0.0",
            "os-tmpdir": "^1.0.0"
          }
        },
        "path-is-absolute": {
          "version": "1.0.1",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "process-nextick-args": {
          "version": "2.0.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "rc": {
          "version": "1.2.8",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "deep-extend": "^0.6.0",
            "ini": "~1.3.0",
            "minimist": "^1.2.0",
            "strip-json-comments": "~2.0.1"
          },
          "dependencies": {
            "minimist": {
              "version": "1.2.0",
              "bundled": true,
              "dev": true,
              "optional": true
            }
          }
        },
        "readable-stream": {
          "version": "2.3.6",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "core-util-is": "~1.0.0",
            "inherits": "~2.0.3",
            "isarray": "~1.0.0",
            "process-nextick-args": "~2.0.0",
            "safe-buffer": "~5.1.1",
            "string_decoder": "~1.1.1",
            "util-deprecate": "~1.0.1"
          }
        },
        "rimraf": {
          "version": "2.6.3",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "glob": "^7.1.3"
          }
        },
        "safe-buffer": {
          "version": "5.1.2",
          "bundled": true,
          "dev": true
        },
        "safer-buffer": {
          "version": "2.1.2",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "sax": {
          "version": "1.2.4",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "semver": {
          "version": "5.6.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "set-blocking": {
          "version": "2.0.0",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "signal-exit": {
          "version": "3.0.2",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "string-width": {
          "version": "1.0.2",
          "bundled": true,
          "dev": true,
          "requires": {
            "code-point-at": "^1.0.0",
            "is-fullwidth-code-point": "^1.0.0",
            "strip-ansi": "^3.0.0"
          }
        },
        "string_decoder": {
          "version": "1.1.1",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "safe-buffer": "~5.1.0"
          }
        },
        "strip-ansi": {
          "version": "3.0.1",
          "bundled": true,
          "dev": true,
          "requires": {
            "ansi-regex": "^2.0.0"
          }
        },
        "strip-json-comments": {
          "version": "2.0.1",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "tar": {
          "version": "4.4.8",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "chownr": "^1.1.1",
            "fs-minipass": "^1.2.5",
            "minipass": "^2.3.4",
            "minizlib": "^1.1.1",
            "mkdirp": "^0.5.0",
            "safe-buffer": "^5.1.2",
            "yallist": "^3.0.2"
          }
        },
        "util-deprecate": {
          "version": "1.0.2",
          "bundled": true,
          "dev": true,
          "optional": true
        },
        "wide-align": {
          "version": "1.1.3",
          "bundled": true,
          "dev": true,
          "optional": true,
          "requires": {
            "string-width": "^1.0.2 || 2"
          }
        },
        "wrappy": {
          "version": "1.0.2",
          "bundled": true,
          "dev": true
        },
        "yallist": {
          "version": "3.0.3",
          "bundled": true,
          "dev": true
        }
      }
    },
    "fstream": {
      "version": "1.0.11",
      "resolved": "https://registry.npmjs.org/fstream/-/fstream-1.0.11.tgz",
      "integrity": "sha1-XB+x8RdHcRTwYyoOtLcbPLD9MXE=",
      "dev": true,
      "requires": {
        "graceful-fs": "^4.1.2",
        "inherits": "~2.0.0",
        "mkdirp": ">=0.5 0",
        "rimraf": "2"
      }
    },
    "gauge": {
      "version": "2.7.4",
      "resolved": "https://registry.npmjs.org/gauge/-/gauge-2.7.4.tgz",
      "integrity": "sha1-LANAXHU4w51+s3sxcCLjJfsBi/c=",
      "dev": true,
      "requires": {
        "aproba": "^1.0.3",
        "console-control-strings": "^1.0.0",
        "has-unicode": "^2.0.0",
        "object-assign": "^4.1.0",
        "signal-exit": "^3.0.0",
        "string-width": "^1.0.1",
        "strip-ansi": "^3.0.1",
        "wide-align": "^1.1.0"
      }
    },
    "gaze": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/gaze/-/gaze-1.1.3.tgz",
      "integrity": "sha512-BRdNm8hbWzFzWHERTrejLqwHDfS4GibPoq5wjTPIoJHoBtKGPg3xAFfxmM+9ztbXelxcf2hwQcaz1PtmFeue8g==",
      "dev": true,
      "optional": true,
      "requires": {
        "globule": "^1.0.0"
      }
    },
    "genfun": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/genfun/-/genfun-5.0.0.tgz",
      "integrity": "sha512-KGDOARWVga7+rnB3z9Sd2Letx515owfk0hSxHGuqjANb1M+x2bGZGqHLiozPsYMdM2OubeMni/Hpwmjq6qIUhA==",
      "dev": true
    },
    "get-caller-file": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/get-caller-file/-/get-caller-file-1.0.3.tgz",
      "integrity": "sha512-3t6rVToeoZfYSGd8YoLFR2DJkiQrIiUrGcjvFX2mDw3bn6k2OtwHN0TNCLbBO+w8qTvimhDkv+LSscbJY1vE6w==",
      "dev": true
    },
    "get-stdin": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/get-stdin/-/get-stdin-4.0.1.tgz",
      "integrity": "sha1-uWjGsKBDhDJJAui/Gl3zJXmkUP4=",
      "dev": true
    },
    "get-stream": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/get-stream/-/get-stream-3.0.0.tgz",
      "integrity": "sha1-jpQ9E1jcN1VQVOy+LtsFqhdO3hQ=",
      "dev": true
    },
    "get-value": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/get-value/-/get-value-2.0.6.tgz",
      "integrity": "sha1-3BXKHGcjh8p2vTesCjlbogQqLCg=",
      "dev": true
    },
    "getpass": {
      "version": "0.1.7",
      "resolved": "https://registry.npmjs.org/getpass/-/getpass-0.1.7.tgz",
      "integrity": "sha1-Xv+OPmhNVprkyysSgmBOi6YhSfo=",
      "dev": true,
      "requires": {
        "assert-plus": "^1.0.0"
      }
    },
    "glob": {
      "version": "7.1.3",
      "resolved": "https://registry.npmjs.org/glob/-/glob-7.1.3.tgz",
      "integrity": "sha512-vcfuiIxogLV4DlGBHIUOwI0IbrJ8HWPc4MU7HzviGeNho/UJDfi6B5p3sHeWIQ0KGIU0Jpxi5ZHxemQfLkkAwQ==",
      "dev": true,
      "requires": {
        "fs.realpath": "^1.0.0",
        "inflight": "^1.0.4",
        "inherits": "2",
        "minimatch": "^3.0.4",
        "once": "^1.3.0",
        "path-is-absolute": "^1.0.0"
      }
    },
    "glob-base": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/glob-base/-/glob-base-0.3.0.tgz",
      "integrity": "sha1-27Fk9iIbHAscz4Kuoyi0l98Oo8Q=",
      "dev": true,
      "requires": {
        "glob-parent": "^2.0.0",
        "is-glob": "^2.0.0"
      },
      "dependencies": {
        "glob-parent": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/glob-parent/-/glob-parent-2.0.0.tgz",
          "integrity": "sha1-gTg9ctsFT8zPUzbaqQLxgvbtuyg=",
          "dev": true,
          "requires": {
            "is-glob": "^2.0.0"
          }
        },
        "is-extglob": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-extglob/-/is-extglob-1.0.0.tgz",
          "integrity": "sha1-rEaBd8SUNAWgkvyPKXYMb/xiBsA=",
          "dev": true
        },
        "is-glob": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/is-glob/-/is-glob-2.0.1.tgz",
          "integrity": "sha1-0Jb5JqPe1WAPP9/ZEZjLCIjC2GM=",
          "dev": true,
          "requires": {
            "is-extglob": "^1.0.0"
          }
        }
      }
    },
    "glob-parent": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/glob-parent/-/glob-parent-3.1.0.tgz",
      "integrity": "sha1-nmr2KZ2NO9K9QEMIMr0RPfkGxa4=",
      "dev": true,
      "requires": {
        "is-glob": "^3.1.0",
        "path-dirname": "^1.0.0"
      },
      "dependencies": {
        "is-glob": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/is-glob/-/is-glob-3.1.0.tgz",
          "integrity": "sha1-e6WuJCF4BKxwcHuWkiVnSGzD6Eo=",
          "dev": true,
          "requires": {
            "is-extglob": "^2.1.0"
          }
        }
      }
    },
    "globals": {
      "version": "9.18.0",
      "resolved": "https://registry.npmjs.org/globals/-/globals-9.18.0.tgz",
      "integrity": "sha512-S0nG3CLEQiY/ILxqtztTWH/3iRRdyBLw6KMDxnKMchrtbj2OFmehVh0WUCfW3DUrIgx/qFrJPICrq4Z4sTR9UQ==",
      "dev": true
    },
    "globby": {
      "version": "7.1.1",
      "resolved": "https://registry.npmjs.org/globby/-/globby-7.1.1.tgz",
      "integrity": "sha1-+yzP+UAfhgCUXfral0QMypcrhoA=",
      "dev": true,
      "requires": {
        "array-union": "^1.0.1",
        "dir-glob": "^2.0.0",
        "glob": "^7.1.2",
        "ignore": "^3.3.5",
        "pify": "^3.0.0",
        "slash": "^1.0.0"
      }
    },
    "globule": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/globule/-/globule-1.2.1.tgz",
      "integrity": "sha512-g7QtgWF4uYSL5/dn71WxubOrS7JVGCnFPEnoeChJmBnyR9Mw8nGoEwOgJL/RC2Te0WhbsEUCejfH8SZNJ+adYQ==",
      "dev": true,
      "optional": true,
      "requires": {
        "glob": "~7.1.1",
        "lodash": "~4.17.10",
        "minimatch": "~3.0.2"
      }
    },
    "graceful-fs": {
      "version": "4.1.15",
      "resolved": "https://registry.npmjs.org/graceful-fs/-/graceful-fs-4.1.15.tgz",
      "integrity": "sha512-6uHUhOPEBgQ24HM+r6b/QwWfZq+yiFcipKFrOFiBEnWdy5sdzYoi+pJeQaPI5qOLRFqWmAXUPQNsielzdLoecA==",
      "dev": true
    },
    "handle-thing": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/handle-thing/-/handle-thing-2.0.0.tgz",
      "integrity": "sha512-d4sze1JNC454Wdo2fkuyzCr6aHcbL6PGGuFAz0Li/NcOm1tCHGnWDRmJP85dh9IhQErTc2svWFEX5xHIOo//kQ==",
      "dev": true
    },
    "handlebars": {
      "version": "4.0.12",
      "resolved": "https://registry.npmjs.org/handlebars/-/handlebars-4.0.12.tgz",
      "integrity": "sha512-RhmTekP+FZL+XNhwS1Wf+bTTZpdLougwt5pcgA1tuz6Jcx0fpH/7z0qd71RKnZHBCxIRBHfBOnio4gViPemNzA==",
      "dev": true,
      "requires": {
        "async": "^2.5.0",
        "optimist": "^0.6.1",
        "source-map": "^0.6.1",
        "uglify-js": "^3.1.4"
      },
      "dependencies": {
        "async": {
          "version": "2.6.1",
          "resolved": "https://registry.npmjs.org/async/-/async-2.6.1.tgz",
          "integrity": "sha512-fNEiL2+AZt6AlAw/29Cr0UDe4sRAHCpEHh54WMz+Bb7QfNcFw4h3loofyJpLeQs4Yx7yuqu/2dLgM5hKOs6HlQ==",
          "dev": true,
          "requires": {
            "lodash": "^4.17.10"
          }
        },
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "har-schema": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/har-schema/-/har-schema-2.0.0.tgz",
      "integrity": "sha1-qUwiJOvKwEeCoNkDVSHyRzW37JI=",
      "dev": true
    },
    "har-validator": {
      "version": "5.1.3",
      "resolved": "https://registry.npmjs.org/har-validator/-/har-validator-5.1.3.tgz",
      "integrity": "sha512-sNvOCzEQNr/qrvJgc3UG/kD4QtlHycrzwS+6mfTrrSq97BvaYcPZZI1ZSqGSPR73Cxn4LKTD4PttRwfU7jWq5g==",
      "dev": true,
      "requires": {
        "ajv": "^6.5.5",
        "har-schema": "^2.0.0"
      }
    },
    "has-ansi": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/has-ansi/-/has-ansi-2.0.0.tgz",
      "integrity": "sha1-NPUEnOHs3ysGSa8+8k5F7TVBbZE=",
      "dev": true,
      "requires": {
        "ansi-regex": "^2.0.0"
      }
    },
    "has-binary2": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/has-binary2/-/has-binary2-1.0.3.tgz",
      "integrity": "sha512-G1LWKhDSvhGeAQ8mPVQlqNcOB2sJdwATtZKl2pDKKHfpf/rYj24lkinxf69blJbnsvtqqNU+L3SL50vzZhXOnw==",
      "dev": true,
      "requires": {
        "isarray": "2.0.1"
      },
      "dependencies": {
        "isarray": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/isarray/-/isarray-2.0.1.tgz",
          "integrity": "sha1-o32U7ZzaLVmGXJ92/llu4fM4dB4=",
          "dev": true
        }
      }
    },
    "has-cors": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/has-cors/-/has-cors-1.1.0.tgz",
      "integrity": "sha1-XkdHk/fqmEPRu5nCPu9J/xJv/zk=",
      "dev": true
    },
    "has-flag": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/has-flag/-/has-flag-3.0.0.tgz",
      "integrity": "sha1-tdRU3CGZriJWmfNGfloH87lVuv0=",
      "dev": true
    },
    "has-unicode": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/has-unicode/-/has-unicode-2.0.1.tgz",
      "integrity": "sha1-4Ob+aijPUROIVeCG0Wkedx3iqLk=",
      "dev": true
    },
    "has-value": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/has-value/-/has-value-1.0.0.tgz",
      "integrity": "sha1-GLKB2lhbHFxR3vJMkw7SmgvmsXc=",
      "dev": true,
      "requires": {
        "get-value": "^2.0.6",
        "has-values": "^1.0.0",
        "isobject": "^3.0.0"
      }
    },
    "has-values": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/has-values/-/has-values-1.0.0.tgz",
      "integrity": "sha1-lbC2P+whRmGab+V/51Yo1aOe/k8=",
      "dev": true,
      "requires": {
        "is-number": "^3.0.0",
        "kind-of": "^4.0.0"
      },
      "dependencies": {
        "kind-of": {
          "version": "4.0.0",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-4.0.0.tgz",
          "integrity": "sha1-IIE989cSkosgc3hpGkUGb65y3Vc=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "hash-base": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/hash-base/-/hash-base-3.0.4.tgz",
      "integrity": "sha1-X8hoaEfs1zSZQDMZprCj8/auSRg=",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "safe-buffer": "^5.0.1"
      }
    },
    "hash.js": {
      "version": "1.1.7",
      "resolved": "https://registry.npmjs.org/hash.js/-/hash.js-1.1.7.tgz",
      "integrity": "sha512-taOaskGt4z4SOANNseOviYDvjEJinIkRgmp7LbKP2YTTmVxWBl87s/uzK9r+44BclBSp2X7K1hqeNfz9JbBeXA==",
      "dev": true,
      "requires": {
        "inherits": "^2.0.3",
        "minimalistic-assert": "^1.0.1"
      }
    },
    "hmac-drbg": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/hmac-drbg/-/hmac-drbg-1.0.1.tgz",
      "integrity": "sha1-0nRXAQJabHdabFRXk+1QL8DGSaE=",
      "dev": true,
      "requires": {
        "hash.js": "^1.0.3",
        "minimalistic-assert": "^1.0.0",
        "minimalistic-crypto-utils": "^1.0.1"
      }
    },
    "hosted-git-info": {
      "version": "2.7.1",
      "resolved": "https://registry.npmjs.org/hosted-git-info/-/hosted-git-info-2.7.1.tgz",
      "integrity": "sha512-7T/BxH19zbcCTa8XkMlbK5lTo1WtgkFi3GvdWEyNuc4Vex7/9Dqbnpsf4JMydcfj9HCg4zUWFTL3Za6lapg5/w==",
      "dev": true
    },
    "hpack.js": {
      "version": "2.1.6",
      "resolved": "https://registry.npmjs.org/hpack.js/-/hpack.js-2.1.6.tgz",
      "integrity": "sha1-h3dMCUnlE/QuhFdbPEVoH63ioLI=",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "obuf": "^1.0.0",
        "readable-stream": "^2.0.1",
        "wbuf": "^1.1.0"
      }
    },
    "html-entities": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/html-entities/-/html-entities-1.2.1.tgz",
      "integrity": "sha1-DfKTUfByEWNRXfueVUPl9u7VFi8=",
      "dev": true
    },
    "http-cache-semantics": {
      "version": "3.8.1",
      "resolved": "https://registry.npmjs.org/http-cache-semantics/-/http-cache-semantics-3.8.1.tgz",
      "integrity": "sha512-5ai2iksyV8ZXmnZhHH4rWPoxxistEexSi5936zIQ1bnNTW5VnA85B6P/VpXiRM017IgRvb2kKo1a//y+0wSp3w==",
      "dev": true
    },
    "http-deceiver": {
      "version": "1.2.7",
      "resolved": "https://registry.npmjs.org/http-deceiver/-/http-deceiver-1.2.7.tgz",
      "integrity": "sha1-+nFolEq5pRnTN8sL7HKE3D5yPYc=",
      "dev": true
    },
    "http-errors": {
      "version": "1.6.3",
      "resolved": "https://registry.npmjs.org/http-errors/-/http-errors-1.6.3.tgz",
      "integrity": "sha1-i1VoC7S+KDoLW/TqLjhYC+HZMg0=",
      "dev": true,
      "requires": {
        "depd": "~1.1.2",
        "inherits": "2.0.3",
        "setprototypeof": "1.1.0",
        "statuses": ">= 1.4.0 < 2"
      }
    },
    "http-parser-js": {
      "version": "0.5.0",
      "resolved": "https://registry.npmjs.org/http-parser-js/-/http-parser-js-0.5.0.tgz",
      "integrity": "sha512-cZdEF7r4gfRIq7ezX9J0T+kQmJNOub71dWbgAXVHDct80TKP4MCETtZQ31xyv38UwgzkWPYF/Xc0ge55dW9Z9w==",
      "dev": true
    },
    "http-proxy": {
      "version": "1.17.0",
      "resolved": "https://registry.npmjs.org/http-proxy/-/http-proxy-1.17.0.tgz",
      "integrity": "sha512-Taqn+3nNvYRfJ3bGvKfBSRwy1v6eePlm3oc/aWVxZp57DQr5Eq3xhKJi7Z4hZpS8PC3H4qI+Yly5EmFacGuA/g==",
      "dev": true,
      "requires": {
        "eventemitter3": "^3.0.0",
        "follow-redirects": "^1.0.0",
        "requires-port": "^1.0.0"
      }
    },
    "http-proxy-agent": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/http-proxy-agent/-/http-proxy-agent-2.1.0.tgz",
      "integrity": "sha512-qwHbBLV7WviBl0rQsOzH6o5lwyOIvwp/BdFnvVxXORldu5TmjFfjzBcWUWS5kWAZhmv+JtiDhSuQCp4sBfbIgg==",
      "dev": true,
      "requires": {
        "agent-base": "4",
        "debug": "3.1.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        }
      }
    },
    "http-proxy-middleware": {
      "version": "0.18.0",
      "resolved": "https://registry.npmjs.org/http-proxy-middleware/-/http-proxy-middleware-0.18.0.tgz",
      "integrity": "sha512-Fs25KVMPAIIcgjMZkVHJoKg9VcXcC1C8yb9JUgeDvVXY0S/zgVIhMb+qVswDIgtJe2DfckMSY2d6TuTEutlk6Q==",
      "dev": true,
      "requires": {
        "http-proxy": "^1.16.2",
        "is-glob": "^4.0.0",
        "lodash": "^4.17.5",
        "micromatch": "^3.1.9"
      }
    },
    "http-signature": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/http-signature/-/http-signature-1.2.0.tgz",
      "integrity": "sha1-muzZJRFHcvPZW2WmCruPfBj7rOE=",
      "dev": true,
      "requires": {
        "assert-plus": "^1.0.0",
        "jsprim": "^1.2.2",
        "sshpk": "^1.7.0"
      }
    },
    "https-browserify": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/https-browserify/-/https-browserify-1.0.0.tgz",
      "integrity": "sha1-7AbBDgo0wPL68Zn3/X/Hj//QPHM=",
      "dev": true
    },
    "https-proxy-agent": {
      "version": "2.2.1",
      "resolved": "https://registry.npmjs.org/https-proxy-agent/-/https-proxy-agent-2.2.1.tgz",
      "integrity": "sha512-HPCTS1LW51bcyMYbxUIOO4HEOlQ1/1qRaFWcyxvwaqUS9TY88aoEuHUY33kuAh1YhVVaDQhLZsnPd+XNARWZlQ==",
      "dev": true,
      "requires": {
        "agent-base": "^4.1.0",
        "debug": "^3.1.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.2.6",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
          "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        }
      }
    },
    "humanize-ms": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/humanize-ms/-/humanize-ms-1.2.1.tgz",
      "integrity": "sha1-xG4xWaKT9riW2ikxbYtv6Lt5u+0=",
      "dev": true,
      "requires": {
        "ms": "^2.0.0"
      }
    },
    "iconv-lite": {
      "version": "0.4.23",
      "resolved": "https://registry.npmjs.org/iconv-lite/-/iconv-lite-0.4.23.tgz",
      "integrity": "sha512-neyTUVFtahjf0mB3dZT77u+8O0QB89jFdnBkd5P1JgYPbPaia3gXXOVL2fq8VyU2gMMD7SaN7QukTB/pmXYvDA==",
      "dev": true,
      "requires": {
        "safer-buffer": ">= 2.1.2 < 3"
      }
    },
    "ieee754": {
      "version": "1.1.12",
      "resolved": "https://registry.npmjs.org/ieee754/-/ieee754-1.1.12.tgz",
      "integrity": "sha512-GguP+DRY+pJ3soyIiGPTvdiVXjZ+DbXOxGpXn3eMvNW4x4irjqXm4wHKscC+TfxSJ0yw/S1F24tqdMNsMZTiLA==",
      "dev": true
    },
    "iferr": {
      "version": "0.1.5",
      "resolved": "https://registry.npmjs.org/iferr/-/iferr-0.1.5.tgz",
      "integrity": "sha1-xg7taebY/bazEEofy8ocGS3FtQE=",
      "dev": true
    },
    "ignore": {
      "version": "3.3.10",
      "resolved": "https://registry.npmjs.org/ignore/-/ignore-3.3.10.tgz",
      "integrity": "sha512-Pgs951kaMm5GXP7MOvxERINe3gsaVjUWFm+UZPSq9xYriQAksyhg0csnS0KXSNRD5NmNdapXEpjxG49+AKh/ug==",
      "dev": true
    },
    "ignore-walk": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/ignore-walk/-/ignore-walk-3.0.1.tgz",
      "integrity": "sha512-DTVlMx3IYPe0/JJcYP7Gxg7ttZZu3IInhuEhbchuqneY9wWe5Ojy2mXLBaQFUQmo0AW2r3qG7m1mg86js+gnlQ==",
      "dev": true,
      "requires": {
        "minimatch": "^3.0.4"
      }
    },
    "image-size": {
      "version": "0.5.5",
      "resolved": "https://registry.npmjs.org/image-size/-/image-size-0.5.5.tgz",
      "integrity": "sha1-Cd/Uq50g4p6xw+gLiZA3jfnjy5w=",
      "dev": true,
      "optional": true
    },
    "immediate": {
      "version": "3.0.6",
      "resolved": "https://registry.npmjs.org/immediate/-/immediate-3.0.6.tgz",
      "integrity": "sha1-nbHb0Pr43m++D13V5Wu2BigN5ps=",
      "dev": true
    },
    "import-cwd": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/import-cwd/-/import-cwd-2.1.0.tgz",
      "integrity": "sha1-qmzzbnInYShcs3HsZRn1PiQ1sKk=",
      "dev": true,
      "requires": {
        "import-from": "^2.1.0"
      }
    },
    "import-from": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/import-from/-/import-from-2.1.0.tgz",
      "integrity": "sha1-M1238qev/VOqpHHUuAId7ja387E=",
      "dev": true,
      "requires": {
        "resolve-from": "^3.0.0"
      }
    },
    "import-local": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/import-local/-/import-local-2.0.0.tgz",
      "integrity": "sha512-b6s04m3O+s3CGSbqDIyP4R6aAwAeYlVq9+WUWep6iHa8ETRf9yei1U48C5MmfJmV9AiLYYBKPMq/W+/WRpQmCQ==",
      "dev": true,
      "requires": {
        "pkg-dir": "^3.0.0",
        "resolve-cwd": "^2.0.0"
      },
      "dependencies": {
        "find-up": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/find-up/-/find-up-3.0.0.tgz",
          "integrity": "sha512-1yD6RmLI1XBfxugvORwlck6f75tYL+iR0jqwsOrOxMZyGYqUuDhJ0l4AXdO1iX/FTs9cBAMEk1gWSEx1kSbylg==",
          "dev": true,
          "requires": {
            "locate-path": "^3.0.0"
          }
        },
        "locate-path": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/locate-path/-/locate-path-3.0.0.tgz",
          "integrity": "sha512-7AO748wWnIhNqAuaty2ZWHkQHRSNfPVIsPIfwEOWO22AmaoVrWavlOcMR5nzTLNYvp36X220/maaRsrec1G65A==",
          "dev": true,
          "requires": {
            "p-locate": "^3.0.0",
            "path-exists": "^3.0.0"
          }
        },
        "p-limit": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/p-limit/-/p-limit-2.1.0.tgz",
          "integrity": "sha512-NhURkNcrVB+8hNfLuysU8enY5xn2KXphsHBaC2YmRNTZRc7RWusw6apSpdEj3jo4CMb6W9nrF6tTnsJsJeyu6g==",
          "dev": true,
          "requires": {
            "p-try": "^2.0.0"
          }
        },
        "p-locate": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/p-locate/-/p-locate-3.0.0.tgz",
          "integrity": "sha512-x+12w/To+4GFfgJhBEpiDcLozRJGegY+Ei7/z0tSLkMmxGZNybVMSfWj9aJn8Z5Fc7dBUNJOOVgPv2H7IwulSQ==",
          "dev": true,
          "requires": {
            "p-limit": "^2.0.0"
          }
        },
        "p-try": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/p-try/-/p-try-2.0.0.tgz",
          "integrity": "sha512-hMp0onDKIajHfIkdRk3P4CdCmErkYAxxDtP3Wx/4nZ3aGlau2VKh3mZpcuFkH27WQkL/3WBCPOktzA9ZOAnMQQ==",
          "dev": true
        },
        "pkg-dir": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/pkg-dir/-/pkg-dir-3.0.0.tgz",
          "integrity": "sha512-/E57AYkoeQ25qkxMj5PBOVgF8Kiu/h7cYS30Z5+R7WaiCCBfLq58ZI/dSeaEKb9WVJV5n/03QwrN3IeWIFllvw==",
          "dev": true,
          "requires": {
            "find-up": "^3.0.0"
          }
        }
      }
    },
    "imurmurhash": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/imurmurhash/-/imurmurhash-0.1.4.tgz",
      "integrity": "sha1-khi5srkoojixPcT7a21XbyMUU+o=",
      "dev": true
    },
    "in-publish": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/in-publish/-/in-publish-2.0.0.tgz",
      "integrity": "sha1-4g/146KvwmkDILbcVSaCqcf631E=",
      "dev": true,
      "optional": true
    },
    "indent-string": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/indent-string/-/indent-string-2.1.0.tgz",
      "integrity": "sha1-ji1INIdCEhtKghi3oTfppSBJ3IA=",
      "dev": true,
      "optional": true,
      "requires": {
        "repeating": "^2.0.0"
      }
    },
    "indexof": {
      "version": "0.0.1",
      "resolved": "https://registry.npmjs.org/indexof/-/indexof-0.0.1.tgz",
      "integrity": "sha1-gtwzbSMrkGIXnQWrMpOmYFn9Q10=",
      "dev": true
    },
    "inflight": {
      "version": "1.0.6",
      "resolved": "https://registry.npmjs.org/inflight/-/inflight-1.0.6.tgz",
      "integrity": "sha1-Sb1jMdfQLQwJvJEKEHW6gWW1bfk=",
      "dev": true,
      "requires": {
        "once": "^1.3.0",
        "wrappy": "1"
      }
    },
    "inherits": {
      "version": "2.0.3",
      "resolved": "https://registry.npmjs.org/inherits/-/inherits-2.0.3.tgz",
      "integrity": "sha1-Yzwsg+PaQqUC9SRmAiSA9CCCYd4=",
      "dev": true
    },
    "ini": {
      "version": "1.3.5",
      "resolved": "https://registry.npmjs.org/ini/-/ini-1.3.5.tgz",
      "integrity": "sha512-RZY5huIKCMRWDUqZlEi72f/lmXKMvuszcMBduliQ3nnWbx9X/ZBQO7DijMEYS9EhHBb2qacRUMtC7svLwe0lcw==",
      "dev": true
    },
    "inquirer": {
      "version": "6.2.1",
      "resolved": "https://registry.npmjs.org/inquirer/-/inquirer-6.2.1.tgz",
      "integrity": "sha512-088kl3DRT2dLU5riVMKKr1DlImd6X7smDhpXUCkJDCKvTEJeRiXh0G132HG9u5a+6Ylw9plFRY7RuTnwohYSpg==",
      "dev": true,
      "requires": {
        "ansi-escapes": "^3.0.0",
        "chalk": "^2.0.0",
        "cli-cursor": "^2.1.0",
        "cli-width": "^2.0.0",
        "external-editor": "^3.0.0",
        "figures": "^2.0.0",
        "lodash": "^4.17.10",
        "mute-stream": "0.0.7",
        "run-async": "^2.2.0",
        "rxjs": "^6.1.0",
        "string-width": "^2.1.0",
        "strip-ansi": "^5.0.0",
        "through": "^2.3.6"
      },
      "dependencies": {
        "ansi-regex": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-3.0.0.tgz",
          "integrity": "sha1-7QMXwyIGT3lGbAKWa922Bas32Zg=",
          "dev": true
        },
        "is-fullwidth-code-point": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/is-fullwidth-code-point/-/is-fullwidth-code-point-2.0.0.tgz",
          "integrity": "sha1-o7MKXE8ZkYMWeqq5O+764937ZU8=",
          "dev": true
        },
        "string-width": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/string-width/-/string-width-2.1.1.tgz",
          "integrity": "sha512-nOqH59deCq9SRHlxq1Aw85Jnt4w6KvLKqWVik6oA9ZklXLNIOlqg4F2yrT1MVaTjAqvVwdfeZ7w7aCvJD7ugkw==",
          "dev": true,
          "requires": {
            "is-fullwidth-code-point": "^2.0.0",
            "strip-ansi": "^4.0.0"
          },
          "dependencies": {
            "strip-ansi": {
              "version": "4.0.0",
              "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-4.0.0.tgz",
              "integrity": "sha1-qEeQIusaw2iocTibY1JixQXuNo8=",
              "dev": true,
              "requires": {
                "ansi-regex": "^3.0.0"
              }
            }
          }
        },
        "strip-ansi": {
          "version": "5.0.0",
          "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-5.0.0.tgz",
          "integrity": "sha512-Uu7gQyZI7J7gn5qLn1Np3G9vcYGTVqB+lFTytnDJv83dd8T22aGH451P3jueT2/QemInJDfxHB5Tde5OzgG1Ow==",
          "dev": true,
          "requires": {
            "ansi-regex": "^4.0.0"
          },
          "dependencies": {
            "ansi-regex": {
              "version": "4.0.0",
              "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-4.0.0.tgz",
              "integrity": "sha512-iB5Dda8t/UqpPI/IjsejXu5jOGDrzn41wJyljwPH65VCIbk6+1BzFIMJGFwTNrYXT1CrD+B4l19U7awiQ8rk7w==",
              "dev": true
            }
          }
        }
      }
    },
    "internal-ip": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/internal-ip/-/internal-ip-3.0.1.tgz",
      "integrity": "sha512-NXXgESC2nNVtU+pqmC9e6R8B1GpKxzsAQhffvh5AL79qKnodd+L7tnEQmTiUAVngqLalPbSqRA7XGIEL5nCd0Q==",
      "dev": true,
      "requires": {
        "default-gateway": "^2.6.0",
        "ipaddr.js": "^1.5.2"
      }
    },
    "interpret": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/interpret/-/interpret-1.2.0.tgz",
      "integrity": "sha512-mT34yGKMNceBQUoVn7iCDKDntA7SC6gycMAWzGx1z/CMCTV7b2AAtXlo3nRyHZ1FelRkQbQjprHSYGwzLtkVbw==",
      "dev": true
    },
    "invariant": {
      "version": "2.2.4",
      "resolved": "https://registry.npmjs.org/invariant/-/invariant-2.2.4.tgz",
      "integrity": "sha512-phJfQVBuaJM5raOpJjSfkiD6BpbCE4Ns//LaXl6wGYtUBY83nWS6Rf9tXm2e8VaK60JEjYldbPif/A2B1C2gNA==",
      "dev": true,
      "requires": {
        "loose-envify": "^1.0.0"
      }
    },
    "invert-kv": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/invert-kv/-/invert-kv-1.0.0.tgz",
      "integrity": "sha1-EEqOSqym09jNFXqO+L+rLXo//bY=",
      "dev": true
    },
    "ip": {
      "version": "1.1.5",
      "resolved": "https://registry.npmjs.org/ip/-/ip-1.1.5.tgz",
      "integrity": "sha1-vd7XARQpCCjAoDnnLvJfWq7ENUo=",
      "dev": true
    },
    "ip-regex": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/ip-regex/-/ip-regex-2.1.0.tgz",
      "integrity": "sha1-+ni/XS5pE8kRzp+BnuUUa7bYROk=",
      "dev": true
    },
    "ipaddr.js": {
      "version": "1.8.0",
      "resolved": "https://registry.npmjs.org/ipaddr.js/-/ipaddr.js-1.8.0.tgz",
      "integrity": "sha1-6qM9bd16zo9/b+DJygRA5wZzix4=",
      "dev": true
    },
    "is-accessor-descriptor": {
      "version": "0.1.6",
      "resolved": "https://registry.npmjs.org/is-accessor-descriptor/-/is-accessor-descriptor-0.1.6.tgz",
      "integrity": "sha1-qeEss66Nh2cn7u84Q/igiXtcmNY=",
      "dev": true,
      "requires": {
        "kind-of": "^3.0.2"
      },
      "dependencies": {
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "is-arrayish": {
      "version": "0.2.1",
      "resolved": "https://registry.npmjs.org/is-arrayish/-/is-arrayish-0.2.1.tgz",
      "integrity": "sha1-d8mYQFJ6qOyxqLppe4BkWnqSap0=",
      "dev": true
    },
    "is-binary-path": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/is-binary-path/-/is-binary-path-1.0.1.tgz",
      "integrity": "sha1-dfFmQrSA8YenEcgUFh/TpKdlWJg=",
      "dev": true,
      "requires": {
        "binary-extensions": "^1.0.0"
      }
    },
    "is-buffer": {
      "version": "1.1.6",
      "resolved": "https://registry.npmjs.org/is-buffer/-/is-buffer-1.1.6.tgz",
      "integrity": "sha512-NcdALwpXkTm5Zvvbk7owOUSvVvBKDgKP5/ewfXEznmQFfs4ZRmanOeKBTjRVjka3QFoN6XJ+9F3USqfHqTaU5w==",
      "dev": true
    },
    "is-builtin-module": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/is-builtin-module/-/is-builtin-module-1.0.0.tgz",
      "integrity": "sha1-VAVy0096wxGfj3bDDLwbHgN6/74=",
      "dev": true,
      "requires": {
        "builtin-modules": "^1.0.0"
      }
    },
    "is-data-descriptor": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/is-data-descriptor/-/is-data-descriptor-0.1.4.tgz",
      "integrity": "sha1-C17mSDiOLIYCgueT8YVv7D8wG1Y=",
      "dev": true,
      "requires": {
        "kind-of": "^3.0.2"
      },
      "dependencies": {
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "is-descriptor": {
      "version": "0.1.6",
      "resolved": "https://registry.npmjs.org/is-descriptor/-/is-descriptor-0.1.6.tgz",
      "integrity": "sha512-avDYr0SB3DwO9zsMov0gKCESFYqCnE4hq/4z3TdUlukEy5t9C0YRq7HLrsN52NAcqXKaepeCD0n+B0arnVG3Hg==",
      "dev": true,
      "requires": {
        "is-accessor-descriptor": "^0.1.6",
        "is-data-descriptor": "^0.1.4",
        "kind-of": "^5.0.0"
      },
      "dependencies": {
        "kind-of": {
          "version": "5.1.0",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-5.1.0.tgz",
          "integrity": "sha512-NGEErnH6F2vUuXDh+OlbcKW7/wOcfdRHaZ7VWtqCztfHri/++YKmP51OdWeGPuqCOba6kk2OTe5d02VmTB80Pw==",
          "dev": true
        }
      }
    },
    "is-directory": {
      "version": "0.3.1",
      "resolved": "https://registry.npmjs.org/is-directory/-/is-directory-0.3.1.tgz",
      "integrity": "sha1-YTObbyR1/Hcv2cnYP1yFddwVSuE=",
      "dev": true
    },
    "is-dotfile": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/is-dotfile/-/is-dotfile-1.0.3.tgz",
      "integrity": "sha1-pqLzL/0t+wT1yiXs0Pa4PPeYoeE=",
      "dev": true
    },
    "is-equal-shallow": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/is-equal-shallow/-/is-equal-shallow-0.1.3.tgz",
      "integrity": "sha1-IjgJj8Ih3gvPpdnqxMRdY4qhxTQ=",
      "dev": true,
      "requires": {
        "is-primitive": "^2.0.0"
      }
    },
    "is-extendable": {
      "version": "0.1.1",
      "resolved": "https://registry.npmjs.org/is-extendable/-/is-extendable-0.1.1.tgz",
      "integrity": "sha1-YrEQ4omkcUGOPsNqYX1HLjAd/Ik=",
      "dev": true
    },
    "is-extglob": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/is-extglob/-/is-extglob-2.1.1.tgz",
      "integrity": "sha1-qIwCU1eR8C7TfHahueqXc8gz+MI=",
      "dev": true
    },
    "is-finite": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/is-finite/-/is-finite-1.0.2.tgz",
      "integrity": "sha1-zGZ3aVYCvlUO8R6LSqYwU0K20Ko=",
      "dev": true,
      "requires": {
        "number-is-nan": "^1.0.0"
      }
    },
    "is-fullwidth-code-point": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/is-fullwidth-code-point/-/is-fullwidth-code-point-1.0.0.tgz",
      "integrity": "sha1-754xOG8DGn8NZDr4L95QxFfvAMs=",
      "dev": true,
      "requires": {
        "number-is-nan": "^1.0.0"
      }
    },
    "is-glob": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/is-glob/-/is-glob-4.0.0.tgz",
      "integrity": "sha1-lSHHaEXMJhCoUgPd8ICpWML/q8A=",
      "dev": true,
      "requires": {
        "is-extglob": "^2.1.1"
      }
    },
    "is-number": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/is-number/-/is-number-3.0.0.tgz",
      "integrity": "sha1-JP1iAaR4LPUFYcgQJ2r8fRLXEZU=",
      "dev": true,
      "requires": {
        "kind-of": "^3.0.2"
      },
      "dependencies": {
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "is-path-cwd": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/is-path-cwd/-/is-path-cwd-1.0.0.tgz",
      "integrity": "sha1-0iXsIxMuie3Tj9p2dHLmLmXxEG0=",
      "dev": true
    },
    "is-path-in-cwd": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/is-path-in-cwd/-/is-path-in-cwd-1.0.1.tgz",
      "integrity": "sha512-FjV1RTW48E7CWM7eE/J2NJvAEEVektecDBVBE5Hh3nM1Jd0kvhHtX68Pr3xsDf857xt3Y4AkwVULK1Vku62aaQ==",
      "dev": true,
      "requires": {
        "is-path-inside": "^1.0.0"
      }
    },
    "is-path-inside": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/is-path-inside/-/is-path-inside-1.0.1.tgz",
      "integrity": "sha1-jvW33lBDej/cprToZe96pVy0gDY=",
      "dev": true,
      "requires": {
        "path-is-inside": "^1.0.1"
      }
    },
    "is-plain-object": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/is-plain-object/-/is-plain-object-2.0.4.tgz",
      "integrity": "sha512-h5PpgXkWitc38BBMYawTYMWJHFZJVnBquFE57xFpjB8pJFiF6gZ+bU+WyI/yqXiFR5mdLsgYNaPe8uao6Uv9Og==",
      "dev": true,
      "requires": {
        "isobject": "^3.0.1"
      }
    },
    "is-posix-bracket": {
      "version": "0.1.1",
      "resolved": "https://registry.npmjs.org/is-posix-bracket/-/is-posix-bracket-0.1.1.tgz",
      "integrity": "sha1-MzTceXdDaOkvAW5vvAqI9c1ua8Q=",
      "dev": true
    },
    "is-primitive": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/is-primitive/-/is-primitive-2.0.0.tgz",
      "integrity": "sha1-IHurkWOEmcB7Kt8kCkGochADRXU=",
      "dev": true
    },
    "is-promise": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/is-promise/-/is-promise-2.1.0.tgz",
      "integrity": "sha1-eaKp7OfwlugPNtKy87wWwf9L8/o=",
      "dev": true
    },
    "is-stream": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/is-stream/-/is-stream-1.1.0.tgz",
      "integrity": "sha1-EtSj3U5o4Lec6428hBc66A2RykQ=",
      "dev": true
    },
    "is-typedarray": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/is-typedarray/-/is-typedarray-1.0.0.tgz",
      "integrity": "sha1-5HnICFjfDBsR3dppQPlgEfzaSpo=",
      "dev": true
    },
    "is-utf8": {
      "version": "0.2.1",
      "resolved": "https://registry.npmjs.org/is-utf8/-/is-utf8-0.2.1.tgz",
      "integrity": "sha1-Sw2hRCEE0bM2NA6AeX6GXPOffXI=",
      "dev": true
    },
    "is-windows": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/is-windows/-/is-windows-1.0.2.tgz",
      "integrity": "sha512-eXK1UInq2bPmjyX6e3VHIzMLobc4J94i4AWn+Hpq3OU5KkrRC96OAcR3PRJ/pGu6m8TRnBHP9dkXQVsT/COVIA==",
      "dev": true
    },
    "is-wsl": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/is-wsl/-/is-wsl-1.1.0.tgz",
      "integrity": "sha1-HxbkqiKwTRM2tmGIpmrzxgDDpm0=",
      "dev": true
    },
    "isarray": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/isarray/-/isarray-1.0.0.tgz",
      "integrity": "sha1-u5NdSFgsuhaMBoNJV6VKPgcSTxE=",
      "dev": true
    },
    "isbinaryfile": {
      "version": "3.0.3",
      "resolved": "https://registry.npmjs.org/isbinaryfile/-/isbinaryfile-3.0.3.tgz",
      "integrity": "sha512-8cJBL5tTd2OS0dM4jz07wQd5g0dCCqIhUxPIGtZfa5L6hWlvV5MHTITy/DBAsF+Oe2LS1X3krBUhNwaGUWpWxw==",
      "dev": true,
      "requires": {
        "buffer-alloc": "^1.2.0"
      }
    },
    "isexe": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/isexe/-/isexe-2.0.0.tgz",
      "integrity": "sha1-6PvzdNxVb/iUehDcsFctYz8s+hA=",
      "dev": true
    },
    "isobject": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/isobject/-/isobject-3.0.1.tgz",
      "integrity": "sha1-TkMekrEalzFjaqH5yNHMvP2reN8=",
      "dev": true
    },
    "isstream": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/isstream/-/isstream-0.1.2.tgz",
      "integrity": "sha1-R+Y/evVa+m+S4VAOaQ64uFKcCZo=",
      "dev": true
    },
    "istanbul": {
      "version": "0.4.5",
      "resolved": "https://registry.npmjs.org/istanbul/-/istanbul-0.4.5.tgz",
      "integrity": "sha1-ZcfXPUxNqE1POsMQuRj7C4Azczs=",
      "dev": true,
      "requires": {
        "abbrev": "1.0.x",
        "async": "1.x",
        "escodegen": "1.8.x",
        "esprima": "2.7.x",
        "glob": "^5.0.15",
        "handlebars": "^4.0.1",
        "js-yaml": "3.x",
        "mkdirp": "0.5.x",
        "nopt": "3.x",
        "once": "1.x",
        "resolve": "1.1.x",
        "supports-color": "^3.1.0",
        "which": "^1.1.1",
        "wordwrap": "^1.0.0"
      },
      "dependencies": {
        "glob": {
          "version": "5.0.15",
          "resolved": "https://registry.npmjs.org/glob/-/glob-5.0.15.tgz",
          "integrity": "sha1-G8k2ueAvSmA/zCIuz3Yz0wuLk7E=",
          "dev": true,
          "requires": {
            "inflight": "^1.0.4",
            "inherits": "2",
            "minimatch": "2 || 3",
            "once": "^1.3.0",
            "path-is-absolute": "^1.0.0"
          }
        },
        "has-flag": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/has-flag/-/has-flag-1.0.0.tgz",
          "integrity": "sha1-nZ55MWXOAXoA8AQYxD+UKnsdEfo=",
          "dev": true
        },
        "supports-color": {
          "version": "3.2.3",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-3.2.3.tgz",
          "integrity": "sha1-ZawFBLOVQXHYpklGsq48u4pfVPY=",
          "dev": true,
          "requires": {
            "has-flag": "^1.0.0"
          }
        }
      }
    },
    "istanbul-api": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/istanbul-api/-/istanbul-api-2.0.6.tgz",
      "integrity": "sha512-8W5oeAGWXhtTJjAyVfvavOLVyZCTNCKsyF6GON/INKlBdO7uJ/bv3qnPj5M6ERKzmMCJS1kntnjjGuJ86fn3rQ==",
      "dev": true,
      "requires": {
        "async": "^2.6.1",
        "compare-versions": "^3.2.1",
        "fileset": "^2.0.3",
        "istanbul-lib-coverage": "^2.0.1",
        "istanbul-lib-hook": "^2.0.1",
        "istanbul-lib-instrument": "^3.0.0",
        "istanbul-lib-report": "^2.0.2",
        "istanbul-lib-source-maps": "^2.0.1",
        "istanbul-reports": "^2.0.1",
        "js-yaml": "^3.12.0",
        "make-dir": "^1.3.0",
        "once": "^1.4.0"
      },
      "dependencies": {
        "async": {
          "version": "2.6.1",
          "resolved": "https://registry.npmjs.org/async/-/async-2.6.1.tgz",
          "integrity": "sha512-fNEiL2+AZt6AlAw/29Cr0UDe4sRAHCpEHh54WMz+Bb7QfNcFw4h3loofyJpLeQs4Yx7yuqu/2dLgM5hKOs6HlQ==",
          "dev": true,
          "requires": {
            "lodash": "^4.17.10"
          }
        },
        "istanbul-lib-coverage": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/istanbul-lib-coverage/-/istanbul-lib-coverage-2.0.1.tgz",
          "integrity": "sha512-nPvSZsVlbG9aLhZYaC3Oi1gT/tpyo3Yt5fNyf6NmcKIayz4VV/txxJFFKAK/gU4dcNn8ehsanBbVHVl0+amOLA==",
          "dev": true
        },
        "istanbul-lib-instrument": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/istanbul-lib-instrument/-/istanbul-lib-instrument-3.0.0.tgz",
          "integrity": "sha512-eQY9vN9elYjdgN9Iv6NS/00bptm02EBBk70lRMaVjeA6QYocQgenVrSgC28TJurdnZa80AGO3ASdFN+w/njGiQ==",
          "dev": true,
          "requires": {
            "@babel/generator": "^7.0.0",
            "@babel/parser": "^7.0.0",
            "@babel/template": "^7.0.0",
            "@babel/traverse": "^7.0.0",
            "@babel/types": "^7.0.0",
            "istanbul-lib-coverage": "^2.0.1",
            "semver": "^5.5.0"
          }
        }
      }
    },
    "istanbul-instrumenter-loader": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/istanbul-instrumenter-loader/-/istanbul-instrumenter-loader-3.0.1.tgz",
      "integrity": "sha512-a5SPObZgS0jB/ixaKSMdn6n/gXSrK2S6q/UfRJBT3e6gQmVjwZROTODQsYW5ZNwOu78hG62Y3fWlebaVOL0C+w==",
      "dev": true,
      "requires": {
        "convert-source-map": "^1.5.0",
        "istanbul-lib-instrument": "^1.7.3",
        "loader-utils": "^1.1.0",
        "schema-utils": "^0.3.0"
      },
      "dependencies": {
        "ajv": {
          "version": "5.5.2",
          "resolved": "https://registry.npmjs.org/ajv/-/ajv-5.5.2.tgz",
          "integrity": "sha1-c7Xuyj+rZT49P5Qis0GtQiBdyWU=",
          "dev": true,
          "requires": {
            "co": "^4.6.0",
            "fast-deep-equal": "^1.0.0",
            "fast-json-stable-stringify": "^2.0.0",
            "json-schema-traverse": "^0.3.0"
          }
        },
        "fast-deep-equal": {
          "version": "1.1.0",
          "resolved": "https://registry.npmjs.org/fast-deep-equal/-/fast-deep-equal-1.1.0.tgz",
          "integrity": "sha1-wFNHeBfIa1HaqFPIHgWbcz0CNhQ=",
          "dev": true
        },
        "json-schema-traverse": {
          "version": "0.3.1",
          "resolved": "https://registry.npmjs.org/json-schema-traverse/-/json-schema-traverse-0.3.1.tgz",
          "integrity": "sha1-NJptRMU6Ud6JtAgFxdXlm0F9M0A=",
          "dev": true
        },
        "schema-utils": {
          "version": "0.3.0",
          "resolved": "https://registry.npmjs.org/schema-utils/-/schema-utils-0.3.0.tgz",
          "integrity": "sha1-9YdyIs4+kx7a4DnxfrNxbnE3+M8=",
          "dev": true,
          "requires": {
            "ajv": "^5.0.0"
          }
        }
      }
    },
    "istanbul-lib-coverage": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/istanbul-lib-coverage/-/istanbul-lib-coverage-1.2.1.tgz",
      "integrity": "sha512-PzITeunAgyGbtY1ibVIUiV679EFChHjoMNRibEIobvmrCRaIgwLxNucOSimtNWUhEib/oO7QY2imD75JVgCJWQ==",
      "dev": true
    },
    "istanbul-lib-hook": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/istanbul-lib-hook/-/istanbul-lib-hook-2.0.1.tgz",
      "integrity": "sha512-ufiZoiJ8CxY577JJWEeFuxXZoMqiKpq/RqZtOAYuQLvlkbJWscq9n3gc4xrCGH9n4pW0qnTxOz1oyMmVtk8E1w==",
      "dev": true,
      "requires": {
        "append-transform": "^1.0.0"
      }
    },
    "istanbul-lib-instrument": {
      "version": "1.10.2",
      "resolved": "https://registry.npmjs.org/istanbul-lib-instrument/-/istanbul-lib-instrument-1.10.2.tgz",
      "integrity": "sha512-aWHxfxDqvh/ZlxR8BBaEPVSWDPUkGD63VjGQn3jcw8jCp7sHEMKcrj4xfJn/ABzdMEHiQNyvDQhqm5o8+SQg7A==",
      "dev": true,
      "requires": {
        "babel-generator": "^6.18.0",
        "babel-template": "^6.16.0",
        "babel-traverse": "^6.18.0",
        "babel-types": "^6.18.0",
        "babylon": "^6.18.0",
        "istanbul-lib-coverage": "^1.2.1",
        "semver": "^5.3.0"
      }
    },
    "istanbul-lib-report": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/istanbul-lib-report/-/istanbul-lib-report-2.0.2.tgz",
      "integrity": "sha512-rJ8uR3peeIrwAxoDEbK4dJ7cqqtxBisZKCuwkMtMv0xYzaAnsAi3AHrHPAAtNXzG/bcCgZZ3OJVqm1DTi9ap2Q==",
      "dev": true,
      "requires": {
        "istanbul-lib-coverage": "^2.0.1",
        "make-dir": "^1.3.0",
        "supports-color": "^5.4.0"
      },
      "dependencies": {
        "istanbul-lib-coverage": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/istanbul-lib-coverage/-/istanbul-lib-coverage-2.0.1.tgz",
          "integrity": "sha512-nPvSZsVlbG9aLhZYaC3Oi1gT/tpyo3Yt5fNyf6NmcKIayz4VV/txxJFFKAK/gU4dcNn8ehsanBbVHVl0+amOLA==",
          "dev": true
        },
        "supports-color": {
          "version": "5.5.0",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-5.5.0.tgz",
          "integrity": "sha512-QjVjwdXIt408MIiAqCX4oUKsgU2EqAGzs2Ppkm4aQYbjm+ZEWEcW4SfFNTr4uMNZma0ey4f5lgLrkB0aX0QMow==",
          "dev": true,
          "requires": {
            "has-flag": "^3.0.0"
          }
        }
      }
    },
    "istanbul-lib-source-maps": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/istanbul-lib-source-maps/-/istanbul-lib-source-maps-2.0.1.tgz",
      "integrity": "sha512-30l40ySg+gvBLcxTrLzR4Z2XTRj3HgRCA/p2rnbs/3OiTaoj054gAbuP5DcLOtwqmy4XW8qXBHzrmP2/bQ9i3A==",
      "dev": true,
      "requires": {
        "debug": "^3.1.0",
        "istanbul-lib-coverage": "^2.0.1",
        "make-dir": "^1.3.0",
        "rimraf": "^2.6.2",
        "source-map": "^0.6.1"
      },
      "dependencies": {
        "debug": {
          "version": "3.2.6",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
          "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "istanbul-lib-coverage": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/istanbul-lib-coverage/-/istanbul-lib-coverage-2.0.1.tgz",
          "integrity": "sha512-nPvSZsVlbG9aLhZYaC3Oi1gT/tpyo3Yt5fNyf6NmcKIayz4VV/txxJFFKAK/gU4dcNn8ehsanBbVHVl0+amOLA==",
          "dev": true
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        },
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "istanbul-reports": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/istanbul-reports/-/istanbul-reports-2.0.1.tgz",
      "integrity": "sha512-CT0QgMBJqs6NJLF678ZHcquUAZIoBIUNzdJrRJfpkI9OnzG6MkUfHxbJC3ln981dMswC7/B1mfX3LNkhgJxsuw==",
      "dev": true,
      "requires": {
        "handlebars": "^4.0.11"
      }
    },
    "jasmine": {
      "version": "2.8.0",
      "resolved": "https://registry.npmjs.org/jasmine/-/jasmine-2.8.0.tgz",
      "integrity": "sha1-awicChFXax8W3xG4AUbZHU6Lij4=",
      "dev": true,
      "requires": {
        "exit": "^0.1.2",
        "glob": "^7.0.6",
        "jasmine-core": "~2.8.0"
      },
      "dependencies": {
        "jasmine-core": {
          "version": "2.8.0",
          "resolved": "https://registry.npmjs.org/jasmine-core/-/jasmine-core-2.8.0.tgz",
          "integrity": "sha1-vMl5rh+f0FcB5F5S5l06XWPxok4=",
          "dev": true
        }
      }
    },
    "jasmine-core": {
      "version": "2.99.1",
      "resolved": "https://registry.npmjs.org/jasmine-core/-/jasmine-core-2.99.1.tgz",
      "integrity": "sha1-5kAN8ea1bhMLYcS80JPap/boyhU=",
      "dev": true
    },
    "jasmine-spec-reporter": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/jasmine-spec-reporter/-/jasmine-spec-reporter-4.2.1.tgz",
      "integrity": "sha512-FZBoZu7VE5nR7Nilzy+Np8KuVIOxF4oXDPDknehCYBDE080EnlPu0afdZNmpGDBRCUBv3mj5qgqCRmk6W/K8vg==",
      "dev": true,
      "requires": {
        "colors": "1.1.2"
      }
    },
    "jasminewd2": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/jasminewd2/-/jasminewd2-2.2.0.tgz",
      "integrity": "sha1-43zwsX8ZnM4jvqcbIDk5Uka07E4=",
      "dev": true
    },
    "js-base64": {
      "version": "2.5.1",
      "resolved": "https://registry.npmjs.org/js-base64/-/js-base64-2.5.1.tgz",
      "integrity": "sha512-M7kLczedRMYX4L8Mdh4MzyAMM9O5osx+4FcOQuTvr3A9F2D9S5JXheN0ewNbrvK2UatkTRhL5ejGmGSjNMiZuw==",
      "dev": true,
      "optional": true
    },
    "js-tokens": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/js-tokens/-/js-tokens-3.0.2.tgz",
      "integrity": "sha1-mGbfOVECEw449/mWvOtlRDIJwls=",
      "dev": true
    },
    "js-yaml": {
      "version": "3.12.1",
      "resolved": "https://registry.npmjs.org/js-yaml/-/js-yaml-3.12.1.tgz",
      "integrity": "sha512-um46hB9wNOKlwkHgiuyEVAybXBjwFUV0Z/RaHJblRd9DXltue9FTYvzCr9ErQrK9Adz5MU4gHWVaNUfdmrC8qA==",
      "dev": true,
      "requires": {
        "argparse": "^1.0.7",
        "esprima": "^4.0.0"
      },
      "dependencies": {
        "esprima": {
          "version": "4.0.1",
          "resolved": "https://registry.npmjs.org/esprima/-/esprima-4.0.1.tgz",
          "integrity": "sha512-eGuFFw7Upda+g4p+QHvnW0RyTX/SVeJBDM/gCtMARO0cLuT2HcEKnTPvhjV6aGeqrCB/sbNop0Kszm0jsaWU4A==",
          "dev": true
        }
      }
    },
    "jsbn": {
      "version": "0.1.1",
      "resolved": "https://registry.npmjs.org/jsbn/-/jsbn-0.1.1.tgz",
      "integrity": "sha1-peZUwuWi3rXyAdls77yoDA7y9RM=",
      "dev": true
    },
    "jsesc": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/jsesc/-/jsesc-1.3.0.tgz",
      "integrity": "sha1-RsP+yMGJKxKwgz25vHYiF226s0s=",
      "dev": true
    },
    "json-parse-better-errors": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/json-parse-better-errors/-/json-parse-better-errors-1.0.2.tgz",
      "integrity": "sha512-mrqyZKfX5EhL7hvqcV6WG1yYjnjeuYDzDhhcAAUrq8Po85NBQBJP+ZDUT75qZQ98IkUoBqdkExkukOU7Ts2wrw==",
      "dev": true
    },
    "json-schema": {
      "version": "0.2.3",
      "resolved": "https://registry.npmjs.org/json-schema/-/json-schema-0.2.3.tgz",
      "integrity": "sha1-tIDIkuWaLwWVTOcnvT8qTogvnhM=",
      "dev": true
    },
    "json-schema-traverse": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/json-schema-traverse/-/json-schema-traverse-0.4.1.tgz",
      "integrity": "sha512-xbbCH5dCYU5T8LcEhhuh7HJ88HXuW3qsI3Y0zOZFKfZEHcpWiHU/Jxzk629Brsab/mMiHQti9wMP+845RPe3Vg==",
      "dev": true
    },
    "json-stringify-safe": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/json-stringify-safe/-/json-stringify-safe-5.0.1.tgz",
      "integrity": "sha1-Epai1Y/UXxmg9s4B1lcB4sc1tus=",
      "dev": true
    },
    "json3": {
      "version": "3.3.2",
      "resolved": "https://registry.npmjs.org/json3/-/json3-3.3.2.tgz",
      "integrity": "sha1-PAQ0dD35Pi9cQq7nsZvLSDV19OE=",
      "dev": true
    },
    "json5": {
      "version": "0.5.1",
      "resolved": "https://registry.npmjs.org/json5/-/json5-0.5.1.tgz",
      "integrity": "sha1-Hq3nrMASA0rYTiOWdn6tn6VJWCE=",
      "dev": true
    },
    "jsonparse": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/jsonparse/-/jsonparse-1.3.1.tgz",
      "integrity": "sha1-P02uSpH6wxX3EGL4UhzCOfE2YoA=",
      "dev": true
    },
    "jsprim": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/jsprim/-/jsprim-1.4.1.tgz",
      "integrity": "sha1-MT5mvB5cwG5Di8G3SZwuXFastqI=",
      "dev": true,
      "requires": {
        "assert-plus": "1.0.0",
        "extsprintf": "1.3.0",
        "json-schema": "0.2.3",
        "verror": "1.10.0"
      }
    },
    "jszip": {
      "version": "3.1.5",
      "resolved": "https://registry.npmjs.org/jszip/-/jszip-3.1.5.tgz",
      "integrity": "sha512-5W8NUaFRFRqTOL7ZDDrx5qWHJyBXy6velVudIzQUSoqAAYqzSh2Z7/m0Rf1QbmQJccegD0r+YZxBjzqoBiEeJQ==",
      "dev": true,
      "requires": {
        "core-js": "~2.3.0",
        "es6-promise": "~3.0.2",
        "lie": "~3.1.0",
        "pako": "~1.0.2",
        "readable-stream": "~2.0.6"
      },
      "dependencies": {
        "core-js": {
          "version": "2.3.0",
          "resolved": "https://registry.npmjs.org/core-js/-/core-js-2.3.0.tgz",
          "integrity": "sha1-+rg/uwstjchfpjbEudNMdUIMbWU=",
          "dev": true
        },
        "es6-promise": {
          "version": "3.0.2",
          "resolved": "https://registry.npmjs.org/es6-promise/-/es6-promise-3.0.2.tgz",
          "integrity": "sha1-AQ1YWEI6XxGJeWZfRkhqlcbuK7Y=",
          "dev": true
        },
        "process-nextick-args": {
          "version": "1.0.7",
          "resolved": "https://registry.npmjs.org/process-nextick-args/-/process-nextick-args-1.0.7.tgz",
          "integrity": "sha1-FQ4gt1ZZCtP5EJPyWk8q2L/zC6M=",
          "dev": true
        },
        "readable-stream": {
          "version": "2.0.6",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-2.0.6.tgz",
          "integrity": "sha1-j5A0HmilPMySh4jaz80Rs265t44=",
          "dev": true,
          "requires": {
            "core-util-is": "~1.0.0",
            "inherits": "~2.0.1",
            "isarray": "~1.0.0",
            "process-nextick-args": "~1.0.6",
            "string_decoder": "~0.10.x",
            "util-deprecate": "~1.0.1"
          }
        },
        "string_decoder": {
          "version": "0.10.31",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-0.10.31.tgz",
          "integrity": "sha1-YuIDvEF2bGwoyfyEMB2rHFMQ+pQ=",
          "dev": true
        }
      }
    },
    "karma": {
      "version": "3.1.4",
      "resolved": "https://registry.npmjs.org/karma/-/karma-3.1.4.tgz",
      "integrity": "sha512-31Vo8Qr5glN+dZEVIpnPCxEGleqE0EY6CtC2X9TagRV3rRQ3SNrvfhddICkJgUK3AgqpeKSZau03QumTGhGoSw==",
      "dev": true,
      "requires": {
        "bluebird": "^3.3.0",
        "body-parser": "^1.16.1",
        "chokidar": "^2.0.3",
        "colors": "^1.1.0",
        "combine-lists": "^1.0.0",
        "connect": "^3.6.0",
        "core-js": "^2.2.0",
        "di": "^0.0.1",
        "dom-serialize": "^2.2.0",
        "expand-braces": "^0.1.1",
        "flatted": "^2.0.0",
        "glob": "^7.1.1",
        "graceful-fs": "^4.1.2",
        "http-proxy": "^1.13.0",
        "isbinaryfile": "^3.0.0",
        "lodash": "^4.17.5",
        "log4js": "^3.0.0",
        "mime": "^2.3.1",
        "minimatch": "^3.0.2",
        "optimist": "^0.6.1",
        "qjobs": "^1.1.4",
        "range-parser": "^1.2.0",
        "rimraf": "^2.6.0",
        "safe-buffer": "^5.0.1",
        "socket.io": "2.1.1",
        "source-map": "^0.6.1",
        "tmp": "0.0.33",
        "useragent": "2.3.0"
      },
      "dependencies": {
        "mime": {
          "version": "2.4.0",
          "resolved": "https://registry.npmjs.org/mime/-/mime-2.4.0.tgz",
          "integrity": "sha512-ikBcWwyqXQSHKtciCcctu9YfPbFYZ4+gbHEmE0Q8jzcTYQg5dHCr3g2wwAZjPoJfQVXZq6KXAjpXOTf5/cjT7w==",
          "dev": true
        },
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "karma-chrome-launcher": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/karma-chrome-launcher/-/karma-chrome-launcher-2.2.0.tgz",
      "integrity": "sha512-uf/ZVpAabDBPvdPdveyk1EPgbnloPvFFGgmRhYLTDH7gEB4nZdSBk8yTU47w1g/drLSx5uMOkjKk7IWKfWg/+w==",
      "dev": true,
      "requires": {
        "fs-access": "^1.0.0",
        "which": "^1.2.1"
      }
    },
    "karma-coverage-istanbul-reporter": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/karma-coverage-istanbul-reporter/-/karma-coverage-istanbul-reporter-2.0.4.tgz",
      "integrity": "sha512-xJS7QSQIVU6VK9HuJ/ieE5yynxKhjCCkd96NLY/BX/HXsx0CskU9JJiMQbd4cHALiddMwI4OWh1IIzeWrsavJw==",
      "dev": true,
      "requires": {
        "istanbul-api": "^2.0.5",
        "minimatch": "^3.0.4"
      }
    },
    "karma-jasmine": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/karma-jasmine/-/karma-jasmine-1.1.2.tgz",
      "integrity": "sha1-OU8rJf+0pkS5rabyLUQ+L9CIhsM=",
      "dev": true
    },
    "karma-jasmine-html-reporter": {
      "version": "0.2.2",
      "resolved": "https://registry.npmjs.org/karma-jasmine-html-reporter/-/karma-jasmine-html-reporter-0.2.2.tgz",
      "integrity": "sha1-SKjl7xiAdhfuK14zwRlMNbQ5Ukw=",
      "dev": true,
      "requires": {
        "karma-jasmine": "^1.0.2"
      }
    },
    "karma-source-map-support": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/karma-source-map-support/-/karma-source-map-support-1.3.0.tgz",
      "integrity": "sha512-HcPqdAusNez/ywa+biN4EphGz62MmQyPggUsDfsHqa7tSe4jdsxgvTKuDfIazjL+IOxpVWyT7Pr4dhAV+sxX5Q==",
      "dev": true,
      "requires": {
        "source-map-support": "^0.5.5"
      }
    },
    "killable": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/killable/-/killable-1.0.1.tgz",
      "integrity": "sha512-LzqtLKlUwirEUyl/nicirVmNiPvYs7l5n8wOPP7fyJVpUPkvCnW/vuiXGpylGUlnPDnB7311rARzAt3Mhswpjg==",
      "dev": true
    },
    "kind-of": {
      "version": "6.0.2",
      "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-6.0.2.tgz",
      "integrity": "sha512-s5kLOcnH0XqDO+FvuaLX8DDjZ18CGFk7VygH40QoKPUQhW4e2rvM0rwUq0t8IQDOwYSeLK01U90OjzBTme2QqA==",
      "dev": true
    },
    "lcid": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/lcid/-/lcid-1.0.0.tgz",
      "integrity": "sha1-MIrMr6C8SDo4Z7S28rlQYlHRuDU=",
      "dev": true,
      "requires": {
        "invert-kv": "^1.0.0"
      }
    },
    "less": {
      "version": "3.9.0",
      "resolved": "https://registry.npmjs.org/less/-/less-3.9.0.tgz",
      "integrity": "sha512-31CmtPEZraNUtuUREYjSqRkeETFdyEHSEPAGq4erDlUXtda7pzNmctdljdIagSb589d/qXGWiiP31R5JVf+v0w==",
      "dev": true,
      "requires": {
        "clone": "^2.1.2",
        "errno": "^0.1.1",
        "graceful-fs": "^4.1.2",
        "image-size": "~0.5.0",
        "mime": "^1.4.1",
        "mkdirp": "^0.5.0",
        "promise": "^7.1.1",
        "request": "^2.83.0",
        "source-map": "~0.6.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true,
          "optional": true
        }
      }
    },
    "less-loader": {
      "version": "4.1.0",
      "resolved": "https://registry.npmjs.org/less-loader/-/less-loader-4.1.0.tgz",
      "integrity": "sha512-KNTsgCE9tMOM70+ddxp9yyt9iHqgmSs0yTZc5XH5Wo+g80RWRIYNqE58QJKm/yMud5wZEvz50ugRDuzVIkyahg==",
      "dev": true,
      "requires": {
        "clone": "^2.1.1",
        "loader-utils": "^1.1.0",
        "pify": "^3.0.0"
      }
    },
    "levn": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/levn/-/levn-0.3.0.tgz",
      "integrity": "sha1-OwmSTt+fCDwEkP3UwLxEIeBHZO4=",
      "dev": true,
      "requires": {
        "prelude-ls": "~1.1.2",
        "type-check": "~0.3.2"
      }
    },
    "license-webpack-plugin": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/license-webpack-plugin/-/license-webpack-plugin-2.0.4.tgz",
      "integrity": "sha512-FQgOqrrIcD4C/VQo6ecWgXZULK5rs0kIDJtHcSVO6SBUrD63kEHZwmKOvBTquFQSgMQn/yeH68qooKDfqiBF2Q==",
      "dev": true,
      "requires": {
        "@types/webpack-sources": "^0.1.5",
        "webpack-sources": "^1.2.0"
      }
    },
    "lie": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/lie/-/lie-3.1.1.tgz",
      "integrity": "sha1-mkNrLMd0bKWd56QfpGmz77dr2H4=",
      "dev": true,
      "requires": {
        "immediate": "~3.0.5"
      }
    },
    "load-json-file": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/load-json-file/-/load-json-file-1.1.0.tgz",
      "integrity": "sha1-lWkFcI1YtLq0wiYbBPWfMcmTdMA=",
      "dev": true,
      "requires": {
        "graceful-fs": "^4.1.2",
        "parse-json": "^2.2.0",
        "pify": "^2.0.0",
        "pinkie-promise": "^2.0.0",
        "strip-bom": "^2.0.0"
      },
      "dependencies": {
        "pify": {
          "version": "2.3.0",
          "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
          "integrity": "sha1-7RQaasBDqEnqWISY59yosVMw6Qw=",
          "dev": true
        }
      }
    },
    "loader-runner": {
      "version": "2.4.0",
      "resolved": "https://registry.npmjs.org/loader-runner/-/loader-runner-2.4.0.tgz",
      "integrity": "sha512-Jsmr89RcXGIwivFY21FcRrisYZfvLMTWx5kOLc+JTxtpBOG6xML0vzbc6SEQG2FO9/4Fc3wW4LVcB5DmGflaRw==",
      "dev": true
    },
    "loader-utils": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/loader-utils/-/loader-utils-1.1.0.tgz",
      "integrity": "sha1-yYrvSIvM7aL/teLeZG1qdUQp9c0=",
      "dev": true,
      "requires": {
        "big.js": "^3.1.3",
        "emojis-list": "^2.0.0",
        "json5": "^0.5.0"
      }
    },
    "locate-path": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/locate-path/-/locate-path-2.0.0.tgz",
      "integrity": "sha1-K1aLJl7slExtnA3pw9u7ygNUzY4=",
      "dev": true,
      "requires": {
        "p-locate": "^2.0.0",
        "path-exists": "^3.0.0"
      }
    },
    "lodash": {
      "version": "4.17.11",
      "resolved": "https://registry.npmjs.org/lodash/-/lodash-4.17.11.tgz",
      "integrity": "sha512-cQKh8igo5QUhZ7lg38DYWAxMvjSAKG0A8wGSVimP07SIUEK2UO+arSRKbRZWtelMtN5V0Hkwh5ryOto/SshYIg==",
      "dev": true
    },
    "lodash.assign": {
      "version": "4.2.0",
      "resolved": "https://registry.npmjs.org/lodash.assign/-/lodash.assign-4.2.0.tgz",
      "integrity": "sha1-DZnzzNem0mHRm9rrkkUAXShYCOc=",
      "dev": true,
      "optional": true
    },
    "lodash.clonedeep": {
      "version": "4.5.0",
      "resolved": "https://registry.npmjs.org/lodash.clonedeep/-/lodash.clonedeep-4.5.0.tgz",
      "integrity": "sha1-4j8/nE+Pvd6HJSnBBxhXoIblzO8=",
      "dev": true
    },
    "lodash.debounce": {
      "version": "4.0.8",
      "resolved": "https://registry.npmjs.org/lodash.debounce/-/lodash.debounce-4.0.8.tgz",
      "integrity": "sha1-gteb/zCmfEAF/9XiUVMArZyk168=",
      "dev": true
    },
    "lodash.mergewith": {
      "version": "4.6.1",
      "resolved": "https://registry.npmjs.org/lodash.mergewith/-/lodash.mergewith-4.6.1.tgz",
      "integrity": "sha512-eWw5r+PYICtEBgrBE5hhlT6aAa75f411bgDz/ZL2KZqYV03USvucsxcHUIlGTDTECs1eunpI7HOV7U+WLDvNdQ==",
      "dev": true,
      "optional": true
    },
    "lodash.tail": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/lodash.tail/-/lodash.tail-4.1.1.tgz",
      "integrity": "sha1-0jM6NtnncXyK0vfKyv7HwytERmQ=",
      "dev": true
    },
    "log4js": {
      "version": "3.0.6",
      "resolved": "https://registry.npmjs.org/log4js/-/log4js-3.0.6.tgz",
      "integrity": "sha512-ezXZk6oPJCWL483zj64pNkMuY/NcRX5MPiB0zE6tjZM137aeusrOnW1ecxgF9cmwMWkBMhjteQxBPoZBh9FDxQ==",
      "dev": true,
      "requires": {
        "circular-json": "^0.5.5",
        "date-format": "^1.2.0",
        "debug": "^3.1.0",
        "rfdc": "^1.1.2",
        "streamroller": "0.7.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.2.6",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
          "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        }
      }
    },
    "loglevel": {
      "version": "1.6.1",
      "resolved": "https://registry.npmjs.org/loglevel/-/loglevel-1.6.1.tgz",
      "integrity": "sha1-4PyVEztu8nbNyIh82vJKpvFW+Po=",
      "dev": true
    },
    "loose-envify": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/loose-envify/-/loose-envify-1.4.0.tgz",
      "integrity": "sha512-lyuxPGr/Wfhrlem2CL/UcnUc1zcqKAImBDzukY7Y5F/yQiNdko6+fRLevlw1HgMySw7f611UIY408EtxRSoK3Q==",
      "dev": true,
      "requires": {
        "js-tokens": "^3.0.0 || ^4.0.0"
      }
    },
    "loud-rejection": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/loud-rejection/-/loud-rejection-1.6.0.tgz",
      "integrity": "sha1-W0b4AUft7leIcPCG0Eghz5mOVR8=",
      "dev": true,
      "optional": true,
      "requires": {
        "currently-unhandled": "^0.4.1",
        "signal-exit": "^3.0.0"
      }
    },
    "lru-cache": {
      "version": "4.1.5",
      "resolved": "https://registry.npmjs.org/lru-cache/-/lru-cache-4.1.5.tgz",
      "integrity": "sha512-sWZlbEP2OsHNkXrMl5GYk/jKk70MBng6UU4YI/qGDYbgf6YbP4EvmqISbXCoJiRKs+1bSpFHVgQxvJ17F2li5g==",
      "dev": true,
      "requires": {
        "pseudomap": "^1.0.2",
        "yallist": "^2.1.2"
      }
    },
    "magic-string": {
      "version": "0.25.1",
      "resolved": "https://registry.npmjs.org/magic-string/-/magic-string-0.25.1.tgz",
      "integrity": "sha512-sCuTz6pYom8Rlt4ISPFn6wuFodbKMIHUMv4Qko9P17dpxb7s52KJTmRuZZqHdGmLCK9AOcDare039nRIcfdkEg==",
      "dev": true,
      "requires": {
        "sourcemap-codec": "^1.4.1"
      }
    },
    "make-dir": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/make-dir/-/make-dir-1.3.0.tgz",
      "integrity": "sha512-2w31R7SJtieJJnQtGc7RVL2StM2vGYVfqUOvUDxH6bC6aJTxPxTF0GnIgCyu7tjockiUWAYQRbxa7vKn34s5sQ==",
      "dev": true,
      "requires": {
        "pify": "^3.0.0"
      }
    },
    "make-error": {
      "version": "1.3.5",
      "resolved": "https://registry.npmjs.org/make-error/-/make-error-1.3.5.tgz",
      "integrity": "sha512-c3sIjNUow0+8swNwVpqoH4YCShKNFkMaw6oH1mNS2haDZQqkeZFlHS3dhoeEbKKmJB4vXpJucU6oH75aDYeE9g==",
      "dev": true
    },
    "make-fetch-happen": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/make-fetch-happen/-/make-fetch-happen-4.0.1.tgz",
      "integrity": "sha512-7R5ivfy9ilRJ1EMKIOziwrns9fGeAD4bAha8EB7BIiBBLHm2KeTUGCrICFt2rbHfzheTLynv50GnNTK1zDTrcQ==",
      "dev": true,
      "requires": {
        "agentkeepalive": "^3.4.1",
        "cacache": "^11.0.1",
        "http-cache-semantics": "^3.8.1",
        "http-proxy-agent": "^2.1.0",
        "https-proxy-agent": "^2.2.1",
        "lru-cache": "^4.1.2",
        "mississippi": "^3.0.0",
        "node-fetch-npm": "^2.0.2",
        "promise-retry": "^1.1.1",
        "socks-proxy-agent": "^4.0.0",
        "ssri": "^6.0.0"
      },
      "dependencies": {
        "cacache": {
          "version": "11.3.2",
          "resolved": "https://registry.npmjs.org/cacache/-/cacache-11.3.2.tgz",
          "integrity": "sha512-E0zP4EPGDOaT2chM08Als91eYnf8Z+eH1awwwVsngUmgppfM5jjJ8l3z5vO5p5w/I3LsiXawb1sW0VY65pQABg==",
          "dev": true,
          "requires": {
            "bluebird": "^3.5.3",
            "chownr": "^1.1.1",
            "figgy-pudding": "^3.5.1",
            "glob": "^7.1.3",
            "graceful-fs": "^4.1.15",
            "lru-cache": "^5.1.1",
            "mississippi": "^3.0.0",
            "mkdirp": "^0.5.1",
            "move-concurrently": "^1.0.1",
            "promise-inflight": "^1.0.1",
            "rimraf": "^2.6.2",
            "ssri": "^6.0.1",
            "unique-filename": "^1.1.1",
            "y18n": "^4.0.0"
          },
          "dependencies": {
            "lru-cache": {
              "version": "5.1.1",
              "resolved": "https://registry.npmjs.org/lru-cache/-/lru-cache-5.1.1.tgz",
              "integrity": "sha512-KpNARQA3Iwv+jTA0utUVVbrh+Jlrr1Fv0e56GGzAFOXN7dk/FviaDW8LHmK52DlcH4WP2n6gI8vN1aesBFgo9w==",
              "dev": true,
              "requires": {
                "yallist": "^3.0.2"
              }
            }
          }
        },
        "mississippi": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/mississippi/-/mississippi-3.0.0.tgz",
          "integrity": "sha512-x471SsVjUtBRtcvd4BzKE9kFC+/2TeWgKCgw0bZcw1b9l2X3QX5vCWgF+KaZaYm87Ss//rHnWryupDrgLvmSkA==",
          "dev": true,
          "requires": {
            "concat-stream": "^1.5.0",
            "duplexify": "^3.4.2",
            "end-of-stream": "^1.1.0",
            "flush-write-stream": "^1.0.0",
            "from2": "^2.1.0",
            "parallel-transform": "^1.1.0",
            "pump": "^3.0.0",
            "pumpify": "^1.3.3",
            "stream-each": "^1.1.0",
            "through2": "^2.0.0"
          }
        },
        "pump": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/pump/-/pump-3.0.0.tgz",
          "integrity": "sha512-LwZy+p3SFs1Pytd/jYct4wpv49HiYCqd9Rlc5ZVdk0V+8Yzv6jR5Blk3TRmPL1ft69TxP0IMZGJ+WPFU2BFhww==",
          "dev": true,
          "requires": {
            "end-of-stream": "^1.1.0",
            "once": "^1.3.1"
          }
        },
        "ssri": {
          "version": "6.0.1",
          "resolved": "https://registry.npmjs.org/ssri/-/ssri-6.0.1.tgz",
          "integrity": "sha512-3Wge10hNcT1Kur4PDFwEieXSCMCJs/7WvSACcrMYrNp+b8kDL1/0wJch5Ni2WrtwEa2IO8OsVfeKIciKCDx/QA==",
          "dev": true,
          "requires": {
            "figgy-pudding": "^3.5.1"
          }
        },
        "yallist": {
          "version": "3.0.3",
          "resolved": "https://registry.npmjs.org/yallist/-/yallist-3.0.3.tgz",
          "integrity": "sha512-S+Zk8DEWE6oKpV+vI3qWkaK+jSbIK86pCwe2IF/xwIpQ8jEuxpw9NyaGjmp9+BoJv5FV2piqCDcoCtStppiq2A==",
          "dev": true
        }
      }
    },
    "map-age-cleaner": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/map-age-cleaner/-/map-age-cleaner-0.1.3.tgz",
      "integrity": "sha512-bJzx6nMoP6PDLPBFmg7+xRKeFZvFboMrGlxmNj9ClvX53KrmvM5bXFXEWjbz4cz1AFn+jWJ9z/DJSz7hrs0w3w==",
      "dev": true,
      "requires": {
        "p-defer": "^1.0.0"
      }
    },
    "map-cache": {
      "version": "0.2.2",
      "resolved": "https://registry.npmjs.org/map-cache/-/map-cache-0.2.2.tgz",
      "integrity": "sha1-wyq9C9ZSXZsFFkW7TyasXcmKDb8=",
      "dev": true
    },
    "map-obj": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/map-obj/-/map-obj-1.0.1.tgz",
      "integrity": "sha1-2TPOuSBdgr3PSIb2dCvcK03qFG0=",
      "dev": true
    },
    "map-visit": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/map-visit/-/map-visit-1.0.0.tgz",
      "integrity": "sha1-7Nyo8TFE5mDxtb1B8S80edmN+48=",
      "dev": true,
      "requires": {
        "object-visit": "^1.0.0"
      }
    },
    "math-random": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/math-random/-/math-random-1.0.4.tgz",
      "integrity": "sha512-rUxjysqif/BZQH2yhd5Aaq7vXMSx9NdEsQcyA07uEzIvxgI7zIr33gGsh+RU0/XjmQpCW7RsVof1vlkvQVCK5A==",
      "dev": true
    },
    "md5.js": {
      "version": "1.3.5",
      "resolved": "https://registry.npmjs.org/md5.js/-/md5.js-1.3.5.tgz",
      "integrity": "sha512-xitP+WxNPcTTOgnTJcrhM0xvdPepipPSf3I8EIpGKeFLjt3PlJLIDG3u8EX53ZIubkb+5U2+3rELYpEhHhzdkg==",
      "dev": true,
      "requires": {
        "hash-base": "^3.0.0",
        "inherits": "^2.0.1",
        "safe-buffer": "^5.1.2"
      }
    },
    "media-typer": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/media-typer/-/media-typer-0.3.0.tgz",
      "integrity": "sha1-hxDXrwqmJvj/+hzgAWhUUmMlV0g=",
      "dev": true
    },
    "mem": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/mem/-/mem-4.0.0.tgz",
      "integrity": "sha512-WQxG/5xYc3tMbYLXoXPm81ET2WDULiU5FxbuIoNbJqLOOI8zehXFdZuiUEgfdrU2mVB1pxBZUGlYORSrpuJreA==",
      "dev": true,
      "requires": {
        "map-age-cleaner": "^0.1.1",
        "mimic-fn": "^1.0.0",
        "p-is-promise": "^1.1.0"
      }
    },
    "memory-fs": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/memory-fs/-/memory-fs-0.4.1.tgz",
      "integrity": "sha1-OpoguEYlI+RHz7x+i7gO1me/xVI=",
      "dev": true,
      "requires": {
        "errno": "^0.1.3",
        "readable-stream": "^2.0.1"
      }
    },
    "meow": {
      "version": "3.7.0",
      "resolved": "https://registry.npmjs.org/meow/-/meow-3.7.0.tgz",
      "integrity": "sha1-cstmi0JSKCkKu/qFaJJYcwioAfs=",
      "dev": true,
      "optional": true,
      "requires": {
        "camelcase-keys": "^2.0.0",
        "decamelize": "^1.1.2",
        "loud-rejection": "^1.0.0",
        "map-obj": "^1.0.1",
        "minimist": "^1.1.3",
        "normalize-package-data": "^2.3.4",
        "object-assign": "^4.0.1",
        "read-pkg-up": "^1.0.1",
        "redent": "^1.0.0",
        "trim-newlines": "^1.0.0"
      },
      "dependencies": {
        "minimist": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/minimist/-/minimist-1.2.0.tgz",
          "integrity": "sha1-o1AIsg9BOD7sH7kU9M1d95omQoQ=",
          "dev": true,
          "optional": true
        }
      }
    },
    "merge-descriptors": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/merge-descriptors/-/merge-descriptors-1.0.1.tgz",
      "integrity": "sha1-sAqqVW3YtEVoFQ7J0blT8/kMu2E=",
      "dev": true
    },
    "methods": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/methods/-/methods-1.1.2.tgz",
      "integrity": "sha1-VSmk1nZUE07cxSZmVoNbD4Ua/O4=",
      "dev": true
    },
    "micromatch": {
      "version": "3.1.10",
      "resolved": "https://registry.npmjs.org/micromatch/-/micromatch-3.1.10.tgz",
      "integrity": "sha512-MWikgl9n9M3w+bpsY3He8L+w9eF9338xRl8IAO5viDizwSzziFEyUzo2xrrloB64ADbTf8uA8vRqqttDTOmccg==",
      "dev": true,
      "requires": {
        "arr-diff": "^4.0.0",
        "array-unique": "^0.3.2",
        "braces": "^2.3.1",
        "define-property": "^2.0.2",
        "extend-shallow": "^3.0.2",
        "extglob": "^2.0.4",
        "fragment-cache": "^0.2.1",
        "kind-of": "^6.0.2",
        "nanomatch": "^1.2.9",
        "object.pick": "^1.3.0",
        "regex-not": "^1.0.0",
        "snapdragon": "^0.8.1",
        "to-regex": "^3.0.2"
      }
    },
    "miller-rabin": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/miller-rabin/-/miller-rabin-4.0.1.tgz",
      "integrity": "sha512-115fLhvZVqWwHPbClyntxEVfVDfl9DLLTuJvq3g2O/Oxi8AiNouAHvDSzHS0viUJc+V5vm3eq91Xwqn9dp4jRA==",
      "dev": true,
      "requires": {
        "bn.js": "^4.0.0",
        "brorand": "^1.0.1"
      }
    },
    "mime": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/mime/-/mime-1.6.0.tgz",
      "integrity": "sha512-x0Vn8spI+wuJ1O6S7gnbaQg8Pxh4NNHb7KSINmEWKiPE4RKOplvijn+NkmYmmRgP68mc70j2EbeTFRsrswaQeg==",
      "dev": true,
      "optional": true
    },
    "mime-db": {
      "version": "1.37.0",
      "resolved": "https://registry.npmjs.org/mime-db/-/mime-db-1.37.0.tgz",
      "integrity": "sha512-R3C4db6bgQhlIhPU48fUtdVmKnflq+hRdad7IyKhtFj06VPNVdk2RhiYL3UjQIlso8L+YxAtFkobT0VK+S/ybg==",
      "dev": true
    },
    "mime-types": {
      "version": "2.1.21",
      "resolved": "https://registry.npmjs.org/mime-types/-/mime-types-2.1.21.tgz",
      "integrity": "sha512-3iL6DbwpyLzjR3xHSFNFeb9Nz/M8WDkX33t1GFQnFOllWk8pOrh/LSrB5OXlnlW5P9LH73X6loW/eogc+F5lJg==",
      "dev": true,
      "requires": {
        "mime-db": "~1.37.0"
      }
    },
    "mimic-fn": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/mimic-fn/-/mimic-fn-1.2.0.tgz",
      "integrity": "sha512-jf84uxzwiuiIVKiOLpfYk7N46TSy8ubTonmneY9vrpHNAnp0QBt2BxWV9dO3/j+BoVAb+a5G6YDPW3M5HOdMWQ==",
      "dev": true
    },
    "mini-css-extract-plugin": {
      "version": "0.4.4",
      "resolved": "https://registry.npmjs.org/mini-css-extract-plugin/-/mini-css-extract-plugin-0.4.4.tgz",
      "integrity": "sha512-o+Jm+ocb0asEngdM6FsZWtZsRzA8koFUudIDwYUfl94M3PejPHG7Vopw5hN9V8WsMkSFpm3tZP3Fesz89EyrfQ==",
      "dev": true,
      "requires": {
        "loader-utils": "^1.1.0",
        "schema-utils": "^1.0.0",
        "webpack-sources": "^1.1.0"
      }
    },
    "minimalistic-assert": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/minimalistic-assert/-/minimalistic-assert-1.0.1.tgz",
      "integrity": "sha512-UtJcAD4yEaGtjPezWuO9wC4nwUnVH/8/Im3yEHQP4b67cXlD/Qr9hdITCU1xDbSEXg2XKNaP8jsReV7vQd00/A==",
      "dev": true
    },
    "minimalistic-crypto-utils": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/minimalistic-crypto-utils/-/minimalistic-crypto-utils-1.0.1.tgz",
      "integrity": "sha1-9sAMHAsIIkblxNmd+4x8CDsrWCo=",
      "dev": true
    },
    "minimatch": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/minimatch/-/minimatch-3.0.4.tgz",
      "integrity": "sha512-yJHVQEhyqPLUTgt9B83PXu6W3rx4MvvHvSUvToogpwoGDOUQ+yDrR0HRot+yOCdCO7u4hX3pWft6kWBBcqh0UA==",
      "dev": true,
      "requires": {
        "brace-expansion": "^1.1.7"
      }
    },
    "minimist": {
      "version": "0.0.8",
      "resolved": "https://registry.npmjs.org/minimist/-/minimist-0.0.8.tgz",
      "integrity": "sha1-hX/Kv8M5fSYluCKCYuhqp6ARsF0=",
      "dev": true
    },
    "minipass": {
      "version": "2.3.5",
      "resolved": "https://registry.npmjs.org/minipass/-/minipass-2.3.5.tgz",
      "integrity": "sha512-Gi1W4k059gyRbyVUZQ4mEqLm0YIUiGYfvxhF6SIlk3ui1WVxMTGfGdQ2SInh3PDrRTVvPKgULkpJtT4RH10+VA==",
      "dev": true,
      "requires": {
        "safe-buffer": "^5.1.2",
        "yallist": "^3.0.0"
      },
      "dependencies": {
        "yallist": {
          "version": "3.0.3",
          "resolved": "https://registry.npmjs.org/yallist/-/yallist-3.0.3.tgz",
          "integrity": "sha512-S+Zk8DEWE6oKpV+vI3qWkaK+jSbIK86pCwe2IF/xwIpQ8jEuxpw9NyaGjmp9+BoJv5FV2piqCDcoCtStppiq2A==",
          "dev": true
        }
      }
    },
    "minizlib": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/minizlib/-/minizlib-1.2.1.tgz",
      "integrity": "sha512-7+4oTUOWKg7AuL3vloEWekXY2/D20cevzsrNT2kGWm+39J9hGTCBv8VI5Pm5lXZ/o3/mdR4f8rflAPhnQb8mPA==",
      "dev": true,
      "requires": {
        "minipass": "^2.2.1"
      }
    },
    "mississippi": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/mississippi/-/mississippi-2.0.0.tgz",
      "integrity": "sha512-zHo8v+otD1J10j/tC+VNoGK9keCuByhKovAvdn74dmxJl9+mWHnx6EMsDN4lgRoMI/eYo2nchAxniIbUPb5onw==",
      "dev": true,
      "requires": {
        "concat-stream": "^1.5.0",
        "duplexify": "^3.4.2",
        "end-of-stream": "^1.1.0",
        "flush-write-stream": "^1.0.0",
        "from2": "^2.1.0",
        "parallel-transform": "^1.1.0",
        "pump": "^2.0.1",
        "pumpify": "^1.3.3",
        "stream-each": "^1.1.0",
        "through2": "^2.0.0"
      }
    },
    "mixin-deep": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/mixin-deep/-/mixin-deep-1.3.1.tgz",
      "integrity": "sha512-8ZItLHeEgaqEvd5lYBXfm4EZSFCX29Jb9K+lAHhDKzReKBQKj3R+7NOF6tjqYi9t4oI8VUfaWITJQm86wnXGNQ==",
      "dev": true,
      "requires": {
        "for-in": "^1.0.2",
        "is-extendable": "^1.0.1"
      },
      "dependencies": {
        "is-extendable": {
          "version": "1.0.1",
          "resolved": "https://registry.npmjs.org/is-extendable/-/is-extendable-1.0.1.tgz",
          "integrity": "sha512-arnXMxT1hhoKo9k1LZdmlNyJdDDfy2v0fXjFlmok4+i8ul/6WlbVge9bhM74OpNPQPMGUToDtz+KXa1PneJxOA==",
          "dev": true,
          "requires": {
            "is-plain-object": "^2.0.4"
          }
        }
      }
    },
    "mixin-object": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/mixin-object/-/mixin-object-2.0.1.tgz",
      "integrity": "sha1-T7lJRB2rGCVA8f4DW6YOGUel5X4=",
      "dev": true,
      "requires": {
        "for-in": "^0.1.3",
        "is-extendable": "^0.1.1"
      },
      "dependencies": {
        "for-in": {
          "version": "0.1.8",
          "resolved": "https://registry.npmjs.org/for-in/-/for-in-0.1.8.tgz",
          "integrity": "sha1-2Hc5COMSVhCZUrH9ubP6hn0ndeE=",
          "dev": true
        }
      }
    },
    "mkdirp": {
      "version": "0.5.1",
      "resolved": "https://registry.npmjs.org/mkdirp/-/mkdirp-0.5.1.tgz",
      "integrity": "sha1-MAV0OOrGz3+MR2fzhkjWaX11yQM=",
      "dev": true,
      "requires": {
        "minimist": "0.0.8"
      }
    },
    "move-concurrently": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/move-concurrently/-/move-concurrently-1.0.1.tgz",
      "integrity": "sha1-viwAX9oy4LKa8fBdfEszIUxwH5I=",
      "dev": true,
      "requires": {
        "aproba": "^1.1.1",
        "copy-concurrently": "^1.0.0",
        "fs-write-stream-atomic": "^1.0.8",
        "mkdirp": "^0.5.1",
        "rimraf": "^2.5.4",
        "run-queue": "^1.0.3"
      }
    },
    "ms": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/ms/-/ms-2.0.0.tgz",
      "integrity": "sha1-VgiurfwAvmwpAd9fmGF4jeDVl8g=",
      "dev": true
    },
    "multicast-dns": {
      "version": "6.2.3",
      "resolved": "https://registry.npmjs.org/multicast-dns/-/multicast-dns-6.2.3.tgz",
      "integrity": "sha512-ji6J5enbMyGRHIAkAOu3WdV8nggqviKCEKtXcOqfphZZtQrmHKycfynJ2V7eVPUA4NhJ6V7Wf4TmGbTwKE9B6g==",
      "dev": true,
      "requires": {
        "dns-packet": "^1.3.1",
        "thunky": "^1.0.2"
      }
    },
    "multicast-dns-service-types": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/multicast-dns-service-types/-/multicast-dns-service-types-1.1.0.tgz",
      "integrity": "sha1-iZ8R2WhuXgXLkbNdXw5jt3PPyQE=",
      "dev": true
    },
    "mute-stream": {
      "version": "0.0.7",
      "resolved": "https://registry.npmjs.org/mute-stream/-/mute-stream-0.0.7.tgz",
      "integrity": "sha1-MHXOk7whuPq0PhvE2n6BFe0ee6s=",
      "dev": true
    },
    "nan": {
      "version": "2.12.1",
      "resolved": "https://registry.npmjs.org/nan/-/nan-2.12.1.tgz",
      "integrity": "sha512-JY7V6lRkStKcKTvHO5NVSQRv+RV+FIL5pvDoLiAtSL9pKlC5x9PKQcZDsq7m4FO4d57mkhC6Z+QhAh3Jdk5JFw==",
      "dev": true,
      "optional": true
    },
    "nanomatch": {
      "version": "1.2.13",
      "resolved": "https://registry.npmjs.org/nanomatch/-/nanomatch-1.2.13.tgz",
      "integrity": "sha512-fpoe2T0RbHwBTBUOftAfBPaDEi06ufaUai0mE6Yn1kacc3SnTErfb/h+X94VXzI64rKFHYImXSvdwGGCmwOqCA==",
      "dev": true,
      "requires": {
        "arr-diff": "^4.0.0",
        "array-unique": "^0.3.2",
        "define-property": "^2.0.2",
        "extend-shallow": "^3.0.2",
        "fragment-cache": "^0.2.1",
        "is-windows": "^1.0.2",
        "kind-of": "^6.0.2",
        "object.pick": "^1.3.0",
        "regex-not": "^1.0.0",
        "snapdragon": "^0.8.1",
        "to-regex": "^3.0.1"
      }
    },
    "negotiator": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/negotiator/-/negotiator-0.6.1.tgz",
      "integrity": "sha1-KzJxhOiZIQEXeyhWP7XnECrNDKk=",
      "dev": true
    },
    "neo-async": {
      "version": "2.6.0",
      "resolved": "https://registry.npmjs.org/neo-async/-/neo-async-2.6.0.tgz",
      "integrity": "sha512-MFh0d/Wa7vkKO3Y3LlacqAEeHK0mckVqzDieUKTT+KGxi+zIpeVsFxymkIiRpbpDziHc290Xr9A1O4Om7otoRA==",
      "dev": true
    },
    "nice-try": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/nice-try/-/nice-try-1.0.5.tgz",
      "integrity": "sha512-1nh45deeb5olNY7eX82BkPO7SSxR5SSYJiPTrTdFUVYwAl8CKMA5N9PjTYkHiRjisVcxcQ1HXdLhx2qxxJzLNQ==",
      "dev": true
    },
    "node-fetch-npm": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/node-fetch-npm/-/node-fetch-npm-2.0.2.tgz",
      "integrity": "sha512-nJIxm1QmAj4v3nfCvEeCrYSoVwXyxLnaPBK5W1W5DGEJwjlKuC2VEUycGw5oxk+4zZahRrB84PUJJgEmhFTDFw==",
      "dev": true,
      "requires": {
        "encoding": "^0.1.11",
        "json-parse-better-errors": "^1.0.0",
        "safe-buffer": "^5.1.1"
      }
    },
    "node-forge": {
      "version": "0.7.5",
      "resolved": "https://registry.npmjs.org/node-forge/-/node-forge-0.7.5.tgz",
      "integrity": "sha512-MmbQJ2MTESTjt3Gi/3yG1wGpIMhUfcIypUCGtTizFR9IiccFwxSpfp0vtIZlkFclEqERemxfnSdZEMR9VqqEFQ==",
      "dev": true
    },
    "node-gyp": {
      "version": "3.8.0",
      "resolved": "https://registry.npmjs.org/node-gyp/-/node-gyp-3.8.0.tgz",
      "integrity": "sha512-3g8lYefrRRzvGeSowdJKAKyks8oUpLEd/DyPV4eMhVlhJ0aNaZqIrNUIPuEWWTAoPqyFkfGrM67MC69baqn6vA==",
      "dev": true,
      "optional": true,
      "requires": {
        "fstream": "^1.0.0",
        "glob": "^7.0.3",
        "graceful-fs": "^4.1.2",
        "mkdirp": "^0.5.0",
        "nopt": "2 || 3",
        "npmlog": "0 || 1 || 2 || 3 || 4",
        "osenv": "0",
        "request": "^2.87.0",
        "rimraf": "2",
        "semver": "~5.3.0",
        "tar": "^2.0.0",
        "which": "1"
      },
      "dependencies": {
        "semver": {
          "version": "5.3.0",
          "resolved": "https://registry.npmjs.org/semver/-/semver-5.3.0.tgz",
          "integrity": "sha1-myzl094C0XxgEq0yaqa00M9U+U8=",
          "dev": true,
          "optional": true
        }
      }
    },
    "node-libs-browser": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/node-libs-browser/-/node-libs-browser-2.2.0.tgz",
      "integrity": "sha512-5MQunG/oyOaBdttrL40dA7bUfPORLRWMUJLQtMg7nluxUvk5XwnLdL9twQHFAjRx/y7mIMkLKT9++qPbbk6BZA==",
      "dev": true,
      "requires": {
        "assert": "^1.1.1",
        "browserify-zlib": "^0.2.0",
        "buffer": "^4.3.0",
        "console-browserify": "^1.1.0",
        "constants-browserify": "^1.0.0",
        "crypto-browserify": "^3.11.0",
        "domain-browser": "^1.1.1",
        "events": "^3.0.0",
        "https-browserify": "^1.0.0",
        "os-browserify": "^0.3.0",
        "path-browserify": "0.0.0",
        "process": "^0.11.10",
        "punycode": "^1.2.4",
        "querystring-es3": "^0.2.0",
        "readable-stream": "^2.3.3",
        "stream-browserify": "^2.0.1",
        "stream-http": "^2.7.2",
        "string_decoder": "^1.0.0",
        "timers-browserify": "^2.0.4",
        "tty-browserify": "0.0.0",
        "url": "^0.11.0",
        "util": "^0.11.0",
        "vm-browserify": "0.0.4"
      },
      "dependencies": {
        "punycode": {
          "version": "1.4.1",
          "resolved": "https://registry.npmjs.org/punycode/-/punycode-1.4.1.tgz",
          "integrity": "sha1-wNWmOycYgArY4esPpSachN1BhF4=",
          "dev": true
        }
      }
    },
    "node-releases": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/node-releases/-/node-releases-1.1.3.tgz",
      "integrity": "sha512-6VrvH7z6jqqNFY200kdB6HdzkgM96Oaj9v3dqGfgp6mF+cHmU4wyQKZ2/WPDRVoR0Jz9KqbamaBN0ZhdUaysUQ==",
      "dev": true,
      "requires": {
        "semver": "^5.3.0"
      }
    },
    "node-sass": {
      "version": "4.10.0",
      "resolved": "https://registry.npmjs.org/node-sass/-/node-sass-4.10.0.tgz",
      "integrity": "sha512-fDQJfXszw6vek63Fe/ldkYXmRYK/QS6NbvM3i5oEo9ntPDy4XX7BcKZyTKv+/kSSxRtXXc7l+MSwEmYc0CSy6Q==",
      "dev": true,
      "optional": true,
      "requires": {
        "async-foreach": "^0.1.3",
        "chalk": "^1.1.1",
        "cross-spawn": "^3.0.0",
        "gaze": "^1.0.0",
        "get-stdin": "^4.0.1",
        "glob": "^7.0.3",
        "in-publish": "^2.0.0",
        "lodash.assign": "^4.2.0",
        "lodash.clonedeep": "^4.3.2",
        "lodash.mergewith": "^4.6.0",
        "meow": "^3.7.0",
        "mkdirp": "^0.5.1",
        "nan": "^2.10.0",
        "node-gyp": "^3.8.0",
        "npmlog": "^4.0.0",
        "request": "^2.88.0",
        "sass-graph": "^2.2.4",
        "stdout-stream": "^1.4.0",
        "true-case-path": "^1.0.2"
      },
      "dependencies": {
        "ansi-styles": {
          "version": "2.2.1",
          "resolved": "https://registry.npmjs.org/ansi-styles/-/ansi-styles-2.2.1.tgz",
          "integrity": "sha1-tDLdM1i2NM914eRmQ2gkBTPB3b4=",
          "dev": true,
          "optional": true
        },
        "chalk": {
          "version": "1.1.3",
          "resolved": "https://registry.npmjs.org/chalk/-/chalk-1.1.3.tgz",
          "integrity": "sha1-qBFcVeSnAv5NFQq9OHKCKn4J/Jg=",
          "dev": true,
          "optional": true,
          "requires": {
            "ansi-styles": "^2.2.1",
            "escape-string-regexp": "^1.0.2",
            "has-ansi": "^2.0.0",
            "strip-ansi": "^3.0.0",
            "supports-color": "^2.0.0"
          }
        },
        "supports-color": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-2.0.0.tgz",
          "integrity": "sha1-U10EXOa2Nj+kARcIRimZXp3zJMc=",
          "dev": true,
          "optional": true
        }
      }
    },
    "nopt": {
      "version": "3.0.6",
      "resolved": "https://registry.npmjs.org/nopt/-/nopt-3.0.6.tgz",
      "integrity": "sha1-xkZdvwirzU2zWTF/eaxopkayj/k=",
      "dev": true,
      "requires": {
        "abbrev": "1"
      }
    },
    "normalize-package-data": {
      "version": "2.4.0",
      "resolved": "https://registry.npmjs.org/normalize-package-data/-/normalize-package-data-2.4.0.tgz",
      "integrity": "sha512-9jjUFbTPfEy3R/ad/2oNbKtW9Hgovl5O1FvFWKkKblNXoN/Oou6+9+KKohPK13Yc3/TyunyWhJp6gvRNR/PPAw==",
      "dev": true,
      "requires": {
        "hosted-git-info": "^2.1.4",
        "is-builtin-module": "^1.0.0",
        "semver": "2 || 3 || 4 || 5",
        "validate-npm-package-license": "^3.0.1"
      }
    },
    "normalize-path": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/normalize-path/-/normalize-path-2.1.1.tgz",
      "integrity": "sha1-GrKLVW4Zg2Oowab35vogE3/mrtk=",
      "dev": true,
      "requires": {
        "remove-trailing-separator": "^1.0.1"
      }
    },
    "normalize-range": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/normalize-range/-/normalize-range-0.1.2.tgz",
      "integrity": "sha1-LRDAa9/TEuqXd2laTShDlFa3WUI=",
      "dev": true
    },
    "npm-bundled": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/npm-bundled/-/npm-bundled-1.0.5.tgz",
      "integrity": "sha512-m/e6jgWu8/v5niCUKQi9qQl8QdeEduFA96xHDDzFGqly0OOjI7c+60KM/2sppfnUU9JJagf+zs+yGhqSOFj71g==",
      "dev": true
    },
    "npm-package-arg": {
      "version": "6.1.0",
      "resolved": "https://registry.npmjs.org/npm-package-arg/-/npm-package-arg-6.1.0.tgz",
      "integrity": "sha512-zYbhP2k9DbJhA0Z3HKUePUgdB1x7MfIfKssC+WLPFMKTBZKpZh5m13PgexJjCq6KW7j17r0jHWcCpxEqnnncSA==",
      "dev": true,
      "requires": {
        "hosted-git-info": "^2.6.0",
        "osenv": "^0.1.5",
        "semver": "^5.5.0",
        "validate-npm-package-name": "^3.0.0"
      }
    },
    "npm-packlist": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/npm-packlist/-/npm-packlist-1.2.0.tgz",
      "integrity": "sha512-7Mni4Z8Xkx0/oegoqlcao/JpPCPEMtUvsmB0q7mgvlMinykJLSRTYuFqoQLYgGY8biuxIeiHO+QNJKbCfljewQ==",
      "dev": true,
      "requires": {
        "ignore-walk": "^3.0.1",
        "npm-bundled": "^1.0.1"
      }
    },
    "npm-pick-manifest": {
      "version": "2.2.3",
      "resolved": "https://registry.npmjs.org/npm-pick-manifest/-/npm-pick-manifest-2.2.3.tgz",
      "integrity": "sha512-+IluBC5K201+gRU85vFlUwX3PFShZAbAgDNp2ewJdWMVSppdo/Zih0ul2Ecky/X7b51J7LrrUAP+XOmOCvYZqA==",
      "dev": true,
      "requires": {
        "figgy-pudding": "^3.5.1",
        "npm-package-arg": "^6.0.0",
        "semver": "^5.4.1"
      }
    },
    "npm-registry-fetch": {
      "version": "3.9.0",
      "resolved": "https://registry.npmjs.org/npm-registry-fetch/-/npm-registry-fetch-3.9.0.tgz",
      "integrity": "sha512-srwmt8YhNajAoSAaDWndmZgx89lJwIZ1GWxOuckH4Coek4uHv5S+o/l9FLQe/awA+JwTnj4FJHldxhlXdZEBmw==",
      "dev": true,
      "requires": {
        "JSONStream": "^1.3.4",
        "bluebird": "^3.5.1",
        "figgy-pudding": "^3.4.1",
        "lru-cache": "^4.1.3",
        "make-fetch-happen": "^4.0.1",
        "npm-package-arg": "^6.1.0"
      }
    },
    "npm-run-path": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/npm-run-path/-/npm-run-path-2.0.2.tgz",
      "integrity": "sha1-NakjLfo11wZ7TLLd8jV7GHFTbF8=",
      "dev": true,
      "requires": {
        "path-key": "^2.0.0"
      }
    },
    "npmlog": {
      "version": "4.1.2",
      "resolved": "https://registry.npmjs.org/npmlog/-/npmlog-4.1.2.tgz",
      "integrity": "sha512-2uUqazuKlTaSI/dC8AzicUck7+IrEaOnN/e0jd3Xtt1KcGpwx30v50mL7oPyr/h9bL3E4aZccVwpwP+5W9Vjkg==",
      "dev": true,
      "requires": {
        "are-we-there-yet": "~1.1.2",
        "console-control-strings": "~1.1.0",
        "gauge": "~2.7.3",
        "set-blocking": "~2.0.0"
      }
    },
    "null-check": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/null-check/-/null-check-1.0.0.tgz",
      "integrity": "sha1-l33/1xdgErnsMNKjnbXPcqBDnt0=",
      "dev": true
    },
    "num2fraction": {
      "version": "1.2.2",
      "resolved": "https://registry.npmjs.org/num2fraction/-/num2fraction-1.2.2.tgz",
      "integrity": "sha1-b2gragJ6Tp3fpFZM0lidHU5mnt4=",
      "dev": true
    },
    "number-is-nan": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/number-is-nan/-/number-is-nan-1.0.1.tgz",
      "integrity": "sha1-CXtgK1NCKlIsGvuHkDGDNpQaAR0=",
      "dev": true
    },
    "oauth-sign": {
      "version": "0.9.0",
      "resolved": "https://registry.npmjs.org/oauth-sign/-/oauth-sign-0.9.0.tgz",
      "integrity": "sha512-fexhUFFPTGV8ybAtSIGbV6gOkSv8UtRbDBnAyLQw4QPKkgNlsH2ByPGtMUqdWkos6YCRmAqViwgZrJc/mRDzZQ==",
      "dev": true
    },
    "object-assign": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/object-assign/-/object-assign-4.1.1.tgz",
      "integrity": "sha1-IQmtx5ZYh8/AXLvUQsrIv7s2CGM=",
      "dev": true
    },
    "object-component": {
      "version": "0.0.3",
      "resolved": "https://registry.npmjs.org/object-component/-/object-component-0.0.3.tgz",
      "integrity": "sha1-8MaapQ78lbhmwYb0AKM3acsvEpE=",
      "dev": true
    },
    "object-copy": {
      "version": "0.1.0",
      "resolved": "https://registry.npmjs.org/object-copy/-/object-copy-0.1.0.tgz",
      "integrity": "sha1-fn2Fi3gb18mRpBupde04EnVOmYw=",
      "dev": true,
      "requires": {
        "copy-descriptor": "^0.1.0",
        "define-property": "^0.2.5",
        "kind-of": "^3.0.3"
      },
      "dependencies": {
        "define-property": {
          "version": "0.2.5",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-0.2.5.tgz",
          "integrity": "sha1-w1se+RjsPJkPmlvFe+BKrOxcgRY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^0.1.0"
          }
        },
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "object-visit": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/object-visit/-/object-visit-1.0.1.tgz",
      "integrity": "sha1-95xEk68MU3e1n+OdOV5BBC3QRbs=",
      "dev": true,
      "requires": {
        "isobject": "^3.0.0"
      }
    },
    "object.omit": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/object.omit/-/object.omit-2.0.1.tgz",
      "integrity": "sha1-Gpx0SCnznbuFjHbKNXmuKlTr0fo=",
      "dev": true,
      "requires": {
        "for-own": "^0.1.4",
        "is-extendable": "^0.1.1"
      },
      "dependencies": {
        "for-own": {
          "version": "0.1.5",
          "resolved": "https://registry.npmjs.org/for-own/-/for-own-0.1.5.tgz",
          "integrity": "sha1-UmXGgaTylNq78XyVCbZ2OqhFEM4=",
          "dev": true,
          "requires": {
            "for-in": "^1.0.1"
          }
        }
      }
    },
    "object.pick": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/object.pick/-/object.pick-1.3.0.tgz",
      "integrity": "sha1-h6EKxMFpS9Lhy/U1kaZhQftd10c=",
      "dev": true,
      "requires": {
        "isobject": "^3.0.1"
      }
    },
    "obuf": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/obuf/-/obuf-1.1.2.tgz",
      "integrity": "sha512-PX1wu0AmAdPqOL1mWhqmlOd8kOIZQwGZw6rh7uby9fTc5lhaOWFLX3I6R1hrF9k3zUY40e6igsLGkDXK92LJNg==",
      "dev": true
    },
    "on-finished": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/on-finished/-/on-finished-2.3.0.tgz",
      "integrity": "sha1-IPEzZIGwg811M3mSoWlxqi2QaUc=",
      "dev": true,
      "requires": {
        "ee-first": "1.1.1"
      }
    },
    "on-headers": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/on-headers/-/on-headers-1.0.1.tgz",
      "integrity": "sha1-ko9dD0cNSTQmUepnlLCFfBAGk/c=",
      "dev": true
    },
    "once": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/once/-/once-1.4.0.tgz",
      "integrity": "sha1-WDsap3WWHUsROsF9nFC6753Xa9E=",
      "dev": true,
      "requires": {
        "wrappy": "1"
      }
    },
    "onetime": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/onetime/-/onetime-2.0.1.tgz",
      "integrity": "sha1-BnQoIw/WdEOyeUsiu6UotoZ5YtQ=",
      "dev": true,
      "requires": {
        "mimic-fn": "^1.0.0"
      }
    },
    "opn": {
      "version": "5.4.0",
      "resolved": "https://registry.npmjs.org/opn/-/opn-5.4.0.tgz",
      "integrity": "sha512-YF9MNdVy/0qvJvDtunAOzFw9iasOQHpVthTCvGzxt61Il64AYSGdK+rYwld7NAfk9qJ7dt+hymBNSc9LNYS+Sw==",
      "dev": true,
      "requires": {
        "is-wsl": "^1.1.0"
      }
    },
    "optimist": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/optimist/-/optimist-0.6.1.tgz",
      "integrity": "sha1-2j6nRob6IaGaERwybpDrFaAZZoY=",
      "dev": true,
      "requires": {
        "minimist": "~0.0.1",
        "wordwrap": "~0.0.2"
      },
      "dependencies": {
        "wordwrap": {
          "version": "0.0.3",
          "resolved": "https://registry.npmjs.org/wordwrap/-/wordwrap-0.0.3.tgz",
          "integrity": "sha1-o9XabNXAvAAI03I0u68b7WMFkQc=",
          "dev": true
        }
      }
    },
    "optionator": {
      "version": "0.8.2",
      "resolved": "https://registry.npmjs.org/optionator/-/optionator-0.8.2.tgz",
      "integrity": "sha1-NkxeQJ0/TWMB1sC0wFu6UBgK62Q=",
      "dev": true,
      "requires": {
        "deep-is": "~0.1.3",
        "fast-levenshtein": "~2.0.4",
        "levn": "~0.3.0",
        "prelude-ls": "~1.1.2",
        "type-check": "~0.3.2",
        "wordwrap": "~1.0.0"
      }
    },
    "original": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/original/-/original-1.0.2.tgz",
      "integrity": "sha512-hyBVl6iqqUOJ8FqRe+l/gS8H+kKYjrEndd5Pm1MfBtsEKA038HkkdbAl/72EAXGyonD/PFsvmVG+EvcIpliMBg==",
      "dev": true,
      "requires": {
        "url-parse": "^1.4.3"
      }
    },
    "os-browserify": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/os-browserify/-/os-browserify-0.3.0.tgz",
      "integrity": "sha1-hUNzx/XCMVkU/Jv8a9gjj92h7Cc=",
      "dev": true
    },
    "os-homedir": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/os-homedir/-/os-homedir-1.0.2.tgz",
      "integrity": "sha1-/7xJiDNuDoM94MFox+8VISGqf7M=",
      "dev": true
    },
    "os-locale": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/os-locale/-/os-locale-1.4.0.tgz",
      "integrity": "sha1-IPnxeuKe00XoveWDsT0gCYA8FNk=",
      "dev": true,
      "optional": true,
      "requires": {
        "lcid": "^1.0.0"
      }
    },
    "os-tmpdir": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/os-tmpdir/-/os-tmpdir-1.0.2.tgz",
      "integrity": "sha1-u+Z0BseaqFxc/sdm/lc0VV36EnQ=",
      "dev": true
    },
    "osenv": {
      "version": "0.1.5",
      "resolved": "https://registry.npmjs.org/osenv/-/osenv-0.1.5.tgz",
      "integrity": "sha512-0CWcCECdMVc2Rw3U5w9ZjqX6ga6ubk1xDVKxtBQPK7wis/0F2r9T6k4ydGYhecl7YUBxBVxhL5oisPsNxAPe2g==",
      "dev": true,
      "requires": {
        "os-homedir": "^1.0.0",
        "os-tmpdir": "^1.0.0"
      }
    },
    "p-defer": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/p-defer/-/p-defer-1.0.0.tgz",
      "integrity": "sha1-n26xgvbJqozXQwBKfU+WsZaw+ww=",
      "dev": true
    },
    "p-finally": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/p-finally/-/p-finally-1.0.0.tgz",
      "integrity": "sha1-P7z7FbiZpEEjs0ttzBi3JDNqLK4=",
      "dev": true
    },
    "p-is-promise": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/p-is-promise/-/p-is-promise-1.1.0.tgz",
      "integrity": "sha1-nJRWmJ6fZYgBewQ01WCXZ1w9oF4=",
      "dev": true
    },
    "p-limit": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/p-limit/-/p-limit-1.3.0.tgz",
      "integrity": "sha512-vvcXsLAJ9Dr5rQOPk7toZQZJApBl2K4J6dANSsEuh6QI41JYcsS/qhTGa9ErIUUgK3WNQoJYvylxvjqmiqEA9Q==",
      "dev": true,
      "requires": {
        "p-try": "^1.0.0"
      }
    },
    "p-locate": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/p-locate/-/p-locate-2.0.0.tgz",
      "integrity": "sha1-IKAQOyIqcMj9OcwuWAaA893l7EM=",
      "dev": true,
      "requires": {
        "p-limit": "^1.1.0"
      }
    },
    "p-map": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/p-map/-/p-map-1.2.0.tgz",
      "integrity": "sha512-r6zKACMNhjPJMTl8KcFH4li//gkrXWfbD6feV8l6doRHlzljFWGJ2AP6iKaCJXyZmAUMOPtvbW7EXkbWO/pLEA==",
      "dev": true
    },
    "p-try": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/p-try/-/p-try-1.0.0.tgz",
      "integrity": "sha1-y8ec26+P1CKOE/Yh8rGiN8GyB7M=",
      "dev": true
    },
    "pacote": {
      "version": "9.1.1",
      "resolved": "https://registry.npmjs.org/pacote/-/pacote-9.1.1.tgz",
      "integrity": "sha512-f28Rq5ozzKAA9YwIKw61/ipwAatUZseYmVssDbHHaexF0wRIVotapVEZPAjOT7Eu3LYVqEp0NVpNizoAnYBUaA==",
      "dev": true,
      "requires": {
        "bluebird": "^3.5.2",
        "cacache": "^11.2.0",
        "figgy-pudding": "^3.5.1",
        "get-stream": "^4.1.0",
        "glob": "^7.1.3",
        "lru-cache": "^4.1.3",
        "make-fetch-happen": "^4.0.1",
        "minimatch": "^3.0.4",
        "minipass": "^2.3.5",
        "mississippi": "^3.0.0",
        "mkdirp": "^0.5.1",
        "normalize-package-data": "^2.4.0",
        "npm-package-arg": "^6.1.0",
        "npm-packlist": "^1.1.12",
        "npm-pick-manifest": "^2.1.0",
        "npm-registry-fetch": "^3.8.0",
        "osenv": "^0.1.5",
        "promise-inflight": "^1.0.1",
        "promise-retry": "^1.1.1",
        "protoduck": "^5.0.1",
        "rimraf": "^2.6.2",
        "safe-buffer": "^5.1.2",
        "semver": "^5.6.0",
        "ssri": "^6.0.1",
        "tar": "^4.4.6",
        "unique-filename": "^1.1.1",
        "which": "^1.3.1"
      },
      "dependencies": {
        "cacache": {
          "version": "11.3.2",
          "resolved": "https://registry.npmjs.org/cacache/-/cacache-11.3.2.tgz",
          "integrity": "sha512-E0zP4EPGDOaT2chM08Als91eYnf8Z+eH1awwwVsngUmgppfM5jjJ8l3z5vO5p5w/I3LsiXawb1sW0VY65pQABg==",
          "dev": true,
          "requires": {
            "bluebird": "^3.5.3",
            "chownr": "^1.1.1",
            "figgy-pudding": "^3.5.1",
            "glob": "^7.1.3",
            "graceful-fs": "^4.1.15",
            "lru-cache": "^5.1.1",
            "mississippi": "^3.0.0",
            "mkdirp": "^0.5.1",
            "move-concurrently": "^1.0.1",
            "promise-inflight": "^1.0.1",
            "rimraf": "^2.6.2",
            "ssri": "^6.0.1",
            "unique-filename": "^1.1.1",
            "y18n": "^4.0.0"
          },
          "dependencies": {
            "lru-cache": {
              "version": "5.1.1",
              "resolved": "https://registry.npmjs.org/lru-cache/-/lru-cache-5.1.1.tgz",
              "integrity": "sha512-KpNARQA3Iwv+jTA0utUVVbrh+Jlrr1Fv0e56GGzAFOXN7dk/FviaDW8LHmK52DlcH4WP2n6gI8vN1aesBFgo9w==",
              "dev": true,
              "requires": {
                "yallist": "^3.0.2"
              }
            }
          }
        },
        "get-stream": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/get-stream/-/get-stream-4.1.0.tgz",
          "integrity": "sha512-GMat4EJ5161kIy2HevLlr4luNjBgvmj413KaQA7jt4V8B4RDsfpHk7WQ9GVqfYyyx8OS/L66Kox+rJRNklLK7w==",
          "dev": true,
          "requires": {
            "pump": "^3.0.0"
          }
        },
        "mississippi": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/mississippi/-/mississippi-3.0.0.tgz",
          "integrity": "sha512-x471SsVjUtBRtcvd4BzKE9kFC+/2TeWgKCgw0bZcw1b9l2X3QX5vCWgF+KaZaYm87Ss//rHnWryupDrgLvmSkA==",
          "dev": true,
          "requires": {
            "concat-stream": "^1.5.0",
            "duplexify": "^3.4.2",
            "end-of-stream": "^1.1.0",
            "flush-write-stream": "^1.0.0",
            "from2": "^2.1.0",
            "parallel-transform": "^1.1.0",
            "pump": "^3.0.0",
            "pumpify": "^1.3.3",
            "stream-each": "^1.1.0",
            "through2": "^2.0.0"
          }
        },
        "pump": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/pump/-/pump-3.0.0.tgz",
          "integrity": "sha512-LwZy+p3SFs1Pytd/jYct4wpv49HiYCqd9Rlc5ZVdk0V+8Yzv6jR5Blk3TRmPL1ft69TxP0IMZGJ+WPFU2BFhww==",
          "dev": true,
          "requires": {
            "end-of-stream": "^1.1.0",
            "once": "^1.3.1"
          }
        },
        "semver": {
          "version": "5.6.0",
          "resolved": "https://registry.npmjs.org/semver/-/semver-5.6.0.tgz",
          "integrity": "sha512-RS9R6R35NYgQn++fkDWaOmqGoj4Ek9gGs+DPxNUZKuwE183xjJroKvyo1IzVFeXvUrvmALy6FWD5xrdJT25gMg==",
          "dev": true
        },
        "ssri": {
          "version": "6.0.1",
          "resolved": "https://registry.npmjs.org/ssri/-/ssri-6.0.1.tgz",
          "integrity": "sha512-3Wge10hNcT1Kur4PDFwEieXSCMCJs/7WvSACcrMYrNp+b8kDL1/0wJch5Ni2WrtwEa2IO8OsVfeKIciKCDx/QA==",
          "dev": true,
          "requires": {
            "figgy-pudding": "^3.5.1"
          }
        },
        "tar": {
          "version": "4.4.8",
          "resolved": "https://registry.npmjs.org/tar/-/tar-4.4.8.tgz",
          "integrity": "sha512-LzHF64s5chPQQS0IYBn9IN5h3i98c12bo4NCO7e0sGM2llXQ3p2FGC5sdENN4cTW48O915Sh+x+EXx7XW96xYQ==",
          "dev": true,
          "requires": {
            "chownr": "^1.1.1",
            "fs-minipass": "^1.2.5",
            "minipass": "^2.3.4",
            "minizlib": "^1.1.1",
            "mkdirp": "^0.5.0",
            "safe-buffer": "^5.1.2",
            "yallist": "^3.0.2"
          }
        },
        "yallist": {
          "version": "3.0.3",
          "resolved": "https://registry.npmjs.org/yallist/-/yallist-3.0.3.tgz",
          "integrity": "sha512-S+Zk8DEWE6oKpV+vI3qWkaK+jSbIK86pCwe2IF/xwIpQ8jEuxpw9NyaGjmp9+BoJv5FV2piqCDcoCtStppiq2A==",
          "dev": true
        }
      }
    },
    "pako": {
      "version": "1.0.8",
      "resolved": "https://registry.npmjs.org/pako/-/pako-1.0.8.tgz",
      "integrity": "sha512-6i0HVbUfcKaTv+EG8ZTr75az7GFXcLYk9UyLEg7Notv/Ma+z/UG3TCoz6GiNeOrn1E/e63I0X/Hpw18jHOTUnA==",
      "dev": true
    },
    "parallel-transform": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/parallel-transform/-/parallel-transform-1.1.0.tgz",
      "integrity": "sha1-1BDwZbBdojCB/NEPKIVMKb2jOwY=",
      "dev": true,
      "requires": {
        "cyclist": "~0.2.2",
        "inherits": "^2.0.3",
        "readable-stream": "^2.1.5"
      }
    },
    "parse-asn1": {
      "version": "5.1.3",
      "resolved": "https://registry.npmjs.org/parse-asn1/-/parse-asn1-5.1.3.tgz",
      "integrity": "sha512-VrPoetlz7B/FqjBLD2f5wBVZvsZVLnRUrxVLfRYhGXCODa/NWE4p3Wp+6+aV3ZPL3KM7/OZmxDIwwijD7yuucg==",
      "dev": true,
      "requires": {
        "asn1.js": "^4.0.0",
        "browserify-aes": "^1.0.0",
        "create-hash": "^1.1.0",
        "evp_bytestokey": "^1.0.0",
        "pbkdf2": "^3.0.3",
        "safe-buffer": "^5.1.1"
      }
    },
    "parse-glob": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/parse-glob/-/parse-glob-3.0.4.tgz",
      "integrity": "sha1-ssN2z7EfNVE7rdFz7wu246OIORw=",
      "dev": true,
      "requires": {
        "glob-base": "^0.3.0",
        "is-dotfile": "^1.0.0",
        "is-extglob": "^1.0.0",
        "is-glob": "^2.0.0"
      },
      "dependencies": {
        "is-extglob": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-extglob/-/is-extglob-1.0.0.tgz",
          "integrity": "sha1-rEaBd8SUNAWgkvyPKXYMb/xiBsA=",
          "dev": true
        },
        "is-glob": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/is-glob/-/is-glob-2.0.1.tgz",
          "integrity": "sha1-0Jb5JqPe1WAPP9/ZEZjLCIjC2GM=",
          "dev": true,
          "requires": {
            "is-extglob": "^1.0.0"
          }
        }
      }
    },
    "parse-json": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/parse-json/-/parse-json-2.2.0.tgz",
      "integrity": "sha1-9ID0BDTvgHQfhGkJn43qGPVaTck=",
      "dev": true,
      "requires": {
        "error-ex": "^1.2.0"
      }
    },
    "parse5": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/parse5/-/parse5-4.0.0.tgz",
      "integrity": "sha512-VrZ7eOd3T1Fk4XWNXMgiGBK/z0MG48BWG2uQNU4I72fkQuKUTZpl+u9k+CxEG0twMVzSmXEEz12z5Fnw1jIQFA==",
      "dev": true
    },
    "parseqs": {
      "version": "0.0.5",
      "resolved": "https://registry.npmjs.org/parseqs/-/parseqs-0.0.5.tgz",
      "integrity": "sha1-1SCKNzjkZ2bikbouoXNoSSGouJ0=",
      "dev": true,
      "requires": {
        "better-assert": "~1.0.0"
      }
    },
    "parseuri": {
      "version": "0.0.5",
      "resolved": "https://registry.npmjs.org/parseuri/-/parseuri-0.0.5.tgz",
      "integrity": "sha1-gCBKUNTbt3m/3G6+J3jZDkvOMgo=",
      "dev": true,
      "requires": {
        "better-assert": "~1.0.0"
      }
    },
    "parseurl": {
      "version": "1.3.2",
      "resolved": "https://registry.npmjs.org/parseurl/-/parseurl-1.3.2.tgz",
      "integrity": "sha1-/CidTtiZMRlGDBViUyYs3I3mW/M=",
      "dev": true
    },
    "pascalcase": {
      "version": "0.1.1",
      "resolved": "https://registry.npmjs.org/pascalcase/-/pascalcase-0.1.1.tgz",
      "integrity": "sha1-s2PlXoAGym/iF4TS2yK9FdeRfxQ=",
      "dev": true
    },
    "path-browserify": {
      "version": "0.0.0",
      "resolved": "https://registry.npmjs.org/path-browserify/-/path-browserify-0.0.0.tgz",
      "integrity": "sha1-oLhwcpquIUAFt9UDLsLLuw+0RRo=",
      "dev": true
    },
    "path-dirname": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/path-dirname/-/path-dirname-1.0.2.tgz",
      "integrity": "sha1-zDPSTVJeCZpTiMAzbG4yuRYGCeA=",
      "dev": true
    },
    "path-exists": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/path-exists/-/path-exists-3.0.0.tgz",
      "integrity": "sha1-zg6+ql94yxiSXqfYENe1mwEP1RU=",
      "dev": true
    },
    "path-is-absolute": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/path-is-absolute/-/path-is-absolute-1.0.1.tgz",
      "integrity": "sha1-F0uSaHNVNP+8es5r9TpanhtcX18=",
      "dev": true
    },
    "path-is-inside": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/path-is-inside/-/path-is-inside-1.0.2.tgz",
      "integrity": "sha1-NlQX3t5EQw0cEa9hAn+s8HS9/FM=",
      "dev": true
    },
    "path-key": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/path-key/-/path-key-2.0.1.tgz",
      "integrity": "sha1-QRyttXTFoUDTpLGRDUDYDMn0C0A=",
      "dev": true
    },
    "path-parse": {
      "version": "1.0.6",
      "resolved": "https://registry.npmjs.org/path-parse/-/path-parse-1.0.6.tgz",
      "integrity": "sha512-GSmOT2EbHrINBf9SR7CDELwlJ8AENk3Qn7OikK4nFYAu3Ote2+JYNVvkpAEQm3/TLNEJFD/xZJjzyxg3KBWOzw==",
      "dev": true
    },
    "path-to-regexp": {
      "version": "0.1.7",
      "resolved": "https://registry.npmjs.org/path-to-regexp/-/path-to-regexp-0.1.7.tgz",
      "integrity": "sha1-32BBeABfUi8V60SQ5yR6G/qmf4w=",
      "dev": true
    },
    "path-type": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/path-type/-/path-type-3.0.0.tgz",
      "integrity": "sha512-T2ZUsdZFHgA3u4e5PfPbjd7HDDpxPnQb5jN0SrDsjNSuVXHJqtwTnWqG0B1jZrgmJ/7lj1EmVIByWt1gxGkWvg==",
      "dev": true,
      "requires": {
        "pify": "^3.0.0"
      }
    },
    "pbkdf2": {
      "version": "3.0.17",
      "resolved": "https://registry.npmjs.org/pbkdf2/-/pbkdf2-3.0.17.tgz",
      "integrity": "sha512-U/il5MsrZp7mGg3mSQfn742na2T+1/vHDCG5/iTI3X9MKUuYUZVLQhyRsg06mCgDBTd57TxzgZt7P+fYfjRLtA==",
      "dev": true,
      "requires": {
        "create-hash": "^1.1.2",
        "create-hmac": "^1.1.4",
        "ripemd160": "^2.0.1",
        "safe-buffer": "^5.0.1",
        "sha.js": "^2.4.8"
      }
    },
    "performance-now": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/performance-now/-/performance-now-2.1.0.tgz",
      "integrity": "sha1-Ywn04OX6kT7BxpMHrjZLSzd8nns=",
      "dev": true
    },
    "pify": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/pify/-/pify-3.0.0.tgz",
      "integrity": "sha1-5aSs0sEB/fPZpNB/DbxNtJ3SgXY=",
      "dev": true
    },
    "pinkie": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/pinkie/-/pinkie-2.0.4.tgz",
      "integrity": "sha1-clVrgM+g1IqXToDnckjoDtT3+HA=",
      "dev": true
    },
    "pinkie-promise": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/pinkie-promise/-/pinkie-promise-2.0.1.tgz",
      "integrity": "sha1-ITXW36ejWMBprJsXh3YogihFD/o=",
      "dev": true,
      "requires": {
        "pinkie": "^2.0.0"
      }
    },
    "pkg-dir": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/pkg-dir/-/pkg-dir-2.0.0.tgz",
      "integrity": "sha1-9tXREJ4Z1j7fQo4L1X4Sd3YVM0s=",
      "dev": true,
      "requires": {
        "find-up": "^2.1.0"
      }
    },
    "portfinder": {
      "version": "1.0.17",
      "resolved": "https://registry.npmjs.org/portfinder/-/portfinder-1.0.17.tgz",
      "integrity": "sha512-syFcRIRzVI1BoEFOCaAiizwDolh1S1YXSodsVhncbhjzjZQulhczNRbqnUl9N31Q4dKGOXsNDqxC2BWBgSMqeQ==",
      "dev": true,
      "requires": {
        "async": "^1.5.2",
        "debug": "^2.2.0",
        "mkdirp": "0.5.x"
      }
    },
    "posix-character-classes": {
      "version": "0.1.1",
      "resolved": "https://registry.npmjs.org/posix-character-classes/-/posix-character-classes-0.1.1.tgz",
      "integrity": "sha1-AerA/jta9xoqbAL+q7jB/vfgDqs=",
      "dev": true
    },
    "postcss": {
      "version": "7.0.13",
      "resolved": "https://registry.npmjs.org/postcss/-/postcss-7.0.13.tgz",
      "integrity": "sha512-h8SY6kQTd1wISHWjz+E6cswdhMuyBZRb16pSTv3W4zYZ3/YbyWeJdNUeOXB5IdZqE1U76OUEjjjqsC3z2f3hVg==",
      "dev": true,
      "requires": {
        "chalk": "^2.4.2",
        "source-map": "^0.6.1",
        "supports-color": "^6.1.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "postcss-import": {
      "version": "12.0.1",
      "resolved": "https://registry.npmjs.org/postcss-import/-/postcss-import-12.0.1.tgz",
      "integrity": "sha512-3Gti33dmCjyKBgimqGxL3vcV8w9+bsHwO5UrBawp796+jdardbcFl4RP5w/76BwNL7aGzpKstIfF9I+kdE8pTw==",
      "dev": true,
      "requires": {
        "postcss": "^7.0.1",
        "postcss-value-parser": "^3.2.3",
        "read-cache": "^1.0.0",
        "resolve": "^1.1.7"
      }
    },
    "postcss-load-config": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/postcss-load-config/-/postcss-load-config-2.0.0.tgz",
      "integrity": "sha512-V5JBLzw406BB8UIfsAWSK2KSwIJ5yoEIVFb4gVkXci0QdKgA24jLmHZ/ghe/GgX0lJ0/D1uUK1ejhzEY94MChQ==",
      "dev": true,
      "requires": {
        "cosmiconfig": "^4.0.0",
        "import-cwd": "^2.0.0"
      }
    },
    "postcss-loader": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/postcss-loader/-/postcss-loader-3.0.0.tgz",
      "integrity": "sha512-cLWoDEY5OwHcAjDnkyRQzAXfs2jrKjXpO/HQFcc5b5u/r7aa471wdmChmwfnv7x2u840iat/wi0lQ5nbRgSkUA==",
      "dev": true,
      "requires": {
        "loader-utils": "^1.1.0",
        "postcss": "^7.0.0",
        "postcss-load-config": "^2.0.0",
        "schema-utils": "^1.0.0"
      }
    },
    "postcss-value-parser": {
      "version": "3.3.1",
      "resolved": "https://registry.npmjs.org/postcss-value-parser/-/postcss-value-parser-3.3.1.tgz",
      "integrity": "sha512-pISE66AbVkp4fDQ7VHBwRNXzAAKJjw4Vw7nWI/+Q3vuly7SNfgYXvm6i5IgFylHGK5sP/xHAbB7N49OS4gWNyQ==",
      "dev": true
    },
    "prelude-ls": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/prelude-ls/-/prelude-ls-1.1.2.tgz",
      "integrity": "sha1-IZMqVJ9eUv/ZqCf1cOBL5iqX2lQ=",
      "dev": true
    },
    "preserve": {
      "version": "0.2.0",
      "resolved": "https://registry.npmjs.org/preserve/-/preserve-0.2.0.tgz",
      "integrity": "sha1-gV7R9uvGWSb4ZbMQwHE7yzMVzks=",
      "dev": true
    },
    "process": {
      "version": "0.11.10",
      "resolved": "https://registry.npmjs.org/process/-/process-0.11.10.tgz",
      "integrity": "sha1-czIwDoQBYb2j5podHZGn1LwW8YI=",
      "dev": true
    },
    "process-nextick-args": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/process-nextick-args/-/process-nextick-args-2.0.0.tgz",
      "integrity": "sha512-MtEC1TqN0EU5nephaJ4rAtThHtC86dNN9qCuEhtshvpVBkAW5ZO7BASN9REnF9eoXGcRub+pFuKEpOHE+HbEMw==",
      "dev": true
    },
    "promise": {
      "version": "7.3.1",
      "resolved": "https://registry.npmjs.org/promise/-/promise-7.3.1.tgz",
      "integrity": "sha512-nolQXZ/4L+bP/UGlkfaIujX9BKxGwmQ9OT4mOt5yvy8iK1h3wqTEJCijzGANTCCl9nWjY41juyAn2K3Q1hLLTg==",
      "dev": true,
      "optional": true,
      "requires": {
        "asap": "~2.0.3"
      }
    },
    "promise-inflight": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/promise-inflight/-/promise-inflight-1.0.1.tgz",
      "integrity": "sha1-mEcocL8igTL8vdhoEputEsPAKeM=",
      "dev": true
    },
    "promise-retry": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/promise-retry/-/promise-retry-1.1.1.tgz",
      "integrity": "sha1-ZznpaOMFHaIM5kl/srUPaRHfPW0=",
      "dev": true,
      "requires": {
        "err-code": "^1.0.0",
        "retry": "^0.10.0"
      }
    },
    "protoduck": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/protoduck/-/protoduck-5.0.1.tgz",
      "integrity": "sha512-WxoCeDCoCBY55BMvj4cAEjdVUFGRWed9ZxPlqTKYyw1nDDTQ4pqmnIMAGfJlg7Dx35uB/M+PHJPTmGOvaCaPTg==",
      "dev": true,
      "requires": {
        "genfun": "^5.0.0"
      }
    },
    "protractor": {
      "version": "5.4.2",
      "resolved": "https://registry.npmjs.org/protractor/-/protractor-5.4.2.tgz",
      "integrity": "sha512-zlIj64Cr6IOWP7RwxVeD8O4UskLYPoyIcg0HboWJL9T79F1F0VWtKkGTr/9GN6BKL+/Q/GmM7C9kFVCfDbP5sA==",
      "dev": true,
      "requires": {
        "@types/q": "^0.0.32",
        "@types/selenium-webdriver": "^3.0.0",
        "blocking-proxy": "^1.0.0",
        "browserstack": "^1.5.1",
        "chalk": "^1.1.3",
        "glob": "^7.0.3",
        "jasmine": "2.8.0",
        "jasminewd2": "^2.1.0",
        "optimist": "~0.6.0",
        "q": "1.4.1",
        "saucelabs": "^1.5.0",
        "selenium-webdriver": "3.6.0",
        "source-map-support": "~0.4.0",
        "webdriver-js-extender": "2.1.0",
        "webdriver-manager": "^12.0.6"
      },
      "dependencies": {
        "ansi-styles": {
          "version": "2.2.1",
          "resolved": "https://registry.npmjs.org/ansi-styles/-/ansi-styles-2.2.1.tgz",
          "integrity": "sha1-tDLdM1i2NM914eRmQ2gkBTPB3b4=",
          "dev": true
        },
        "chalk": {
          "version": "1.1.3",
          "resolved": "https://registry.npmjs.org/chalk/-/chalk-1.1.3.tgz",
          "integrity": "sha1-qBFcVeSnAv5NFQq9OHKCKn4J/Jg=",
          "dev": true,
          "requires": {
            "ansi-styles": "^2.2.1",
            "escape-string-regexp": "^1.0.2",
            "has-ansi": "^2.0.0",
            "strip-ansi": "^3.0.0",
            "supports-color": "^2.0.0"
          }
        },
        "del": {
          "version": "2.2.2",
          "resolved": "https://registry.npmjs.org/del/-/del-2.2.2.tgz",
          "integrity": "sha1-wSyYHQZ4RshLyvhiz/kw2Qf/0ag=",
          "dev": true,
          "requires": {
            "globby": "^5.0.0",
            "is-path-cwd": "^1.0.0",
            "is-path-in-cwd": "^1.0.0",
            "object-assign": "^4.0.1",
            "pify": "^2.0.0",
            "pinkie-promise": "^2.0.0",
            "rimraf": "^2.2.8"
          }
        },
        "globby": {
          "version": "5.0.0",
          "resolved": "https://registry.npmjs.org/globby/-/globby-5.0.0.tgz",
          "integrity": "sha1-69hGZ8oNuzMLmbz8aOrCvFQ3Dg0=",
          "dev": true,
          "requires": {
            "array-union": "^1.0.1",
            "arrify": "^1.0.0",
            "glob": "^7.0.3",
            "object-assign": "^4.0.1",
            "pify": "^2.0.0",
            "pinkie-promise": "^2.0.0"
          }
        },
        "minimist": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/minimist/-/minimist-1.2.0.tgz",
          "integrity": "sha1-o1AIsg9BOD7sH7kU9M1d95omQoQ=",
          "dev": true
        },
        "pify": {
          "version": "2.3.0",
          "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
          "integrity": "sha1-7RQaasBDqEnqWISY59yosVMw6Qw=",
          "dev": true
        },
        "source-map": {
          "version": "0.5.7",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.5.7.tgz",
          "integrity": "sha1-igOdLRAh0i0eoUyA2OpGi6LvP8w=",
          "dev": true
        },
        "source-map-support": {
          "version": "0.4.18",
          "resolved": "https://registry.npmjs.org/source-map-support/-/source-map-support-0.4.18.tgz",
          "integrity": "sha512-try0/JqxPLF9nOjvSta7tVondkP5dwgyLDjVoyMDlmjugT2lRZ1OfsrYTkCd2hkDnJTKRbO/Rl3orm8vlsUzbA==",
          "dev": true,
          "requires": {
            "source-map": "^0.5.6"
          }
        },
        "supports-color": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-2.0.0.tgz",
          "integrity": "sha1-U10EXOa2Nj+kARcIRimZXp3zJMc=",
          "dev": true
        },
        "webdriver-manager": {
          "version": "12.1.1",
          "resolved": "https://registry.npmjs.org/webdriver-manager/-/webdriver-manager-12.1.1.tgz",
          "integrity": "sha512-L9TEQmZs6JbMMRQI1w60mfps265/NCr0toYJl7p/R2OAk6oXAfwI6jqYP7EWae+d7Ad2S2Aj4+rzxoSjqk3ZuA==",
          "dev": true,
          "requires": {
            "adm-zip": "^0.4.9",
            "chalk": "^1.1.1",
            "del": "^2.2.0",
            "glob": "^7.0.3",
            "ini": "^1.3.4",
            "minimist": "^1.2.0",
            "q": "^1.4.1",
            "request": "^2.87.0",
            "rimraf": "^2.5.2",
            "semver": "^5.3.0",
            "xml2js": "^0.4.17"
          }
        }
      }
    },
    "proxy-addr": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/proxy-addr/-/proxy-addr-2.0.4.tgz",
      "integrity": "sha512-5erio2h9jp5CHGwcybmxmVqHmnCBZeewlfJ0pex+UW7Qny7OOZXTtH56TGNyBizkgiOwhJtMKrVzDTeKcySZwA==",
      "dev": true,
      "requires": {
        "forwarded": "~0.1.2",
        "ipaddr.js": "1.8.0"
      }
    },
    "prr": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/prr/-/prr-1.0.1.tgz",
      "integrity": "sha1-0/wRS6BplaRexok/SEzrHXj19HY=",
      "dev": true
    },
    "pseudomap": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/pseudomap/-/pseudomap-1.0.2.tgz",
      "integrity": "sha1-8FKijacOYYkX7wqKw0wa5aaChrM=",
      "dev": true
    },
    "psl": {
      "version": "1.1.31",
      "resolved": "https://registry.npmjs.org/psl/-/psl-1.1.31.tgz",
      "integrity": "sha512-/6pt4+C+T+wZUieKR620OpzN/LlnNKuWjy1iFLQ/UG35JqHlR/89MP1d96dUfkf6Dne3TuLQzOYEYshJ+Hx8mw==",
      "dev": true
    },
    "public-encrypt": {
      "version": "4.0.3",
      "resolved": "https://registry.npmjs.org/public-encrypt/-/public-encrypt-4.0.3.tgz",
      "integrity": "sha512-zVpa8oKZSz5bTMTFClc1fQOnyyEzpl5ozpi1B5YcvBrdohMjH2rfsBtyXcuNuwjsDIXmBYlF2N5FlJYhR29t8Q==",
      "dev": true,
      "requires": {
        "bn.js": "^4.1.0",
        "browserify-rsa": "^4.0.0",
        "create-hash": "^1.1.0",
        "parse-asn1": "^5.0.0",
        "randombytes": "^2.0.1",
        "safe-buffer": "^5.1.2"
      }
    },
    "pump": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/pump/-/pump-2.0.1.tgz",
      "integrity": "sha512-ruPMNRkN3MHP1cWJc9OWr+T/xDP0jhXYCLfJcBuX54hhfIBnaQmAUMfDcG4DM5UMWByBbJY69QSphm3jtDKIkA==",
      "dev": true,
      "requires": {
        "end-of-stream": "^1.1.0",
        "once": "^1.3.1"
      }
    },
    "pumpify": {
      "version": "1.5.1",
      "resolved": "https://registry.npmjs.org/pumpify/-/pumpify-1.5.1.tgz",
      "integrity": "sha512-oClZI37HvuUJJxSKKrC17bZ9Cu0ZYhEAGPsPUy9KlMUmv9dKX2o77RUmq7f3XjIxbwyGwYzbzQ1L2Ks8sIradQ==",
      "dev": true,
      "requires": {
        "duplexify": "^3.6.0",
        "inherits": "^2.0.3",
        "pump": "^2.0.0"
      }
    },
    "punycode": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/punycode/-/punycode-2.1.1.tgz",
      "integrity": "sha512-XRsRjdf+j5ml+y/6GKHPZbrF/8p2Yga0JPtdqTIY2Xe5ohJPD9saDJJLPvp9+NSBprVvevdXZybnj2cv8OEd0A==",
      "dev": true
    },
    "q": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/q/-/q-1.4.1.tgz",
      "integrity": "sha1-VXBbzZPF82c1MMLCy8DCs63cKG4=",
      "dev": true
    },
    "qjobs": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/qjobs/-/qjobs-1.2.0.tgz",
      "integrity": "sha512-8YOJEHtxpySA3fFDyCRxA+UUV+fA+rTWnuWvylOK/NCjhY+b4ocCtmu8TtsWb+mYeU+GCHf/S66KZF/AsteKHg==",
      "dev": true
    },
    "qs": {
      "version": "6.5.2",
      "resolved": "https://registry.npmjs.org/qs/-/qs-6.5.2.tgz",
      "integrity": "sha512-N5ZAX4/LxJmF+7wN74pUD6qAh9/wnvdQcjq9TZjevvXzSUo7bfmw91saqMjzGS2xq91/odN2dW/WOl7qQHNDGA==",
      "dev": true
    },
    "querystring": {
      "version": "0.2.0",
      "resolved": "https://registry.npmjs.org/querystring/-/querystring-0.2.0.tgz",
      "integrity": "sha1-sgmEkgO7Jd+CDadW50cAWHhSFiA=",
      "dev": true
    },
    "querystring-es3": {
      "version": "0.2.1",
      "resolved": "https://registry.npmjs.org/querystring-es3/-/querystring-es3-0.2.1.tgz",
      "integrity": "sha1-nsYfeQSYdXB9aUFFlv2Qek1xHnM=",
      "dev": true
    },
    "querystringify": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/querystringify/-/querystringify-2.1.0.tgz",
      "integrity": "sha512-sluvZZ1YiTLD5jsqZcDmFyV2EwToyXZBfpoVOmktMmW+VEnhgakFHnasVph65fOjGPTWN0Nw3+XQaSeMayr0kg==",
      "dev": true
    },
    "randomatic": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/randomatic/-/randomatic-3.1.1.tgz",
      "integrity": "sha512-TuDE5KxZ0J461RVjrJZCJc+J+zCkTb1MbH9AQUq68sMhOMcy9jLcb3BrZKgp9q9Ncltdg4QVqWrH02W2EFFVYw==",
      "dev": true,
      "requires": {
        "is-number": "^4.0.0",
        "kind-of": "^6.0.0",
        "math-random": "^1.0.1"
      },
      "dependencies": {
        "is-number": {
          "version": "4.0.0",
          "resolved": "https://registry.npmjs.org/is-number/-/is-number-4.0.0.tgz",
          "integrity": "sha512-rSklcAIlf1OmFdyAqbnWTLVelsQ58uvZ66S/ZyawjWqIviTWCjg2PzVGw8WUA+nNuPTqb4wgA+NszrJ+08LlgQ==",
          "dev": true
        }
      }
    },
    "randombytes": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/randombytes/-/randombytes-2.0.6.tgz",
      "integrity": "sha512-CIQ5OFxf4Jou6uOKe9t1AOgqpeU5fd70A8NPdHSGeYXqXsPe6peOwI0cUl88RWZ6sP1vPMV3avd/R6cZ5/sP1A==",
      "dev": true,
      "requires": {
        "safe-buffer": "^5.1.0"
      }
    },
    "randomfill": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/randomfill/-/randomfill-1.0.4.tgz",
      "integrity": "sha512-87lcbR8+MhcWcUiQ+9e+Rwx8MyR2P7qnt15ynUlbm3TU/fjbgz4GsvfSUDTemtCCtVCqb4ZcEFlyPNTh9bBTLw==",
      "dev": true,
      "requires": {
        "randombytes": "^2.0.5",
        "safe-buffer": "^5.1.0"
      }
    },
    "range-parser": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/range-parser/-/range-parser-1.2.0.tgz",
      "integrity": "sha1-9JvmtIeJTdxA3MlKMi9hEJLgDV4=",
      "dev": true
    },
    "raw-body": {
      "version": "2.3.3",
      "resolved": "https://registry.npmjs.org/raw-body/-/raw-body-2.3.3.tgz",
      "integrity": "sha512-9esiElv1BrZoI3rCDuOuKCBRbuApGGaDPQfjSflGxdy4oyzqghxu6klEkkVIvBje+FF0BX9coEv8KqW6X/7njw==",
      "dev": true,
      "requires": {
        "bytes": "3.0.0",
        "http-errors": "1.6.3",
        "iconv-lite": "0.4.23",
        "unpipe": "1.0.0"
      }
    },
    "raw-loader": {
      "version": "0.5.1",
      "resolved": "https://registry.npmjs.org/raw-loader/-/raw-loader-0.5.1.tgz",
      "integrity": "sha1-DD0L6u2KAclm2Xh793goElKpeao=",
      "dev": true
    },
    "read-cache": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/read-cache/-/read-cache-1.0.0.tgz",
      "integrity": "sha1-5mTvMRYRZsl1HNvo28+GtftY93Q=",
      "dev": true,
      "requires": {
        "pify": "^2.3.0"
      },
      "dependencies": {
        "pify": {
          "version": "2.3.0",
          "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
          "integrity": "sha1-7RQaasBDqEnqWISY59yosVMw6Qw=",
          "dev": true
        }
      }
    },
    "read-pkg": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/read-pkg/-/read-pkg-1.1.0.tgz",
      "integrity": "sha1-9f+qXs0pyzHAR0vKfXVra7KePyg=",
      "dev": true,
      "requires": {
        "load-json-file": "^1.0.0",
        "normalize-package-data": "^2.3.2",
        "path-type": "^1.0.0"
      },
      "dependencies": {
        "path-type": {
          "version": "1.1.0",
          "resolved": "https://registry.npmjs.org/path-type/-/path-type-1.1.0.tgz",
          "integrity": "sha1-WcRPfuSR2nBNpBXaWkBwuk+P5EE=",
          "dev": true,
          "requires": {
            "graceful-fs": "^4.1.2",
            "pify": "^2.0.0",
            "pinkie-promise": "^2.0.0"
          }
        },
        "pify": {
          "version": "2.3.0",
          "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
          "integrity": "sha1-7RQaasBDqEnqWISY59yosVMw6Qw=",
          "dev": true
        }
      }
    },
    "read-pkg-up": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/read-pkg-up/-/read-pkg-up-1.0.1.tgz",
      "integrity": "sha1-nWPBMnbAZZGNV/ACpX9AobZD+wI=",
      "dev": true,
      "requires": {
        "find-up": "^1.0.0",
        "read-pkg": "^1.0.0"
      },
      "dependencies": {
        "find-up": {
          "version": "1.1.2",
          "resolved": "https://registry.npmjs.org/find-up/-/find-up-1.1.2.tgz",
          "integrity": "sha1-ay6YIrGizgpgq2TWEOzK1TyyTQ8=",
          "dev": true,
          "requires": {
            "path-exists": "^2.0.0",
            "pinkie-promise": "^2.0.0"
          }
        },
        "path-exists": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/path-exists/-/path-exists-2.1.0.tgz",
          "integrity": "sha1-D+tsZPD8UY2adU3V77YscCJ2H0s=",
          "dev": true,
          "requires": {
            "pinkie-promise": "^2.0.0"
          }
        }
      }
    },
    "readable-stream": {
      "version": "2.3.6",
      "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-2.3.6.tgz",
      "integrity": "sha512-tQtKA9WIAhBF3+VLAseyMqZeBjW0AHJoxOtYqSUZNJxauErmLbVm2FW1y+J/YA9dUrAC39ITejlZWhVIwawkKw==",
      "dev": true,
      "requires": {
        "core-util-is": "~1.0.0",
        "inherits": "~2.0.3",
        "isarray": "~1.0.0",
        "process-nextick-args": "~2.0.0",
        "safe-buffer": "~5.1.1",
        "string_decoder": "~1.1.1",
        "util-deprecate": "~1.0.1"
      }
    },
    "readdirp": {
      "version": "2.2.1",
      "resolved": "https://registry.npmjs.org/readdirp/-/readdirp-2.2.1.tgz",
      "integrity": "sha512-1JU/8q+VgFZyxwrJ+SVIOsh+KywWGpds3NTqikiKpDMZWScmAYyKIgqkO+ARvNWJfXeXR1zxz7aHF4u4CyH6vQ==",
      "dev": true,
      "requires": {
        "graceful-fs": "^4.1.11",
        "micromatch": "^3.1.10",
        "readable-stream": "^2.0.2"
      }
    },
    "rechoir": {
      "version": "0.6.2",
      "resolved": "https://registry.npmjs.org/rechoir/-/rechoir-0.6.2.tgz",
      "integrity": "sha1-hSBLVNuoLVdC4oyWdW70OvUOM4Q=",
      "dev": true,
      "requires": {
        "resolve": "^1.1.6"
      }
    },
    "redent": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/redent/-/redent-1.0.0.tgz",
      "integrity": "sha1-z5Fqsf1fHxbfsggi3W7H9zDCr94=",
      "dev": true,
      "optional": true,
      "requires": {
        "indent-string": "^2.1.0",
        "strip-indent": "^1.0.1"
      }
    },
    "reflect-metadata": {
      "version": "0.1.13",
      "resolved": "https://registry.npmjs.org/reflect-metadata/-/reflect-metadata-0.1.13.tgz",
      "integrity": "sha512-Ts1Y/anZELhSsjMcU605fU9RE4Oi3p5ORujwbIKXfWa+0Zxs510Qrmrce5/Jowq3cHSZSJqBjypxmHarc+vEWg==",
      "dev": true
    },
    "regenerate": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/regenerate/-/regenerate-1.4.0.tgz",
      "integrity": "sha512-1G6jJVDWrt0rK99kBjvEtziZNCICAuvIPkSiUFIQxVP06RCVpq3dmDo2oi6ABpYaDYaTRr67BEhL8r1wgEZZKg==",
      "dev": true
    },
    "regenerator-runtime": {
      "version": "0.11.1",
      "resolved": "https://registry.npmjs.org/regenerator-runtime/-/regenerator-runtime-0.11.1.tgz",
      "integrity": "sha512-MguG95oij0fC3QV3URf4V2SDYGJhJnJGqvIIgdECeODCT98wSWDAJ94SSuVpYQUoTcGUIL6L4yNB7j1DFFHSBg==",
      "dev": true
    },
    "regex-cache": {
      "version": "0.4.4",
      "resolved": "https://registry.npmjs.org/regex-cache/-/regex-cache-0.4.4.tgz",
      "integrity": "sha512-nVIZwtCjkC9YgvWkpM55B5rBhBYRZhAaJbgcFYXXsHnbZ9UZI9nnVWYZpBlCqv9ho2eZryPnWrZGsOdPwVWXWQ==",
      "dev": true,
      "requires": {
        "is-equal-shallow": "^0.1.3"
      }
    },
    "regex-not": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/regex-not/-/regex-not-1.0.2.tgz",
      "integrity": "sha512-J6SDjUgDxQj5NusnOtdFxDwN/+HWykR8GELwctJ7mdqhcyy1xEc4SRFHUXvxTp661YaVKAjfRLZ9cCqS6tn32A==",
      "dev": true,
      "requires": {
        "extend-shallow": "^3.0.2",
        "safe-regex": "^1.1.0"
      }
    },
    "regexpu-core": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/regexpu-core/-/regexpu-core-1.0.0.tgz",
      "integrity": "sha1-hqdj9Y7k18L2sQLkdkBQ3n7ZDGs=",
      "dev": true,
      "requires": {
        "regenerate": "^1.2.1",
        "regjsgen": "^0.2.0",
        "regjsparser": "^0.1.4"
      }
    },
    "regjsgen": {
      "version": "0.2.0",
      "resolved": "https://registry.npmjs.org/regjsgen/-/regjsgen-0.2.0.tgz",
      "integrity": "sha1-bAFq3qxVT3WCP+N6wFuS1aTtsfc=",
      "dev": true
    },
    "regjsparser": {
      "version": "0.1.5",
      "resolved": "https://registry.npmjs.org/regjsparser/-/regjsparser-0.1.5.tgz",
      "integrity": "sha1-fuj4Tcb6eS0/0K4ijSS9lJ6tIFw=",
      "dev": true,
      "requires": {
        "jsesc": "~0.5.0"
      },
      "dependencies": {
        "jsesc": {
          "version": "0.5.0",
          "resolved": "https://registry.npmjs.org/jsesc/-/jsesc-0.5.0.tgz",
          "integrity": "sha1-597mbjXW/Bb3EP6R1c9p9w8IkR0=",
          "dev": true
        }
      }
    },
    "remove-trailing-separator": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/remove-trailing-separator/-/remove-trailing-separator-1.1.0.tgz",
      "integrity": "sha1-wkvOKig62tW8P1jg1IJJuSN52O8=",
      "dev": true
    },
    "repeat-element": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/repeat-element/-/repeat-element-1.1.3.tgz",
      "integrity": "sha512-ahGq0ZnV5m5XtZLMb+vP76kcAM5nkLqk0lpqAuojSKGgQtn4eRi4ZZGm2olo2zKFH+sMsWaqOCW1dqAnOru72g==",
      "dev": true
    },
    "repeat-string": {
      "version": "1.6.1",
      "resolved": "https://registry.npmjs.org/repeat-string/-/repeat-string-1.6.1.tgz",
      "integrity": "sha1-jcrkcOHIirwtYA//Sndihtp15jc=",
      "dev": true
    },
    "repeating": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/repeating/-/repeating-2.0.1.tgz",
      "integrity": "sha1-UhTFOpJtNVJwdSf7q0FdvAjQbdo=",
      "dev": true,
      "requires": {
        "is-finite": "^1.0.0"
      }
    },
    "request": {
      "version": "2.88.0",
      "resolved": "https://registry.npmjs.org/request/-/request-2.88.0.tgz",
      "integrity": "sha512-NAqBSrijGLZdM0WZNsInLJpkJokL72XYjUpnB0iwsRgxh7dB6COrHnTBNwN0E+lHDAJzu7kLAkDeY08z2/A0hg==",
      "dev": true,
      "requires": {
        "aws-sign2": "~0.7.0",
        "aws4": "^1.8.0",
        "caseless": "~0.12.0",
        "combined-stream": "~1.0.6",
        "extend": "~3.0.2",
        "forever-agent": "~0.6.1",
        "form-data": "~2.3.2",
        "har-validator": "~5.1.0",
        "http-signature": "~1.2.0",
        "is-typedarray": "~1.0.0",
        "isstream": "~0.1.2",
        "json-stringify-safe": "~5.0.1",
        "mime-types": "~2.1.19",
        "oauth-sign": "~0.9.0",
        "performance-now": "^2.1.0",
        "qs": "~6.5.2",
        "safe-buffer": "^5.1.2",
        "tough-cookie": "~2.4.3",
        "tunnel-agent": "^0.6.0",
        "uuid": "^3.3.2"
      }
    },
    "require-directory": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/require-directory/-/require-directory-2.1.1.tgz",
      "integrity": "sha1-jGStX9MNqxyXbiNE/+f3kqam30I=",
      "dev": true
    },
    "require-from-string": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/require-from-string/-/require-from-string-2.0.2.tgz",
      "integrity": "sha512-Xf0nWe6RseziFMu+Ap9biiUbmplq6S9/p+7w7YXP/JBHhrUDDUhwa+vANyubuqfZWTveU//DYVGsDG7RKL/vEw==",
      "dev": true
    },
    "require-main-filename": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/require-main-filename/-/require-main-filename-1.0.1.tgz",
      "integrity": "sha1-l/cXtp1IeE9fUmpsWqj/3aBVpNE=",
      "dev": true
    },
    "requires-port": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/requires-port/-/requires-port-1.0.0.tgz",
      "integrity": "sha1-kl0mAdOaxIXgkc8NpcbmlNw9yv8=",
      "dev": true
    },
    "resolve": {
      "version": "1.1.7",
      "resolved": "https://registry.npmjs.org/resolve/-/resolve-1.1.7.tgz",
      "integrity": "sha1-IDEU2CrSxe2ejgQRs5ModeiJ6Xs=",
      "dev": true
    },
    "resolve-cwd": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/resolve-cwd/-/resolve-cwd-2.0.0.tgz",
      "integrity": "sha1-AKn3OHVW4nA46uIyyqNypqWbZlo=",
      "dev": true,
      "requires": {
        "resolve-from": "^3.0.0"
      }
    },
    "resolve-from": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/resolve-from/-/resolve-from-3.0.0.tgz",
      "integrity": "sha1-six699nWiBvItuZTM17rywoYh0g=",
      "dev": true
    },
    "resolve-url": {
      "version": "0.2.1",
      "resolved": "https://registry.npmjs.org/resolve-url/-/resolve-url-0.2.1.tgz",
      "integrity": "sha1-LGN/53yJOv0qZj/iGqkIAGjiBSo=",
      "dev": true
    },
    "restore-cursor": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/restore-cursor/-/restore-cursor-2.0.0.tgz",
      "integrity": "sha1-n37ih/gv0ybU/RYpI9YhKe7g368=",
      "dev": true,
      "requires": {
        "onetime": "^2.0.0",
        "signal-exit": "^3.0.2"
      }
    },
    "ret": {
      "version": "0.1.15",
      "resolved": "https://registry.npmjs.org/ret/-/ret-0.1.15.tgz",
      "integrity": "sha512-TTlYpa+OL+vMMNG24xSlQGEJ3B/RzEfUlLct7b5G/ytav+wPrplCpVMFuwzXbkecJrb6IYo1iFb0S9v37754mg==",
      "dev": true
    },
    "retry": {
      "version": "0.10.1",
      "resolved": "https://registry.npmjs.org/retry/-/retry-0.10.1.tgz",
      "integrity": "sha1-52OI0heZLCUnUCQdPTlW/tmNj/Q=",
      "dev": true
    },
    "rfdc": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/rfdc/-/rfdc-1.1.2.tgz",
      "integrity": "sha512-92ktAgvZhBzYTIK0Mja9uen5q5J3NRVMoDkJL2VMwq6SXjVCgqvQeVP2XAaUY6HT+XpQYeLSjb3UoitBryKmdA==",
      "dev": true
    },
    "rimraf": {
      "version": "2.6.3",
      "resolved": "https://registry.npmjs.org/rimraf/-/rimraf-2.6.3.tgz",
      "integrity": "sha512-mwqeW5XsA2qAejG46gYdENaxXjx9onRNCfn7L0duuP4hCuTIi/QO7PDK07KJfp1d+izWPrzEJDcSqBa0OZQriA==",
      "dev": true,
      "requires": {
        "glob": "^7.1.3"
      }
    },
    "ripemd160": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/ripemd160/-/ripemd160-2.0.2.tgz",
      "integrity": "sha512-ii4iagi25WusVoiC4B4lq7pbXfAp3D9v5CwfkY33vffw2+pkDjY1D8GaN7spsxvCSx8dkPqOZCEZyfxcmJG2IA==",
      "dev": true,
      "requires": {
        "hash-base": "^3.0.0",
        "inherits": "^2.0.1"
      }
    },
    "run-async": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/run-async/-/run-async-2.3.0.tgz",
      "integrity": "sha1-A3GrSuC91yDUFm19/aZP96RFpsA=",
      "dev": true,
      "requires": {
        "is-promise": "^2.1.0"
      }
    },
    "run-queue": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/run-queue/-/run-queue-1.0.3.tgz",
      "integrity": "sha1-6Eg5bwV9Ij8kOGkkYY4laUFh7Ec=",
      "dev": true,
      "requires": {
        "aproba": "^1.1.1"
      }
    },
    "rxjs": {
      "version": "6.3.3",
      "resolved": "https://registry.npmjs.org/rxjs/-/rxjs-6.3.3.tgz",
      "integrity": "sha512-JTWmoY9tWCs7zvIk/CvRjhjGaOd+OVBM987mxFo+OW66cGpdKjZcpmc74ES1sB//7Kl/PAe8+wEakuhG4pcgOw==",
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "safe-buffer": {
      "version": "5.1.2",
      "resolved": "https://registry.npmjs.org/safe-buffer/-/safe-buffer-5.1.2.tgz",
      "integrity": "sha512-Gd2UZBJDkXlY7GbJxfsE8/nvKkUEU1G38c1siN6QP6a9PT9MmHB8GnpscSmMJSoF8LOIrt8ud/wPtojys4G6+g==",
      "dev": true
    },
    "safe-regex": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/safe-regex/-/safe-regex-1.1.0.tgz",
      "integrity": "sha1-QKNmnzsHfR6UPURinhV91IAjvy4=",
      "dev": true,
      "requires": {
        "ret": "~0.1.10"
      }
    },
    "safer-buffer": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/safer-buffer/-/safer-buffer-2.1.2.tgz",
      "integrity": "sha512-YZo3K82SD7Riyi0E1EQPojLz7kpepnSQI9IyPbHHg1XXXevb5dJI7tpyN2ADxGcQbHG7vcyRHk0cbwqcQriUtg==",
      "dev": true
    },
    "sass-graph": {
      "version": "2.2.4",
      "resolved": "https://registry.npmjs.org/sass-graph/-/sass-graph-2.2.4.tgz",
      "integrity": "sha1-E/vWPNHK8JCLn9k0dq1DpR0eC0k=",
      "dev": true,
      "optional": true,
      "requires": {
        "glob": "^7.0.0",
        "lodash": "^4.0.0",
        "scss-tokenizer": "^0.2.3",
        "yargs": "^7.0.0"
      }
    },
    "sass-loader": {
      "version": "7.1.0",
      "resolved": "https://registry.npmjs.org/sass-loader/-/sass-loader-7.1.0.tgz",
      "integrity": "sha512-+G+BKGglmZM2GUSfT9TLuEp6tzehHPjAMoRRItOojWIqIGPloVCMhNIQuG639eJ+y033PaGTSjLaTHts8Kw79w==",
      "dev": true,
      "requires": {
        "clone-deep": "^2.0.1",
        "loader-utils": "^1.0.1",
        "lodash.tail": "^4.1.1",
        "neo-async": "^2.5.0",
        "pify": "^3.0.0",
        "semver": "^5.5.0"
      }
    },
    "saucelabs": {
      "version": "1.5.0",
      "resolved": "https://registry.npmjs.org/saucelabs/-/saucelabs-1.5.0.tgz",
      "integrity": "sha512-jlX3FGdWvYf4Q3LFfFWS1QvPg3IGCGWxIc8QBFdPTbpTJnt/v17FHXYVAn7C8sHf1yUXo2c7yIM0isDryfYtHQ==",
      "dev": true,
      "requires": {
        "https-proxy-agent": "^2.2.1"
      }
    },
    "sax": {
      "version": "0.5.8",
      "resolved": "https://registry.npmjs.org/sax/-/sax-0.5.8.tgz",
      "integrity": "sha1-1HLbIo6zMcJQaw6MFVJK25OdEsE=",
      "dev": true
    },
    "schema-utils": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/schema-utils/-/schema-utils-1.0.0.tgz",
      "integrity": "sha512-i27Mic4KovM/lnGsy8whRCHhc7VicJajAjTrYg11K9zfZXnYIt4k5F+kZkwjnrhKzLic/HLU4j11mjsz2G/75g==",
      "dev": true,
      "requires": {
        "ajv": "^6.1.0",
        "ajv-errors": "^1.0.0",
        "ajv-keywords": "^3.1.0"
      }
    },
    "scss-tokenizer": {
      "version": "0.2.3",
      "resolved": "https://registry.npmjs.org/scss-tokenizer/-/scss-tokenizer-0.2.3.tgz",
      "integrity": "sha1-jrBtualyMzOCTT9VMGQRSYR85dE=",
      "dev": true,
      "optional": true,
      "requires": {
        "js-base64": "^2.1.8",
        "source-map": "^0.4.2"
      },
      "dependencies": {
        "source-map": {
          "version": "0.4.4",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.4.4.tgz",
          "integrity": "sha1-66T12pwNyZneaAMti092FzZSA2s=",
          "dev": true,
          "optional": true,
          "requires": {
            "amdefine": ">=0.0.4"
          }
        }
      }
    },
    "select-hose": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/select-hose/-/select-hose-2.0.0.tgz",
      "integrity": "sha1-Yl2GWPhlr0Psliv8N2o3NZpJlMo=",
      "dev": true
    },
    "selenium-webdriver": {
      "version": "3.6.0",
      "resolved": "https://registry.npmjs.org/selenium-webdriver/-/selenium-webdriver-3.6.0.tgz",
      "integrity": "sha512-WH7Aldse+2P5bbFBO4Gle/nuQOdVwpHMTL6raL3uuBj/vPG07k6uzt3aiahu352ONBr5xXh0hDlM3LhtXPOC4Q==",
      "dev": true,
      "requires": {
        "jszip": "^3.1.3",
        "rimraf": "^2.5.4",
        "tmp": "0.0.30",
        "xml2js": "^0.4.17"
      },
      "dependencies": {
        "tmp": {
          "version": "0.0.30",
          "resolved": "https://registry.npmjs.org/tmp/-/tmp-0.0.30.tgz",
          "integrity": "sha1-ckGdSovn1s51FI/YsyTlk6cRwu0=",
          "dev": true,
          "requires": {
            "os-tmpdir": "~1.0.1"
          }
        }
      }
    },
    "selfsigned": {
      "version": "1.10.4",
      "resolved": "https://registry.npmjs.org/selfsigned/-/selfsigned-1.10.4.tgz",
      "integrity": "sha512-9AukTiDmHXGXWtWjembZ5NDmVvP2695EtpgbCsxCa68w3c88B+alqbmZ4O3hZ4VWGXeGWzEVdvqgAJD8DQPCDw==",
      "dev": true,
      "requires": {
        "node-forge": "0.7.5"
      }
    },
    "semver": {
      "version": "5.5.1",
      "resolved": "https://registry.npmjs.org/semver/-/semver-5.5.1.tgz",
      "integrity": "sha512-PqpAxfrEhlSUWge8dwIp4tZnQ25DIOthpiaHNIthsjEFQD6EvqUKUDM7L8O2rShkFccYo1VjJR0coWfNkCubRw==",
      "dev": true
    },
    "semver-dsl": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/semver-dsl/-/semver-dsl-1.0.1.tgz",
      "integrity": "sha1-02eN5VVeimH2Ke7QJTZq5fJzQKA=",
      "dev": true,
      "requires": {
        "semver": "^5.3.0"
      }
    },
    "semver-intersect": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/semver-intersect/-/semver-intersect-1.4.0.tgz",
      "integrity": "sha512-d8fvGg5ycKAq0+I6nfWeCx6ffaWJCsBYU0H2Rq56+/zFePYfT8mXkB3tWBSjR5BerkHNZ5eTPIk1/LBYas35xQ==",
      "dev": true,
      "requires": {
        "semver": "^5.0.0"
      }
    },
    "send": {
      "version": "0.16.2",
      "resolved": "https://registry.npmjs.org/send/-/send-0.16.2.tgz",
      "integrity": "sha512-E64YFPUssFHEFBvpbbjr44NCLtI1AohxQ8ZSiJjQLskAdKuriYEP6VyGEsRDH8ScozGpkaX1BGvhanqCwkcEZw==",
      "dev": true,
      "requires": {
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "destroy": "~1.0.4",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "etag": "~1.8.1",
        "fresh": "0.5.2",
        "http-errors": "~1.6.2",
        "mime": "1.4.1",
        "ms": "2.0.0",
        "on-finished": "~2.3.0",
        "range-parser": "~1.2.0",
        "statuses": "~1.4.0"
      },
      "dependencies": {
        "mime": {
          "version": "1.4.1",
          "resolved": "https://registry.npmjs.org/mime/-/mime-1.4.1.tgz",
          "integrity": "sha512-KI1+qOZu5DcW6wayYHSzR/tXKCDC5Om4s1z2QJjDULzLcmf3DvzS7oluY4HCTrc+9FiKmWUgeNLg7W3uIQvxtQ==",
          "dev": true
        }
      }
    },
    "serialize-javascript": {
      "version": "1.6.1",
      "resolved": "https://registry.npmjs.org/serialize-javascript/-/serialize-javascript-1.6.1.tgz",
      "integrity": "sha512-A5MOagrPFga4YaKQSWHryl7AXvbQkEqpw4NNYMTNYUNV51bA8ABHgYFpqKx+YFFrw59xMV1qGH1R4AgoNIVgCw==",
      "dev": true
    },
    "serve-index": {
      "version": "1.9.1",
      "resolved": "https://registry.npmjs.org/serve-index/-/serve-index-1.9.1.tgz",
      "integrity": "sha1-03aNabHn2C5c4FD/9bRTvqEqkjk=",
      "dev": true,
      "requires": {
        "accepts": "~1.3.4",
        "batch": "0.6.1",
        "debug": "2.6.9",
        "escape-html": "~1.0.3",
        "http-errors": "~1.6.2",
        "mime-types": "~2.1.17",
        "parseurl": "~1.3.2"
      }
    },
    "serve-static": {
      "version": "1.13.2",
      "resolved": "https://registry.npmjs.org/serve-static/-/serve-static-1.13.2.tgz",
      "integrity": "sha512-p/tdJrO4U387R9oMjb1oj7qSMaMfmOyd4j9hOFoxZe2baQszgHcSWjuya/CiT5kgZZKRudHNOA0pYXOl8rQ5nw==",
      "dev": true,
      "requires": {
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "parseurl": "~1.3.2",
        "send": "0.16.2"
      }
    },
    "set-blocking": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/set-blocking/-/set-blocking-2.0.0.tgz",
      "integrity": "sha1-BF+XgtARrppoA93TgrJDkrPYkPc=",
      "dev": true
    },
    "set-value": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/set-value/-/set-value-2.0.0.tgz",
      "integrity": "sha512-hw0yxk9GT/Hr5yJEYnHNKYXkIA8mVJgd9ditYZCe16ZczcaELYYcfvaXesNACk2O8O0nTiPQcQhGUQj8JLzeeg==",
      "dev": true,
      "requires": {
        "extend-shallow": "^2.0.1",
        "is-extendable": "^0.1.1",
        "is-plain-object": "^2.0.3",
        "split-string": "^3.0.1"
      },
      "dependencies": {
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        }
      }
    },
    "setimmediate": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/setimmediate/-/setimmediate-1.0.5.tgz",
      "integrity": "sha1-KQy7Iy4waULX1+qbg3Mqt4VvgoU=",
      "dev": true
    },
    "setprototypeof": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/setprototypeof/-/setprototypeof-1.1.0.tgz",
      "integrity": "sha512-BvE/TwpZX4FXExxOxZyRGQQv651MSwmWKZGqvmPcRIjDqWub67kTKuIMx43cZZrS/cBBzwBcNDWoFxt2XEFIpQ==",
      "dev": true
    },
    "sha.js": {
      "version": "2.4.11",
      "resolved": "https://registry.npmjs.org/sha.js/-/sha.js-2.4.11.tgz",
      "integrity": "sha512-QMEp5B7cftE7APOjk5Y6xgrbWu+WkLVQwk8JNjZ8nKRciZaByEW6MubieAiToS7+dwvrjGhH8jRXz3MVd0AYqQ==",
      "dev": true,
      "requires": {
        "inherits": "^2.0.1",
        "safe-buffer": "^5.0.1"
      }
    },
    "shallow-clone": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/shallow-clone/-/shallow-clone-1.0.0.tgz",
      "integrity": "sha512-oeXreoKR/SyNJtRJMAKPDSvd28OqEwG4eR/xc856cRGBII7gX9lvAqDxusPm0846z/w/hWYjI1NpKwJ00NHzRA==",
      "dev": true,
      "requires": {
        "is-extendable": "^0.1.1",
        "kind-of": "^5.0.0",
        "mixin-object": "^2.0.1"
      },
      "dependencies": {
        "kind-of": {
          "version": "5.1.0",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-5.1.0.tgz",
          "integrity": "sha512-NGEErnH6F2vUuXDh+OlbcKW7/wOcfdRHaZ7VWtqCztfHri/++YKmP51OdWeGPuqCOba6kk2OTe5d02VmTB80Pw==",
          "dev": true
        }
      }
    },
    "shebang-command": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/shebang-command/-/shebang-command-1.2.0.tgz",
      "integrity": "sha1-RKrGW2lbAzmJaMOfNj/uXer98eo=",
      "dev": true,
      "requires": {
        "shebang-regex": "^1.0.0"
      }
    },
    "shebang-regex": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/shebang-regex/-/shebang-regex-1.0.0.tgz",
      "integrity": "sha1-2kL0l0DAtC2yypcoVxyxkMmO/qM=",
      "dev": true
    },
    "shelljs": {
      "version": "0.8.3",
      "resolved": "https://registry.npmjs.org/shelljs/-/shelljs-0.8.3.tgz",
      "integrity": "sha512-fc0BKlAWiLpwZljmOvAOTE/gXawtCoNrP5oaY7KIaQbbyHeQVg01pSEuEGvGh3HEdBU4baCD7wQBwADmM/7f7A==",
      "dev": true,
      "requires": {
        "glob": "^7.0.0",
        "interpret": "^1.0.0",
        "rechoir": "^0.6.2"
      }
    },
    "signal-exit": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/signal-exit/-/signal-exit-3.0.2.tgz",
      "integrity": "sha1-tf3AjxKH6hF4Yo5BXiUTK3NkbG0=",
      "dev": true
    },
    "slash": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/slash/-/slash-1.0.0.tgz",
      "integrity": "sha1-xB8vbDn8FtHNF61LXYlhFK5HDVU=",
      "dev": true
    },
    "smart-buffer": {
      "version": "4.0.2",
      "resolved": "https://registry.npmjs.org/smart-buffer/-/smart-buffer-4.0.2.tgz",
      "integrity": "sha512-JDhEpTKzXusOqXZ0BUIdH+CjFdO/CR3tLlf5CN34IypI+xMmXW1uB16OOY8z3cICbJlDAVJzNbwBhNO0wt9OAw==",
      "dev": true
    },
    "snapdragon": {
      "version": "0.8.2",
      "resolved": "https://registry.npmjs.org/snapdragon/-/snapdragon-0.8.2.tgz",
      "integrity": "sha512-FtyOnWN/wCHTVXOMwvSv26d+ko5vWlIDD6zoUJ7LW8vh+ZBC8QdljveRP+crNrtBwioEUWy/4dMtbBjA4ioNlg==",
      "dev": true,
      "requires": {
        "base": "^0.11.1",
        "debug": "^2.2.0",
        "define-property": "^0.2.5",
        "extend-shallow": "^2.0.1",
        "map-cache": "^0.2.2",
        "source-map": "^0.5.6",
        "source-map-resolve": "^0.5.0",
        "use": "^3.1.0"
      },
      "dependencies": {
        "define-property": {
          "version": "0.2.5",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-0.2.5.tgz",
          "integrity": "sha1-w1se+RjsPJkPmlvFe+BKrOxcgRY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^0.1.0"
          }
        },
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        },
        "source-map": {
          "version": "0.5.7",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.5.7.tgz",
          "integrity": "sha1-igOdLRAh0i0eoUyA2OpGi6LvP8w=",
          "dev": true
        }
      }
    },
    "snapdragon-node": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/snapdragon-node/-/snapdragon-node-2.1.1.tgz",
      "integrity": "sha512-O27l4xaMYt/RSQ5TR3vpWCAB5Kb/czIcqUFOM/C4fYcLnbZUc1PkjTAMjof2pBWaSTwOUd6qUHcFGVGj7aIwnw==",
      "dev": true,
      "requires": {
        "define-property": "^1.0.0",
        "isobject": "^3.0.0",
        "snapdragon-util": "^3.0.1"
      },
      "dependencies": {
        "define-property": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-1.0.0.tgz",
          "integrity": "sha1-dp66rz9KY6rTr56NMEybvnm/sOY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^1.0.0"
          }
        },
        "is-accessor-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-accessor-descriptor/-/is-accessor-descriptor-1.0.0.tgz",
          "integrity": "sha512-m5hnHTkcVsPfqx3AKlyttIPb7J+XykHvJP2B9bZDjlhLIoEq4XoK64Vg7boZlVWYK6LUY94dYPEE7Lh0ZkZKcQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-data-descriptor": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/is-data-descriptor/-/is-data-descriptor-1.0.0.tgz",
          "integrity": "sha512-jbRXy1FmtAoCjQkVmIVYwuuqDFUbaOeDjmed1tOGPrsMhtJA4rD9tkgA0F1qJ3gRFRXcHYVkdeaP50Q5rE/jLQ==",
          "dev": true,
          "requires": {
            "kind-of": "^6.0.0"
          }
        },
        "is-descriptor": {
          "version": "1.0.2",
          "resolved": "https://registry.npmjs.org/is-descriptor/-/is-descriptor-1.0.2.tgz",
          "integrity": "sha512-2eis5WqQGV7peooDyLmNEPUrps9+SXX5c9pL3xEB+4e9HnGuDa7mB7kHxHw4CbqS9k1T2hOH3miL8n8WtiYVtg==",
          "dev": true,
          "requires": {
            "is-accessor-descriptor": "^1.0.0",
            "is-data-descriptor": "^1.0.0",
            "kind-of": "^6.0.2"
          }
        }
      }
    },
    "snapdragon-util": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/snapdragon-util/-/snapdragon-util-3.0.1.tgz",
      "integrity": "sha512-mbKkMdQKsjX4BAL4bRYTj21edOf8cN7XHdYUJEe+Zn99hVEYcMvKPct1IqNe7+AZPirn8BCDOQBHQZknqmKlZQ==",
      "dev": true,
      "requires": {
        "kind-of": "^3.2.0"
      },
      "dependencies": {
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "socket.io": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/socket.io/-/socket.io-2.1.1.tgz",
      "integrity": "sha512-rORqq9c+7W0DAK3cleWNSyfv/qKXV99hV4tZe+gGLfBECw3XEhBy7x85F3wypA9688LKjtwO9pX9L33/xQI8yA==",
      "dev": true,
      "requires": {
        "debug": "~3.1.0",
        "engine.io": "~3.2.0",
        "has-binary2": "~1.0.2",
        "socket.io-adapter": "~1.1.0",
        "socket.io-client": "2.1.1",
        "socket.io-parser": "~3.2.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        }
      }
    },
    "socket.io-adapter": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/socket.io-adapter/-/socket.io-adapter-1.1.1.tgz",
      "integrity": "sha1-KoBeihTWNyEk3ZFZrUUC+MsH8Gs=",
      "dev": true
    },
    "socket.io-client": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/socket.io-client/-/socket.io-client-2.1.1.tgz",
      "integrity": "sha512-jxnFyhAuFxYfjqIgduQlhzqTcOEQSn+OHKVfAxWaNWa7ecP7xSNk2Dx/3UEsDcY7NcFafxvNvKPmmO7HTwTxGQ==",
      "dev": true,
      "requires": {
        "backo2": "1.0.2",
        "base64-arraybuffer": "0.1.5",
        "component-bind": "1.0.0",
        "component-emitter": "1.2.1",
        "debug": "~3.1.0",
        "engine.io-client": "~3.2.0",
        "has-binary2": "~1.0.2",
        "has-cors": "1.1.0",
        "indexof": "0.0.1",
        "object-component": "0.0.3",
        "parseqs": "0.0.5",
        "parseuri": "0.0.5",
        "socket.io-parser": "~3.2.0",
        "to-array": "0.1.4"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        }
      }
    },
    "socket.io-parser": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/socket.io-parser/-/socket.io-parser-3.2.0.tgz",
      "integrity": "sha512-FYiBx7rc/KORMJlgsXysflWx/RIvtqZbyGLlHZvjfmPTPeuD/I8MaW7cfFrj5tRltICJdgwflhfZ3NVVbVLFQA==",
      "dev": true,
      "requires": {
        "component-emitter": "1.2.1",
        "debug": "~3.1.0",
        "isarray": "2.0.1"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "dev": true,
          "requires": {
            "ms": "2.0.0"
          }
        },
        "isarray": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/isarray/-/isarray-2.0.1.tgz",
          "integrity": "sha1-o32U7ZzaLVmGXJ92/llu4fM4dB4=",
          "dev": true
        }
      }
    },
    "sockjs": {
      "version": "0.3.19",
      "resolved": "https://registry.npmjs.org/sockjs/-/sockjs-0.3.19.tgz",
      "integrity": "sha512-V48klKZl8T6MzatbLlzzRNhMepEys9Y4oGFpypBFFn1gLI/QQ9HtLLyWJNbPlwGLelOVOEijUbTTJeLLI59jLw==",
      "dev": true,
      "requires": {
        "faye-websocket": "^0.10.0",
        "uuid": "^3.0.1"
      }
    },
    "sockjs-client": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/sockjs-client/-/sockjs-client-1.3.0.tgz",
      "integrity": "sha512-R9jxEzhnnrdxLCNln0xg5uGHqMnkhPSTzUZH2eXcR03S/On9Yvoq2wyUZILRUhZCNVu2PmwWVoyuiPz8th8zbg==",
      "dev": true,
      "requires": {
        "debug": "^3.2.5",
        "eventsource": "^1.0.7",
        "faye-websocket": "~0.11.1",
        "inherits": "^2.0.3",
        "json3": "^3.3.2",
        "url-parse": "^1.4.3"
      },
      "dependencies": {
        "debug": {
          "version": "3.2.6",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
          "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "faye-websocket": {
          "version": "0.11.1",
          "resolved": "https://registry.npmjs.org/faye-websocket/-/faye-websocket-0.11.1.tgz",
          "integrity": "sha1-8O/hjE9W5PQK/H4Gxxn9XuYYjzg=",
          "dev": true,
          "requires": {
            "websocket-driver": ">=0.5.1"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        }
      }
    },
    "socks": {
      "version": "2.2.3",
      "resolved": "https://registry.npmjs.org/socks/-/socks-2.2.3.tgz",
      "integrity": "sha512-+2r83WaRT3PXYoO/1z+RDEBE7Z2f9YcdQnJ0K/ncXXbV5gJ6wYfNAebYFYiiUjM6E4JyXnPY8cimwyvFYHVUUA==",
      "dev": true,
      "requires": {
        "ip": "^1.1.5",
        "smart-buffer": "4.0.2"
      }
    },
    "socks-proxy-agent": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/socks-proxy-agent/-/socks-proxy-agent-4.0.1.tgz",
      "integrity": "sha512-Kezx6/VBguXOsEe5oU3lXYyKMi4+gva72TwJ7pQY5JfqUx2nMk7NXA6z/mpNqIlfQjWYVfeuNvQjexiTaTn6Nw==",
      "dev": true,
      "requires": {
        "agent-base": "~4.2.0",
        "socks": "~2.2.0"
      }
    },
    "source-list-map": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/source-list-map/-/source-list-map-2.0.1.tgz",
      "integrity": "sha512-qnQ7gVMxGNxsiL4lEuJwe/To8UnK7fAnmbGEEH8RpLouuKbeEm0lhbQVFIrNSuB+G7tVrAlVsZgETT5nljf+Iw==",
      "dev": true
    },
    "source-map": {
      "version": "0.7.3",
      "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.7.3.tgz",
      "integrity": "sha512-CkCj6giN3S+n9qrYiBTX5gystlENnRW5jZeNLHpe6aue+SrHcG5VYwujhW9s4dY31mEGsxBDrHR6oI69fTXsaQ==",
      "dev": true
    },
    "source-map-loader": {
      "version": "0.2.4",
      "resolved": "https://registry.npmjs.org/source-map-loader/-/source-map-loader-0.2.4.tgz",
      "integrity": "sha512-OU6UJUty+i2JDpTItnizPrlpOIBLmQbWMuBg9q5bVtnHACqw1tn9nNwqJLbv0/00JjnJb/Ee5g5WS5vrRv7zIQ==",
      "dev": true,
      "requires": {
        "async": "^2.5.0",
        "loader-utils": "^1.1.0"
      },
      "dependencies": {
        "async": {
          "version": "2.6.1",
          "resolved": "https://registry.npmjs.org/async/-/async-2.6.1.tgz",
          "integrity": "sha512-fNEiL2+AZt6AlAw/29Cr0UDe4sRAHCpEHh54WMz+Bb7QfNcFw4h3loofyJpLeQs4Yx7yuqu/2dLgM5hKOs6HlQ==",
          "dev": true,
          "requires": {
            "lodash": "^4.17.10"
          }
        }
      }
    },
    "source-map-resolve": {
      "version": "0.5.2",
      "resolved": "https://registry.npmjs.org/source-map-resolve/-/source-map-resolve-0.5.2.tgz",
      "integrity": "sha512-MjqsvNwyz1s0k81Goz/9vRBe9SZdB09Bdw+/zYyO+3CuPk6fouTaxscHkgtE8jKvf01kVfl8riHzERQ/kefaSA==",
      "dev": true,
      "requires": {
        "atob": "^2.1.1",
        "decode-uri-component": "^0.2.0",
        "resolve-url": "^0.2.1",
        "source-map-url": "^0.4.0",
        "urix": "^0.1.0"
      }
    },
    "source-map-support": {
      "version": "0.5.9",
      "resolved": "https://registry.npmjs.org/source-map-support/-/source-map-support-0.5.9.tgz",
      "integrity": "sha512-gR6Rw4MvUlYy83vP0vxoVNzM6t8MUXqNuRsuBmBHQDu1Fh6X015FrLdgoDKcNdkwGubozq0P4N0Q37UyFVr1EA==",
      "dev": true,
      "requires": {
        "buffer-from": "^1.0.0",
        "source-map": "^0.6.0"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "source-map-url": {
      "version": "0.4.0",
      "resolved": "https://registry.npmjs.org/source-map-url/-/source-map-url-0.4.0.tgz",
      "integrity": "sha1-PpNdfd1zYxuXZZlW1VEo6HtQhKM=",
      "dev": true
    },
    "sourcemap-codec": {
      "version": "1.4.4",
      "resolved": "https://registry.npmjs.org/sourcemap-codec/-/sourcemap-codec-1.4.4.tgz",
      "integrity": "sha512-CYAPYdBu34781kLHkaW3m6b/uUSyMOC2R61gcYMWooeuaGtjof86ZA/8T+qVPPt7np1085CR9hmMGrySwEc8Xg==",
      "dev": true
    },
    "spdx-correct": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/spdx-correct/-/spdx-correct-3.1.0.tgz",
      "integrity": "sha512-lr2EZCctC2BNR7j7WzJ2FpDznxky1sjfxvvYEyzxNyb6lZXHODmEoJeFu4JupYlkfha1KZpJyoqiJ7pgA1qq8Q==",
      "dev": true,
      "requires": {
        "spdx-expression-parse": "^3.0.0",
        "spdx-license-ids": "^3.0.0"
      }
    },
    "spdx-exceptions": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/spdx-exceptions/-/spdx-exceptions-2.2.0.tgz",
      "integrity": "sha512-2XQACfElKi9SlVb1CYadKDXvoajPgBVPn/gOQLrTvHdElaVhr7ZEbqJaRnJLVNeaI4cMEAgVCeBMKF6MWRDCRA==",
      "dev": true
    },
    "spdx-expression-parse": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/spdx-expression-parse/-/spdx-expression-parse-3.0.0.tgz",
      "integrity": "sha512-Yg6D3XpRD4kkOmTpdgbUiEJFKghJH03fiC1OPll5h/0sO6neh2jqRDVHOQ4o/LMea0tgCkbMgea5ip/e+MkWyg==",
      "dev": true,
      "requires": {
        "spdx-exceptions": "^2.1.0",
        "spdx-license-ids": "^3.0.0"
      }
    },
    "spdx-license-ids": {
      "version": "3.0.3",
      "resolved": "https://registry.npmjs.org/spdx-license-ids/-/spdx-license-ids-3.0.3.tgz",
      "integrity": "sha512-uBIcIl3Ih6Phe3XHK1NqboJLdGfwr1UN3k6wSD1dZpmPsIkb8AGNbZYJ1fOBk834+Gxy8rpfDxrS6XLEMZMY2g==",
      "dev": true
    },
    "spdy": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/spdy/-/spdy-4.0.0.tgz",
      "integrity": "sha512-ot0oEGT/PGUpzf/6uk4AWLqkq+irlqHXkrdbk51oWONh3bxQmBuljxPNl66zlRRcIJStWq0QkLUCPOPjgjvU0Q==",
      "dev": true,
      "requires": {
        "debug": "^4.1.0",
        "handle-thing": "^2.0.0",
        "http-deceiver": "^1.2.7",
        "select-hose": "^2.0.0",
        "spdy-transport": "^3.0.0"
      },
      "dependencies": {
        "debug": {
          "version": "4.1.1",
          "resolved": "https://registry.npmjs.org/debug/-/debug-4.1.1.tgz",
          "integrity": "sha512-pYAIzeRo8J6KPEaJ0VWOh5Pzkbw/RetuzehGM7QRRX5he4fPHx2rdKMB256ehJCkX+XRQm16eZLqLNS8RSZXZw==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        }
      }
    },
    "spdy-transport": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/spdy-transport/-/spdy-transport-3.0.0.tgz",
      "integrity": "sha512-hsLVFE5SjA6TCisWeJXFKniGGOpBgMLmerfO2aCyCU5s7nJ/rpAepqmFifv/GCbSbueEeAJJnmSQ2rKC/g8Fcw==",
      "dev": true,
      "requires": {
        "debug": "^4.1.0",
        "detect-node": "^2.0.4",
        "hpack.js": "^2.1.6",
        "obuf": "^1.1.2",
        "readable-stream": "^3.0.6",
        "wbuf": "^1.7.3"
      },
      "dependencies": {
        "debug": {
          "version": "4.1.1",
          "resolved": "https://registry.npmjs.org/debug/-/debug-4.1.1.tgz",
          "integrity": "sha512-pYAIzeRo8J6KPEaJ0VWOh5Pzkbw/RetuzehGM7QRRX5he4fPHx2rdKMB256ehJCkX+XRQm16eZLqLNS8RSZXZw==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        },
        "readable-stream": {
          "version": "3.1.1",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-3.1.1.tgz",
          "integrity": "sha512-DkN66hPyqDhnIQ6Jcsvx9bFjhw214O4poMBcIMgPVpQvNy9a0e0Uhg5SqySyDKAmUlwt8LonTBz1ezOnM8pUdA==",
          "dev": true,
          "requires": {
            "inherits": "^2.0.3",
            "string_decoder": "^1.1.1",
            "util-deprecate": "^1.0.1"
          }
        }
      }
    },
    "speed-measure-webpack-plugin": {
      "version": "1.2.5",
      "resolved": "https://registry.npmjs.org/speed-measure-webpack-plugin/-/speed-measure-webpack-plugin-1.2.5.tgz",
      "integrity": "sha512-S/guYjC4Izn5wY2d0+M4zowED/F77Lxh9yjkTZ+XAr244pr9c1MYNcXcRe9lx2hmAj0GPbOrBXgOF2YIp/CZ8A==",
      "dev": true,
      "requires": {
        "chalk": "^2.0.1"
      }
    },
    "split-string": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/split-string/-/split-string-3.1.0.tgz",
      "integrity": "sha512-NzNVhJDYpwceVVii8/Hu6DKfD2G+NrQHlS/V/qgv763EYudVwEcMQNxd2lh+0VrUByXN/oJkl5grOhYWvQUYiw==",
      "dev": true,
      "requires": {
        "extend-shallow": "^3.0.0"
      }
    },
    "sprintf-js": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/sprintf-js/-/sprintf-js-1.0.3.tgz",
      "integrity": "sha1-BOaSb2YolTVPPdAVIDYzuFcpfiw=",
      "dev": true
    },
    "sshpk": {
      "version": "1.16.1",
      "resolved": "https://registry.npmjs.org/sshpk/-/sshpk-1.16.1.tgz",
      "integrity": "sha512-HXXqVUq7+pcKeLqqZj6mHFUMvXtOJt1uoUx09pFW6011inTMxqI8BA8PM95myrIyyKwdnzjdFjLiE6KBPVtJIg==",
      "dev": true,
      "requires": {
        "asn1": "~0.2.3",
        "assert-plus": "^1.0.0",
        "bcrypt-pbkdf": "^1.0.0",
        "dashdash": "^1.12.0",
        "ecc-jsbn": "~0.1.1",
        "getpass": "^0.1.1",
        "jsbn": "~0.1.0",
        "safer-buffer": "^2.0.2",
        "tweetnacl": "~0.14.0"
      }
    },
    "ssri": {
      "version": "5.3.0",
      "resolved": "https://registry.npmjs.org/ssri/-/ssri-5.3.0.tgz",
      "integrity": "sha512-XRSIPqLij52MtgoQavH/x/dU1qVKtWUAAZeOHsR9c2Ddi4XerFy3mc1alf+dLJKl9EUIm/Ht+EowFkTUOA6GAQ==",
      "dev": true,
      "requires": {
        "safe-buffer": "^5.1.1"
      }
    },
    "static-extend": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/static-extend/-/static-extend-0.1.2.tgz",
      "integrity": "sha1-YICcOcv/VTNyJv1eC1IPNB8ftcY=",
      "dev": true,
      "requires": {
        "define-property": "^0.2.5",
        "object-copy": "^0.1.0"
      },
      "dependencies": {
        "define-property": {
          "version": "0.2.5",
          "resolved": "https://registry.npmjs.org/define-property/-/define-property-0.2.5.tgz",
          "integrity": "sha1-w1se+RjsPJkPmlvFe+BKrOxcgRY=",
          "dev": true,
          "requires": {
            "is-descriptor": "^0.1.0"
          }
        }
      }
    },
    "stats-webpack-plugin": {
      "version": "0.7.0",
      "resolved": "https://registry.npmjs.org/stats-webpack-plugin/-/stats-webpack-plugin-0.7.0.tgz",
      "integrity": "sha512-NT0YGhwuQ0EOX+uPhhUcI6/+1Sq/pMzNuSCBVT4GbFl/ac6I/JZefBcjlECNfAb1t3GOx5dEj1Z7x0cAxeeVLQ==",
      "dev": true,
      "requires": {
        "lodash": "^4.17.4"
      }
    },
    "statuses": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/statuses/-/statuses-1.4.0.tgz",
      "integrity": "sha512-zhSCtt8v2NDrRlPQpCNtw/heZLtfUDqxBM1udqikb/Hbk52LK4nQSwr10u77iopCW5LsyHpuXS0GnEc48mLeew==",
      "dev": true
    },
    "stdout-stream": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/stdout-stream/-/stdout-stream-1.4.1.tgz",
      "integrity": "sha512-j4emi03KXqJWcIeF8eIXkjMFN1Cmb8gUlDYGeBALLPo5qdyTfA9bOtl8m33lRoC+vFMkP3gl0WsDr6+gzxbbTA==",
      "dev": true,
      "optional": true,
      "requires": {
        "readable-stream": "^2.0.1"
      }
    },
    "stream-browserify": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/stream-browserify/-/stream-browserify-2.0.2.tgz",
      "integrity": "sha512-nX6hmklHs/gr2FuxYDltq8fJA1GDlxKQCz8O/IM4atRqBH8OORmBNgfvW5gG10GT/qQ9u0CzIvr2X5Pkt6ntqg==",
      "dev": true,
      "requires": {
        "inherits": "~2.0.1",
        "readable-stream": "^2.0.2"
      }
    },
    "stream-each": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/stream-each/-/stream-each-1.2.3.tgz",
      "integrity": "sha512-vlMC2f8I2u/bZGqkdfLQW/13Zihpej/7PmSiMQsbYddxuTsJp8vRe2x2FvVExZg7FaOds43ROAuFJwPR4MTZLw==",
      "dev": true,
      "requires": {
        "end-of-stream": "^1.1.0",
        "stream-shift": "^1.0.0"
      }
    },
    "stream-http": {
      "version": "2.8.3",
      "resolved": "https://registry.npmjs.org/stream-http/-/stream-http-2.8.3.tgz",
      "integrity": "sha512-+TSkfINHDo4J+ZobQLWiMouQYB+UVYFttRA94FpEzzJ7ZdqcL4uUUQ7WkdkI4DSozGmgBUE/a47L+38PenXhUw==",
      "dev": true,
      "requires": {
        "builtin-status-codes": "^3.0.0",
        "inherits": "^2.0.1",
        "readable-stream": "^2.3.6",
        "to-arraybuffer": "^1.0.0",
        "xtend": "^4.0.0"
      }
    },
    "stream-shift": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/stream-shift/-/stream-shift-1.0.0.tgz",
      "integrity": "sha1-1cdSgl5TZ+eG944Y5EXqIjoVWVI=",
      "dev": true
    },
    "streamroller": {
      "version": "0.7.0",
      "resolved": "https://registry.npmjs.org/streamroller/-/streamroller-0.7.0.tgz",
      "integrity": "sha512-WREzfy0r0zUqp3lGO096wRuUp7ho1X6uo/7DJfTlEi0Iv/4gT7YHqXDjKC2ioVGBZtE8QzsQD9nx1nIuoZ57jQ==",
      "dev": true,
      "requires": {
        "date-format": "^1.2.0",
        "debug": "^3.1.0",
        "mkdirp": "^0.5.1",
        "readable-stream": "^2.3.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.2.6",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
          "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        }
      }
    },
    "string-width": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/string-width/-/string-width-1.0.2.tgz",
      "integrity": "sha1-EYvfW4zcUaKn5w0hHgfisLmxB9M=",
      "dev": true,
      "requires": {
        "code-point-at": "^1.0.0",
        "is-fullwidth-code-point": "^1.0.0",
        "strip-ansi": "^3.0.0"
      }
    },
    "string_decoder": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.1.1.tgz",
      "integrity": "sha512-n/ShnvDi6FHbbVfviro+WojiFzv+s8MPMHBczVePfUpDJLwoLT0ht1l4YwBCbi8pJAveEEdnkHyPyTP/mzRfwg==",
      "dev": true,
      "requires": {
        "safe-buffer": "~5.1.0"
      }
    },
    "strip-ansi": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-3.0.1.tgz",
      "integrity": "sha1-ajhfuIU9lS1f8F0Oiq+UJ43GPc8=",
      "dev": true,
      "requires": {
        "ansi-regex": "^2.0.0"
      }
    },
    "strip-bom": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/strip-bom/-/strip-bom-2.0.0.tgz",
      "integrity": "sha1-YhmoVhZSBJHzV4i9vxRHqZx+aw4=",
      "dev": true,
      "requires": {
        "is-utf8": "^0.2.0"
      }
    },
    "strip-eof": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/strip-eof/-/strip-eof-1.0.0.tgz",
      "integrity": "sha1-u0P/VZim6wXYm1n80SnJgzE2Br8=",
      "dev": true
    },
    "strip-indent": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/strip-indent/-/strip-indent-1.0.1.tgz",
      "integrity": "sha1-DHlipq3vp7vUrDZkYKY4VSrhoKI=",
      "dev": true,
      "optional": true,
      "requires": {
        "get-stdin": "^4.0.1"
      }
    },
    "style-loader": {
      "version": "0.23.1",
      "resolved": "https://registry.npmjs.org/style-loader/-/style-loader-0.23.1.tgz",
      "integrity": "sha512-XK+uv9kWwhZMZ1y7mysB+zoihsEj4wneFWAS5qoiLwzW0WzSqMrrsIy+a3zkQJq0ipFtBpX5W3MqyRIBF/WFGg==",
      "dev": true,
      "requires": {
        "loader-utils": "^1.1.0",
        "schema-utils": "^1.0.0"
      }
    },
    "stylus": {
      "version": "0.54.5",
      "resolved": "https://registry.npmjs.org/stylus/-/stylus-0.54.5.tgz",
      "integrity": "sha1-QrlWCTHKcJDOhRWnmLqeaqPW3Hk=",
      "dev": true,
      "requires": {
        "css-parse": "1.7.x",
        "debug": "*",
        "glob": "7.0.x",
        "mkdirp": "0.5.x",
        "sax": "0.5.x",
        "source-map": "0.1.x"
      },
      "dependencies": {
        "glob": {
          "version": "7.0.6",
          "resolved": "https://registry.npmjs.org/glob/-/glob-7.0.6.tgz",
          "integrity": "sha1-IRuvr0nlJbjNkyYNFKsTYVKz9Xo=",
          "dev": true,
          "requires": {
            "fs.realpath": "^1.0.0",
            "inflight": "^1.0.4",
            "inherits": "2",
            "minimatch": "^3.0.2",
            "once": "^1.3.0",
            "path-is-absolute": "^1.0.0"
          }
        },
        "source-map": {
          "version": "0.1.43",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.1.43.tgz",
          "integrity": "sha1-wkvBRspRfBRx9drL4lcbK3+eM0Y=",
          "dev": true,
          "requires": {
            "amdefine": ">=0.0.4"
          }
        }
      }
    },
    "stylus-loader": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/stylus-loader/-/stylus-loader-3.0.2.tgz",
      "integrity": "sha512-+VomPdZ6a0razP+zinir61yZgpw2NfljeSsdUF5kJuEzlo3khXhY19Fn6l8QQz1GRJGtMCo8nG5C04ePyV7SUA==",
      "dev": true,
      "requires": {
        "loader-utils": "^1.0.2",
        "lodash.clonedeep": "^4.5.0",
        "when": "~3.6.x"
      }
    },
    "supports-color": {
      "version": "6.1.0",
      "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-6.1.0.tgz",
      "integrity": "sha512-qe1jfm1Mg7Nq/NSh6XE24gPXROEVsWHxC1LIx//XNlD9iw7YZQGjZNjYN7xGaEG6iKdA8EtNFW6R0gjnVXp+wQ==",
      "dev": true,
      "requires": {
        "has-flag": "^3.0.0"
      }
    },
    "symbol-observable": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/symbol-observable/-/symbol-observable-1.2.0.tgz",
      "integrity": "sha512-e900nM8RRtGhlV36KGEU9k65K3mPb1WV70OdjfxlG2EAuM1noi/E/BaW/uMhL7bPEssK8QV57vN3esixjUvcXQ==",
      "dev": true
    },
    "tapable": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/tapable/-/tapable-1.1.1.tgz",
      "integrity": "sha512-9I2ydhj8Z9veORCw5PRm4u9uebCn0mcCa6scWoNcbZ6dAtoo2618u9UUzxgmsCOreJpqDDuv61LvwofW7hLcBA==",
      "dev": true
    },
    "tar": {
      "version": "2.2.1",
      "resolved": "https://registry.npmjs.org/tar/-/tar-2.2.1.tgz",
      "integrity": "sha1-jk0qJWwOIYXGsYrWlK7JaLg8sdE=",
      "dev": true,
      "optional": true,
      "requires": {
        "block-stream": "*",
        "fstream": "^1.0.2",
        "inherits": "2"
      }
    },
    "terser": {
      "version": "3.14.1",
      "resolved": "https://registry.npmjs.org/terser/-/terser-3.14.1.tgz",
      "integrity": "sha512-NSo3E99QDbYSMeJaEk9YW2lTg3qS9V0aKGlb+PlOrei1X02r1wSBHCNX/O+yeTRFSWPKPIGj6MqvvdqV4rnVGw==",
      "dev": true,
      "requires": {
        "commander": "~2.17.1",
        "source-map": "~0.6.1",
        "source-map-support": "~0.5.6"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "terser-webpack-plugin": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/terser-webpack-plugin/-/terser-webpack-plugin-1.2.1.tgz",
      "integrity": "sha512-GGSt+gbT0oKcMDmPx4SRSfJPE1XaN3kQRWG4ghxKQw9cn5G9x6aCKSsgYdvyM0na9NJ4Drv0RG6jbBByZ5CMjw==",
      "dev": true,
      "requires": {
        "cacache": "^11.0.2",
        "find-cache-dir": "^2.0.0",
        "schema-utils": "^1.0.0",
        "serialize-javascript": "^1.4.0",
        "source-map": "^0.6.1",
        "terser": "^3.8.1",
        "webpack-sources": "^1.1.0",
        "worker-farm": "^1.5.2"
      },
      "dependencies": {
        "cacache": {
          "version": "11.3.2",
          "resolved": "https://registry.npmjs.org/cacache/-/cacache-11.3.2.tgz",
          "integrity": "sha512-E0zP4EPGDOaT2chM08Als91eYnf8Z+eH1awwwVsngUmgppfM5jjJ8l3z5vO5p5w/I3LsiXawb1sW0VY65pQABg==",
          "dev": true,
          "requires": {
            "bluebird": "^3.5.3",
            "chownr": "^1.1.1",
            "figgy-pudding": "^3.5.1",
            "glob": "^7.1.3",
            "graceful-fs": "^4.1.15",
            "lru-cache": "^5.1.1",
            "mississippi": "^3.0.0",
            "mkdirp": "^0.5.1",
            "move-concurrently": "^1.0.1",
            "promise-inflight": "^1.0.1",
            "rimraf": "^2.6.2",
            "ssri": "^6.0.1",
            "unique-filename": "^1.1.1",
            "y18n": "^4.0.0"
          }
        },
        "find-cache-dir": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/find-cache-dir/-/find-cache-dir-2.0.0.tgz",
          "integrity": "sha512-LDUY6V1Xs5eFskUVYtIwatojt6+9xC9Chnlk/jYOOvn3FAFfSaWddxahDGyNHh0b2dMXa6YW2m0tk8TdVaXHlA==",
          "dev": true,
          "requires": {
            "commondir": "^1.0.1",
            "make-dir": "^1.0.0",
            "pkg-dir": "^3.0.0"
          }
        },
        "find-up": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/find-up/-/find-up-3.0.0.tgz",
          "integrity": "sha512-1yD6RmLI1XBfxugvORwlck6f75tYL+iR0jqwsOrOxMZyGYqUuDhJ0l4AXdO1iX/FTs9cBAMEk1gWSEx1kSbylg==",
          "dev": true,
          "requires": {
            "locate-path": "^3.0.0"
          }
        },
        "locate-path": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/locate-path/-/locate-path-3.0.0.tgz",
          "integrity": "sha512-7AO748wWnIhNqAuaty2ZWHkQHRSNfPVIsPIfwEOWO22AmaoVrWavlOcMR5nzTLNYvp36X220/maaRsrec1G65A==",
          "dev": true,
          "requires": {
            "p-locate": "^3.0.0",
            "path-exists": "^3.0.0"
          }
        },
        "lru-cache": {
          "version": "5.1.1",
          "resolved": "https://registry.npmjs.org/lru-cache/-/lru-cache-5.1.1.tgz",
          "integrity": "sha512-KpNARQA3Iwv+jTA0utUVVbrh+Jlrr1Fv0e56GGzAFOXN7dk/FviaDW8LHmK52DlcH4WP2n6gI8vN1aesBFgo9w==",
          "dev": true,
          "requires": {
            "yallist": "^3.0.2"
          }
        },
        "mississippi": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/mississippi/-/mississippi-3.0.0.tgz",
          "integrity": "sha512-x471SsVjUtBRtcvd4BzKE9kFC+/2TeWgKCgw0bZcw1b9l2X3QX5vCWgF+KaZaYm87Ss//rHnWryupDrgLvmSkA==",
          "dev": true,
          "requires": {
            "concat-stream": "^1.5.0",
            "duplexify": "^3.4.2",
            "end-of-stream": "^1.1.0",
            "flush-write-stream": "^1.0.0",
            "from2": "^2.1.0",
            "parallel-transform": "^1.1.0",
            "pump": "^3.0.0",
            "pumpify": "^1.3.3",
            "stream-each": "^1.1.0",
            "through2": "^2.0.0"
          }
        },
        "p-limit": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/p-limit/-/p-limit-2.1.0.tgz",
          "integrity": "sha512-NhURkNcrVB+8hNfLuysU8enY5xn2KXphsHBaC2YmRNTZRc7RWusw6apSpdEj3jo4CMb6W9nrF6tTnsJsJeyu6g==",
          "dev": true,
          "requires": {
            "p-try": "^2.0.0"
          }
        },
        "p-locate": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/p-locate/-/p-locate-3.0.0.tgz",
          "integrity": "sha512-x+12w/To+4GFfgJhBEpiDcLozRJGegY+Ei7/z0tSLkMmxGZNybVMSfWj9aJn8Z5Fc7dBUNJOOVgPv2H7IwulSQ==",
          "dev": true,
          "requires": {
            "p-limit": "^2.0.0"
          }
        },
        "p-try": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/p-try/-/p-try-2.0.0.tgz",
          "integrity": "sha512-hMp0onDKIajHfIkdRk3P4CdCmErkYAxxDtP3Wx/4nZ3aGlau2VKh3mZpcuFkH27WQkL/3WBCPOktzA9ZOAnMQQ==",
          "dev": true
        },
        "pkg-dir": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/pkg-dir/-/pkg-dir-3.0.0.tgz",
          "integrity": "sha512-/E57AYkoeQ25qkxMj5PBOVgF8Kiu/h7cYS30Z5+R7WaiCCBfLq58ZI/dSeaEKb9WVJV5n/03QwrN3IeWIFllvw==",
          "dev": true,
          "requires": {
            "find-up": "^3.0.0"
          }
        },
        "pump": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/pump/-/pump-3.0.0.tgz",
          "integrity": "sha512-LwZy+p3SFs1Pytd/jYct4wpv49HiYCqd9Rlc5ZVdk0V+8Yzv6jR5Blk3TRmPL1ft69TxP0IMZGJ+WPFU2BFhww==",
          "dev": true,
          "requires": {
            "end-of-stream": "^1.1.0",
            "once": "^1.3.1"
          }
        },
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        },
        "ssri": {
          "version": "6.0.1",
          "resolved": "https://registry.npmjs.org/ssri/-/ssri-6.0.1.tgz",
          "integrity": "sha512-3Wge10hNcT1Kur4PDFwEieXSCMCJs/7WvSACcrMYrNp+b8kDL1/0wJch5Ni2WrtwEa2IO8OsVfeKIciKCDx/QA==",
          "dev": true,
          "requires": {
            "figgy-pudding": "^3.5.1"
          }
        },
        "yallist": {
          "version": "3.0.3",
          "resolved": "https://registry.npmjs.org/yallist/-/yallist-3.0.3.tgz",
          "integrity": "sha512-S+Zk8DEWE6oKpV+vI3qWkaK+jSbIK86pCwe2IF/xwIpQ8jEuxpw9NyaGjmp9+BoJv5FV2piqCDcoCtStppiq2A==",
          "dev": true
        }
      }
    },
    "through": {
      "version": "2.3.8",
      "resolved": "https://registry.npmjs.org/through/-/through-2.3.8.tgz",
      "integrity": "sha1-DdTJ/6q8NXlgsbckEV1+Doai4fU=",
      "dev": true
    },
    "through2": {
      "version": "2.0.5",
      "resolved": "https://registry.npmjs.org/through2/-/through2-2.0.5.tgz",
      "integrity": "sha512-/mrRod8xqpA+IHSLyGCQ2s8SPHiCDEeQJSep1jqLYeEUClOFG2Qsh+4FU6G9VeqpZnGW/Su8LQGc4YKni5rYSQ==",
      "dev": true,
      "requires": {
        "readable-stream": "~2.3.6",
        "xtend": "~4.0.1"
      }
    },
    "thunky": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/thunky/-/thunky-1.0.3.tgz",
      "integrity": "sha512-YwT8pjmNcAXBZqrubu22P4FYsh2D4dxRmnWBOL8Jk8bUcRUtc5326kx32tuTmFDAZtLOGEVNl8POAR8j896Iow==",
      "dev": true
    },
    "timers-browserify": {
      "version": "2.0.10",
      "resolved": "https://registry.npmjs.org/timers-browserify/-/timers-browserify-2.0.10.tgz",
      "integrity": "sha512-YvC1SV1XdOUaL6gx5CoGroT3Gu49pK9+TZ38ErPldOWW4j49GI1HKs9DV+KGq/w6y+LZ72W1c8cKz2vzY+qpzg==",
      "dev": true,
      "requires": {
        "setimmediate": "^1.0.4"
      }
    },
    "tmp": {
      "version": "0.0.33",
      "resolved": "https://registry.npmjs.org/tmp/-/tmp-0.0.33.tgz",
      "integrity": "sha512-jRCJlojKnZ3addtTOjdIqoRuPEKBvNXcGYqzO6zWZX8KfKEpnGY5jfggJQ3EjKuu8D4bJRr0y+cYJFmYbImXGw==",
      "dev": true,
      "requires": {
        "os-tmpdir": "~1.0.2"
      }
    },
    "to-array": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/to-array/-/to-array-0.1.4.tgz",
      "integrity": "sha1-F+bBH3PdTz10zaek/zI46a2b+JA=",
      "dev": true
    },
    "to-arraybuffer": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/to-arraybuffer/-/to-arraybuffer-1.0.1.tgz",
      "integrity": "sha1-fSKbH8xjfkZsoIEYCDanqr/4P0M=",
      "dev": true
    },
    "to-fast-properties": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/to-fast-properties/-/to-fast-properties-1.0.3.tgz",
      "integrity": "sha1-uDVx+k2MJbguIxsG46MFXeTKGkc=",
      "dev": true
    },
    "to-object-path": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/to-object-path/-/to-object-path-0.3.0.tgz",
      "integrity": "sha1-KXWIt7Dn4KwI4E5nL4XB9JmeF68=",
      "dev": true,
      "requires": {
        "kind-of": "^3.0.2"
      },
      "dependencies": {
        "kind-of": {
          "version": "3.2.2",
          "resolved": "https://registry.npmjs.org/kind-of/-/kind-of-3.2.2.tgz",
          "integrity": "sha1-MeohpzS6ubuw8yRm2JOupR5KPGQ=",
          "dev": true,
          "requires": {
            "is-buffer": "^1.1.5"
          }
        }
      }
    },
    "to-regex": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/to-regex/-/to-regex-3.0.2.tgz",
      "integrity": "sha512-FWtleNAtZ/Ki2qtqej2CXTOayOH9bHDQF+Q48VpWyDXjbYxA4Yz8iDB31zXOBUlOHHKidDbqGVrTUvQMPmBGBw==",
      "dev": true,
      "requires": {
        "define-property": "^2.0.2",
        "extend-shallow": "^3.0.2",
        "regex-not": "^1.0.2",
        "safe-regex": "^1.1.0"
      }
    },
    "to-regex-range": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/to-regex-range/-/to-regex-range-2.1.1.tgz",
      "integrity": "sha1-fIDBe53+vlmeJzZ+DU3VWQFB2zg=",
      "dev": true,
      "requires": {
        "is-number": "^3.0.0",
        "repeat-string": "^1.6.1"
      }
    },
    "tough-cookie": {
      "version": "2.4.3",
      "resolved": "https://registry.npmjs.org/tough-cookie/-/tough-cookie-2.4.3.tgz",
      "integrity": "sha512-Q5srk/4vDM54WJsJio3XNn6K2sCG+CQ8G5Wz6bZhRZoAe/+TxjWB/GlFAnYEbkYVlON9FMk/fE3h2RLpPXo4lQ==",
      "dev": true,
      "requires": {
        "psl": "^1.1.24",
        "punycode": "^1.4.1"
      },
      "dependencies": {
        "punycode": {
          "version": "1.4.1",
          "resolved": "https://registry.npmjs.org/punycode/-/punycode-1.4.1.tgz",
          "integrity": "sha1-wNWmOycYgArY4esPpSachN1BhF4=",
          "dev": true
        }
      }
    },
    "tree-kill": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/tree-kill/-/tree-kill-1.2.0.tgz",
      "integrity": "sha512-DlX6dR0lOIRDFxI0mjL9IYg6OTncLm/Zt+JiBhE5OlFcAR8yc9S7FFXU9so0oda47frdM/JFsk7UjNt9vscKcg==",
      "dev": true
    },
    "trim-newlines": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/trim-newlines/-/trim-newlines-1.0.0.tgz",
      "integrity": "sha1-WIeWa7WCpFA6QetST301ARgVphM=",
      "dev": true,
      "optional": true
    },
    "trim-right": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/trim-right/-/trim-right-1.0.1.tgz",
      "integrity": "sha1-yy4SAwZ+DI3h9hQJS5/kVwTqYAM=",
      "dev": true
    },
    "true-case-path": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/true-case-path/-/true-case-path-1.0.3.tgz",
      "integrity": "sha512-m6s2OdQe5wgpFMC+pAJ+q9djG82O2jcHPOI6RNg1yy9rCYR+WD6Nbpl32fDpfC56nirdRy+opFa/Vk7HYhqaew==",
      "dev": true,
      "optional": true,
      "requires": {
        "glob": "^7.1.2"
      }
    },
    "ts-node": {
      "version": "7.0.1",
      "resolved": "https://registry.npmjs.org/ts-node/-/ts-node-7.0.1.tgz",
      "integrity": "sha512-BVwVbPJRspzNh2yfslyT1PSbl5uIk03EZlb493RKHN4qej/D06n1cEhjlOJG69oFsE7OT8XjpTUcYf6pKTLMhw==",
      "dev": true,
      "requires": {
        "arrify": "^1.0.0",
        "buffer-from": "^1.1.0",
        "diff": "^3.1.0",
        "make-error": "^1.1.1",
        "minimist": "^1.2.0",
        "mkdirp": "^0.5.1",
        "source-map-support": "^0.5.6",
        "yn": "^2.0.0"
      },
      "dependencies": {
        "minimist": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/minimist/-/minimist-1.2.0.tgz",
          "integrity": "sha1-o1AIsg9BOD7sH7kU9M1d95omQoQ=",
          "dev": true
        }
      }
    },
    "tslib": {
      "version": "1.9.3",
      "resolved": "https://registry.npmjs.org/tslib/-/tslib-1.9.3.tgz",
      "integrity": "sha512-4krF8scpejhaOgqzBEcGM7yDIEfi0/8+8zDRZhNZZ2kjmHJ4hv3zCbQWxoJGz1iw5U0Jl0nma13xzHXcncMavQ=="
    },
    "tslint": {
      "version": "5.11.0",
      "resolved": "https://registry.npmjs.org/tslint/-/tslint-5.11.0.tgz",
      "integrity": "sha1-mPMMAurjzecAYgHkwzywi0hYHu0=",
      "dev": true,
      "requires": {
        "babel-code-frame": "^6.22.0",
        "builtin-modules": "^1.1.1",
        "chalk": "^2.3.0",
        "commander": "^2.12.1",
        "diff": "^3.2.0",
        "glob": "^7.1.1",
        "js-yaml": "^3.7.0",
        "minimatch": "^3.0.4",
        "resolve": "^1.3.2",
        "semver": "^5.3.0",
        "tslib": "^1.8.0",
        "tsutils": "^2.27.2"
      },
      "dependencies": {
        "resolve": {
          "version": "1.10.0",
          "resolved": "https://registry.npmjs.org/resolve/-/resolve-1.10.0.tgz",
          "integrity": "sha512-3sUr9aq5OfSg2S9pNtPA9hL1FVEAjvfOC4leW0SNf/mpnaakz2a9femSd6LqAww2RaFctwyf1lCqnTHuF1rxDg==",
          "dev": true,
          "requires": {
            "path-parse": "^1.0.6"
          }
        }
      }
    },
    "tsutils": {
      "version": "2.29.0",
      "resolved": "https://registry.npmjs.org/tsutils/-/tsutils-2.29.0.tgz",
      "integrity": "sha512-g5JVHCIJwzfISaXpXE1qvNalca5Jwob6FjI4AoPlqMusJ6ftFE7IkkFoMhVLRgK+4Kx3gkzb8UZK5t5yTTvEmA==",
      "dev": true,
      "requires": {
        "tslib": "^1.8.1"
      }
    },
    "tty-browserify": {
      "version": "0.0.0",
      "resolved": "https://registry.npmjs.org/tty-browserify/-/tty-browserify-0.0.0.tgz",
      "integrity": "sha1-oVe6QC2iTpv5V/mqadUk7tQpAaY=",
      "dev": true
    },
    "tunnel-agent": {
      "version": "0.6.0",
      "resolved": "https://registry.npmjs.org/tunnel-agent/-/tunnel-agent-0.6.0.tgz",
      "integrity": "sha1-J6XeoGs2sEoKmWZ3SykIaPD8QP0=",
      "dev": true,
      "requires": {
        "safe-buffer": "^5.0.1"
      }
    },
    "tweetnacl": {
      "version": "0.14.5",
      "resolved": "https://registry.npmjs.org/tweetnacl/-/tweetnacl-0.14.5.tgz",
      "integrity": "sha1-WuaBd/GS1EViadEIr6k/+HQ/T2Q=",
      "dev": true
    },
    "type-check": {
      "version": "0.3.2",
      "resolved": "https://registry.npmjs.org/type-check/-/type-check-0.3.2.tgz",
      "integrity": "sha1-WITKtRLPHTVeP7eE8wgEsrUg23I=",
      "dev": true,
      "requires": {
        "prelude-ls": "~1.1.2"
      }
    },
    "type-is": {
      "version": "1.6.16",
      "resolved": "https://registry.npmjs.org/type-is/-/type-is-1.6.16.tgz",
      "integrity": "sha512-HRkVv/5qY2G6I8iab9cI7v1bOIdhm94dVjQCPFElW9W+3GeDOSHmy2EBYe4VTApuzolPcmgFTN3ftVJRKR2J9Q==",
      "dev": true,
      "requires": {
        "media-typer": "0.3.0",
        "mime-types": "~2.1.18"
      }
    },
    "typedarray": {
      "version": "0.0.6",
      "resolved": "https://registry.npmjs.org/typedarray/-/typedarray-0.0.6.tgz",
      "integrity": "sha1-hnrHTjhkGHsdPUfZlqeOxciDB3c=",
      "dev": true
    },
    "typescript": {
      "version": "3.2.4",
      "resolved": "https://registry.npmjs.org/typescript/-/typescript-3.2.4.tgz",
      "integrity": "sha512-0RNDbSdEokBeEAkgNbxJ+BLwSManFy9TeXz8uW+48j/xhEXv1ePME60olyzw2XzUqUBNAYFeJadIqAgNqIACwg==",
      "dev": true
    },
    "uglify-js": {
      "version": "3.4.9",
      "resolved": "https://registry.npmjs.org/uglify-js/-/uglify-js-3.4.9.tgz",
      "integrity": "sha512-8CJsbKOtEbnJsTyv6LE6m6ZKniqMiFWmm9sRbopbkGs3gMPPfd3Fh8iIA4Ykv5MgaTbqHr4BaoGLJLZNhsrW1Q==",
      "dev": true,
      "optional": true,
      "requires": {
        "commander": "~2.17.1",
        "source-map": "~0.6.1"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true,
          "optional": true
        }
      }
    },
    "ultron": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/ultron/-/ultron-1.1.1.tgz",
      "integrity": "sha512-UIEXBNeYmKptWH6z8ZnqTeS8fV74zG0/eRU9VGkpzz+LIJNs8W/zM/L+7ctCkRrgbNnnR0xxw4bKOr0cW0N0Og==",
      "dev": true
    },
    "union-value": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/union-value/-/union-value-1.0.0.tgz",
      "integrity": "sha1-XHHDTLW61dzr4+oM0IIHulqhrqQ=",
      "dev": true,
      "requires": {
        "arr-union": "^3.1.0",
        "get-value": "^2.0.6",
        "is-extendable": "^0.1.1",
        "set-value": "^0.4.3"
      },
      "dependencies": {
        "extend-shallow": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/extend-shallow/-/extend-shallow-2.0.1.tgz",
          "integrity": "sha1-Ua99YUrZqfYQ6huvu5idaxxWiQ8=",
          "dev": true,
          "requires": {
            "is-extendable": "^0.1.0"
          }
        },
        "set-value": {
          "version": "0.4.3",
          "resolved": "https://registry.npmjs.org/set-value/-/set-value-0.4.3.tgz",
          "integrity": "sha1-fbCPnT0i3H945Trzw79GZuzfzPE=",
          "dev": true,
          "requires": {
            "extend-shallow": "^2.0.1",
            "is-extendable": "^0.1.1",
            "is-plain-object": "^2.0.1",
            "to-object-path": "^0.3.0"
          }
        }
      }
    },
    "unique-filename": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/unique-filename/-/unique-filename-1.1.1.tgz",
      "integrity": "sha512-Vmp0jIp2ln35UTXuryvjzkjGdRyf9b2lTXuSYUiPmzRcl3FDtYqAwOnTJkAngD9SWhnoJzDbTKwaOrZ+STtxNQ==",
      "dev": true,
      "requires": {
        "unique-slug": "^2.0.0"
      }
    },
    "unique-slug": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/unique-slug/-/unique-slug-2.0.1.tgz",
      "integrity": "sha512-n9cU6+gITaVu7VGj1Z8feKMmfAjEAQGhwD9fE3zvpRRa0wEIx8ODYkVGfSc94M2OX00tUFV8wH3zYbm1I8mxFg==",
      "dev": true,
      "requires": {
        "imurmurhash": "^0.1.4"
      }
    },
    "unpipe": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/unpipe/-/unpipe-1.0.0.tgz",
      "integrity": "sha1-sr9O6FFKrmFltIF4KdIbLvSZBOw=",
      "dev": true
    },
    "unset-value": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/unset-value/-/unset-value-1.0.0.tgz",
      "integrity": "sha1-g3aHP30jNRef+x5vw6jtDfyKtVk=",
      "dev": true,
      "requires": {
        "has-value": "^0.3.1",
        "isobject": "^3.0.0"
      },
      "dependencies": {
        "has-value": {
          "version": "0.3.1",
          "resolved": "https://registry.npmjs.org/has-value/-/has-value-0.3.1.tgz",
          "integrity": "sha1-ex9YutpiyoJ+wKIHgCVlSEWZXh8=",
          "dev": true,
          "requires": {
            "get-value": "^2.0.3",
            "has-values": "^0.1.4",
            "isobject": "^2.0.0"
          },
          "dependencies": {
            "isobject": {
              "version": "2.1.0",
              "resolved": "https://registry.npmjs.org/isobject/-/isobject-2.1.0.tgz",
              "integrity": "sha1-8GVWEJaj8dou9GJy+BXIQNh+DIk=",
              "dev": true,
              "requires": {
                "isarray": "1.0.0"
              }
            }
          }
        },
        "has-values": {
          "version": "0.1.4",
          "resolved": "https://registry.npmjs.org/has-values/-/has-values-0.1.4.tgz",
          "integrity": "sha1-bWHeldkd/Km5oCCJrThL/49it3E=",
          "dev": true
        }
      }
    },
    "upath": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/upath/-/upath-1.1.0.tgz",
      "integrity": "sha512-bzpH/oBhoS/QI/YtbkqCg6VEiPYjSZtrHQM6/QnJS6OL9pKUFLqb3aFh4Scvwm45+7iAgiMkLhSbaZxUqmrprw==",
      "dev": true
    },
    "uri-js": {
      "version": "4.2.2",
      "resolved": "https://registry.npmjs.org/uri-js/-/uri-js-4.2.2.tgz",
      "integrity": "sha512-KY9Frmirql91X2Qgjry0Wd4Y+YTdrdZheS8TFwvkbLWf/G5KNJDCh6pKL5OZctEW4+0Baa5idK2ZQuELRwPznQ==",
      "dev": true,
      "requires": {
        "punycode": "^2.1.0"
      }
    },
    "urix": {
      "version": "0.1.0",
      "resolved": "https://registry.npmjs.org/urix/-/urix-0.1.0.tgz",
      "integrity": "sha1-2pN/emLiH+wf0Y1Js1wpNQZ6bHI=",
      "dev": true
    },
    "url": {
      "version": "0.11.0",
      "resolved": "https://registry.npmjs.org/url/-/url-0.11.0.tgz",
      "integrity": "sha1-ODjpfPxgUh63PFJajlW/3Z4uKPE=",
      "dev": true,
      "requires": {
        "punycode": "1.3.2",
        "querystring": "0.2.0"
      },
      "dependencies": {
        "punycode": {
          "version": "1.3.2",
          "resolved": "https://registry.npmjs.org/punycode/-/punycode-1.3.2.tgz",
          "integrity": "sha1-llOgNvt8HuQjQvIyXM7v6jkmxI0=",
          "dev": true
        }
      }
    },
    "url-parse": {
      "version": "1.4.4",
      "resolved": "https://registry.npmjs.org/url-parse/-/url-parse-1.4.4.tgz",
      "integrity": "sha512-/92DTTorg4JjktLNLe6GPS2/RvAd/RGr6LuktmWSMLEOa6rjnlrFXNgSbSmkNvCoL2T028A0a1JaJLzRMlFoHg==",
      "dev": true,
      "requires": {
        "querystringify": "^2.0.0",
        "requires-port": "^1.0.0"
      }
    },
    "use": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/use/-/use-3.1.1.tgz",
      "integrity": "sha512-cwESVXlO3url9YWlFW/TA9cshCEhtu7IKJ/p5soJ/gGpj7vbvFrAY/eIioQ6Dw23KjZhYgiIo8HOs1nQ2vr/oQ==",
      "dev": true
    },
    "useragent": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/useragent/-/useragent-2.3.0.tgz",
      "integrity": "sha512-4AoH4pxuSvHCjqLO04sU6U/uE65BYza8l/KKBS0b0hnUPWi+cQ2BpeTEwejCSx9SPV5/U03nniDTrWx5NrmKdw==",
      "dev": true,
      "requires": {
        "lru-cache": "4.1.x",
        "tmp": "0.0.x"
      }
    },
    "util": {
      "version": "0.11.1",
      "resolved": "https://registry.npmjs.org/util/-/util-0.11.1.tgz",
      "integrity": "sha512-HShAsny+zS2TZfaXxD9tYj4HQGlBezXZMZuM/S5PKLLoZkShZiGk9o5CzukI1LVHZvjdvZ2Sj1aW/Ndn2NB/HQ==",
      "dev": true,
      "requires": {
        "inherits": "2.0.3"
      }
    },
    "util-deprecate": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/util-deprecate/-/util-deprecate-1.0.2.tgz",
      "integrity": "sha1-RQ1Nyfpw3nMnYvvS1KKJgUGaDM8=",
      "dev": true
    },
    "utils-merge": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/utils-merge/-/utils-merge-1.0.1.tgz",
      "integrity": "sha1-n5VxD1CiZ5R7LMwSR0HBAoQn5xM=",
      "dev": true
    },
    "uuid": {
      "version": "3.3.2",
      "resolved": "https://registry.npmjs.org/uuid/-/uuid-3.3.2.tgz",
      "integrity": "sha512-yXJmeNaw3DnnKAOKJE51sL/ZaYfWJRl1pK9dr19YFCu0ObS231AB1/LbqTKRAQ5kw8A90rA6fr4riOUpTZvQZA==",
      "dev": true
    },
    "validate-npm-package-license": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/validate-npm-package-license/-/validate-npm-package-license-3.0.4.tgz",
      "integrity": "sha512-DpKm2Ui/xN7/HQKCtpZxoRWBhZ9Z0kqtygG8XCgNQ8ZlDnxuQmWhj566j8fN4Cu3/JmbhsDo7fcAJq4s9h27Ew==",
      "dev": true,
      "requires": {
        "spdx-correct": "^3.0.0",
        "spdx-expression-parse": "^3.0.0"
      }
    },
    "validate-npm-package-name": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/validate-npm-package-name/-/validate-npm-package-name-3.0.0.tgz",
      "integrity": "sha1-X6kS2B630MdK/BQN5zF/DKffQ34=",
      "dev": true,
      "requires": {
        "builtins": "^1.0.3"
      }
    },
    "vary": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/vary/-/vary-1.1.2.tgz",
      "integrity": "sha1-IpnwLG3tMNSllhsLn3RSShj2NPw=",
      "dev": true
    },
    "verror": {
      "version": "1.10.0",
      "resolved": "https://registry.npmjs.org/verror/-/verror-1.10.0.tgz",
      "integrity": "sha1-OhBcoXBTr1XW4nDB+CiGguGNpAA=",
      "dev": true,
      "requires": {
        "assert-plus": "^1.0.0",
        "core-util-is": "1.0.2",
        "extsprintf": "^1.2.0"
      }
    },
    "vm-browserify": {
      "version": "0.0.4",
      "resolved": "https://registry.npmjs.org/vm-browserify/-/vm-browserify-0.0.4.tgz",
      "integrity": "sha1-XX6kW7755Kb/ZflUOOCofDV9WnM=",
      "dev": true,
      "requires": {
        "indexof": "0.0.1"
      }
    },
    "void-elements": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/void-elements/-/void-elements-2.0.1.tgz",
      "integrity": "sha1-wGavtYK7HLQSjWDqkjkulNXp2+w=",
      "dev": true
    },
    "watchpack": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/watchpack/-/watchpack-1.6.0.tgz",
      "integrity": "sha512-i6dHe3EyLjMmDlU1/bGQpEw25XSjkJULPuAVKCbNRefQVq48yXKUpwg538F7AZTf9kyr57zj++pQFltUa5H7yA==",
      "dev": true,
      "requires": {
        "chokidar": "^2.0.2",
        "graceful-fs": "^4.1.2",
        "neo-async": "^2.5.0"
      }
    },
    "wbuf": {
      "version": "1.7.3",
      "resolved": "https://registry.npmjs.org/wbuf/-/wbuf-1.7.3.tgz",
      "integrity": "sha512-O84QOnr0icsbFGLS0O3bI5FswxzRr8/gHwWkDlQFskhSPryQXvrTMxjxGP4+iWYoauLoBvfDpkrOauZ+0iZpDA==",
      "dev": true,
      "requires": {
        "minimalistic-assert": "^1.0.0"
      }
    },
    "webdriver-js-extender": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/webdriver-js-extender/-/webdriver-js-extender-2.1.0.tgz",
      "integrity": "sha512-lcUKrjbBfCK6MNsh7xaY2UAUmZwe+/ib03AjVOpFobX4O7+83BUveSrLfU0Qsyb1DaKJdQRbuU+kM9aZ6QUhiQ==",
      "dev": true,
      "requires": {
        "@types/selenium-webdriver": "^3.0.0",
        "selenium-webdriver": "^3.0.1"
      }
    },
    "webpack": {
      "version": "4.28.4",
      "resolved": "https://registry.npmjs.org/webpack/-/webpack-4.28.4.tgz",
      "integrity": "sha512-NxjD61WsK/a3JIdwWjtIpimmvE6UrRi3yG54/74Hk9rwNj5FPkA4DJCf1z4ByDWLkvZhTZE+P3C/eh6UD5lDcw==",
      "dev": true,
      "requires": {
        "@webassemblyjs/ast": "1.7.11",
        "@webassemblyjs/helper-module-context": "1.7.11",
        "@webassemblyjs/wasm-edit": "1.7.11",
        "@webassemblyjs/wasm-parser": "1.7.11",
        "acorn": "^5.6.2",
        "acorn-dynamic-import": "^3.0.0",
        "ajv": "^6.1.0",
        "ajv-keywords": "^3.1.0",
        "chrome-trace-event": "^1.0.0",
        "enhanced-resolve": "^4.1.0",
        "eslint-scope": "^4.0.0",
        "json-parse-better-errors": "^1.0.2",
        "loader-runner": "^2.3.0",
        "loader-utils": "^1.1.0",
        "memory-fs": "~0.4.1",
        "micromatch": "^3.1.8",
        "mkdirp": "~0.5.0",
        "neo-async": "^2.5.0",
        "node-libs-browser": "^2.0.0",
        "schema-utils": "^0.4.4",
        "tapable": "^1.1.0",
        "terser-webpack-plugin": "^1.1.0",
        "watchpack": "^1.5.0",
        "webpack-sources": "^1.3.0"
      },
      "dependencies": {
        "schema-utils": {
          "version": "0.4.7",
          "resolved": "https://registry.npmjs.org/schema-utils/-/schema-utils-0.4.7.tgz",
          "integrity": "sha512-v/iwU6wvwGK8HbU9yi3/nhGzP0yGSuhQMzL6ySiec1FSrZZDkhm4noOSWzrNFo/jEc+SJY6jRTwuwbSXJPDUnQ==",
          "dev": true,
          "requires": {
            "ajv": "^6.1.0",
            "ajv-keywords": "^3.1.0"
          }
        }
      }
    },
    "webpack-core": {
      "version": "0.6.9",
      "resolved": "https://registry.npmjs.org/webpack-core/-/webpack-core-0.6.9.tgz",
      "integrity": "sha1-/FcViMhVjad76e+23r3Fo7FyvcI=",
      "dev": true,
      "requires": {
        "source-list-map": "~0.1.7",
        "source-map": "~0.4.1"
      },
      "dependencies": {
        "source-list-map": {
          "version": "0.1.8",
          "resolved": "https://registry.npmjs.org/source-list-map/-/source-list-map-0.1.8.tgz",
          "integrity": "sha1-xVCyq1Qn9rPyH1r+rYjE9Vh7IQY=",
          "dev": true
        },
        "source-map": {
          "version": "0.4.4",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.4.4.tgz",
          "integrity": "sha1-66T12pwNyZneaAMti092FzZSA2s=",
          "dev": true,
          "requires": {
            "amdefine": ">=0.0.4"
          }
        }
      }
    },
    "webpack-dev-middleware": {
      "version": "3.4.0",
      "resolved": "https://registry.npmjs.org/webpack-dev-middleware/-/webpack-dev-middleware-3.4.0.tgz",
      "integrity": "sha512-Q9Iyc0X9dP9bAsYskAVJ/hmIZZQwf/3Sy4xCAZgL5cUkjZmUZLt4l5HpbST/Pdgjn3u6pE7u5OdGd1apgzRujA==",
      "dev": true,
      "requires": {
        "memory-fs": "~0.4.1",
        "mime": "^2.3.1",
        "range-parser": "^1.0.3",
        "webpack-log": "^2.0.0"
      },
      "dependencies": {
        "mime": {
          "version": "2.4.0",
          "resolved": "https://registry.npmjs.org/mime/-/mime-2.4.0.tgz",
          "integrity": "sha512-ikBcWwyqXQSHKtciCcctu9YfPbFYZ4+gbHEmE0Q8jzcTYQg5dHCr3g2wwAZjPoJfQVXZq6KXAjpXOTf5/cjT7w==",
          "dev": true
        }
      }
    },
    "webpack-dev-server": {
      "version": "3.1.14",
      "resolved": "https://registry.npmjs.org/webpack-dev-server/-/webpack-dev-server-3.1.14.tgz",
      "integrity": "sha512-mGXDgz5SlTxcF3hUpfC8hrQ11yhAttuUQWf1Wmb+6zo3x6rb7b9mIfuQvAPLdfDRCGRGvakBWHdHOa0I9p/EVQ==",
      "dev": true,
      "requires": {
        "ansi-html": "0.0.7",
        "bonjour": "^3.5.0",
        "chokidar": "^2.0.0",
        "compression": "^1.5.2",
        "connect-history-api-fallback": "^1.3.0",
        "debug": "^3.1.0",
        "del": "^3.0.0",
        "express": "^4.16.2",
        "html-entities": "^1.2.0",
        "http-proxy-middleware": "~0.18.0",
        "import-local": "^2.0.0",
        "internal-ip": "^3.0.1",
        "ip": "^1.1.5",
        "killable": "^1.0.0",
        "loglevel": "^1.4.1",
        "opn": "^5.1.0",
        "portfinder": "^1.0.9",
        "schema-utils": "^1.0.0",
        "selfsigned": "^1.9.1",
        "semver": "^5.6.0",
        "serve-index": "^1.7.2",
        "sockjs": "0.3.19",
        "sockjs-client": "1.3.0",
        "spdy": "^4.0.0",
        "strip-ansi": "^3.0.0",
        "supports-color": "^5.1.0",
        "url": "^0.11.0",
        "webpack-dev-middleware": "3.4.0",
        "webpack-log": "^2.0.0",
        "yargs": "12.0.2"
      },
      "dependencies": {
        "ansi-regex": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-3.0.0.tgz",
          "integrity": "sha1-7QMXwyIGT3lGbAKWa922Bas32Zg=",
          "dev": true
        },
        "camelcase": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/camelcase/-/camelcase-4.1.0.tgz",
          "integrity": "sha1-1UVjW+HjPFQmScaRc+Xeas+uNN0=",
          "dev": true
        },
        "cliui": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/cliui/-/cliui-4.1.0.tgz",
          "integrity": "sha512-4FG+RSG9DL7uEwRUZXZn3SS34DiDPfzP0VOiEwtUWlE+AR2EIg+hSyvrIgUUfhdgR/UkAeW2QHgeP+hWrXs7jQ==",
          "dev": true,
          "requires": {
            "string-width": "^2.1.1",
            "strip-ansi": "^4.0.0",
            "wrap-ansi": "^2.0.0"
          },
          "dependencies": {
            "strip-ansi": {
              "version": "4.0.0",
              "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-4.0.0.tgz",
              "integrity": "sha1-qEeQIusaw2iocTibY1JixQXuNo8=",
              "dev": true,
              "requires": {
                "ansi-regex": "^3.0.0"
              }
            }
          }
        },
        "cross-spawn": {
          "version": "6.0.5",
          "resolved": "https://registry.npmjs.org/cross-spawn/-/cross-spawn-6.0.5.tgz",
          "integrity": "sha512-eTVLrBSt7fjbDygz805pMnstIs2VTBNkRm0qxZd+M7A5XDdxVRWO5MxGBXZhjY4cqLYLdtrGqRf8mBPmzwSpWQ==",
          "dev": true,
          "requires": {
            "nice-try": "^1.0.4",
            "path-key": "^2.0.1",
            "semver": "^5.5.0",
            "shebang-command": "^1.2.0",
            "which": "^1.2.9"
          }
        },
        "debug": {
          "version": "3.2.6",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
          "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "decamelize": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/decamelize/-/decamelize-2.0.0.tgz",
          "integrity": "sha512-Ikpp5scV3MSYxY39ymh45ZLEecsTdv/Xj2CaQfI8RLMuwi7XvjX9H/fhraiSuU+C5w5NTDu4ZU72xNiZnurBPg==",
          "dev": true,
          "requires": {
            "xregexp": "4.0.0"
          }
        },
        "execa": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/execa/-/execa-1.0.0.tgz",
          "integrity": "sha512-adbxcyWV46qiHyvSp50TKt05tB4tK3HcmF7/nxfAdhnox83seTDbwnaqKO4sXRy7roHAIFqJP/Rw/AuEbX61LA==",
          "dev": true,
          "requires": {
            "cross-spawn": "^6.0.0",
            "get-stream": "^4.0.0",
            "is-stream": "^1.1.0",
            "npm-run-path": "^2.0.0",
            "p-finally": "^1.0.0",
            "signal-exit": "^3.0.0",
            "strip-eof": "^1.0.0"
          }
        },
        "find-up": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/find-up/-/find-up-3.0.0.tgz",
          "integrity": "sha512-1yD6RmLI1XBfxugvORwlck6f75tYL+iR0jqwsOrOxMZyGYqUuDhJ0l4AXdO1iX/FTs9cBAMEk1gWSEx1kSbylg==",
          "dev": true,
          "requires": {
            "locate-path": "^3.0.0"
          }
        },
        "get-stream": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/get-stream/-/get-stream-4.1.0.tgz",
          "integrity": "sha512-GMat4EJ5161kIy2HevLlr4luNjBgvmj413KaQA7jt4V8B4RDsfpHk7WQ9GVqfYyyx8OS/L66Kox+rJRNklLK7w==",
          "dev": true,
          "requires": {
            "pump": "^3.0.0"
          }
        },
        "invert-kv": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/invert-kv/-/invert-kv-2.0.0.tgz",
          "integrity": "sha512-wPVv/y/QQ/Uiirj/vh3oP+1Ww+AWehmi1g5fFWGPF6IpCBCDVrhgHRMvrLfdYcwDh3QJbGXDW4JAuzxElLSqKA==",
          "dev": true
        },
        "is-fullwidth-code-point": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/is-fullwidth-code-point/-/is-fullwidth-code-point-2.0.0.tgz",
          "integrity": "sha1-o7MKXE8ZkYMWeqq5O+764937ZU8=",
          "dev": true
        },
        "lcid": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/lcid/-/lcid-2.0.0.tgz",
          "integrity": "sha512-avPEb8P8EGnwXKClwsNUgryVjllcRqtMYa49NTsbQagYuT1DcXnl1915oxWjoyGrXR6zH/Y0Zc96xWsPcoDKeA==",
          "dev": true,
          "requires": {
            "invert-kv": "^2.0.0"
          }
        },
        "locate-path": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/locate-path/-/locate-path-3.0.0.tgz",
          "integrity": "sha512-7AO748wWnIhNqAuaty2ZWHkQHRSNfPVIsPIfwEOWO22AmaoVrWavlOcMR5nzTLNYvp36X220/maaRsrec1G65A==",
          "dev": true,
          "requires": {
            "p-locate": "^3.0.0",
            "path-exists": "^3.0.0"
          }
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg==",
          "dev": true
        },
        "os-locale": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/os-locale/-/os-locale-3.1.0.tgz",
          "integrity": "sha512-Z8l3R4wYWM40/52Z+S265okfFj8Kt2cC2MKY+xNi3kFs+XGI7WXu/I309QQQYbRW4ijiZ+yxs9pqEhJh0DqW3Q==",
          "dev": true,
          "requires": {
            "execa": "^1.0.0",
            "lcid": "^2.0.0",
            "mem": "^4.0.0"
          }
        },
        "p-limit": {
          "version": "2.1.0",
          "resolved": "https://registry.npmjs.org/p-limit/-/p-limit-2.1.0.tgz",
          "integrity": "sha512-NhURkNcrVB+8hNfLuysU8enY5xn2KXphsHBaC2YmRNTZRc7RWusw6apSpdEj3jo4CMb6W9nrF6tTnsJsJeyu6g==",
          "dev": true,
          "requires": {
            "p-try": "^2.0.0"
          }
        },
        "p-locate": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/p-locate/-/p-locate-3.0.0.tgz",
          "integrity": "sha512-x+12w/To+4GFfgJhBEpiDcLozRJGegY+Ei7/z0tSLkMmxGZNybVMSfWj9aJn8Z5Fc7dBUNJOOVgPv2H7IwulSQ==",
          "dev": true,
          "requires": {
            "p-limit": "^2.0.0"
          }
        },
        "p-try": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/p-try/-/p-try-2.0.0.tgz",
          "integrity": "sha512-hMp0onDKIajHfIkdRk3P4CdCmErkYAxxDtP3Wx/4nZ3aGlau2VKh3mZpcuFkH27WQkL/3WBCPOktzA9ZOAnMQQ==",
          "dev": true
        },
        "pump": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/pump/-/pump-3.0.0.tgz",
          "integrity": "sha512-LwZy+p3SFs1Pytd/jYct4wpv49HiYCqd9Rlc5ZVdk0V+8Yzv6jR5Blk3TRmPL1ft69TxP0IMZGJ+WPFU2BFhww==",
          "dev": true,
          "requires": {
            "end-of-stream": "^1.1.0",
            "once": "^1.3.1"
          }
        },
        "semver": {
          "version": "5.6.0",
          "resolved": "https://registry.npmjs.org/semver/-/semver-5.6.0.tgz",
          "integrity": "sha512-RS9R6R35NYgQn++fkDWaOmqGoj4Ek9gGs+DPxNUZKuwE183xjJroKvyo1IzVFeXvUrvmALy6FWD5xrdJT25gMg==",
          "dev": true
        },
        "string-width": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/string-width/-/string-width-2.1.1.tgz",
          "integrity": "sha512-nOqH59deCq9SRHlxq1Aw85Jnt4w6KvLKqWVik6oA9ZklXLNIOlqg4F2yrT1MVaTjAqvVwdfeZ7w7aCvJD7ugkw==",
          "dev": true,
          "requires": {
            "is-fullwidth-code-point": "^2.0.0",
            "strip-ansi": "^4.0.0"
          },
          "dependencies": {
            "strip-ansi": {
              "version": "4.0.0",
              "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-4.0.0.tgz",
              "integrity": "sha1-qEeQIusaw2iocTibY1JixQXuNo8=",
              "dev": true,
              "requires": {
                "ansi-regex": "^3.0.0"
              }
            }
          }
        },
        "supports-color": {
          "version": "5.5.0",
          "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-5.5.0.tgz",
          "integrity": "sha512-QjVjwdXIt408MIiAqCX4oUKsgU2EqAGzs2Ppkm4aQYbjm+ZEWEcW4SfFNTr4uMNZma0ey4f5lgLrkB0aX0QMow==",
          "dev": true,
          "requires": {
            "has-flag": "^3.0.0"
          }
        },
        "which-module": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/which-module/-/which-module-2.0.0.tgz",
          "integrity": "sha1-2e8H3Od7mQK4o6j6SzHD4/fm6Ho=",
          "dev": true
        },
        "yargs": {
          "version": "12.0.2",
          "resolved": "https://registry.npmjs.org/yargs/-/yargs-12.0.2.tgz",
          "integrity": "sha512-e7SkEx6N6SIZ5c5H22RTZae61qtn3PYUE8JYbBFlK9sYmh3DMQ6E5ygtaG/2BW0JZi4WGgTR2IV5ChqlqrDGVQ==",
          "dev": true,
          "requires": {
            "cliui": "^4.0.0",
            "decamelize": "^2.0.0",
            "find-up": "^3.0.0",
            "get-caller-file": "^1.0.1",
            "os-locale": "^3.0.0",
            "require-directory": "^2.1.1",
            "require-main-filename": "^1.0.1",
            "set-blocking": "^2.0.0",
            "string-width": "^2.0.0",
            "which-module": "^2.0.0",
            "y18n": "^3.2.1 || ^4.0.0",
            "yargs-parser": "^10.1.0"
          }
        },
        "yargs-parser": {
          "version": "10.1.0",
          "resolved": "https://registry.npmjs.org/yargs-parser/-/yargs-parser-10.1.0.tgz",
          "integrity": "sha512-VCIyR1wJoEBZUqk5PA+oOBF6ypbwh5aNB3I50guxAL/quggdfs4TtNHQrSazFA3fYZ+tEqfs0zIGlv0c/rgjbQ==",
          "dev": true,
          "requires": {
            "camelcase": "^4.1.0"
          }
        }
      }
    },
    "webpack-log": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/webpack-log/-/webpack-log-2.0.0.tgz",
      "integrity": "sha512-cX8G2vR/85UYG59FgkoMamwHUIkSSlV3bBMRsbxVXVUk2j6NleCKjQ/WE9eYg9WY4w25O9w8wKP4rzNZFmUcUg==",
      "dev": true,
      "requires": {
        "ansi-colors": "^3.0.0",
        "uuid": "^3.3.2"
      }
    },
    "webpack-merge": {
      "version": "4.1.4",
      "resolved": "https://registry.npmjs.org/webpack-merge/-/webpack-merge-4.1.4.tgz",
      "integrity": "sha512-TmSe1HZKeOPey3oy1Ov2iS3guIZjWvMT2BBJDzzT5jScHTjVC3mpjJofgueEzaEd6ibhxRDD6MIblDr8tzh8iQ==",
      "dev": true,
      "requires": {
        "lodash": "^4.17.5"
      }
    },
    "webpack-sources": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/webpack-sources/-/webpack-sources-1.3.0.tgz",
      "integrity": "sha512-OiVgSrbGu7NEnEvQJJgdSFPl2qWKkWq5lHMhgiToIiN9w34EBnjYzSYs+VbL5KoYiLNtFFa7BZIKxRED3I32pA==",
      "dev": true,
      "requires": {
        "source-list-map": "^2.0.0",
        "source-map": "~0.6.1"
      },
      "dependencies": {
        "source-map": {
          "version": "0.6.1",
          "resolved": "https://registry.npmjs.org/source-map/-/source-map-0.6.1.tgz",
          "integrity": "sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==",
          "dev": true
        }
      }
    },
    "webpack-subresource-integrity": {
      "version": "1.1.0-rc.6",
      "resolved": "https://registry.npmjs.org/webpack-subresource-integrity/-/webpack-subresource-integrity-1.1.0-rc.6.tgz",
      "integrity": "sha512-Az7y8xTniNhaA0620AV1KPwWOqawurVVDzQSpPAeR5RwNbL91GoBSJAAo9cfd+GiFHwsS5bbHepBw1e6Hzxy4w==",
      "dev": true,
      "requires": {
        "webpack-core": "^0.6.8"
      }
    },
    "websocket-driver": {
      "version": "0.7.0",
      "resolved": "https://registry.npmjs.org/websocket-driver/-/websocket-driver-0.7.0.tgz",
      "integrity": "sha1-DK+dLXVdk67gSdS90NP+LMoqJOs=",
      "dev": true,
      "requires": {
        "http-parser-js": ">=0.4.0",
        "websocket-extensions": ">=0.1.1"
      }
    },
    "websocket-extensions": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/websocket-extensions/-/websocket-extensions-0.1.3.tgz",
      "integrity": "sha512-nqHUnMXmBzT0w570r2JpJxfiSD1IzoI+HGVdd3aZ0yNi3ngvQ4jv1dtHt5VGxfI2yj5yqImPhOK4vmIh2xMbGg==",
      "dev": true
    },
    "when": {
      "version": "3.6.4",
      "resolved": "https://registry.npmjs.org/when/-/when-3.6.4.tgz",
      "integrity": "sha1-RztRfsFZ4rhQBUl6E5g/CVQS404=",
      "dev": true
    },
    "which": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/which/-/which-1.3.1.tgz",
      "integrity": "sha512-HxJdYWq1MTIQbJ3nw0cqssHoTNU267KlrDuGZ1WYlxDStUtKUhOaJmh112/TZmHxxUfuJqPXSOm7tDyas0OSIQ==",
      "dev": true,
      "requires": {
        "isexe": "^2.0.0"
      }
    },
    "which-module": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/which-module/-/which-module-1.0.0.tgz",
      "integrity": "sha1-u6Y8qGGUiZT/MHc2CJ47lgJsKk8=",
      "dev": true,
      "optional": true
    },
    "wide-align": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/wide-align/-/wide-align-1.1.3.tgz",
      "integrity": "sha512-QGkOQc8XL6Bt5PwnsExKBPuMKBxnGxWWW3fU55Xt4feHozMUhdUMaBCk290qpm/wG5u/RSKzwdAC4i51YigihA==",
      "dev": true,
      "requires": {
        "string-width": "^1.0.2 || 2"
      }
    },
    "wordwrap": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/wordwrap/-/wordwrap-1.0.0.tgz",
      "integrity": "sha1-J1hIEIkUVqQXHI0CJkQa3pDLyus=",
      "dev": true
    },
    "worker-farm": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/worker-farm/-/worker-farm-1.6.0.tgz",
      "integrity": "sha512-6w+3tHbM87WnSWnENBUvA2pxJPLhQUg5LKwUQHq3r+XPhIM+Gh2R5ycbwPCyuGbNg+lPgdcnQUhuC02kJCvffQ==",
      "dev": true,
      "requires": {
        "errno": "~0.1.7"
      }
    },
    "wrap-ansi": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/wrap-ansi/-/wrap-ansi-2.1.0.tgz",
      "integrity": "sha1-2Pw9KE3QV5T+hJc8rs3Rz4JP3YU=",
      "dev": true,
      "requires": {
        "string-width": "^1.0.1",
        "strip-ansi": "^3.0.1"
      }
    },
    "wrappy": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/wrappy/-/wrappy-1.0.2.tgz",
      "integrity": "sha1-tSQ9jz7BqjXxNkYFvA0QNuMKtp8=",
      "dev": true
    },
    "ws": {
      "version": "3.3.3",
      "resolved": "https://registry.npmjs.org/ws/-/ws-3.3.3.tgz",
      "integrity": "sha512-nnWLa/NwZSt4KQJu51MYlCcSQ5g7INpOrOMt4XV8j4dqTXdmlUmSHQ8/oLC069ckre0fRsgfvsKwbTdtKLCDkA==",
      "dev": true,
      "requires": {
        "async-limiter": "~1.0.0",
        "safe-buffer": "~5.1.0",
        "ultron": "~1.1.0"
      }
    },
    "xml2js": {
      "version": "0.4.19",
      "resolved": "https://registry.npmjs.org/xml2js/-/xml2js-0.4.19.tgz",
      "integrity": "sha512-esZnJZJOiJR9wWKMyuvSE1y6Dq5LCuJanqhxslH2bxM6duahNZ+HMpCLhBQGZkbX6xRf8x1Y2eJlgt2q3qo49Q==",
      "dev": true,
      "requires": {
        "sax": ">=0.6.0",
        "xmlbuilder": "~9.0.1"
      },
      "dependencies": {
        "sax": {
          "version": "1.2.4",
          "resolved": "https://registry.npmjs.org/sax/-/sax-1.2.4.tgz",
          "integrity": "sha512-NqVDv9TpANUjFm0N8uM5GxL36UgKi9/atZw+x7YFnQ8ckwFGKrl4xX4yWtrey3UJm5nP1kUbnYgLopqWNSRhWw==",
          "dev": true
        }
      }
    },
    "xmlbuilder": {
      "version": "9.0.7",
      "resolved": "https://registry.npmjs.org/xmlbuilder/-/xmlbuilder-9.0.7.tgz",
      "integrity": "sha1-Ey7mPS7FVlxVfiD0wi35rKaGsQ0=",
      "dev": true
    },
    "xmlhttprequest-ssl": {
      "version": "1.5.5",
      "resolved": "https://registry.npmjs.org/xmlhttprequest-ssl/-/xmlhttprequest-ssl-1.5.5.tgz",
      "integrity": "sha1-wodrBhaKrcQOV9l+gRkayPQ5iz4=",
      "dev": true
    },
    "xregexp": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/xregexp/-/xregexp-4.0.0.tgz",
      "integrity": "sha512-PHyM+sQouu7xspQQwELlGwwd05mXUFqwFYfqPO0cC7x4fxyHnnuetmQr6CjJiafIDoH4MogHb9dOoJzR/Y4rFg==",
      "dev": true
    },
    "xtend": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/xtend/-/xtend-4.0.1.tgz",
      "integrity": "sha1-pcbVMr5lbiPbgg77lDofBJmNY68=",
      "dev": true
    },
    "y18n": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/y18n/-/y18n-4.0.0.tgz",
      "integrity": "sha512-r9S/ZyXu/Xu9q1tYlpsLIsa3EeLXXk0VwlxqTcFRfg9EhMW+17kbt9G0NrgCmhGb5vT2hyhJZLfDGx+7+5Uj/w==",
      "dev": true
    },
    "yallist": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/yallist/-/yallist-2.1.2.tgz",
      "integrity": "sha1-HBH5IY8HYImkfdUS+TxmmaaoHVI=",
      "dev": true
    },
    "yargs": {
      "version": "7.1.0",
      "resolved": "https://registry.npmjs.org/yargs/-/yargs-7.1.0.tgz",
      "integrity": "sha1-a6MY6xaWFyf10oT46gA+jWFU0Mg=",
      "dev": true,
      "optional": true,
      "requires": {
        "camelcase": "^3.0.0",
        "cliui": "^3.2.0",
        "decamelize": "^1.1.1",
        "get-caller-file": "^1.0.1",
        "os-locale": "^1.4.0",
        "read-pkg-up": "^1.0.1",
        "require-directory": "^2.1.1",
        "require-main-filename": "^1.0.1",
        "set-blocking": "^2.0.0",
        "string-width": "^1.0.2",
        "which-module": "^1.0.0",
        "y18n": "^3.2.1",
        "yargs-parser": "^5.0.0"
      },
      "dependencies": {
        "camelcase": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/camelcase/-/camelcase-3.0.0.tgz",
          "integrity": "sha1-MvxLn82vhF/N9+c7uXysImHwqwo=",
          "dev": true,
          "optional": true
        },
        "y18n": {
          "version": "3.2.1",
          "resolved": "https://registry.npmjs.org/y18n/-/y18n-3.2.1.tgz",
          "integrity": "sha1-bRX7qITAhnnA136I53WegR4H+kE=",
          "dev": true,
          "optional": true
        }
      }
    },
    "yargs-parser": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/yargs-parser/-/yargs-parser-5.0.0.tgz",
      "integrity": "sha1-J17PDX/+Bcd+ZOfIbkzZS/DhIoo=",
      "dev": true,
      "optional": true,
      "requires": {
        "camelcase": "^3.0.0"
      },
      "dependencies": {
        "camelcase": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/camelcase/-/camelcase-3.0.0.tgz",
          "integrity": "sha1-MvxLn82vhF/N9+c7uXysImHwqwo=",
          "dev": true,
          "optional": true
        }
      }
    },
    "yeast": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/yeast/-/yeast-0.1.2.tgz",
      "integrity": "sha1-AI4G2AlDIMNy28L47XagymyKxBk=",
      "dev": true
    },
    "yn": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/yn/-/yn-2.0.0.tgz",
      "integrity": "sha1-5a2ryKz0CPY4X8dklWhMiOavaJo=",
      "dev": true
    },
    "zone.js": {
      "version": "0.8.29",
      "resolved": "https://registry.npmjs.org/zone.js/-/zone.js-0.8.29.tgz",
      "integrity": "sha512-mla2acNCMkWXBD+c+yeUrBUrzOxYMNFdQ6FGfigGGtEVBPJx07BQeJekjt9DmH1FtZek4E9rE1eRR9qQpxACOQ=="
    }
  }
}






# AngularHelloWorld

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.2.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md








# AngularHelloWorld

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.2.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

{
  "compileOnSave": false,
  "compilerOptions": {
    "baseUrl": "./",
    "outDir": "./dist/out-tsc",
    "sourceMap": true,
    "declaration": false,
    "module": "es2015",
    "moduleResolution": "node",
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "importHelpers": true,
    "target": "es5",
    "typeRoots": [
      "node_modules/@types"
    ],
    "lib": [
      "es2018",
      "dom"
    ]
  }
}

{
  "rulesDirectory": [
    "codelyzer"
  ],
  "rules": {
    "arrow-return-shorthand": true,
    "callable-types": true,
    "class-name": true,
    "comment-format": [
      true,
      "check-space"
    ],
    "curly": true,
    "deprecation": {
      "severity": "warn"
    },
    "eofline": true,
    "forin": true,
    "import-blacklist": [
      true,
      "rxjs/Rx"
    ],
    "import-spacing": true,
    "indent": [
      true,
      "spaces"
    ],
    "interface-over-type-literal": true,
    "label-position": true,
    "max-line-length": [
      true,
      140
    ],
    "member-access": false,
    "member-ordering": [
      true,
      {
        "order": [
          "static-field",
          "instance-field",
          "static-method",
          "instance-method"
        ]
      }
    ],
    "no-arg": true,
    "no-bitwise": true,
    "no-console": [
      true,
      "debug",
      "info",
      "time",
      "timeEnd",
      "trace"
    ],
    "no-construct": true,
    "no-debugger": true,
    "no-duplicate-super": true,
    "no-empty": false,
    "no-empty-interface": true,
    "no-eval": true,
    "no-inferrable-types": [
      true,
      "ignore-params"
    ],
    "no-misused-new": true,
    "no-non-null-assertion": true,
    "no-redundant-jsdoc": true,
    "no-shadowed-variable": true,
    "no-string-literal": false,
    "no-string-throw": true,
    "no-switch-case-fall-through": true,
    "no-trailing-whitespace": true,
    "no-unnecessary-initializer": true,
    "no-unused-expression": true,
    "no-use-before-declare": true,
    "no-var-keyword": true,
    "object-literal-sort-keys": false,
    "one-line": [
      true,
      "check-open-brace",
      "check-catch",
      "check-else",
      "check-whitespace"
    ],
    "prefer-const": true,
    "quotemark": [
      true,
      "single"
    ],
    "radix": true,
    "semicolon": [
      true,
      "always"
    ],
    "triple-equals": [
      true,
      "allow-null-check"
    ],
    "typedef-whitespace": [
      true,
      {
        "call-signature": "nospace",
        "index-signature": "nospace",
        "parameter": "nospace",
        "property-declaration": "nospace",
        "variable-declaration": "nospace"
      }
    ],
    "unified-signatures": true,
    "variable-name": false,
    "whitespace": [
      true,
      "check-branch",
      "check-decl",
      "check-operator",
      "check-separator",
      "check-type"
    ],
    "no-output-on-prefix": true,
    "use-input-property-decorator": true,
    "use-output-property-decorator": true,
    "use-host-property-decorator": true,
    "no-input-rename": true,
    "no-output-rename": true,
    "use-life-cycle-interface": true,
    "use-pipe-transform-interface": true,
    "component-class-suffix": true,
    "directive-class-suffix": true
  }
}


















