# Overview
This was performed 08/06/19

## How Front-End Works
`newjersey.js` makes calls to `Request URL: https://js-agent.newrelic.com/nr-spa-1130.min.js`
w/ response
```
[function]
```
and
`https://bam.nr-data.net/.....`
w/ response
```
NREUM.setToken({'stn':0,'err':0,'ins':0,'cap':0,'spa':0})
```

or
Node.js agent-based instrumentation https://docs.newrelic.com/docs/agents/nodejs-agent/supported-features/new-relic-browser-nodejs-agent


## Learned
- cdn javascript OR agent-based (more setup but better if integrating other back-end APM solutions)
- need `pro free trial` to capture JS errors
- I get access to Overview, Page Views, Browsers, Geo, without Pro Trial
- I don't get access to Session Traces, AJAX, JS Errors, Filterable Geography
![Image of Browser Application](./img/browser-application.png)
- The Browser Pro features are: https://docs.newrelic.com/docs/browser/new-relic-browser/browser-pro-features
- [Javascript Errors](https://docs.newrelic.com/docs/browser/new-relic-browser/browser-pro-features/javascript-errors-page-detect-analyze-errors)
- https://docs.newrelic.com/docs/browser/new-relic-browser/browser-pro-features/javascript-errors-page-detect-analyze-errors#ui-features
- what they really emphasize is "Available options in UI" ![Image of Available Options](./img/available-options-in-ui.png)

## Does Well
- "Top 5 Errors by Count" see `/img/js-error-view.png`, this is a huge +1 for NewJersey
- filter by HandledErrors specifically, method `.noticeError`, see `/img/filter-by-handled-errors.png` and https://docs.newrelic.com/docs/browser/new-relic-browser/browser-agent-spa-api/notice-error . Update - realize we have this already as `handled: yes` and `handled: no`, **if you know to filter by it in Issues Dashboard**
- ["SPA Monitoring"](https://docs.newrelic.com/docs/browser/single-page-app-monitoring/get-started/install-single-page-app-monitoring-new-relic-browser) feature, branded as such 

## Has
- [sourcemaps uploading](https://docs.newrelic.com/docs/browser/new-relic-browser/browser-pro-features/upload-source-maps-un-minify-js-errors)

## Other
https://vuejs.org/v2/guide/
- Definition of a NewRelic [Event](https://docs.newrelic.com/docs/using-new-relic/welcome-new-relic/get-started/glossary#event)
- Definition of a NewRelic [Attribute](https://docs.newrelic.com/docs/using-new-relic/welcome-new-relic/get-started/glossary#attribute) which is like a Tag


## Ding Ding Ding
https://docs.newrelic.com/docs/browser/new-relic-browser/browser-pro-features/javascript-errors-page-detect-analyze-errors#ui-features

![Image Ding Ding Ding](./img/ding-ding-ding.png)
```
Unavailable errors include:

SyntaxError or Script error: These occur while the script is loading, so they do not produce a stack trace.
In-line JavaScript or event handler errors: These are unwrapped.
Errors thrown from third-party scripts that reside on another domain are not available.
Errors occurring on older browsers: These may not be able to provide a usable stack trace. In some cases, they may not provide a stack trace at all.
Error collection is done by wrapping JavaScript functions, so errors thrown by the browser at a lower level (such as cross-origin resource sharing  errors) also are not available.

```

## Break New Jersey
for...loop
