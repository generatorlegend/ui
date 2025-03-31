# Migration Guide

This guide provides instructions for migrating your project to the latest version of our component library. It covers breaking changes, new features, and step-by-step instructions for updating existing projects.

## Table of Contents

1. [Introduction](#introduction)
2. [Breaking Changes](#breaking-changes)
3. [New Features](#new-features)
4. [Migration Steps](#migration-steps)
5. [Icon Library Migration](#icon-library-migration)
6. [Troubleshooting](#troubleshooting)

## Introduction

Our component library is constantly evolving to provide better features and performance. This guide will help you update your project to the latest version smoothly.

## Breaking Changes

- (List any breaking changes here)

## New Features

- Icon library migration support

## Migration Steps

1. Update your `package.json` to use the latest version of our component library.
2. Run `npm install` or `yarn install` to update the dependencies.
3. Review the breaking changes section and update your code accordingly.
4. Run the migration command to apply any necessary changes:

```bash
npx shadcn migrate
```

5. Follow any additional instructions provided by the migration tool.

## Icon Library Migration

We've introduced a new feature to migrate your UI components to a different icon library. This can be especially useful if you want to switch to a more performant or feature-rich icon set.

To migrate your icons:

1. Ensure you're in the root directory of your project.
2. Run the following command:

```bash
npx shadcn migrate icons
```

3. The migration tool will analyze your `components.json` file and update your components to use the new icon library.

If you want to see a list of available migrations, you can use the `--list` option:

```bash
npx shadcn migrate --list
```

## Troubleshooting

If you encounter any issues during the migration process, here are some common problems and their solutions:

### Missing components.json file

If you see an error message like "No `components.json` file found," make sure you're running the migration command from the root of your project where the `components.json` file is located.

### Invalid migration specified

If you receive an error about an invalid migration, make sure you're using one of the available migration options. You can see the list of available migrations by running:

```bash
npx shadcn migrate --list
```

### Other issues

If you encounter any other problems during the migration process, please check our GitHub issues or open a new issue with details about the error you're experiencing.

Remember to always backup your project before performing any migration to ensure you can revert changes if necessary.