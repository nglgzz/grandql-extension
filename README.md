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

Install

```
npm prune --production
cd ../ && cp -r grandql-extension ~/<relate-extensions-dir>/WEB
```
- OS X `relate-extensions-dir`: `~/Library/Application\ Support/com.Neo4j.Relate/Data/extensions`
- Linux `relate-extensions-dir`: `~/.local/share/neo4j-relate/extensions`
- Win32 `relate-extensions-dir`: `%APPDATA%\Local\Neo4j\Relate\Data\extensions`



Or create symlink (?)

(didn't seem to work) :-(
```
ln -s /Users/lyonwj/Dropbox/github/grandql-extension  /Users/lyonwj/Library/Application\ Support/com.Neo4j.Relate/Data/extensions/WEB/
```

## GrandQL Endpoints

For each dbms the following endpoints will be created:

`POST` `/grandql/{dbms.name}` - the GraphQL endpoint for the dbms. Initial schema will be inferred from the database.

`POST` `/grandql/updateSchema/{dbms.name}/` - the management endpoint for the GraphQL API for dbms. Send either the GraphQL type definitions, or `{infer: true}` to use inferred type definitions

`{schema: $typeDefs}` - to set schema using $typeDefs

Example:
```
curl --location --request POST 'localhost:3000/grandql/updateSchema/foobar/' \
     --header 'Content-Type: application/json' \
     --data-raw '{
        "schema": "type Person {name: String}"
      }'
```
`{infer: true}` - to infer schema from database

Example:
```
curl --location --request POST 'localhost:3000/grandql/updateSchema/foobar/' \
     --header 'Content-Type: application/json' \
     --data-raw '{
      "infer": true
    }'
```

TODO

- [ ] handle persistence (save type definitions to filesystem)
- [ ] serve UI for updating schema (GraphQL Graph App)