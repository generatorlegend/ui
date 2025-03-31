---
title: Troubleshooting FAQ
description: Frequently asked questions and common issues when working with the component library
---

# Troubleshooting FAQ

This page compiles a list of frequently asked questions and common issues you might encounter when working with our component library. We provide clear solutions and workarounds for each problem.

## Table of Contents

1. [Configuration Issues](#configuration-issues)
2. [Component Import Problems](#component-import-problems)
3. [Build Errors](#build-errors)
4. [API and Network Issues](#api-and-network-issues)

## Configuration Issues

### Q: I'm getting a "MISSING_CONFIG" error. What should I do?

This error occurs when the configuration file is not found in your project.

**Solution:** Ensure that you have created a configuration file (usually `shadcn.config.json`) in your project root. If you haven't created one yet, you can generate it using the initialization command:

```bash
npx shadcn init
```

### Q: I'm seeing a "TAILWIND_NOT_CONFIGURED" error. How do I fix it?

This error indicates that Tailwind CSS is not properly configured in your project.

**Solution:** Make sure you have Tailwind CSS installed and configured correctly. Check your `tailwind.config.js` file and ensure it's set up properly. If you're unsure, you can refer to the Tailwind CSS installation guide for your specific framework.

### Q: What does the "IMPORT_ALIAS_MISSING" error mean?

This error suggests that the import alias used in the component library is not configured in your project.

**Solution:** Add the necessary import alias to your project's configuration. For example, if you're using Next.js, you might need to add the following to your `jsconfig.json` or `tsconfig.json`:

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./*"]
    }
  }
}
```

## Component Import Problems

### Q: I'm having trouble importing components. What could be wrong?

If you're experiencing issues importing components, it could be due to a few reasons:

1. **Incorrect import path**: Double-check that you're using the correct import path for the component.
2. **Component not installed**: Ensure you've installed the component using the CLI command.
3. **Casing issues**: Make sure the component name in the import statement matches the exact casing of the component file.

**Solution:** Verify your import statement and make sure the component is installed. If issues persist, try running the installation command again:

```bash
npx shadcn add [component-name]
```

## Build Errors

### Q: I'm getting a "BUILD_MISSING_REGISTRY_FILE" error during build. How can I resolve this?

This error occurs when the registry file is missing during the build process.

**Solution:** Ensure that you have run the `init` command to generate the necessary files:

```bash
npx shadcn init
```

If the problem persists, check if the registry file exists in your project and if it has the correct content.

## API and Network Issues

### Q: I'm encountering a "COMPONENT_URL_NOT_FOUND" error. What does this mean?

This error suggests that the URL for fetching a component's data is not valid or the component doesn't exist.

**Solution:** 
1. Check your internet connection.
2. Verify that you're using the latest version of the library.
3. If the issue persists, it might be a temporary problem with the component registry. Try again later or check the project's GitHub issues for any known problems.

### Q: What do the "COMPONENT_URL_UNAUTHORIZED" or "COMPONENT_URL_FORBIDDEN" errors indicate?

These errors suggest that you don't have the necessary permissions to access the component data.

**Solution:** 
1. Ensure you're authenticated if the component requires authentication.
2. Check if you have the necessary permissions or subscription level to access the component.
3. If you believe this is an error, contact the library maintainers for support.

## Still Having Issues?

If you're encountering an error not listed here or if the provided solutions don't resolve your issue, please:

1. Check the project's GitHub issues to see if it's a known problem.
2. If it's not already reported, consider opening a new issue with details about the error and steps to reproduce it.
3. For immediate help, you can also reach out to the community on our Discord channel or discussion forums.

Remember, when reporting issues, always include:
- Your operating system
- Node.js version
- Package manager (npm, yarn, pnpm) and its version
- The exact error message or stack trace
- Steps to reproduce the issue

This information will help us assist you more effectively and potentially improve the library for all users.