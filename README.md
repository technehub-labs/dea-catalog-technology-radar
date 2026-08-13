# dea-catalog-technology-radar

> DEA catalog for **Technology Radar Entry** — OpenDEAM v0.3.0 (ADR-0003).

## Technology Radar Entry (`TRE`)

- **Entity id:** `dea:entity-technology-radar-entry`
- **Allocation:** L2 · L2-innovation-foresight
- **Status:** proposed

An emerging technology or technique being tracked (assess/trial/adopt/hold) prior to becoming a governed L5 Technology.

## Relationships (from the OpenDEAM model)

- **TRE → EXP** — evaluated via (dependency, 1:0..N)
- **TRE → TEC** — graduates to (realization, 0..1:0..1)

## Allocation contract

This repo's `metamodel-pointer.yaml` is validated in CI against the pinned
OpenDEAM root model (`v0.3.0`) via the reusable
`validate-against-model.yml` workflow. Drift fails CI.

Content (entity instances) lands when the entity promotes from
`proposed` to `planned`/`scaffold` per the model lifecycle.

## License

Apache 2.0 — see [LICENSE](./LICENSE) and [NOTICE](./NOTICE).
