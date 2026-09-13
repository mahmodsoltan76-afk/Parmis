# Parmis root route fix

The root URL `/` now redirects to `/install` so the Worker does not show the decoy/default page.
After deployment open:

- `/`
- `/install`

Make sure a KV namespace is bound with the exact variable name `KV`; the admin/install flow requires it.
