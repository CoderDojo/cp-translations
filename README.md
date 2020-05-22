# cp-translations

Translations for the CoderDojo Community Platform

## Deployment

This repo self-publish on commit. Please update the repos depending on it after it has been published when necessary.
This easiest way to see if that string is used is to `git grep translation_key` into each of the repos.

### Repos

- cp-dojos-service (email only)
- cp-events-service (email only)
- cp-users-service (email only)
- cp-zen-platform (angular front-end)
- cp-zen-frontend (vuejs front-end)

## Trigger a Build

To trigger a build of the translations without a new commit (e.g. to include new community translations)

Generate a circle api token from the [account/api page](https://circleci.com/account/api)

Use the token in the following curl request:

```
curl -XPOST https://circleci.com/api/v1.1/project/github/CoderDojo/cp-translations/build\?circle-token\=[TOKEN]
```
