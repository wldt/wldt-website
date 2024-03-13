# Customizations

Customizations for the [Doks Core](https://github.com/gethyas/doks-core) integration go here.

## Usage

Copy the file(s) you'd like to override from `./node_modules/@hyas/doks-core/` and paste to `./themes/my-doks-theme/`. Make sure to keep the folder structure.

Supported folders are: `archetypes`, `assets`, `data`, and `layouts`.

## Running Local Instance

```
npm run dev
```

## Create new content

```
npm run create about/test.md
```

## Mounting settings

If needed, you can change the mountings settings in `./config/_default/module.toml`. See also the Hugo docs: [Module Config: mounts](https://gohugo.io/hugo-modules/configuration/#module-config-mounts).
