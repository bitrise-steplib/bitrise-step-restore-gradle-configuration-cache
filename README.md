# Restore Gradle configuration cache

[![Step changelog](https://shields.io/github/v/release/bitrise-steplib/bitrise-step-restore-gradle-configuration-cache?include_prereleases&label=changelog&color=blueviolet)](https://github.com/bitrise-steplib/bitrise-step-restore-gradle-configuration-cache/releases)

Restores the Gradle configuration cache folder used by Gradle. Uses the Bitrise Build Cache infrastructure.

<details>
<summary>Description</summary>

This step restores the Gradle configuration cache folder from the Bitrise Build Cache to speed up future builds.

For more information on how configuration caching works, refer to the [Gradle user guide](https://docs.gradle.org/current/userguide/configuration_cache.html).

**IMPORTANT NOTES:**
- You must have an active Bitrise Build Cache Trial or Subscription for your workspace to use this step.
- You also need to set up the encryption key `GRADLE_ENCRYPTION_KEY` in Bitrise Secrets by using the result from running `openssl rand -base64 16`.
- Setting the encryption key is supported only from Gradle version 8.6 onwards, so your project must be using Gradle 8.6 or higher.

</details>

## 🧩 Get started

Add this step directly to your workflow in the [Bitrise Workflow Editor](https://docs.bitrise.io/en/bitrise-ci/workflows-and-pipelines/steps/adding-steps-to-a-workflow.html).

You can also run this step directly with [Bitrise CLI](https://github.com/bitrise-io/bitrise).

## ⚙️ Configuration

<details>
<summary>Inputs</summary>

| Key | Description | Flags | Default |
| --- | --- | --- | --- |
| `key_override` | Custom override key used to restore the cache from a previously saved entry (by the `Save Gradle configuration cache` step).  If not specified, by default a key is generated from the app slug and the current branch. If not specified, the contents can also be restored from a fallback key consisting only of the app slug. This helps reduce cache misses on new feature branches. |  |  |
| `verbose` | Enable logging additional information for troubleshooting | required | `false` |
</details>

<details>
<summary>Outputs</summary>
There are no outputs defined in this step
</details>

## 🙋 Contributing

We welcome [pull requests](https://github.com/bitrise-steplib/bitrise-step-restore-gradle-configuration-cache/pulls) and [issues](https://github.com/bitrise-steplib/bitrise-step-restore-gradle-configuration-cache/issues) against this repository.

For pull requests, work on your changes in a forked repository and use the Bitrise CLI to [run step tests locally](https://docs.bitrise.io/en/bitrise-ci/bitrise-cli/running-your-first-local-build-with-the-cli.html).

Learn more about developing steps:

- [Create your own step](https://docs.bitrise.io/en/bitrise-ci/workflows-and-pipelines/developing-your-own-bitrise-step/developing-a-new-step.html)
