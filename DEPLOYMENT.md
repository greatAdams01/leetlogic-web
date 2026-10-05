# Netlify

For the standalone `leetlogic-web` repository:

- Base directory: repository root (leave blank).
- Build command: `npm run build`.
- Publish directory: `.next`.
- Install development dependencies during the build. If custom installation flags
  omit them, remove those flags or use `npm install --include=dev`.
- Keep Netlify's automatically detected Next.js runtime enabled.

`typescript`, `@types/node`, and React type definitions are declared in this
package because Next.js needs them during production builds. Do not rely on
dependencies installed in a parent workspace.

The Next.js configuration selects the parent pnpm workspace only when one exists,
so this package also works as a nested Git checkout during local development.

After updating the repository, trigger a new Netlify deploy. A missing build-cache
warning on the first build is informational, not a deployment failure.

See [Netlify's build configuration documentation](https://docs.netlify.com/build/configure-builds/overview/).
