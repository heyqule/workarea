---
title: Workarea 3.1.26
excerpt: Patch release notes for Workarea 3.1.26.
---

# Workarea 3.1.26

Patch release notes for Workarea 3.1.26.

## Prevent Creation of Invalid Search Customizations

Block saving of customizations when not valid. Return error message back
to the user.

### Issues

- [ECOMMERCE-6289](https://jira.tools.weblinc.com/browse/ECOMMERCE-6289)

### Pull Requests

- [3545](https://stash.tools.weblinc.com/projects/WL/repos/workarea/pull-requests/3545/overview)

### Commits

- [e813c44888ee4dabc254d2a26122bd7136b7a8da](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/e813c44888ee4dabc254d2a26122bd7136b7a8da)


## Load Mailer Previews From Plugins and Applications

New or modified previews were not being automatically included in plugins and
host applications, resulting in custom previews not displaying. To resolve this
issue, Workarea now loads all mailer previews at the same time.

### Issues

- [ECOMMERCE-6299](https://jira.tools.weblinc.com/browse/ECOMMERCE-6299)

### Pull Requests

- [3555](https://stash.tools.weblinc.com/projects/WL/repos/workarea/pull-requests/3555/overview)

### Commits

- [c2e997500922ee7e324b00e7443cb944bf859ff2](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/c2e997500922ee7e324b00e7443cb944bf859ff2)


## Lock Orders Before Checking Inventory On Items

Prevents concurrency issues where inventory causes items to be removed
from the order while it's being placed. The `before_action :check_lock`
callback now runs _before_ `:check_inventory`, ensuring that an order's
lock status is known prior to editing it.

### Issues

- [ECOMMERCE-6300](https://jira.tools.weblinc.com/browse/ECOMMERCE-6300)

### Pull Requests

- [3558](https://stash.tools.weblinc.com/projects/WL/repos/workarea/pull-requests/3558/overview)

### Commits

- [31352139b561cc3e6d750312b7c3f6d9811b2c5c](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/31352139b561cc3e6d750312b7c3f6d9811b2c5c)
- [55c91722a6d00484ad4f2a601ab55725e750e7c4](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/55c91722a6d00484ad4f2a601ab55725e750e7c4)


## Specify JSON Format in Product List Content Block Partial

Part of a larger issue with Rails template overrides, previously this
could be caused by overriding the
`workarea/admin/catalog_products/index.html.haml` view without
overriding its corresponding `index.json.jbuilder`. The index
HTML template now includes a `format: :json` in the path so that this
cannot happen if one forgets to override a JSON template corresponding
to their HTML template.

### Issues

- [ECOMMERCE-6271](https://jira.tools.weblinc.com/browse/ECOMMERCE-6271)

### Pull Requests

- [3556](https://stash.tools.weblinc.com/projects/WL/repos/workarea/pull-requests/3556/overview)

### Commits

- [3aeeb0536e87950fb3c0c56650bec6ff36744aae](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/3aeeb0536e87950fb3c0c56650bec6ff36744aae)


## Fix Overriding SVG Icons in Style Guides

SVG icons could not be overridden in the style guides, instead, the icon
would just be appended to the end of the list, leaving the original icon
in place. Update the `#style_guide_icons` helper to ensure only 1 of each
filename exists, so icons will appear to override each other in the
style guide.

### Issues

- [ECOMMERCE-6183](https://jira.tools.weblinc.com/browse/ECOMMERCE-6183)

### Pull Requests

- [3552](https://stash.tools.weblinc.com/projects/WL/repos/workarea/pull-requests/3552/overview)

### Commits

- [b290bf9b9e33f28ea0d8a50b9f1f403a8d5fb817](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/b290bf9b9e33f28ea0d8a50b9f1f403a8d5fb817)


## Add Proper Link Class To Facet Partial Links

The facet partial links in the Result Filters UI didn't have the right
class name associated with their elements. Workarea now uses a `.result-filters__link`
class name for these elements.

### Issues

- [ECOMMERCE-6249](https://jira.tools.weblinc.com/browse/ECOMMERCE-6249)

### Pull Requests

- [3539](https://stash.tools.weblinc.com/projects/WL/repos/workarea/pull-requests/3539/overview)

### Commits

- [5f1dd9e43cf6cbfb0d16f058fe05c594468cfaaa](https://stash.tools.weblinc.com/projects/WL/repos/workarea/commits/5f1dd9e43cf6cbfb0d16f058fe05c594468cfaaa)


