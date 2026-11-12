# webstorm-vite-lit-ts template

A template project for WebStorm using Vite, lit and Typescript.

It includes the sample Writerside documents and a documentation build workflow for publishing documentation to GitHub Pages.  

## Build and publish on GitHub

The build and publish workflow is adopted from the [Writerside documentation](https://www.jetbrains.com/help/writerside/deploy-docs-to-github-pages.html).  The workfow
performs the full build-test-publish cycle.

The following changes were made to the original workflow:

<table>
    <tr>
        <th>Original workflow</th>
        <th>Modified workflow</th>
    </tr>
<tr>
<td valign="top">

```yaml
name:

on:
  push:
    branches: ["main"]
  workflow_dispatch:

env:
  INSTANCE: 'Writerside/hi'
  DOCKER_VERSION: 'latest'
```

</td>
<td valign="top">

```yaml
name: Build documentation

on:
  workflow_dispatch:

env:
  INSTANCE: 'Writerside/d'
  DOCKER_VERSION: '2026.09.0357'
```

</td>
</tr>
</table>

* A `name` was set for the workflow.


* The `push` event is disabled to prevent the workflow from running on every commit.  You can trigger the workflow manually within the GitHub UI.
This is to minimise running the workflow unnecessarily on every commit.


* `INSTANCE` was changed to the project's Writerside instance.


* `DOCKER_VERSION` was changed to the Writerside plug-in version.  Not sure this is necessary but should ensure deployed version
is more aligned to local Writerside preview versions.


The remainder of the workflow is unchanged.