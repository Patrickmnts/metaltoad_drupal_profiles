## Steps for installation manually

drush dl drupal-7.x
cd drupal-7.x-dev
cp -r ../metaltoad_drupal_profiles profiles/metaltoad
drush make profiles/metaltoad/metaltoad.make -y --no-core
# FIXME: 5.4.10 broken.
# Drush command terminated abnormally due to an unrecoverable error.
# Error: Call-time pass-by-reference has been removed in /Users/vosechu/out/play/drupal-7.x-dev/sites/all/themes/boilerplate/boilerplate.drush.inc, line 92
rm sites/all/themes/boilerplate/boilerplate.drush.inc
drush site-install --db-url="mysql://root@root:localhost:8889/drupal-test"
drush pm-disable securepages
