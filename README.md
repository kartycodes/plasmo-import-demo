# Demo of Server Restart Behavior

This repo is a minimal reproducible example of a behavior that I'm observing in the Plasmo browser extension framework.  I'm not sure if its expected behavior or not.

## Background

1. There are two npm workspaces in this repo
  1. apps, which contains the plasmo extension
  1. packages, which contains a single package called components
1. In the components package there is an exported function called `exportedFunction`
1. In the extension, popup.tsx, there is some code that imports this function

## Desired / Actual Behavior:

### Follow these steps:

1. Make a change in `packages/components/index.ts` 
  1. e.g. add a new function, and export it
1. Make a change in `apps/demo-extension/popup.tsx` that takes advantage of this change and save the file.

### Desired Behavior:
1. When plasmo rebuilds the extension, it picks up the changes in the components package

### Actual Behavior:
1. When plasmo rebuilds the extension, the changes are not picked up.
1. Restart the dev server
1. The changes are now visible