# Project brief: Airbnb in Barcelona

## The client

A Barcelona city-council team that is preparing a report on short-term rentals. They are not technical. They want a short, honest analysis they can quote in a meeting, with a few clear charts.

## Their questions (pick the ones you want to answer; you may add your own)

1. How are listings distributed across districts and room types?
2. What drives the nightly price: district, room type, size, reviews?
3. How many listings show a tourist registration number, and does that vary by district or host size?
4. Are "professional" hosts (many listings) different from hosts with a single listing?

Part of the work is deciding **which questions to answer and how deep to go**. Defend that choice in `docs/DECISIONS.md`.

## The data

`data/barcelona_listings.csv`: 8,000 listings sampled at random from the Inside Airbnb snapshot of 2026-09-17 (CC BY 4.0). One row per listing.

| Column | Meaning |
|--------|---------|
| `id`, `name`, `host_id` | Listing id, listing title, host id |
| `host_is_superhost` | `t` / `f` |
| `district`, `neighbourhood` | 10 districts, ~70 neighbourhoods |
| `latitude`, `longitude` | Location |
| `property_type`, `room_type` | Free-text type, and one of 4 room types |
| `accommodates`, `bedrooms`, `beds`, `bathrooms_text` | Size (bathrooms are text, e.g. `1.5 shared baths`) |
| `amenities` | List of amenities, stored as text |
| `price` | Nightly price as text, e.g. `$274.00` |
| `minimum_nights`, `availability_365` | Booking rules and days available next year |
| `number_of_reviews`, `number_of_reviews_ltm`, `reviews_per_month` | Review counts (ltm = last twelve months) |
| `first_review`, `last_review` | Dates |
| `review_scores_*` | Scores from 1 to 5 |
| `license` | Free text (with HTML line breaks) listing a Barcelona regional registration number, a Spanish national number and/or `Exempt - seasonal rental`; empty if none shown |
| `calculated_host_listings_count` | How many listings the host has in all of Barcelona (the full snapshot, not this sample) |
| `estimated_occupancy_l365d` | Inside Airbnb's estimate of nights booked in the last year |
| `last_scraped` | Date of the snapshot |

The data is real, so it is messy. Expect text where you want numbers, missing values, and outliers. Every cleaning step is a decision.

## Deliverable

`01_data_analysis/analysis.ipynb` that runs top to bottom, ending with 3 to 5 findings written for the client, plus an updated `docs/DECISIONS.md` and `docs/TECH_STACK.md`.
