# SPT Calculator

## Installation
### Proxy
The API Proxy provides a passthrough to the CBPs internal API (at https://i94.cbp.dhs.gov/) without modifying the data. It is a python flask app. A working `Python 3` environment is a prerequisite.

Before using, the allowed CORS origin needs to be set (for example to "*" in development mode, but don't do this in production!) in line 6. To install and run at http://localhost:8000/i94, execute:

```
cd proxy
pip3 install requirements.txt
python3 app.py
```

Note that the API Proxy does not provide an index page and will just return a status code 204 without any content when accessed with a browser. This is intended behaviour.

### Client
The frontened is built on vue.js and can be installed with `npm`. A working npm installation is a prerequisite. To install locally:
```
cd client
npm install
```

If downloading the travel history from the CBP is desired, the correct URL of the API Proxy needs to be configured in `src/components/SPT.vue`. It is set as `const path` in `methods: onDownload(evt)`. The production setting http://proxy.sptcalc.com/i94 will not work locally since the API Proxy does not permit CORS with localhost. 

A development server, that includes hot-reload can be started at http://localhost:8080 with the command
```
npm run serve
```


## The Substantial Presence Test
More information can be found here https://www.irs.gov/individuals/international-taxpayers/substantial-presence-test