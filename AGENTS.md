# Repository Guide

## Architecture Overview

- `app.js` starts the Express app, connects to MongoDB, mounts middleware, serves `public/`, and wires the route tree.
- `app/controllers/` contains the HTTP APIs.
- `app/models/` contains the Mongoose schemas.
- `libs/` contains shared server helpers.
- `public/` contains the AngularJS frontend, views, and static assets.
- `uploads/` is the runtime file store for uploaded files.

## Coding Conventions

- Match the existing style in the file you are editing.
- Use CommonJS, `var`, and semicolon-terminated JavaScript on the server side.
- Keep changes small and local to the relevant controller, model, or view.
- Prefer existing helpers and response patterns instead of introducing new ones.
- Avoid adding new dependencies unless absolutely necessary.

## Testing Commands

- Install dependencies: `npm install`
- Start the app: `node app.js`
- `npm test` is not configured and currently exits with an error message.
- Manual smoke testing should cover login, ticket creation, file upload/download, ticket messaging, and ticket status changes.

## Development Workflow

- Update the relevant controller, model, or view for the feature or fix.
- Check any related auth, session, or response helper code before changing API behavior.
- Verify the flow in the browser after a hard refresh, since the app is served as static assets.
- Keep ticket and email side effects in mind when editing support-ticket flows.
