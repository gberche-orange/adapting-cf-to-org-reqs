# adapting-cf-to-org-reqs
Impact maps for cfsummit 2015 talk ["How to adapt cf to org specific requirements"](http://cfsummit2015.sched.org/event/4ae1613af9d05e6f84ead3bcdab8ee30?iframe=no#.VT-5_uHTK8g)

To read it, use http://mindmup.com with this permalink https://www.mindmup.com/#m:h1gberche-orange/adapting-cf-to-org-reqs:master:/Adapting%20CF%20to%20organizations.mup Mind mup github add-on will ask you to grant OAuth permissions to your github repos, but won't actually use that unless you choose to save a map into one of your repos. Alternatively, you can save this json file to your local computer disk, and use File-> Open/Import -> From a local drive

Alternatively, enable github extension in the extension menu, and then open/import -> from github specifying this repo, or one of your clone.

Then use the keyboard to expand the collapsed nodes ( '/' slash or arrows keys)

Please send PR for sharing your own impact map

# BOF notes: potential useful CF extension for orgs specific reqs ?

Participants: Carlo Ferrris, William , Johantan Regehr, Guillaume Berche

use-cases:
* PCI-DSS compliance: ensure prod anti affinity (host, VM) with non-prod application.
* dev / prod segmentation
 * app network segmentation
 * log consolidation with different archiving policies
 * other meta-data
   * ops entity
   * app code name
   * ops on call contacts/ids
   * app version
   * cost-center (charge back)


Solutions:
* meta-data in the app logs, then used by the log consolidation
* dynamically assigned syslog port
* set env vars 
 * to the app as meta-data with specific naming "env-type=dev"
 * to the space as env-var-groups 
* org-level billing/ chargeback support ??

Potential useful CF extension for orgs specific reqs!
* Support for meta-data in the core platform: for most entities
  * export meta-data in loggregator in templates
  * pluggeable interceptor to the CC API to act upon the provided meta-data
    * on meta-data "env-type=prod", assign automatically a specific placement constraint "label=dev" and specific securuty groups (allow only outgoing traffic to dev network)
* How can diego ssh access preserve container instances immutability ? An Lock/unlock mechanism
* How can I have progressive CF release updates that affect only parts of my cf apps ? (e.g. 209 applies to non production apps)
  * Tie in placement constraints ("non-prod" label) assigned to some DEAS, and bosh deploy initial canaries targetting those labels


