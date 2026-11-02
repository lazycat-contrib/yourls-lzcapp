# YOURLS (LazyCat LPK)

Self-hosted URL shortener.

- Upstream: https://github.com/YOURLS/YOURLS
- Image: `library/yourls:1.10.6` (official Docker Hub image, mirror mode, digest-matched)
- License: MIT (full text in `content/licenses/LICENSE`)
- Containers: YOURLS + MariaDB 10.11

## Notes

- The official image provisions `config.php` from env vars on first start:
  `YOURLS_DB_HOST/NAME/USER/PASS/PREFIX`, `YOURLS_SITE`, `YOURLS_USER`, `YOURLS_PASS`.
  The admin username/password come from deploy params (password random by default), so there
  is no built-in credential.
- `YOURLS_SITE` is set to the app's https domain so generated short links resolve correctly
  behind the LazyCat proxy.
- Webroot mounted at `/lzcapp/var/html`, database at `/lzcapp/var/db`.
- No mail service configured.
- Not yet verified on a real device.
