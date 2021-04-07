---
layout: page
title: About
permalink: /about/
---

### About

On this site you will find links to various in-progress TEI-encoded Pipe Rolls of the Bishopric of Winchester. In these documents, you will notice that there are currently three main thrusts of encoding for textual enrichment. The first is that of geographic locations, the second is a nascent personography, and the final is an ongoing index of labor roles or "occupations" where stated in reference to a person. Future directions will also begin to categorize agricultural products, labor values, and more. This project is a work in progress and a proof of concept.

#### A note about place names
Where identified, named places are linked with the `<placeName>` attribute tag and linked to the [List of Places](https://github.com/comp-methods-fsu-2021/hunter_winchesterrolls/blob/736b796d9b08ac7cea0a8f71986aba94ea3f0d78/XML%20docs/Places.xml), which acts as an authority file. This document provides additional context for the referenced placenames, including a modernized spelling and link to a stable source of information about that place. In some instances, this information source is the [Open Domesday project](https://opendomesday.org/) maintained by Anna Powell-Smith. In the case of placenames that are shared by multiple locations, geographic locations and boroughs are corroberated within the index of the cited textual edition. For instance, the placename "Falaleia" could refer to either Fawley, Buckinghampshire or Fawley, Hampshire, both of which have individual records in Open Doomsday's gazetteer. Holt, 1964 provides an Index of Places, however, that specifies that Falaleia refers to Fawley, Hampshire. (See [Backmatter](https://github.com/comp-methods-fsu-2021/hunter_winchesterrolls/blob/master/1208-1209_Holt/1208-1209_Holt_c_backmatter.txt)). Where no match in the Open Doomsday gazetteer can be found, a link to the location's modern Wikipedia page is substituted. Where no location match is found at all (or in cases where no confident match can be made between a historical place and a modern Wikipedia entry), no link is provided. In all instances, though, the place name is still included in the authority file. This file will be updated with additional information and corrections to proper place names when necessary.

#### A note about person names
Where possible, named individuals are identified with a `<persName>` tag. Entries for named individuals that appear multiple times througout the text, especially those listed in some form of official capacity such as reeves, include a tag attribute to link their appearances together and are compiled in the [Personography](https://github.com/comp-methods-fsu-2021/hunter_winchesterrolls/blob/736b796d9b08ac7cea0a8f71986aba94ea3f0d78/XML%20docs/People.xml), which acts as an authority file. This file provides a  tag links to a personography index in the frontmatter head of the document. Those that are identifiable on stable web reference databases such as Wikipedia or Wikidata are also linked to that source. If there are no stable sources of biographical information, no link is made.

#### A note about occupations
When referenced in relation to a person, Latin names for professions or occupations are ascribed the `<term>` tag and attributed with one of a set of markers that correspond to that occupation. The occupation attribute tags are displayed at the beginning of the document in the frontmatter head of the document.

#### File structure
The files included in the "XML Rolls" page are divided along the lines above. Firstly, encoded text of the rolls themselves are linked to via their year.