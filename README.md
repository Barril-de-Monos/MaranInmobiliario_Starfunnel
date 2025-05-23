# Maran Inmobiliario, StarFunnel + Astro + Static CMS

[![License: CC BY-ND 4.0](https://img.shields.io/badge/License-CC_BY--ND_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nd/4.0/)


## Clone this repo or deploy to netlify

Easily deploy this theme to Netlify or Vercel.

## 1. Setting up the .env file

rename the `env.txt` to `.env` and fill in your details

    BLOG_SLUG=news 
    WEBSITE_LANGUAGE=en
    CURRENCY=USD 
    NODE_VERSION=18 
    NEWSLETTER_PROVIDER=mailchimp

    MAILCHIMP_API_KEY=XXX
    MAILCHIMP_SERVER_PREFIX=us21	
    MAILCHIMP_LIST_ID=XXX

    SLACK_CHANNEL_ID=XXX
    SLACK_TOKEN=XXX

    FROM_EMAIL_ADDRESS=hello@youremail.com
    TO_EMAIL_ADDRESS=hello@youremail.com 

    MAILGUN_API_KEY=XXX
    MAILGUN_DOMAIN=your-domain.com
    MAILGUN_API_URL=https://api.eu.mailgun.net

    POSTMARK_SERVER_TOKEN=XXX

Also add this to your netlify deploy settings.

### 2. Configure your Static CMS Backend

Navigate to `src/pages/admin.astro` and provide your Git repository details. You can find a list of all supported Git backends at:
<https://www.staticcms.org/docs/backends-overview>

**_Gitlab Example:_**

```javascript

const config = {
	locale: lang,
	site_url: url,
	logo_url: 'https://starfunnel.unfolding.io/logo.svg',
	local_backend: true,
	backend: {
		name: 'gitlab',
		repo: '/<your-gitlab-repo>',
		auth_type: 'pkce', // Required for pkce
		app_id: 'xxxx', // Application ID from your GitLab settings
		commit_messages: {
			create: 'Create {{collection}} "{{slug}}"',
			update: 'Update {{collection}} "{{slug}}"',
			delete: 'Delete {{collection}} "{{slug}}"',
			uploadMedia: 'Upload "{{path}}"',
			deleteMedia: 'Delete "{{path}}"'
		}
	},
	search: 'true',
    ....
}

```

### 3. Add your site to the astro config and set your adapter (vercel or netlify)


```javascript

export default defineConfig({
	site: 'https://your-website.com',
	output: "hybrid",
  	adapter: vercel(), // vercel() or netlify()

    ....

```

### 4. Install dependencies

```bash
npm install
```

### 🛠️ 5. Start Development server

```bash
npm run dev
```

If you wish to engage the local backend:

```bash
npm run cms-proxy-server
```

Now you can open Static CMS on http&#x3A;//localhost:4321/admin/

## 🛸 Commands

All commands are run from the root of the project, from a terminal:

| Command                    | Action                                           |
| -------------------------- | ------------------------------------------------ |
| `npm install`              | Installs dependencies                            |
| `npm run dev`              | Starts local dev server at `localhost:4321`      |
| `npm run cms-proxy-server` | Starts Staticcms proxy server for local-backend  |
| `npm run build`            | Build your production site to `./dist/`          |
| `npm run preview`          | Preview your build locally, before deploying     |
| `npm run astro ...`        | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help`  | Get help using the Astro CL                      |

## 👀 Want to learn more about Astro?

Check out [Astro documentation](https://docs.astro.build) or jump into Astro's [Discord server](https://astro.build/chat).

## 📚 Tech Stack

Astro, MDX, Vue, TailwindCSS

## 🛟 Support

If you encounter any issues or bugs, we encourage you to open an issue in the repository. To help us quickly address the problem, please provide detailed information about the bug and steps to reproduce it.

For those seeking priority assistance, we offer premium support services. Feel free to reach out to us by email at [hello@unfolding.io.](mailto:hello@unfolding.io.) We're here to help!

## 🚕 Roadmap

As we journey towards v1.0, we want to integrate the best sales tools on the market. If you have requests, please let us know!

## ☕️ Want to Caffeinate your Developer? 

By [caffeinating](https://www.buymeacoffee.com/unfolding.io) your developer, you're not just getting the best out of them; you're also ensuring a cheerful and energetic work environment.😊

[![buymeacoffee](https://starfunnel.unfolding.io/screenshots/bymeacoffee.webp)](https://www.buymeacoffee.com/unfolding.io)





## 📸 Screenshots

![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_1.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_2.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_3.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_4.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_5.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_6.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_7.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_8.jpg)
![StarFunnel](https://starfunnel.unfolding.io/screenshots/screenshot_9.jpg) 






