---
layout: page
title: Project Documentation
permalink: /documentation/
---

### The documents:
[1210-1211](https://github.com/comp-methods-fsu-2021/hunter_winchesterrolls/blob/master/XML%20docs/1210-1211.xml)

### About

On this page you will find links to the various in-progress TEI encoded Winchester Pipe Rolls. In these documents, you will notice that there are currently three main thrusts of encoding for textual enrichment. The first is that of geographic locations, the second is a nascent personography, and the final is an ongoing index of labor roles or "occupations" where stated in reference to a person.

#### A note about place names
Where identified, named places are linked with the `<placeName>` attribute tag and linked to in-document references that provide a modernized spelling and link to a stable source of information about that place. In some instances, this information source is the [Open Domesday project](https://opendomesday.org/) maintained by Anna Powell-Smith. In the case of placenames that are shared by multiple locations, geographic locations and boroughs are corroberated within the index of the cited textual edition (e.g. "Falaleia" could refer to Open Doomsday references to either Fawley, Buckinghampshire or Fawley, Hampshire. Holt, 1964 provides an Index of Places, however, that specifies that Falaleia refers to Fawley, Hampshire. (See [Backmatter](https://github.com/comp-methods-fsu-2021/hunter_winchesterrolls/blob/master/1208-1209_Holt/1208-1209_Holt_c_backmatter.txt)). Where no match in Open Doomsday can be found, a link to the location's modern Wikipedia page is substituted. Where no location match is found at all, no link is provided.

#### A note about person names
Where possible, named individuals are identified with a `<persName>` tag. Entries for named individuals that appear multiple times througout the text, especially those listed in some form of official capacity such as reeves, include a tag attribute to link their appearances together. This tag links to a personography index in the frontmatter head of the document. Those that are identifiable on stable web reference databases such as Wikipedia or Wikidata are also linked to that source. If there are no stable sources of biographical information, no link is made.

#### A note about occupations
When referenced in relation to a person, Latin names for professions or occupations are ascribed the `<term>` tag and attributed with one of a set of markers that correspond to that occupation. The occupation attribute tags are displayed at the beginning of the document in the frontmatter head of the document.

