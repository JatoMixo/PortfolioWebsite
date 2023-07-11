# JatoMixo.com

This is my SvelteKit Project combined with Scss for creating my own website.

## To work with this project
```bash
# Clone the repository
git clone git@github.com:JatoMixo/PortfolioWebsite.git

# Start dev preview (Go to localhost:5173 in your browser)
npm run dev

# To build the actual project
npm run build
```

## Components
There are several built-in components I have made for the website which include:

### Tool Card
Used to show data about the tools I use

```html
<ToolCard image={IMPORTED_IMAGE_FROM_SCRIPT_TAG} name={NAME_OF_THE_TOOL} description={DESCRIPTION_OF_TOOL}/>
```

### Project
Used to show data about a project I have made

```html
<Project name={NAME_OF_PROJECT} description={DESCRIPTION_OF_PROJECT} github={GITHUB_LINK_OF_PROJECT} tool={IMAGE_CONTAINED_LOGO_OF_TOOL_USED}/>
```

### Social Media
Used to show the logo of a social media app like twitter with a link to my account.

```html
<SocialMedia link={LINK_TO_ACCOUNT} image={LOGO_FOR_SOCIAL_MEDIA} image_alt={ALT_PROPERTY_FOR_IMAGE}/>
```