---
title: "Web Development"
oldUrl: /runtime/manual/getting_started/web_frameworks/
---

Deno offers a secure and developer-friendly environment for building web
applications.

1. Deno has [secure defaults](./permissions.md), meaning it requires explicit
   permission for file, network, and environment access, reducing the risk of
   security vulnerabilities.
2. Deno has [built-in TypeScript support](./ts_support.md), allowing you to
   write TypeScript code without additional configuration or tooling.
3. Deno comes with a [standard library](./standard_library.md) that includes
   modules for common tasks like HTTP servers, file system operations, and more.

Most likely, if you're building a more complex application, you'll be
interacting with Deno through a web framework.

## React/Next

[React](https://reactjs.org/) is a popular JavaScript library for building user
interfaces. To use React with Deno, you can use the popular web framework
[Next.js](https://nextjs.org/).

To get started with Next.js in Deno, you can create a new next app and run it
immediately with Deno:

```sh
npx create-next-app@latest --ts my-next-app
cd my-next-app
deno task dev
```

This will create a new Next.js app with TypeScript and run it with Deno. You can
then open your browser to `http://localhost:3000` to see your new app, and start
editing `page.tsx` to see your changes live.

## Fresh

[Fresh](https://fresh.deno.dev/) is the most popular web framework for Deno. It
uses a model where you send no JavaScript to clients by default.

To get started with a Fresh app, you can use the following command and follow
the cli prompts to create your app:

```sh
deno run -A -r https://fresh.deno.dev
cd my-fresh-app
deno task start
```

This will create a new Fresh app and run it with Deno. You can then open your
browser to `http://localhost:8000` to see your new app. Edit `/routes/index.tsx`
to see your changes live.

Fresh does the majority of its rendering on the server, and the client is only
responsible for re-rendering small
[islands of interactivity](https://jasonformat.com/islands-architecture/). This
means the developer explicitly opts in to client side rendering for specific
components.

## Aleph

[Aleph.js](https://alephjs.org/docs/get-started) gives you the same sort of
quick-start with React as Create-React-App. Like Next.js, Aleph provides SSR and
SSG out of the box in order to allow developers to create SEO-friendly apps.

To get started with an Aleph app, you can use the following command and follow
the cli prompts to create your app:

```sh
deno run -A -r https://alephjs.org/init.ts
cd my-app
deno task dev
```

This will create a new Aleph app and run it with Deno. You can then open your
browser to `http://localhost:3000` to see your new app. Edit `/routes/index.tsx`
to see your changes live.

## Ultra

[Ultra](https://ultrajs.dev/) is a modern streaming React framework for Deno.
It's a way to use React to build dynamic media-rich websites, similar to
Next.js.

Deno itself supports JSX and TypeScript out-of-the-box (and therefore Ultra does
as well), but they don't work in the browser. Ultra takes over the task of
transpiling JSX and TypeScript to regular JavaScript.

Other highlights of Ultra include:

- written in Deno.
- powered by import maps.
- 100% esm.
- uses import maps in both development and production, which massively
  simplifies toolchains - you don't have to deal with heaps of bundling and
  transpilation.
- source code is shipped in production, similar to how it's written.
- imports, exports, work as they do in development.

## Lume

[Lume](https://lume.land/) is a static site generator for Deno that is inspired
by other static site generators such Jekyll or Eleventy. It's simple to use and
configure, while being super flexible. Highlights include:

- Support for multiple file formats like Markdown, YAML, JavaScript, TypeScript,
  JSX, Nunjucks.
- You can hook in any processor to transform assets, for example sass or postcss
  for CSS.
- No need to install thousand of packages in `node_modules` or complex bundlers.

## Hono

[Hono](https://hono.dev) is a light-weight web app framework in the tradition of
Express and Sinatra. In just a few lines of code, you can set up an API server
or a server for dynamic web pages. Hono provides a Deno-native installation
path, and works great with Deno’s built-in TypeScript tooling.

- This website is served by Hono running on
  [Deno Deploy](https://deno.com/deploy).

## Oak

[Oak](https://deno.land/x/oak) is a web application framework for Deno, inspired
by Koa and @koa/router.

As a middleware framework, Oak is the glue between your frontend application and
a potential database or other data sources (e.g. REST APIs, GraphQL APIs). Just
to give you an idea, the following is a list of common tech stacks to build
client-server architectures:

- React.js (Frontend) + Oak (Backend) + PostgreSQL (Database)
- Vue.js (Frontend) + Oak (Backend) + MongoDB (Database)
- Angular.js (Frontend) + Oak (Backend) + Neo4j (Database)

Oak offers additional functionality over the native Deno HTTP server, including
a basic router, JSON parser, middlewares, plugins, etc.
