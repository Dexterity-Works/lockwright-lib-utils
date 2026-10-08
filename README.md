# lockwright-lib-utils

Small shared utils for Lockwright apps and libraries. Plain ESM source, no build step.

Site: [lockwright.dexterity.works](https://lockwright.dexterity.works)

Community fork of PearPass (Apache 2.0). Not affiliated with or endorsed by Tether Data or the Pears project.

## Subpaths

Import by subpath. There is no root export, so a bundler that does not tree-shake (Metro) only pulls in the util you use.

| Import | Exports |
| --- | --- |
| `lockwright-lib-utils/generate-unique-id` | `generateUniqueId` |
| `lockwright-lib-utils/password-check` | `checkPasswordStrength`, `checkPassphraseStrength`, `constantTimeHashCompare`, `validatePasswordChange`, `PASSWORD_STRENGTH` |
| `lockwright-lib-utils/password-generator` | `generatePassword`, `generatePassphrase` |
| `lockwright-lib-utils/qr` | `generateQRCodeSVG` |
| `lockwright-lib-utils/validator` | `Validator` |

```js
import { Validator } from 'lockwright-lib-utils/validator'

Validator.string().required().minLength(3).validate('ab') // "Minimum length is 3"
```

`generate-unique-id` and `password-generator` ship `.native.js` files that Metro picks on React Native. They use `expo-crypto` there, an optional peer dependency. `qr` depends on `qrcode`.

## Install

Add it as a git dependency pinned by commit:

```json
"lockwright-lib-utils": "git+https://github.com/Dexterity-Works/lockwright-lib-utils.git#<commit sha>"
```

The package runs no install scripts.

## Develop

```bash
npm ci
npm run lint
npm test
```

## History

This package absorbed five former repos, now archived with their history:

- `lockwright-utils-generate-unique-id`
- `lockwright-utils-password-check`
- `lockwright-utils-password-generator`
- `lockwright-utils-qr`
- `lockwright-utils-validator` (this repo, renamed)

## License

Apache License, Version 2.0. See [LICENSE](./LICENSE.md) and [NOTICE](./NOTICE.md).
