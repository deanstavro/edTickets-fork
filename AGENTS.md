# Repository Guidelines

## Project Structure & Module Organization
This repository is split into two main areas:
- `app/`: Express/Mongoose backend code. Controllers live in `app/controllers/` and data models in `app/models/`.
- `public/`: AngularJS frontend and static assets. Views are in `public/views/`, client controllers/services in `public/angular/`, and shared CSS/JS/images in `public/css/`, `public/js/`, `public/img/`, and `public/fonts/`.

Keep backend logic in `app/` and browser-facing code in `public/`. Avoid mixing server routes, data models, and UI code in the same file.

## Build, Test, and Development Commands
- `npm install`: installs the Node dependencies listed in `package.json`.
- `node app.js`: starts the application locally. The README expects MongoDB to be running first.
- `npm test`: currently a placeholder and exits with an error. There is no automated test runner configured yet.

## Coding Style & Naming Conventions
The codebase uses standard JavaScript with CommonJS modules on the server and AngularJS patterns on the client.
- Use 2-space indentation and semicolons to match the existing files.
- Name backend modules by responsibility, such as `users.js`, `tickets.js`, `User.js`, and `Ticket.js`.
- Keep Angular filenames descriptive: `*Controller.js` for controllers and `*Service.js` for services.
- Prefer lowercase, hyphen-free filenames for server files; preserve existing PascalCase for Mongoose models.

## Testing Guidelines
No test framework is configured in this repository. If you add tests, place them close to the code they cover and use clear names such as `tickets.spec.js` or `users.test.js`.
Until tests exist, verify changes manually by running the app, exercising login/signup/ticket flows, and checking browser and server logs for errors.

## Commit & Pull Request Guidelines
Recent commit messages are short, imperative, and lowercase-oriented, such as `remove AGENTS`, `small color change`, and `Polish navbar styling`. Follow that style: keep commits focused and descriptive.
Pull requests should include:
- A short summary of the change and why it was made
- Screenshots for UI changes in `public/`
- Notes about any database or environment changes
- Links to related issues when applicable

## Configuration & Security Notes
The README notes email credentials belong in `app/config/config.js`. Do not commit real secrets. Treat JWT, MongoDB, and SMTP settings as environment-specific configuration.
