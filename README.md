# Astro SSR image prerendering test case

Running `yarn build` in this Astro repo should generate multiple versions of the `Stortorget.jpg` for the `Picture` component on the prerendered home page at build time, but it doesn't.

To compare:

- Comment out `output` and `adapter` in `astro.config.mjs`.
- Run `yarn build`.
- `ls -R dist` and note that there are several `Stortorget.*` images.
- Uncomment `output` and `adapter`.
- Run `yarn build`.
- `ls -R dist` and note that there are is only one `Stortorget.*` image.

The page does work in `yarn preview`, because the `/_image` URL generates images on demand, but it consumes server resources.
