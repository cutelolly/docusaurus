---
sidebar_position: 2
---

# Translate your site

Let's translate `docs/intro.md` to French.

## Configure i18n

Modify `docusaurus.config.js` to add support for the `fr` locale:

```js title="docusaurus.config.js"
module.exports = {
  i18n: {
    defaultLocale: 'en',
    locales: ['en', 'zh-Hans', 'fr'],
  },
};
```

## Translate a doc

### fr(法语)
Copy the `docs/intro.md` file to the `i18n/fr` folder:

```bash
mkdir -p i18n/fr/docusaurus-plugin-content-docs/current/

cp docs/intro.md i18n/fr/docusaurus-plugin-content-docs/current/intro.md
```

Translate `i18n/fr/docusaurus-plugin-content-docs/current/intro.md` in French.

### en(英语)
Copy the `docs/intro.md` file to the `i18n/en` folder:

```bash
mkdir -p i18n/en/docusaurus-plugin-content-docs/current/

cp docs/intro.md i18n/en/docusaurus-plugin-content-docs/current/intro.md
```

Translate `i18n/en/docusaurus-plugin-content-docs/current/intro.md` in French.

### zh-Hans(汉语)

Copy the `docs/intro.md` file to the `i18n/zh-Hans` folder:

```bash
[linux]
mkdir -p i18n/zh-Hans/docusaurus-plugin-content-docs/current/
[windows]
mkdir -p i18n\zh-Hans\docusaurus-plugin-content-docs\current
mkdir -p i18n\en\docusaurus-plugin-content-docs\current
[linux]
cp docs/intro.md i18n/zh-Hans/docusaurus-plugin-content-docs/current/intro.md
[windows]
copy docs\intro.md i18n\zh-Hans\docusaurus-plugin-content-docs\current\intro.md
copy docs\intro.md i18n\en\docusaurus-plugin-content-docs\current\intro.md
```

Translate `i18n/zh-Hans/docusaurus-plugin-content-docs/current/intro.md` in Chinese.


## Start your localized site

### fr

Start your site on the French locale:

```bash
npm run start -- --locale fr
```

Your localized site is accessible at [http://localhost:3000/fr/](http://localhost:3000/fr/) and the `Getting Started` page is translated.

:::caution

In development, you can only use one locale at a same time.

:::

### en

Start your site on the French locale:

```bash
npm run start -- --locale en
```

Your localized site is accessible at [http://localhost:3000/en/](http://localhost:3000/en/) and the `Getting Started` page is translated.

:::caution

In development, you can only use one locale at a same time.

:::

### zh-Hans

Start your site on the Chinese locale:

```bash
npm run start -- --locale zh-Hans
```

Your localized site is accessible at [http://localhost:3000/zh-Hans/](http://localhost:3000/zh-Hans/) and the `Getting Started` page is translated.

注意：如果简体中文为默认语言，链接为：[http://localhost:3000](http://localhost:3000) 

:::caution

In development, you can only use one locale at a same time.

:::

## Add a Locale Dropdown

To navigate seamlessly across languages, add a locale dropdown.

Modify the `docusaurus.config.js` file:

```js title="docusaurus.config.js"
module.exports = {
  themeConfig: {
    navbar: {
      items: [
        // highlight-start
        {
          type: 'localeDropdown',
        },
        // highlight-end
      ],
    },
  },
};
```

The locale dropdown now appears in your navbar:

![Locale Dropdown](./img/localeDropdown.png)

## Build your localized site

Build your site for a specific locale:

```bash
npm run build -- --locale fr
npm run build -- --locale en
npm run build -- --locale zh-Hans
```

Or build your site to include all the locales at once:

```bash
npm run build
```
