# 15 - Deploying your nx monorepo

The AngularCLI only generates bundles. This means that we cannot build the lib itself. We can only do it by building an app that depends on it.

And then run

```text
ng build --prod -a=admin-portal
```

In this section, we will run some analysis tools to inspect the size of our application.

* Install the [webpack-bundle-analyzer](https://github.com/th0r/webpack-bundle-analyzer)

```text
npm install  --save-dev webpack-bundle-analyzer
```

* Once installed add the following entry to the npm scripts in the package.json:

```text
"bundle-report-admin-portal": "webpack-bundle-analyzer dist/apps/admin-portal/stats.json"
```

* Rebuild with --stats-json

```text
ng build --prod -a=admin-portal --stats-json
```

* Run the following command

```text
 npm run bundle-report
```

