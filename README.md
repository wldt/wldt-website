# WLDT website

This is the website for the White Label Digital Twins library.

## Contributing

You can contribute to this documentation page.
Make your own fork of this repository and submit a pull request.

Before committing run

```bash
npm run lint
```

and follow the linting reccomendations.

## Run the Local Server

```bash
npm run dev
```

## Page Creation

Some examples of page creation through npm commands:

```bash
npm run create docs/guides/dt_model.md
npm run create docs/guides/dt-model/dt_model.md
npm run create docs/guides/dt-model.md
npm run create docs/guides/dt-life-cycle.md
npm run create docs/introduction/library-structure.md
npm run create docs/guides/physical-adapter.md
npm run create docs/guides/_index.md
npm run create docs/guides/shadowing-function.md
npm run create docs/guides/digital-adapter.md
npm run create docs/guides/dt-process.md
npm run create docs/guides/digital-actions.md
npm run create docs/guides/dt-relationships.md
npm run create docs/guides/configurable-adapters.md
npm run create docs/change-logs/change-log-0.3.0.md
npm run create docs/change-logs/_index.md
npm run create docs/adapters/_index.md
npm run create docs/adapters/mqtt_physical.md
npm run create docs/adapters/mqtt_digital.md
npm run create docs/adapters/http_digital.md
```

#### New Change Log Creation

```bash
npm run create docs/change-logs/change-log-0.4.0.md
```

#### Blog Post Creation

```bash
npm run create blog/release_040.md
```

## References

- Hyas: https://gethyas.com/
- Thulite Docs: https://docs.thulite.io/