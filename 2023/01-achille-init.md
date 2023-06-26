---
# Post Title
# String | *REQUIRED*
# Ex: Top 4 React UI Libraries for 2023
title: Achille - Setup Project

# Post Slug
# What is slug? https://www.semrush.com/blog/what-is-a-url-slug
# String | *REQUIRED*
# Ex: top-4-react-ui-libraries-for-2023
# - This is the URL of the post. It should be unique and should not be used by any other post.
# - If you use the same slug of an existing post, the existing post will be updated.
# - In order to let users update the post SLUG, we depend on the post slug as well
#   as it's path in the repo.
# - If you change both path and slug of the post, the post will be treated as a new post and
#   will be published with a new slug.
# - If you change only the slug of the post, the post will be updated with the new slug.
# - If you change only the path of the post, the post will be will be updated with new path
#   and any other changes along with it if any.
slug: achille-01-init

# Tags
# String (comma-separated tag slugs) | *REQUIRED*
# Ex: reactjs, css, python, nodejs
# Upto 5 tag slugs
# - You can find tags information from here https://github.com/Hashnode/support/blob/main/misc/tags.json
# You can also update a post to edit this later.
tags: reactjs, css, react-native, nodejs

# Publication Domain (hashnode.dev subdomain or your custom domain)
# String | *REQUIRED*
# Ex: townhall.hashnode.com
# - This can also be a hashnode.dev subdomain as well.
# - The publication domain name that you want to publish the post to.
#   This should be a valid domain name only.
# - You should be an ADMIN of the publication to publish.
domain: https://coluzziandrea.hashnode.dev/

# Subtitle of the post
# String | Optional
# Ex: A curated list of the best React UI libraries for 2023
subtitle: Setup Achille project

# Cover Image URL of the post
# String | Optional
# Note: You must upload the image to Hashnode's CDN, before you can use it here.
# Ex: https://cdn.hashnode.com/res/hashnode/image/upload/v1681132538878/itnaYF1h-.png
# - To upload, Login to Hashnode and go to https://hashnode.com/uploader
#   Use the URL that is generated after the upload.
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687288442178/A7_Upy1I9.jpg?auto=format

# Should the post be ignored? When true it will not be picked up by Hashnode.
# Boolean | Optional
# Default value: false
# Ex: true
# - It's useful when you want to keep the post in your repo but don't
#   want it to be picked up by Hashnode.
ignorePost:

# Publish on behalf of a team publication member
# Username of the publication member
# String | Optional | *WORKS WITH TEAM PUBLICATION ONLY*
# Ex: sandeep
# - This resembles the Change of author from draft settings of a
#   team publication in Hashnode editor.
# - Fails if the user is not a member of the team publication or
#   if the publication is not a team publication
publishAs:

# Canonical URL of the post
# String | Optional
# What is a canonical URL? https://moz.com/learn/seo/canonicalization
# Ex: https://www.hashnode.com/post/top-4-react-ui-libraries-for-2023
# - This is equivalent to original URL option present in draft settings
#   of a post in Hashnode editor.
# - This is useful when you want to publish a post that is already
#   published on another platform.
canonical: https://coluzziandrea.hashnode.dev/achille/achille-01-init

# Hide from Hashnode Community
# Boolean | Optional
# Default value: false // by default the post will be visible in the Hashnode's public feed.
# Ex: true
# - This is equivalent to "HIDE ARTICLE FROM HASHNODE FEED" option
#   present in draft settings of a post in Hashnode editor.
# - This is useful when you want to publish a post to your publication
#   only but hide it from the Hashnode's public feed.
# - You can also update a post to enable/disable this later.
hideFromHashnodeCommunity:

# SEO Title
# String | Optional
# Ex: Top 4 React UI Libraries for 2023
# - This is equivalent to SEO TITLE option present in draft settings
#   of a post in Hashnode editor.
# - You can also update a post to update this later.
seoTitle: Achille - Setup Project

# SEO Description
# String | Optional
# Ex: A curated list of the best React UI libraries for 2023
# - This is equivalent to SEO DESCRIPTION option present in
#   draft settings of a post in Hashnode editor.
# - You can also update a post to update this later.
seoDescription: Setup Achille project

# Disable comments for a post
# Boolean | Optional
# Default value: false // by default the comments will be enabled for the post.
# Ex: true
# - This is equivalent to "DISABLE COMMENTS" option present in
#   draft settings of a post in Hashnode editor.
# - You can also update a post to enable/disable this later.
disableComments:

# Slug of the series that you want your post to be a part of
# String | Optional
# Ex: react-series
# - This is equivalent to "ADD TO A SERIES" option present in
#   draft settings of a post in Hashnode editor.
# - If invalid series is given, the post will not be added to any series.
# - You can update the post again to correct it later.
# - You can find series information from the series section in your publication dashboard.
#   You can also edit the series information from there.
seriesSlug: achille

# Table of contents
# Boolean | Optional
# Default value: false // by default the table of contents will not be added to the post.
# Ex: true
# - This is equivalent to "GENERATE TABLE OF CONTENTS" option
#   present in draft settings of a post in Hashnode editor.
# - If true, the table of contents will be added to the post.
# - You can also update a post to enable/disable this later.
enableToc:

# Save post as draft
# Boolean | Optional
# Default value: false // by default the post will be published.
# Ex: true
# - If true, the post will be saved as a draft.
# - You can also update a draft with all the above attributes.
# - This draft will be available under Drafts section of the
#   left sidebar in your publication dashboard.
# - Note: Once you remove this attribute, the post will be
#   published and removed from drafts automatically.
# - This follows the same rules as a post create and update
#   flow as well as the slug rules mentioned since
#   beginning of this manual.
saveAsDraft:
# Note:
# This is in beta currently
# Newsletter and Post scheduling is NOT supported as of now.
---

# Achille - Setup Project

Achille is an open source mobile app built on top of [React Native](https://reactnative.dev/).

We'll use [Expo](https://docs.expo.dev/) to setup our project.

We'll use the following command line to create our project ([ref](https://github.com/expo/examples/tree/master/with-typescript))

> npx create-react-native-app -t with-typescript

## Environment & Prequisites

I'm implementing this in Github Codespace environment, but this guide can be applied to all VS Code distributions.

## Execute from Github Codespaces

You have to signup on Expo.

Install Expo CLI Globally

> npm install -g expo-cli

Login to your account

> expo login

insert your username / password

> expo start --tunnel

then scan the QR code from your phone.

## Add Linting

> yarn add @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint eslint-config-prettier eslint-plugin-prettier eslint-plugin-react prettier prettier-eslint -D

Create a _.eslintrc.js_ file with this content:

```js
module.exports = {
  root: true,
  env: {
    node: true,
    browser: true,
    es2021: true,
    'react-native/react-native': true,
    'jest/globals': true,
  },
  extends: [
    'plugin:react/recommended',
    'prettier',
    'eslint:recommended',
    'plugin:jest/recommended',
  ],

  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 'latest',
    sourceType: 'module',
  },

  plugins: ['react', 'react-native'],
  ignorePatterns: ['!.*', 'dist', 'node_modules'],

  settings: {
    react: {
      version: 'detect',
    },
  },
};
```

Create a _.prettierrc_ with this content:

```json
{
  "semi": false,
  "singleQuote": true,
  "trailingComma": "none"
}
```

## References

You can find all the code for this app in [Github Repo](https://github.com/coluzziandrea/achille)
