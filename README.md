# **zatsit** blog contents repository

This repository holds the contents of the **zatsit** blog: articles, authors and their images.
The site itself is built with [Astro](https://astro.build/) in a separate repository,
[zats-blog](https://github.com/zatsit-oss/zats-blog), which reads this content in place.

## Build the blog locally

Clone the shell next to this repository. The shell expects the content under the exact directory name
`zats-blog-content`, a path hard-coded in its `src/consts.ts` and `src/utils/avatars.ts`.

```sh
git clone git@github.com:zatsit-oss/zats-blog.git
git clone git@github.com:zatsit-oss/zats-blog-content.git
cd zats-blog
npm install
npm run dev              # dev server, hot reload on article changes
npm run build && npm run preview   # production build, the only way to test search
```

Feel free to contribute to the blog by creating a pull request.
- [Code of conduct](./CODE_OF_CONDUCT.md)
- [Contributing](./CONTRIBUTING.md)
- [Posting](./POSTING.md)

## Pre-requisites

Committing on this repository requires to do signed commits.
To enable signed commits,
- register your SSH public key in your GitHub account as **Signing key** `Key type
- configure your Git CLI **globally** to sign commits by default.

```
git config --global gpg.format ssh
# here replace ~/.ssh/examplekey.pub with your own public key path
git config --global user.signingkey ~/.ssh/examplekey.pub

git config --global commit.gpgsign true
```

> You can also follow [those instructions](https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification/signing-commits).

## Write a new post

Please follow the [posting guidelines](./POSTING.md) to write a new post.

Opening your Pull Request will trigger a CI/CD pipeline that will generate 
an ephemeral Firebase preview of the whole blog, built with your branch.
Wait a few minutes and check the preview link in the PR checks.
Production is [blog.zatsit.fr](https://blog.zatsit.fr), rebuilt on each merge to `main`.
