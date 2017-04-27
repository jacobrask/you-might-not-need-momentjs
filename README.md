# You might not need Moment.js

Moment.js and Date.js are great modern JavaScript date utility libraries and they are widely used by front-end developers for good reason. For simple tasks when you are targeting modern browsers, you may find out that there are many methods which are already supported natively.

We mostly use the `Date.prototype.toLocaleString` method here, but the following are equivalent:

```
new Date().toLocaleString(navigator.language, { month: 'short' })
new Intl.DateTimeFormat(navigator.language, { month: 'short' }).format(new Date())
```

## Formatting
```
const now = new Date();

// April 27, 2017, 9:20:30 am
moment().format('MMMM Do YYYY, h:mm:ss a')
now.toLocaleString('en-US', { month: 'long', day: 'numeric', year: 'numeric', hour: 'numeric', minute: 'numeric', second: 'numeric' })

// Thursday
moment().format('dddd')
now.toLocaleString('en-US', { weekday: 'long' })

// Apr 27, 17
moment().format("MMM Do YY")
now.toLocaleString('en-US', { month: 'short', day: 'numeric', year: '2-digit' })
```

## Relative time

Currently a stage 1 EcmaScript proposal as [Intl.RelativeTimeFormat](https://github.com/caridy/proposal-intl-relative-time).

## Durations

Currently a stage 1 EcmaScript proposal as [Intl.DurationFormat](https://github.com/tc39/ecma402/issues/47).
