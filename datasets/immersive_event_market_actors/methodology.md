## Immersive Market Participants Dataset – Methodology

### 1. Overview

The Immersive Market Participants dataset provides a curated list of key actors in the global immersive media ecosystem. It is designed to answer a practical research question:

Who are the leading companies, artists, venues, festivals, associations, and technology providers shaping immersive media and immersive events?

The dataset is intended for B2B use cases: market mapping, partner scouting, comparative research, and journalistic background work.

This document explains how entries were selected, categorised, verified, and maintained.

Version: 1.0.0  
Last updated: 2025-11-19  
Maintainer: Martin Sambauer (martin-sambauer.com)


### 2. Source materials

The dataset is primarily derived from:

1. Immersive Events Whitepaper  
   The starting point is a longform whitepaper on immersive events and immersive infrastructures. All organisations, venues, festivals, artists, and service providers mentioned there were extracted as initial candidates.

2. Official websites and public releases  
   Each candidate was verified and enriched using:
   - Official company and institution websites  
   - Festival catalogues and programmes  
   - Press releases and funding announcements  
   - Museum, venue, and institutional profiles  
   - Reputable industry reports or directories

No entry is included solely on the basis of third-party blogs, wikis, or unverified social media posts.


### 3. Inclusion criteria and scope

#### 3.1 Definition of “market participant”

For this dataset, a market participant is any entity that:

- Plays a visible and ongoing role in the immersive media ecosystem, and  
- Contributes to the conception, production, distribution, staging, or institutional support of immersive experiences.

This includes, but is not limited to:

- Technology providers (hardware, software, content tools)  
- Agencies and studios (creative direction, production, experience design)  
- Artists and artistic studios with a substantial immersive body of work  
- Venues (Fulldome theaters, XR venues, immersive art spaces, LBE venues)  
- Events and festivals with a sustained immersive focus  
- Associations, institutes, and networks supporting immersive practice  
- Distributors, platforms, and facilitators focused on immersive content

#### 3.2 Exclusions

The following types of actors are generally excluded:

- Very small, short-lived pop-ups without professional or institutional backing  
- Purely consumer-facing apps or games without clear relevance to the B2B immersive events ecosystem  
- Generic AV suppliers with no demonstrable specialisation in immersive formats  
- Entities whose existence or activity could not be confirmed via a current official source

Borderline cases are documented in the notes field.

#### 3.3 Geographic and temporal scope

- Geography: Global; no regional restriction.  
- Timeframe: Actors that have been active in immersive media roughly from the early 2000s onwards, with emphasis on actors still active at the time of verification.  
- Status: Closed or inactive entities may be included if they are historically relevant; in such cases `status_active` is set to false and notes explain the context.


### 4. Data model

Each row in `immersive-market-participants-extended.csv` represents one market participant.

The target data model is described in detail in `schema.json`. In summary, each entry contains:

- Identification and naming  
  - Stable identifier (`id`)  
  - Canonical name (`name`)

- Classification  
  - Primary category (`category`) such as Technology, Agency, Artist, Event, Venue, Association, Festival, Distributor, Other  
  - Optional subcategories or additional roles (`subcategories`)  
  - Top-level formats and focus areas (`formats`, `tags`)

- Location  
  - Country (`country`, ISO 3166-1 alpha-2)  
  - City and region (`city`, `region`)  
  - Optional coordinates (`latitude`, `longitude`) for mapping

- Web presence  
  - Official website (`website`)  
  - Optional `source_url` if a separate reference page was used

- Descriptive text  
  - Short, neutral description (`description_short`)  
  - Optional longer description (`description_long`)  
  - Optional free-form notes (`notes`)

- Provenance and quality  
  - Year founded or first public activity (`founded_year`, if known)  
  - Activity status (`status_active`)  
  - Source label (`source`, for example “Immersive Events Whitepaper”)  
  - Last manual verification date (`last_verified`)


### 5. Curation workflow

#### 5.1 Candidate extraction

1. All entities mentioned in the Immersive Events Whitepaper were extracted manually.  
2. Names were normalised (removal of legal forms such as Inc., GmbH where appropriate, consistent capitalisation, removal of duplicates).  
3. Entities that clearly referred to the same organisation under slightly different names were merged into a single candidate.

#### 5.2 Verification and enrichment

For each candidate:

1. Locate the official website or institutional profile.  
2. Confirm that the entity exists, is/was active, and clearly related to immersive media or immersive events.  
3. Extract:
   - Canonical name  
   - City and country (headquarters or primary venue location)  
   - One main URL  
   - Short description based on how the entity describes itself

If no reliable official source can be identified, the candidate is either excluded or temporarily kept with `status_active = false` and a note explaining the uncertainty.

