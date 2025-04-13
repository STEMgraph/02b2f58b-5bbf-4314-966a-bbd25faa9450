<!---
{
  "id": "02b2f58b-5bbf-4314-966a-bbd25faa9450",
  "depends_on": ["a0f6c77d-9645-4e6c-80dc-a80608786266"],
  "author": "Stephan Bökelmann",
  "first_used": "2025-04-13",
  "keywords": ["Angular", "CLI", "modern Angular", "command line", "web development"]
}
--->

# Building a Minimal Angular App

> In this exercise you will learn how to scaffold, configure, and run a modern Angular application using only the Angular CLI from the command line. Furthermore we will explore how to avoid unnecessary tooling and keep the setup minimal while still following Angular best practices.

### Introduction

Angular, maintained by Google, is a powerful and structured front-end web application framework that emphasizes maintainability and scalability. Unlike older versions or more lightweight alternatives like React or Vue, Angular requires a well-defined structure and a build process. Fortunately, Angular CLI (Command Line Interface) makes it easy to scaffold and manage Angular applications directly from the terminal. This exercise guides you through setting up a minimal Angular application using only the command line, focusing on core features such as module generation, component creation, and development server setup.

We deliberately avoid extra tooling like IDEs, GUIs, or containerized environments to help you understand the internal workings and structure of an Angular project. All steps are executed via terminal, which encourages a deeper grasp of the file layout, TypeScript integration, and the Angular module system.

To follow this guide, you only need Node.js (v18+), npm (v9+), and Angular CLI installed globally. We'll demonstrate how to create a new project, generate a basic component, and serve the application using built-in Angular tools. This is an ideal starting point for anyone beginning with modern Angular development in a minimalist environment.

### Further Readings and Other Sources

- [Angular CLI Documentation](https://angular.io/cli)
- [Official Angular Getting Started Guide](https://angular.io/start)
- [Understanding Angular Modules](https://angular.io/guide/ngmodules)
- [Video: Angular in 100 Seconds](https://www.youtube.com/watch?v=3qBXWUpoPHo)

### Tasks

#### Task 0: Install Node.js and npm

Before using Angular CLI, make sure you have Node.js (v18 or higher) and npm installed. These are required to run JavaScript outside the browser and manage dependencies. Angular and many modern front-end tools are built on the Node.js ecosystem.

Download and install from the [official Node.js website](https://nodejs.org/).

Verify installation:

```bash
node -v
npm -v
```

These commands check that Node.js and npm were installed correctly and display their version numbers.

#### Task 1: Install Angular CLI Globally

Angular CLI is a command-line interface tool that streamlines the development workflow for Angular applications. It allows you to generate components, services, modules, and other Angular constructs with consistent naming and configuration. Additionally, it provides commands for serving, testing, and building the project.

Installing the CLI globally allows you to use the `ng` command in any terminal session:

```bash
npm install -g @angular/cli
```

After installation, verify it works:

```bash
ng version
```

This ensures your environment is correctly set up to start building Angular apps using the CLI tools.

#### Task 2: Create a New Angular Project

The CLI can generate a fully structured Angular project with a single command:

```bash
ng new minimal-app --defaults --skip-git
cd minimal-app
```

The `--defaults` flag automatically selects the default options such as using CSS for styling and excluding routing for now. The `--skip-git` flag prevents the CLI from initializing a Git repository, which you might not need immediately.

This step sets up a well-organized folder structure including core files like `main.ts`, `app.module.ts`, and configuration files like `angular.json`, `package.json`, and `tsconfig.json`. This foundation follows Angular's architectural best practices.

#### Task 3: Serve the Application

To preview your Angular app in a browser, use the following command:

```bash
ng serve
```

This compiles the TypeScript source code, launches a local development server (typically on port 4200), and watches for file changes to auto-refresh the browser.

Visit `http://localhost:4200` in your browser. You should see the default Angular welcome page. This confirms your setup is functional and ready for development.

> Note: This is different from simply opening an HTML file in a browser or using Python’s built-in `http.server`. Angular uses a full build pipeline that transpiles TypeScript, resolves module dependencies, and supports hot-reloading. Unlike static file serving, `ng serve` integrates with the framework’s tooling for real-time feedback and optimized builds.

#### Task 4: Generate a Component

Angular applications are built from components. A component in Angular is a self-contained unit of UI and behavior, consisting of:
- a **template** (HTML) for layout,
- a **class** (TypeScript) for logic and state,
- **styles** (CSS or similar) for appearance,
- and **metadata** (decorators) to bind them together.

You can generate a new component using:

```bash
ng generate component hello-world
```

This creates a new folder `src/app/hello-world/` with the following files:
- `hello-world.component.ts`: Contains the TypeScript class with component logic.
- `hello-world.component.html`: The UI template.
- `hello-world.component.css`: Styles scoped to the component.
- `hello-world.component.spec.ts`: A starter test file.

Using the CLI to generate components ensures consistent setup and registers the component in `app.module.ts` automatically. This saves time and avoids manual errors.

Components are to Angular what functions are to procedural code: reusable, modular, and composable units that make up an entire application.

#### Task 5: Use the Component in the App

Now that you have a new component, include it in the main application template. Open `src/app/app.component.html` and replace its content:

```html
<h1>Minimal Angular App</h1>
<app-hello-world></app-hello-world>
```

This uses the custom element `<app-hello-world>`, which is defined by the selector property in `hello-world.component.ts`.

Next, edit `src/app/hello-world/hello-world.component.html` to personalize it:

```html
<p>Hello from the HelloWorld Component!</p>
```

When you save these changes, Angular’s development server will auto-reload and show the new output in your browser. This step demonstrates how to integrate and modify a component within the application.

### Questions

1. What are the key files generated by `ng new` and what are their purposes?
2. What is the role of `angular.json` in an Angular CLI project?
3. How does Angular CLI assist in maintaining project structure?
4. Why is it beneficial to avoid extra tooling at the beginning?
5. Can you identify where the `app-hello-world` selector is defined?

### Advice

Working with Angular from the command line offers a purist's insight into how a large-scale web framework operates under the hood. By avoiding IDEs and focusing purely on terminal commands, you sharpen your understanding of project scaffolding, build processes, and component orchestration. Don’t be discouraged by the initial verbosity—once you grasp the CLI commands and folder structures, building larger applications becomes much more intuitive. When you’re ready to go deeper, check out our exercise sheet on [Angular Routing and Navigation](#) for your next step.

