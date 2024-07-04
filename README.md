# Zerops x SvelteKit - Static

Sveltekit is a framework for building robust, fast web applications using Svelte. [Zerops](https://zerops.io) makes deploying and running Sveltekit apps, both server side rendered and static, a breeze. This recipe showcases the Static version, see [zeropsio/recipe-sveltekit-nodejs](https://github.com/zeropsio/recipe-sveltekit-nodejs) for the Node.js version.

![sveltekit](https://github.com/zeropsio/recipe-shared-assets/blob/main/covers/svg/cover-svelte.svg)

<br/>

## Deploy on Zerops

You can either click the deploy button to deploy directly on Zerops, or manually copy the [import yaml](https://github.com/zeropsio/recipe-sveltekit-static/blob/main/zerops-project-import.yml) to the import dialog in the Zerops app.

[![Deploy on Zerops](https://github.com/zeropsio/recipe-shared-assets/blob/main/deploy-button/green/deploy-button.svg)](https://app.zerops.io/recipe/sveltekit-static)


<br/>
<br/>

## Recipe features
- Latest version of **SvelteKit** with SSG running on a **Zerops Static** service.

<br/>

## Production vs. development
This recipe is ready for production as is, and will scale horizontally by adding more containers in case of high traffic surges. If you want to achieve the highest baseline reliability and resiliace, start with at least two containers (add `minContainers: 2` in recipe YAML in the `app` service section, or change the minimum containers in "Automatic Scaling configuration" section of service detail).

<br/>

## Changes made over the default installation
If you want to modify your existing SvelteKit app to efficiently run on Zerops, follow these steps:

1. Install the necessary adapter with:
    ```sh
    pnpm i -D @sveltejs/adapter-static
    ```
2. Add the adapter to your `svelte.config.js` to enable SSG. Also, ensure you have `@sveltejs/vite-plugin-svelte` to avoid errors.
    ```js
    import adapter from '@sveltejs/adapter-static';
    import { vitePreprocess } from '@sveltejs/vite-plugin-svelte';

    /** @type {import('@sveltejs/kit').Config} */
    const config = {
      kit: {
        adapter: adapter(),
      },
      preprocess: vitePreprocess(),
    };

    export default config;
    ```
3. Add the prerender option to your root layout, for example, in `src/routes/+layout.ts`:
    ```js
    // export const ssr = false; default is false
    export const prerender = true;
    ```

Now, just add the [zerops.yml](https://github.com/zeropsio/recipe-sveltekit-static/blob/main/zerops.yml) file to the root of your project.


<br/>
<br/>

Need help setting your project up? Join [Zerops Discord community](https://discord.com/invite/WDvCZ54).