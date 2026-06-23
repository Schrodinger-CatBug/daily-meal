# daily-meal

## Cursor Cloud specific instructions

This repository is currently an **early-stage skeleton**. Be aware of the following before looking for an application to run/build/test:

- The parent repo (`daily-meal`) tracks only `README.md` and `.gitmodules`. There is **no application code, build, lint, or test setup** in the parent repo yet.
- The only sub-project is the git submodule `Schrodinger-CatBug.github.io`, which is a stub `@salary-counter/site` GitHub Pages package. Its `npm run dev` and `npm run build` scripts are **placeholders** that just print `site dev: 待实现` / `site build: 待实现` ("to be implemented"). There is no real dev server, build output, or tests there.
- There are **no dependencies to install**: no lockfiles anywhere, and the submodule `package.json` declares no dependencies.

### Submodule checkout (no SSH key in cloud)

`.gitmodules` uses an SSH URL (`git@github.com:...`). The cloud VM has no SSH key, so rewrite SSH to HTTPS (repo-local) before initializing. The submodule repo is public, so HTTPS works:

```bash
git config url."https://github.com/".insteadOf "git@github.com:"
git submodule update --init --recursive
```

Once real application code lands, update this section with the actual run/build/lint/test commands.
