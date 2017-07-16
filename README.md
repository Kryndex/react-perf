# Performance Regression tests for React

> [View Test Results](https://axemclion.cloudant.com/react-perf/_design/site/index.html#/summary?pagename=DBMonster&browser=chrome)


## Running the tests

1. Install dependencies using `npm install`
2. Start up CouchDB and [Chromedriver](https://sites.google.com/a/chromium.org/chromedriver/downloads)
3. Run `npm test <version>` to test all versions of React and store results in the couchdb server
4. To view results, look at `http://<couchdbServer:5984>/<dbname>/_design/site/index.html`
5. Update UI for site using `node node_modules/perfjankie/lib/cli.js --couch-database=react-perf --only-update-site --couch-server=http://localhost:5984 --couch-user=admin_user --couch-pwd=admin_pass`

# Other notes

- All other test parameters are located in `.\lib\pjRunner.js`
- Individual test apps are present at the location specified in `.\lib\reactVersions.js`
    + The source for the apps are in a branch of this repo
    + To run the app, the test runner in this branch downloads the branch as a zip from github, does `npm install`, and runs the `server.js`
    + Once the tests are finished, the server is killed. 
