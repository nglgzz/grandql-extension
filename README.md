# GRANDstack @relate extension
An early prototype of an extension for the @relate/web package adding the GRAND stack to all installed DBMSs

## Quick Start

Install dependencies:

```
npm ci
npm link @relate/common
```

Build:

```
npm run build
```


Start the GraphQL service:

```
npm start
```

## Seeding The Database

Optionally you can seed the GraphQL service by executing mutations that will write sample data to the database:

```
npm run seedDb
```
