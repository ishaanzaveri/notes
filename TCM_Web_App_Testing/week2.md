# Week 2

## XSS

- Dom based XSS
  - [scip](https://www.scip.ch/en/?labs.20171214)
  - [portswigger](https://portswigger.net/web-security/cross-site-scripting/dom-based)
- Reflected XSS

### Avoiding XSS

- Encoding : changing chars like '<' to '&lt;'
- Filtering : making sure things like `<script>` becomes `script`
- Validation : remove all `<script>` from the query
- Sanitization : combining all of the above
- Secure flags for `Set-Cookie`
