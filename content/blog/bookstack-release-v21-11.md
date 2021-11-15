+++
categories = ["Releases"]
tags = ["Releases"]
title = "BookStack Release v21.11"
date = 2021-11-16T14:04:45Z
author = "Dan Brown"
image = "/images/blog-cover-images/autumn-road-sebastian_unrau.jpg"
slug = "bookstack-release-v21-11"
draft = false
+++

Intro

* [Update instructions](https://www.bookstackapp.com/docs/admin/updates)
* [GitHub release page](https://github.com/BookStackApp/BookStack/releases/tag/v21.11)


**Upgrade Notices**

- **Security Releases** - There were some security vulnerabilities found during the life of 
  v21.10. See the [v21.10.1](/blog/bookstack-release-v21-10-1/), [v21.10.2](/blog/bookstack-release-v21-10-2/) and
  [v21.10.3](/blog/bookstack-release-v21-10-3/) posts for more details.
- **API Changes** - As of v21.11 any dates in API responses will be formatted as per ISO-8601, with `2019-12-02T20:01:00.283041Z` reflecting an example of this format. You may need to review any of your scripts that utilise dates from API responses.
- **Upload Limit** - System file upload limits are now configured using a `FILE_UPLOAD_SIZE_LIMIT` option in your 
  `.env` file. This value is specified as an integer and represents the max upload size in MegaBytes. This defaults to 50MB. This replaces the old `window.uploadLimit` header option that could be set.
- **Search Index Changes** - As detailed below, there have been search indexing and scoring changes in v21.11. 
  It's recommended to run `php artisan bookstack:regenerate-search` to ensure a consistent search experience and take
  advantage of these changes.
- **Logout Endpoints** - Logout endpoints have now changed to be CSRF protected POST endpoints instead of GET endpoints. If you were using these for any external purposes you may now need to implement an alternative workflow.


### New Tags Overview

// TODO

### Search System Enhancements

// TODO

### Search API Endpoints

// TODO

### Framework Upgrades

// TODO

### Translations

// TODO

### Full List of Changes

**Released in v21.11**

* Added a new tag view. ([#3042](https://github.com/BookStackApp/BookStack/pull/3042), [#738](https://github.com/BookStackApp/BookStack/issues/738))
* Added a wide series of improvements to the search system, including: ([#3043](https://github.com/BookStackApp/BookStack/pull/3043), [#2840](https://github.com/BookStackApp/BookStack/issues/2840))
  * Added highlighting of search terms in search results. ([#1891](https://github.com/BookStackApp/BookStack/issues/1891), [#997](https://github.com/BookStackApp/BookStack/issues/997))
  * Added matching of tag names and values through normal search terms. ([#1577](https://github.com/BookStackApp/BookStack/issues/1577))
* Added search API endpoints. ([#909](https://github.com/BookStackApp/BookStack/issues/909))
* Added new `.env` option to limit file uploads. ([#3033](https://github.com/BookStackApp/BookStack/issues/3033))
* Updated the used Laravel framework from version 6 to version 8. Thanks to @laravel-shift for accelerating this. ([#3012](https://github.com/BookStackApp/BookStack/pull/3012), [#3011](https://github.com/BookStackApp/BookStack/pull/3011))
* Implemented initial use of static analysis for PHP code. ([#3039](https://github.com/BookStackApp/BookStack/pull/3039))
* Updated Slack and Facebook logos to be current. Thanks to [@na3shkw](https://github.com/BookStackApp/BookStack/pull/3032). ([#3032](https://github.com/BookStackApp/BookStack/pull/3032))
* Updated user invite/email-confirmation journeys to help prevent potential malicious user manipulation. Thanks again to @haxatron for reporting.  ([#3050](https://github.com/BookStackApp/BookStack/issues/3050))
* Updated logout endpoints to be POST to prevent potential CSRF concerns. Thanks to @hdvinnie for reporting. ([#3047](https://github.com/BookStackApp/BookStack/issues/3047))
* Updated page include system to retain the `pre` tags when including a code block. ([#2406](https://github.com/BookStackApp/BookStack/issues/2406))
* Updated translations with latest changes from Crowdin. ([#3040](https://github.com/BookStackApp/BookStack/pull/3040))
* Fixed issue where using the back button in the page editor could lead you to the same page. ([#2834](https://github.com/BookStackApp/BookStack/issues/2834))
* Fixed issue where setting new search filters could remove existing created_by & updated_by filters. ([#2736](https://github.com/BookStackApp/BookStack/issues/2736))
* Fixed issue where markdown draft pages could convert to HTML. ([#3054](https://github.com/BookStackApp/BookStack/issues/3054))
* Fixed issue where "Skip to content" link could be visible on print views. ([#3051](https://github.com/BookStackApp/BookStack/issues/3051))

**Released in v21.10.1 through v21.10.3**

* Fixed image upload vulnerability. Thanks to @haxatron ([#3010](https://github.com/BookStackApp/BookStack/issues/3010))
* Fixed capitalization for Estonian language option. Thanks to [@IndrekHaav](https://github.com/BookStackApp/BookStack/pull/3008). ([#3008](https://github.com/BookStackApp/BookStack/pull/3008))
* Updated PHP packages to prevent abandoned warning. ([#3007](https://github.com/BookStackApp/BookStack/issues/3007))
* Updated translations with latest changes from Crowdin. ([#3006](https://github.com/BookStackApp/BookStack/pull/3006), [#3023](https://github.com/BookStackApp/BookStack/pull/3023), [#3014](https://github.com/BookStackApp/BookStack/pull/3014))
* Made further fixes to address image upload vulnerability. Thanks again to @haxatron ([#3019](https://github.com/BookStackApp/BookStack/issues/3019))
* Updated AzureAD login library to work with the new Microsoft Graph API. ([#3028](https://github.com/BookStackApp/BookStack/issues/3028))
* Fixed path image file path traversal vulnerability. Thanks @theworstcomrade for reporting. ([#3030](https://github.com/BookStackApp/BookStack/issues/3030))
* Prevented HTML attachments being served inline. Thanks @theworstcomrade for reporting. ([#3027](https://github.com/BookStackApp/BookStack/issues/3027))

### Next Steps

// TODO

----

<span style="font-size: 0.8em;opacity:0.9;">Header Image Credits: <span>Photo by <a href="https://unsplash.com/@sebastian_unrau?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Sebastian Unrau</a> on <a href="https://unsplash.com/?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span></span>