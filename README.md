# adapting-cf-to-org-reqs
Impact maps for cfsummit 2015 talk ["How to adapt cf to org specific requirements"](http://cfsummit2015.sched.org/event/4ae1613af9d05e6f84ead3bcdab8ee30?iframe=no#.VT-5_uHTK8g)

To read it, use http://mindmup.com with this permalink https://www.mindmup.com/#m:h1gberche-orange/adapting-cf-to-org-reqs:master:/Adapting%20CF%20to%20organizations.mup 

Alternatively, enable github extension in the extension menu, and then open/import -> from github specifying this repo, or one of your clone.

Please send PR for sharing your own impact map

# BOF notes: potential useful CF extension for orgs specific reqs ?

Participants: Alberto, William, 

use-cases:
* PCI-DSS compliance: ensure prod anti affinity (host, VM) with non-prod application.
* 

* Support for meta-data in the core platform:
  * export meta-data in loggregator in templates
  * pluggeable interceptor to the CC API to act upon the provided meta-data
    * on meta-data "env-type=prod", assign automatically a specific placement constraint "label=dev" and specific securuty groups (allow only outgoing traffic to dev network)
* How can diego ssh access preserve container instances immutability ? An Lock/unlock mechanism
* How can I have progressive CF release updates that affect only parts of my cf apps ? (e.g. 209 applies to non production apps)
  * Tie in placement constraints ("non-prod" label) assigned to some DEAS, and bosh deploy initial canaries targetting those labels


