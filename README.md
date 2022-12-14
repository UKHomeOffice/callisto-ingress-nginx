# Callisto Ingress Nginx

This repo contains ingress configuration for Callisto.

## Formatting Helm files

Prettier adds spacing between brackets in Helm files which prevents Helm from being able to interpret yaml files, eg. `{{ .Values.name }}` becomes `{ { .Values.name } }`.

To get around this, you need to prevent Prettier from running in Helm files by adding the following to your `settings.json` file:

```json
"[helm]": {
  "editor.formatOnSave": false
},
```

## Considerations
a `DRONE_TOKEN` is used in the drone yaml file to get access to execute drone cli commands. This token is tied to a specific user and stored in the drone secrets for this repo. If the user is removed from drone the `DRONE_TOKEN` must be replaced with someone else's token.
