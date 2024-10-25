# SST Extension Specification

- **Title:** SST
- **Identifier:** <https://dewberry.github.io/sst-stac-extension/v0.1.0-beta/schema.json>
- **Field Name Prefix:** sst
- **Scope:** Item, Collection
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @slawler @nick-j-roberts

This document explains the SST Extension to the [SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.
This extension is meant to formalize and define terms used in documenting metadata produced as part of a pipeline for running stochaistic storm
transposition (SST) modeling. This extension thus far focuses on metadata produced when translating a watershed geometry over a valid transposition
region and summarizing precipitation values found in the translated location. This processing would occur in order to identify precipitation
accumulation metrics which could have realistically occurred within the watershed and over a given duration.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item using dummy values
  - [Collection example](examples/collection.json): Shows the basic usage of the extension in a STAC Collection for the summaries field
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:

- [ ] Catalogs
- [ ] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [ ] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name     | Type                                    | Description                                                                                                                                                                                                                                                           |
| -------------- | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sst:statistics | [Statistics Object](#statistics-object) | **REQUIRED**. Object providing the precipitaion accumulation minimum, mean, and maximum values with units specified, along with the count of gridded AORC cells used to produce the statistics and optionally the normalized mean (AORC mean divided by ATLAS14 mean) |

### Additional Field Information

#### sst:statistics

This is a much more detailed description of the field `sst:statistics`...

### Statistics Object

This is the introduction for the purpose and the content of the Statistics Object...

| Field Name      | Type    | Description                                  |
| --------------- | ------- | -------------------------------------------- |
| min             | number  | **REQUIRED**. Describe the required field... |
| mean            | number  | **REQUIRED**. Describe the required field... |
| max             | number  | **REQUIRED**. Describe the required field... |
| count           | integer | **REQUIRED**. Describe the required field... |
| normalized_mean | number  | Describe the optional field...               |

## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PR's are part of the repository and can be run locally to verify that changes are valid.
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on
your command line run:

```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:

```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:

```bash
npm run format-examples
```
