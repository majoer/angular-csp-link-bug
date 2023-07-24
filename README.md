# Angular Universal CSP link bug reproduction.

## How to reproduce

1. Create a new angular project:

```bash
ng new
```

2. Add nonce to app-root as explained here: https://angular.io/guide/security#content-security-policy<br/>
   We use a dummy value for nonce just for testing, for example:

```html
<!-- src/index.html -->
<app-root ngCspNonce="123"></app-root>
```

3. Add a stylesheet link to head, for example:

```html
<!-- src/index.html -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" />
```

4. Build and see error message

```bash
npm run build

# Index html generation failed.
# link.prev?.setAttribute is not a function
```
