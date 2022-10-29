---
layout: default
title: about
date: 2022-10-29 17:21:59 -0500
---

# about me

i'm esmé cowles and my day job is being an it manager at [princeton university
library](https://library.princeton.edu/).

orcid: <https://orcid.org/0000-0001-7074-1152>


## current projects

### princeton university library it

supervising three development teams at princeton, who develop and maintain our
digital library, discovery, and digital scholarship applications. some of our key
applications:
* [orangelight](https://github.com/pulibrary/orangelight/) / blacklight catalog / <https://catalog.princeton.edu/>
* [pulfalight](https://github.com/pulibrary/pulfalight/) / arclight-based finding aids / <https://findingaids.princeton.edu/>
* [pulmap](https://github.com/pulibrary/pulmap/) / geoblacklight maps portal / <https://maps.princeton.edu/>
* [dpul](https://github.com/pulibrary/dpul/) / (digital pul) spotlight exhibits / <https://dpul.princeton.edu/>
* [figgy](https://github.com/pulibrary/figgy/) / [valkyrie](https://github.com/samvera/valkyrie/)-based repository, a rewrite of [plum](https://github.com/pulibrary/plum)
* princeton data commons (pdc)
   * [pdc discovery](https://github.com/pulibrary/pdc_discovery/) / research data discovery portal / <https://datacommons.princeton.edu/discovery/>
   * [pdc describe](https://github.com/pulibrary/pdc_describe/) / research data ingest platform, launching in late 2022 or early 2023

### samvera
chair-elect of the [samvera](https://samvera.atlassian.net/wiki/spaces/samvera/overview) board, focusing on the long-term sustainability of the samvera software and community.


## older projects

### samvera/valkyrie
participating in <a href="https://samvera.atlassian.net/wiki/spaces/samvera/overview">samvera</a> governannce and development, focusing on <a href="https://github.com/samvera/valkyrie">valkyrie</a>.

### application development team / digital repository and discovery services
managing the application development team at <a href="http://library.princeton.edu/">princeton university library</a>, working on our samvera/blacklight/spotlight/geoblacklight applications.

### digital cicognara
the <a href="http://cicognara.org/">digital cicognara library</a>, a digital reconstruction of a foundational art history library using blacklight and iiif, in partnership with preeminent libraries across the us and europe.

### fedora api specification
editor of the <a href="https://fedora.info/spec/">fedora api specification</a>, an effort to codify the <a href="http://fedorarepository.org/">fedora</a> rest api, align more closely with existing web standards, and allow for multiple implementations to serve different needs.

### pcdm implementation
implementing pcdm in the <a href="https://github.com/samvera/hydra-pcdm/">hydra::pcdm</a>/<a href="https://github.com/samvera/hydra-works/">hydra::works</a>/<a href="https://github.com/samvera/hyrax/">hyrax</a> stack, and pul's implementation, <a href="https://github.com/pulibrary/plum">plum</a>.

### pcdm and metadata working group
presenting on <a href="https://github.com/duraspace/pcdm/wiki">pcdm</a> and <a href="https://wiki.duraspace.org/display/hydra/Hydra+Metadata+Working+Group">metadata working group</a> progress.  promoting interoperability in <a href="https://wiki.duraspace.org/display/samvera/Rights+Metadata+Recommendation">rights</a> and <a href="https://wiki.duraspace.org/display/hydra/Technical+Metadata+Application+Profile">technical</a> metadata, and with <a href="http://iiif.io">iiif</a>.

### fedora 4
participating in <a href="https://wiki.duraspace.org/display/FF/Fedora+Repository+Home">fedora 4</a> sprints, focusing on triplestore support, clustering, large file support, and performance testing.  presenting on the <a href="http://www.slideshare.net/escowles/fedora-4-the-incredible-shrinking-repository-code4lib-2014-32759717">current status of fedora 4</a> at <a href="http://code4lib.org/conference/2014/">code4lib 2014</a>.

### archivesspace technical advisory group
serving on the <a href="http://archivesspace.org">archivesspace</a> technical advisory group.

### vra core oversight committee
serving on the <a href="http://vraweb.org/about/committees/vra-core-oversight/">vra core oversight committee</a>, promoting development of the <a href="https://github.com/mixterj/VRA-RDF-Project">vra rdf vocabulary</a>.

### dams development
maintaining the current version of the ucsd library's dams repository, which combines <a href="http://www.w3.org/RDF">rdf</a> metadata implementing <a href="https://github.com/ucsdlib/dams/tree/master/ontology">our custom ontology</a> and massive file storage with flexible retrieval based on <a href="http://projectblacklight.org">blacklight</a>/ <a href="http://lucene.apache.org/solr/">solr</a>.  current focus is on developing a <a href="http://projecthydra.org/">hydra</a> front-end (<a href="http://library.ucsd.edu/dc/">dams pas</a>, <a href="http://github.com/ucsdlib/damspas">source code</a>) and implementing the <a href="http://fedora-commons.org/">fedora</a> 3 rest api FOR hydra compatability.

### rci data curation
member of the <a href="http://rci.ucsd.edu/services/data-curation.html">rci data curation team</a>, focusing on adapting the dams platform to meet the needs of diverse research data.

### triplestore research
installing, implenting xdre support for, and testing various triplestores, including <a href="http://agraph.franz.com/allegrograph/">allegrograph</a>, <a href="http://www.openrdf.org/">sesame</a>, <a href="http://www.mulgara.org/">mulgara</a>, <a href="http://jena.sourceforge.net/">jena</a>, <a href="http://4store.org/">4store</a>.  implemented custom triplestore in a relational database to address lack of solid production transaction support.

### development environment
maintaining the it department's development environment, porting legacy applications to the new environment, and standardizing features for management (subversion, access control, versioning, monitoring, logging, etc.) across all of the applications currently being developed or maintained.  helping developers, troubleshooting problems, researching new tech, etc.


## really old projects
most of this stuff isn't available any more or has been completely replaced by a different solution.

### ucai
grant-funded project to convert six sets of metadata into a common format and machine-identify duplicates and hierarchical relationships.  <em>discontinued 2006, <a href="http://web.archive.org/web/20110109053622/http://gort.ucsd.edu/ucai/">archived website</a>.</em>

### sage
the centerpiece of the libraries' website, a searchable and browseable database of electronic resources.  now labelled "selected e-resources".  uses java servlets to interface to an oracle database (with <a href="http://www.oracle.com/technology/products/text/index.html">oracletext</a> searching), and xsl for display.  <em>retired 2011, replaced by sfx and libguides.</em>

### rogersync
synchronization between library system (via xml interface) and relational database. <em>retired 2011.</em>

### library hours
application to allow different library locations to maintain a calendar to let users know what's open when. <em>retired 2010, replaced by cms-based hours site.</em>

### xml databases
for the storage element of ucai, using an xml database for a sizeable (roughly 1.2 million documents, totalling around 5 gb) database.  looked at <a href="http://www.softwareag.com/tamino/">tamino</a>, <a href="http://www.teratext.com/">teratext</a>, <a href="http://xml.apache.org/xindice/">xindice</a>, and <a href="http://www.oracle.com/database/berkeley-db/index.html">db xml</a>.  eventually went with a directory structure of xml files and used <a href="http://lucene.apache.org/">lucene</a> for querying.

### e-reserves
<a href="http://www.docutek.com/products/eres/index.html">docutek e-res</a> electronic reserves system.

### compass
heavily-customized netscape compass search engine to search both local content (sage) and related pages spidered from external websites.

### infopath
server-side javascript and perl cgi pages for main [ucsd website](https://www.ucsd.edu/).  now replaced by vignette cms.

### campus map
perl cgi campus map application, using image tiles and flat files.  now replaced by a <a href="http://maps.ucsd.edu/">new version</a>, <a href="http://web.archive.org/web/20020210143040/http://www.ucsd.edu/map/">archived website</a>.

### logserver
perl cgi to filter/subset webserver logs, integrated with web-based and command-line report-generation tools to create custom reports.  replaced by monthly pre-generated <a href="http://awstats.sourceforge.net">awstats</a> reports for each site.

### pcasso
tech support, documentation, and sysadmin for research project.  due to the sensitive nature of the content (medical records), involved working with some exotic tech: b2 dg/ux and trusted oracle 7.
