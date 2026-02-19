1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Deploying websites and apps](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps)
4.  Blocks

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 22 January 2026

Blocks are fully self-contained apps or services – packaged with all dependencies. This means your code runs exactly the same in production as it does locally, and you can use any language or framework. This guide explains how to set up continuous integration (CI) pipelines to push Blocks automatically, which is our recommended deployment approach.

## Deploying Blocks automatically using GitHub and GitLab

### GitHub workflow example

yaml

```
// GitHub WorkFlow

  env:
    REGISTRY: ghcr.io
    APP_IMAGE: ghcr.io/${{ github.repository }}/${{ github.ref_name }}/app
    CONTENSIS_CLIENT_ID: XXX-XXX
    CONTENSIS_SHARED_SECRET: XXX-XXX-XXX-XXX

  deploy:
    name: Push block to Contensis
    permissions:
      contents: read
      packages: write
    runs-on: ubuntu-latest
    needs: build-latest
    steps:
      - name: Push block to Contensis
        id: push-block
        uses: contensis/block-push@v1
        with:
          block-id: my-awesome-website
          alias: demo
          project-id: website
          client-id: ${{ env.CONTENSIS_CLIENT_ID }}
          shared-secret: ${{ env.CONTENSIS_SHARED_SECRET }}
          image-uri: ${{ env.APP_IMAGE }}:build-${{ github.run_number }}
```

#### GitHub CI variables

You’ll need to configure a couple of API keys for the GitHub CI pipeline:

-   **CONTENSIS\_CLIENT\_ID** and **CONTENSIS\_SHARED\_SECRET**  
    These are generated in the CMS and should be linked to a Role with permission to push Blocks. You might name them something like “GitHub Push Block API Key”.

For **private repositories**, you can store these under the `env` section in your `build.yml` file.  
For **public repositories**, store them securely in your GitHub repository’s **Actions > Secrets and variables** section.

### GitLab workflow example

yaml

```
# GitLab Workflow

# Include the workflow pipelines
include:
  - 'https://gitlab.zengenti.com/ops/contensis-ci/-/raw/main/push-block.yml'
  - 'https://gitlab.zengenti.com/ops/contensis-ci/-/raw/main/release-block.yml'

stages:
  ...
  - push-block

variables:
  ...
  APP_IMAGE: '$CI_REGISTRY_IMAGE/$CI_COMMIT_REF_SLUG/app'

push-to-contensis:
  stage: push-block
  variables:
    alias: demo
    project_id: website
    block_id: my-awesome-website
    image_uri: $APP_IMAGE:build-$CI_PIPELINE_IID
    release: 'false' # Whether to release the block upon successful push
    tag_repo: 'true' # Whether to push a tag to the git repo upon successful block push (git_token is required if this is 'true'). Defaults to false.
    # First create a Project Access Token e.g Tag block version (access: api, read_repository) and copy it
    # Then create a CI/CD Variable called GITLAB_ACCESS_TOKEN and paste the token
    git_token: $GITLAB_ACCESS_TOKEN
    client_id: $CONTENSIS_CLIENT_ID
    shared_secret: $CONTENSIS_SHARED_SECRET


release-contensis-block:
  stage: release-block
  variables:
    alias: demo
    project_id: website
    block_id: my-awesome-website
    client_id: $CONTENSIS_CLIENT_ID
    shared_secret: $CONTENSIS_SHARED_SECRE
```

### GitLab CI variables

You’ll need to set up a few API keys for the GitLab CI pipeline:

-   **CONTENSIS\_CLIENT\_ID** and **CONTENSIS\_SHARED\_SECRET**:  
    These are generated from within the CMS and should be tied to a Role with permission to push Blocks. You might label them something like “GitLab Push Block API Key”.
-   **GITLAB\_ACCESS\_TOKEN**:  
    Create this in GitLab under **Settings > Access Tokens**. Make sure to give it the `api` and `read_repository` scopes.

All of these keys should be stored as GitLab CI variables. **Make sure the variable names exactly match what's used in your YAML file** – if they don’t, the pipeline will fail.

### Manual

If necessary, you can push manually using the [Contensis CLI](https://www.npmjs.com/package/contensis-cli). Make sure your account is a System Administrator or has the Block CI role.

#### Example command (using the Contensis CLI):

Shell

```
push block 
my-awesome-website
ghcr.io/contensis/demo/main/app:build-123
main
 --release
 --commit-id 123abc
 --commit-message "initial commit"
 --commit-datetime 2025-01-01T09:00
 --author-email j.doe@zengenti.com
 --committer-email j.doe@zengenti.com
 --repository-url https://github.com/contensis/leif-demo
 --provider GitHub
```

Use `push block --help` or check the [Contensis CLI documentation](https://github.com/contensis/cli/blob/main/packages/contensis-cli/README.md#get-block-logs) for more information.

---

## The `manifest.json` file

Check out our [advanced guide](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps/blocks/blocks-advanced-configuration) for a deep dive into the manifest.json file. Learn how to include it in your Docker image, configure ports, manage routing behaviour, and handle static assets.

---

## Targeting specific Block versions

Use query strings, headers, or cookies to target specific block versions.

The `x-block-config` cookie will be set, and a redirect will strip out the original query params.

For example:

JavaScript

```
https://www.website.com?block-a-block-branch=develop&block-a-block-versiono=3
```

Becomes:

JavaScript

```
https://www.website.com (with x-block-config cookie set)
```

---

## Troubleshooting Blocks

If you are having issues with a Block:

-   Check the necessary [renderers](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps/renderers/renderers-overview) are set up in Site View or Content Types.
-   Ensure a Site View node exists for each static path.
-   [Check the console logs](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps/blocks/view-the-console-logs-for-a-block) for the Block version that's failing. Make sure you check all three data centres.
-   Pull and run the Docker image locally and debug any errors.
-   Getting 500s? Make sure:
    
    -   `manifest.json` exists in the image
    -   `enableFullUriRouting` is `true` for Contensis React Base or Node.js/Express projects