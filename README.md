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
- OS X `relate-extensions-dir`: `~/Library/Application \Support/com.Neo4j.Relate/Data/extensions`
- Linux `relate-extensions-dir`: `~/.local/share/neo4j-relate/extensions`
- Win32 `relate-extensions-dir`: `%APPDATA%\Local\Neo4j\Relate\Data\extensions`
