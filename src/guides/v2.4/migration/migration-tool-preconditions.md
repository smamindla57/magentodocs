---
group: migration-guide
subgroup: C_DMTool
title: Preconditions
menu_title: Preconditions
menu_node:
menu_order: 1
functional_areas:
  - Tools
migrated_to: https://experienceleague.adobe.com/docs/commerce-operations/tools/data-migration/basics/prerequisites.html
layout: migrated
---

Before starting migration, make sure the following requirements are met.

## Magento 2 system

*  Set up your Magento 2 system so that it meets the [system requirements]({{ page.baseurl }}/install-gde/system-requirements.html).

   Use a topology and design that at least matches your existing Magento 1 system.

*  [Install Magento 2]({{ page.baseurl }}/install-gde/bk-install-guide.html).

## Cron

Do not start Magento 2 cron jobs.

## Database

*  After installation, back up or [dump](https://dev.mysql.com/doc/refman/5.1/en/mysqldump.html) your Magento 2 database as soon as possible. This allows you to restore the initial database state if migration is not successful.

*  Verify if the Data Migration Tool has network access to connect the Magento 1 and Magento 2 databases.

   Open ports in your firewall so that the Migration Tool can communicate with the databases.

*  Make sure your MySQL accounts have all the necessary privileges to access Magento databases.

  If Binary Logging is enabled for your Magento 1 database, set the global [`log_bin_trust_function_creators`](https://dev.mysql.com/doc/refman/5.7/en/server-system-variables.html#sysvar_log_bin_trust_function_creators) MySQL system variable to `1`, or grant the [SUPER privilege](https://dev.mysql.com/doc/refman/5.7/en/privileges-provided.html#priv_super) to your account.

*  We do not recommend creating new entities (products, categories, attributes, etc.) in your Magento 2 store before migration because the Data Migration Tool overwrites such new entities with the old ones from Magento 1.

## Extensions

Migrate Magento 1 extension code to Magento 2.

To find the latest extensions versions, visit [Commerce Marketplace](https://marketplace.magento.com/) or contact your extension provider.

You can also use the Magento [Code Migration Tool](https://github.com/magento/code-migration/blob/develop/README.md).

{:.ref-header}
Related topics

*  [Install the Data Migration Tool]({{ page.baseurl }}/migration/migration-tool-install.html)
