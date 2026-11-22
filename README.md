# WordPress fixture for the Wodby 1 migration E2E

A plain WordPress site whose code is deployed from Git on Wodby 1. The Wodby 1 to Wodby 2 migration end-to-end test
migrates it and builds the same repository on Wodby 2.

- `web/` is the web root and holds WordPress core, committed as released by wordpress.org. Set the app's docroot to
  `web` on Wodby 1; it is the Wodby 2 WordPress default.
- `wp-config.php` is not committed: both platforms write it on container start.
- `web/e2e-wodby1-fixture.html` lets the test check that the migrated site was built from this repository.
- `.wodby/pipeline.yml` builds and deploys it with Wodby CI on Wodby 2. WordPress core is committed, so it has no
  Composer step.

Keep the content stable: the test depends on it.
