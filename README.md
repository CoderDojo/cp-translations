# cp-translations

Translations for the CoderDojo Community Platform

Any new languages that are translated on crowdin will need adding to the [CircleCI Config](./.circleci/config.yml) in the 'Download translations' section, on this line (abbreviated):

```
for lang in it pt-PT de ...
```

## Deployment

This repo self-publish on commit. Please update the package.json file in the repos depending on it after it has been published when necessary.
This easiest way to see if that string is used is to `git grep translation_key` into each of the repos.

### Repos

- cp-dojos-service (email only)
- cp-events-service (email only)
- cp-users-service (email only)
- cp-zen-frontend (vuejs front-end)

Once these are all updated, merged and deployed, you will need to update the main repo to pull in both the updated cp-translations and cp-zen-frontend packages:

- cp-zen-platform (angular front-end)

## Trigger a Build

To trigger a build of the translations without a new commit (e.g. to include new community translations)

Generate a circle api token from the [account/api page](https://circleci.com/account/api)

Use the token in the following curl request:

```
curl -XPOST https://circleci.com/api/v1.1/project/github/CoderDojo/cp-translations/build\?circle-token\=[TOKEN]
```
