---
title: Frontend Overview
description: This article provides an overview of frontend and assets.
originalLink: https://documentation.spryker.com/v1/docs/frontend-overview
originalArticleId: e146f984-368b-448f-9900-8e5d0935f1f2
redirect_from:
  - /v1/docs/frontend-overview
  - /v1/docs/en/frontend-overview
---

To learn how to build your assets in our Demoshop, see [Demoshop Guide](/docs/scos/dev/developer-guides/201811.0/development-guide/front-end/legacy-demoshop/demoshop-guide.html).

## Asset Management
A set of resources used to build the UI, that includes html, css (or less, sass, stylus, etc.) and js (or jsx, etc.) files, images, fonts and so on.

Assets are files, a large collection of files; a solution to manage them it’s crucial.

We point out 4 different steps to achieve this:

1. [download and structure](/docs/scos/dev/developer-guides/201811.0/development-guide/front-end/legacy-demoshop/download-and-structure.html): get external dependencies and put assets into the corresponding folders;
2. [development](/docs/scos/dev/features/201811.0/sdk/development.html): create your frontend;
3. [transpile/build and optimization](/docs/scos/dev/developer-guides/201811.0/development-guide/front-end/legacy-demoshop/build-and-optimization.html): manipulate and optimize assets;
4. [public folder](/docs/scos/dev/developer-guides/201811.0/development-guide/front-end/legacy-demoshop/public-folder.html): place built output into a public and accessible folder.

### Legend
We will use path aliases to help you dive into the assets docs:

* `@project`: your project root folder;
* `@core`: Spryker core folder, usually (but not necessary) `@project/vendor/spryker`.