#### 5.3 Categorisation

Each participant receives one primary category:

- Technology  
- Agency  
- Artist  
- Event  
- Venue  
- Association  
- Festival  
- Distributor  
- Other

The primary category reflects the role that is most relevant for immersive events and B2B mapping. Additional roles can be encoded in `subcategories` and `tags`.

Classification is guided by:

- Self-descriptions on the official website  
- Dominant activity in the immersive ecosystem  
- Context in which the participant appears in the whitepaper

When an entity clearly straddles multiple roles (e.g. a studio that also runs a permanent venue), the primary category is chosen to support typical analytical use cases (for example, classifying it as Agency if it mainly works as a creative/production studio, with “Venue” added as a subcategory).

#### 5.4 Location and regional assignment

Location is assigned in this order:

1. Headquarters or main operating city for companies and associations.  
2. Physical location of the venue for immersive spaces.  
3. Primary host city for festivals and events.

Regions (for example “Europe”, “North America”, “Latin America”, “Middle East & North Africa”, “Asia-Pacific”) are assigned manually based on the country.

Coordinates, where available, are derived from official addresses and geocoded using standard online tools. When precise coordinates cannot be found, `latitude` and `longitude` remain null.

#### 5.5 Descriptions

Descriptions are written to be:

- Neutral and factual  
- Short enough for tabular use (typically one sentence for `description_short`)  
- Based on how the entity describes itself, with marketing language toned down

Descriptions are not generated automatically. Each description is based on manual reading and summarisation of official sources.

#### 5.6 Quality checks

Before release, the following checks are applied:

- Every row must have `id`, `name`, `category`, `country`, `website`, `description_short`, and `source`.  
- Duplicate names or near-duplicates are reviewed and merged where appropriate.  
- URLs are checked for obvious typos and basic reachability.  
- Category distribution is reviewed to ensure there are no obvious mis-classifications.  
- Spot checks across regions to ensure a reasonable global spread.

Any unresolved issues are documented in `notes`.


### 6. Data quality, biases, and limitations

Despite careful curation, the dataset has structural limitations:

- Incompleteness  
  The global immersive ecosystem is evolving and fragmented. The dataset does not claim to be exhaustive. It focuses on actors that are visible and verifiable through public sources.

- Regional and language bias  
  Actors with strong English-language or European / North American web presence are easier to identify. Smaller players in other regions may be under-represented.

- Temporal volatility  
  Immersive studios, festivals, and venues can open, close, or pivot quickly. Even with `last_verified` dates, status information can become outdated.

- Classification ambiguity  
  Many participants fulfil multiple roles. The primary category is a pragmatic decision and does not capture the full complexity of their activities.

- Textual descriptions  
  Descriptions are concise and narrative by design. They are not meant as a controlled vocabulary and should not be interpreted as exhaustive definitions of an entity.

Users are encouraged to treat the dataset as a well-documented starting point rather than as a definitive registry. For any high-stakes decisions or public claims, always cross-check with the original sources.


### 7. Updates and community contributions

The dataset is maintained in a public repository and can be extended via pull requests.

Recommended workflow for contributors:

1. Check whether the participant is already listed.  
2. For new entries:
   - Provide at least `name`, `category`, `country`, `website`, `description_short`, and `source`.  
   - Include `source_url` and a `last_verified` date.  
   - Follow the existing style for descriptions and categories.
3. For updates:
   - Explain the change in the pull request description (for example, “updated website”, “organisation closed”, “reclassified category”).  
   - When marking an entity as inactive, set `status_active` to false and add a brief note.

Contributions that improve geographic balance, add under-represented categories, or correct mis-classifications are particularly welcome.


### 8. Licensing and reuse

The dataset is released under Creative Commons Attribution 4.0 International (CC BY 4.0) for all structural and factual elements (names, categories, locations, URLs, flags, and all derived statistics).

Textual descriptions, however, remain narrative content authored for this dataset. To avoid large-scale duplication and SEO abuse:

- You may quote and reference individual descriptions under CC BY 4.0 with proper attribution.  
- 1:1 bulk reproduction or commercial mirroring of the full text column is not permitted without prior written permission from the author.  
- Aggregated analyses, visualisations, and derived insights based on the dataset are encouraged under CC BY 4.0 with attribution to Martin Sambauer.

Preferred citation format:

Sambauer, Martin (2025): Immersive Market Participants Dataset. Version 1.0.0. Available via immersive-data-hub (GitHub).


### 9. Explore and licensing

Explore. repository folder · CSV dataset · article with insights  
Licensing. CC BY 4.0 · © Martin Sambauer · martin-sambauer.com
