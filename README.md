# authjs-env

Load [Auth.js](https://authjs.dev) providers dynamically, by detecting environment variables.

## Usage

Install the package:

```sh
pnpm install -D authjs-env
```

Define env vars in your `.env` or in your hosting settings.

For example, for Github, define a `GITHUB_ID` & `GITHUB_SECRET`.

```
# in .env
GITHUB_ID=...
GITHUB_SECRET=...
```

### SvelteKit

Import `providers` in `src/hooks.server.js`:

```javascript
import { SvelteKitAuth } from "@auth/sveltekit"
import { providers } from 'authjs-env'

export const handle = SvelteKitAuth({
  providers
})
```

### React

Import `providers` in `auth.ts`:

```javascript
import NextAuth from "next-auth"
import { providers } from 'authjs-env'

export const { handlers, auth } = NextAuth({ providers })
```

## Supported Providers

- [Apple](https://authjs.dev/reference/core/providers/apple)
- [Google](https://authjs.dev/reference/core/providers/google)
- [GitHub](https://authjs.dev/reference/core/providers/github)

The aim is to support all providers! Please open a PR if the one you want is missing.

## License

MIT
