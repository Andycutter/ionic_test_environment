Config files for e2e, karma and protractor to copy into ionic application to test.

Remember to still run:

`npm install --save-dev angular2-template-loader html-loader jasmine jasmine-spec-reporter karma karma-chrome-launcher karma-jasmine karma-jasmine-html-reporter karma-sourcemap-loader karma-webpack karma-coverage-istanbul-reporter istanbul-instrumenter-loader null-loader protractor ts-loader ts-node @types/jasmine @types/node ionic-mocks`

And modify package.json with:

```
"scripts": {
    "clean": "ionic-app-scripts clean",
    "build": "ionic-app-scripts build",
    "lint": "ionic-app-scripts lint",
    "ionic:build": "ionic-app-scripts build",
    "ionic:serve": "ionic-app-scripts serve",
    "test": "karma start ./test-config/karma.conf.js",
    "test-ci": "karma start ./test-config/karma.conf.js --single-run",
    "test-coverage": "karma start ./test-config/karma.conf.js --coverage",
    "e2e": "npm run e2e-update && npm run e2e-test",
    "e2e-test": "protractor ./test-config/protractor.conf.js",
    "e2e-update": "webdriver-manager update --standalone false --gecko false"
},
```

and update version of dependencies:

```
"ts-loader": "^3.0.3",
"karma-jasmine-html-reporter": "^0.2.2",
"karma-jasmine": "^1.1.0",
"jasmine": "^2.5.3",
```

and run `npm install`