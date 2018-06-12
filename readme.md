# mocking-currency-conversion-graphql

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:0 orderedList:0 -->

- [What's this?](#whats-this)
- [How can I use it?](#how-can-i-use-it)
- [Where is this deployed? :rocket:](#where-is-this-deployed-rocket)
- [Any env vars?](#any-env-vars)

<!-- /TOC -->

### What's this?
A graphql server that provides currency rates from [OpenExchange](http://openexchangerates.org).

### How can I use it?
Here is an example:

* base: String --> The base to calculate the rest of the currencies
* currencies: [{abbreviation: String, rate: String}] --> The currencies to return (if no input is given will return all the currencies).

```GraphQL
query {
  getConversions(base: "USD", currencies: ["EUR", "GBP", "AUR"]) {
    base,
    timestamp
    rates {
      abbreviation
      rate
    }
  }
}
```

### Where is this deployed? :rocket:

It's hosted on https://graphql-currencies.now.sh

### Any env vars?
Yes, here are their key names:

- API_KEY
- MONGODB_URI
- PORT
