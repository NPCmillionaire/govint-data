# govint-data

Prebuilt public datasets for [govint](https://github.com/NPCmillionaire/govint).

## FAA aircraft registry

The FAA's [ReleasableAircraft.zip](https://registry.faa.gov/database/ReleasableAircraft.zip) often rejects scripted downloads. When that happens, `govint sync faa` falls back to the copy in the [`faa` release](https://github.com/NPCmillionaire/govint-data/releases/tag/faa):

- `faa.sqlite.gz` is the registry (MASTER + ACFTREF) as a ready-to-use SQLite database.
- `faa.manifest.json` holds the data date, row count, and SHA-256. govint checks the checksum before loading.

faa.gov also blocks GitHub's servers, so the release is refreshed by hand from a browser download:

```
govint mirror faa --file ~/Downloads/ReleasableAircraft.zip --publish NPCmillionaire/govint-data
```

The data is a US government work in the public domain. It lists registered owners' names and addresses exactly as the FAA publishes them.
