# Setting Up Husky with Commitlint: A Comprehensive Guide

[Husky](https://typicode.github.io/husky/) is a powerful tool for managing Git hooks, and when combined with Commitlint, it helps maintain consistent commit message standards in your projects. In this guide, we'll walk you through the process of setting up Husky and Commitlint for your project.

## Setting Up Husky

Getting started with Husky is straightforward, and the official [getting-started guide](https://typicode.github.io/husky/getting-started.html) provides detailed information on this. Here, we'll cover the basics.

### Automatic Installation

The quickest way to initialize your project with Husky is to use `husky-init`. Depending on your package manager, use one of the following commands:

-   For `npm`:

    ```bash
    npx husky-init && npm install
    ```

-   For `pnpm`:

    ```bash
    pnpm dlx husky-init && pnpm install
    ```

-   For `yarn` (Yarn 2+):
    ```bash
    yarn dlx husky-init --yarn2 && yarn
    ```

After running the appropriate command, Husky will:

-   Add a `prepare` script to your `package.json`.
-   Create a sample `pre-commit` hook that you can customize (by default, it runs `npm test` when you commit).
-   Configure the Git hooks path.

### Manual Setup

If you prefer a manual setup, follow these steps:

1. Install Husky as a development dependency:

    ```bash
    # Install Husky v6
    npm install husky --save-dev
    # or
    pnpm add husky --save-dev
    # or
    yarn add husky --save-dev
    ```

2. Enable Git Hooks:

    ```bash
    npx husky install
    ```

3. To automatically enable Git hooks after installing, edit your `package.json` to include the following:
    ```json
    {
    	"scripts": {
    		"prepare": "husky install"
    	}
    }
    ```

> **INFO** \
> For Yarn 2+, Husky needs to be installed differently due to the lack of support for the `prepare` lifecycle script. This does not apply to Yarn 1. Refer to Yarn 2+ documentation for installation details.

## Setting Up Commitlint

Now that you have Husky in place, let's configure Commitlint. Commitlint ensures that your commit messages follow a conventional format.

### Installing Dependencies

Before configuring Commitlint, install the necessary devDependencies:

```bash
# Install Commitlint dependencies
npm install --save-dev @commitlint/config-conventional @commitlint/cli
# or
pnpm add --save-dev @commitlint/config-conventional @commitlint/cli
# or
yarn add --save-dev @commitlint/config-conventional @commitlint/cli
```

### Creating a Configuration File

Create a configuration file for Commitlint with the following command:

```bash
# Configure Commitlint to use the conventional config
echo "module.exports = { extends: ['@commitlint/config-conventional'] };" > commitlint.config.js
```

Alternatively, you can define the configuration in a `.commitlintrc.js`, `.commitlintrc`, `.commitlintrc.json`, `.commitlintrc.yml` file, or include a `commitlint` field in your `package.json`.

### Adding the commit-msg Hook

To integrate Commitlint with Husky's `commit-msg` hook, use this command:

```bash
npx husky add .husky/commit-msg 'npx --no -- commitlint --edit ${1}'
```

With Husky and Commitlint set up, your project is now equipped to enforce consistent commit message standards. This comprehensive guide should help you get started seamlessly.
