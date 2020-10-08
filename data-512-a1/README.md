## README

Goal: Display a data visualization of the number of page views and page counts on the English Wikipedia website, whether it be the main site, the mobile site (app and web) or total views over a period of time.

Data Sources:
Wikimedia Foundation REST API
CC-BY-SA 3.0 and GFDL licenses
[Terms of Use](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)

[Pagecounts documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
[Pagecounts endpoint](https://wikimedia.org/api/rest_v1/#!/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)
[Pageviews documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)
[Pageviews endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)


[Pagecounts API link](https://wikimedia.org/api/rest_v1/metrics/legacy/pagecounts/aggregate/{project}/{access-site}/{granularity}/{start}/{end})

[Pageviews API link](https://wikimedia.org/api/rest_v1/metrics/pageviews/aggregate/{project}/{access}/{agent}/{granularity}/{start}/{end})


Final CSV details:
* year: integer, in YYYY format
* month: integer, in MM format
* pagecount_all_views: integer, of total pagecount of desktop and mobile
* pagecount_desktop_views: integer, of desktop pagecount
* pagecount_mobile_views: integer, of mobile pagecount
* pageview_all_views: integer, of total pageview of desktop and mobile
* pageview_desktop_views: integer, of desktop pageviews
* pageview_mobile_views: integer, of mobile pageviews

Special considerations: 
* Pageview API excludes spiders and crawlers, but Pagecounts API does not
* There is one year of overlapping traffic data between the two APIs
* For data collected in Pageviews API, the mobile-app and mobile-web pageviews values are combined into pageview_mobile_views.