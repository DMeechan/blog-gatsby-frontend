# Gatsby Blog

Forked & modified from the [Gatsby Starter Ghost](https://github.com/TryGhost/gatsby-starter-ghost).

A blog built to be lightning fast using [Ghost](https://ghost.org) (CMS) & [Gatsby](https://gatsbyjs.org) (frontend).


# Installing

```bash
git clone https://github.com/DMeechan/blog-gatsby-frontend
```

```bash
cd blog-gatsby-frontend
```

Then install dependencies

```bash
yarn install
```

&nbsp;

# Running

Start the development server. You now have a Gatsby site pulling content from headless Ghost.

```bash
yarn run dev
```

By default, the starter will populate content from a default Ghost install located at https://gatsby.ghost.io.

To use your own install, you will need to edit the `.ghost.json` config file with your credentials. Change the `apiUrl` value to the URL of your Ghost site. For people using the self-hosted version of Ghost, it's the same URL used to access your site.

Next, update the `contentApiKey` value to a key associated with the Ghost site. A key can be provided by creating an integration within Ghost Admin. Navigate to Integrations and click "Add new integration". Name the integration appropriately and click create.

To use this starter without issues, your Ghost installation needs to be at least on version `2.10.0`.

The default Ghost version that is used for this starter is `3.x`. If your Ghost installation is on a lower version, you'll also need to pass in a `version` property in your `.ghost.json` settings:

**Ghost <=3.0.0**
```json
{
    "apiUrl": "https://gatsby.ghost.io",
    "contentApiKey": "9cc5c67c358edfdd81455149d0"
}
```

&nbsp;

# Deploying with Netlify

The starter contains three config files specifically for deploying with Netlify. A `netlify.toml` file for build settings, a `/static/_headers` file with default security headers set for all routes, and `/static/_redirects` to set Netlify custom domain redirects.

To deploy to your Netlify account, hit the button below.

Content API Keys are generally not considered to be sensitive information, they exist so that they can be changed in the event of abuse; so most people commit it directly to their `.ghost.json` config file. If you prefer to keep this information out of your repository you can remove this config and set [Netlify ENV variables](https://www.netlify.com/docs/continuous-deployment/#build-environment-variables) for production builds instead.

Once deployed, you can set up a [Ghost + Netlify Integration](https://docs.ghost.org/integrations/netlify/) to use deploy hooks from Ghost to trigger Netlify rebuilds. That way, any time data changes in Ghost, your site will rebuild on Netlify.

&nbsp;

# Optimising

You can disable the default Ghost Handlebars Theme front-end by enabling the `Make this site private` flag within your Ghost settings. This enables password protection in front of the Ghost install and sets `<meta name="robots" content="noindex" />` so your Gatsby front-end becomes the source of truth for SEO.

&nbsp;

# Extra options

```bash
# Create a production build, locally
yarn run build
```

```bash
# Or serve a production build, locally
yarn run serve
```

Gatsby `develop` uses the `development` config in `.ghost.json` - while Gatsby `build` uses the `production` config.

&nbsp;
