# Project brief: Airbnb in Barcelona

## The client

A Barcelona city-council team that is preparing a report on short-term rentals. They are not technical. They have the data below but no idea what is worth looking at. They want **you** to tell them: find one question worth answering, answer it honestly, and give them a few clear charts they can quote in a meeting.

## How you will work

1. **Explore** (`/explore-data`): get to know the data in `eda.ipynb`. Write what you learn in `DATA_NOTES.md`.
2. **Frame** (`/frame-question`): choose your question and write it in `QUESTION.md`.
3. **Plan** (`/plan-analysis` in Plan mode): decide how to answer it.
4. **Build and review**: `analysis.ipynb`, one cell at a time. Then `/review` and `/quiz-me`.

The question is yours. The agent will help you sharpen it, but it will not choose it for you.

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

## Deliverables

1. `eda.ipynb` and `DATA_NOTES.md`: what the data is and what you noticed.
2. `QUESTION.md`: your question, who it is for, and how you measure it.
3. `analysis.ipynb`: runs top to bottom and ends with your answer, written for the client in a few sentences.
4. `docs/DECISIONS.md` and `docs/TECH_STACK.md`, updated.
