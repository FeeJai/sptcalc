# SPT Calculator

## Frontend
The Substantial Presence Test Calculator is a single page javascript-app that runs entirely in the browser built with `vue.js`. It contains just one component, named SPT.vue that cotains all the logic. It is built using `bootstrap-vue` for styling, `axios` to handle AJAX requests and `moment.js` to process and verify dates. For privacy reasons, data is not stored and the app is reset upon refresh.

## API Proxy
Because of the browser CORS, it is not possible to access the official Customs and Border Protection API directly from the app. This is why a simple proxy had been built using Python3 and the WebFramework `Flask`. Its entire logic is contained in the file `app.py`.

## Heroku
Both apps are deployed on a free Heroku dyno; a demo is available at http://www.sptcalc.com/.

The frontend is deployed using the buildpack `https://github.com/heroku/heroku-buildpack-static`, an FOSS project aimed at serving single page web apps with compilation on upload without the permanent node.js overhead. Its (simple) configuration can be found in the file `client/static.json`.

The proxy is deployed with the heroku builtin python service. The packages have been locked into the file `requirements.txt` and the run commant has been saved into the `Procfile`, which instructs the Heroku Dyno to serve the Flask App with GUnicorn. 