# The dataset: Airbnb listings in Barcelona

## Where it comes from

[Inside Airbnb](https://insideairbnb.com) is an independent project that collects the public information on Airbnb's website to study how short-term rentals affect cities. Every few months it visits every listing page in a city and saves what it finds: a **snapshot** of the city on that date.

This file is the Barcelona snapshot taken on **17 to 19 September 2026**. It is a random sample of **8,000 of its 15,236 listings** (31 columns), licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Why it matters: short-term rentals are a political topic in Barcelona. Tourist flats need a licence, and the city has announced it will stop renewing those licences by 2028. Neighbours, hotels, hosts and the council all argue with data like this.

## What one row is

**One listing**: a home or room advertised on Airbnb, as it looked on the day it was scraped.

- It is **not a booking**: we never see who stayed, when, or what they paid.
- It is **not a host**: one host can have many listings (`host_id` repeats).
- It is **one moment**: we don't see how a listing changed over time.

## What it can and cannot tell you

| It can tell you | It cannot tell you |
|-----------------|--------------------|
| Where listings are, and what kind (whole flats, rooms...) | How many nights were really booked: occupancy is an **estimate** based on reviews |
| The nightly price the host asks | The price guests actually paid |
| Who hosts: individuals or hosts with dozens of listings | Whether a listing is legal: the licence column is what the host typed |
| What guests rated, and how many reviews | **Why** anything happens: it shows patterns, not causes |

## Columns

| Group | Columns | Notes |
|-------|---------|-------|
| Listing | `id`, `name`, `property_type`, `room_type` | `room_type` has 4 values; `property_type` is free text |
| Host | `host_id`, `host_is_superhost`, `calculated_host_listings_count` | Superhost is `t` / `f`. The listings count is for **all of Barcelona**, not this sample |
| Location | `district`, `neighbourhood`, `latitude`, `longitude` | 10 districts, 67 neighbourhoods |
| Size | `accommodates`, `bedrooms`, `beds`, `bathrooms_text`, `amenities` | Bathrooms are text (`1.5 shared baths`); amenities is a list stored as text |
| Price and rules | `price`, `minimum_nights`, `availability_365` | Price is text like `$274.00`; the `$` is a formatting quirk, amounts are in euros. Availability = days open for booking in the next year |
| Reviews | `number_of_reviews`, `number_of_reviews_ltm`, `reviews_per_month`, `first_review`, `last_review`, `review_scores_*` | `ltm` = last twelve months. Scores go from 1 to 5. Empty when a listing has no reviews |
| Regulation | `license` | Free text, sometimes with HTML line breaks: a regional registration number, a national one, and/or `Exempt - seasonal rental`. Empty if the host shows none |
| Activity | `estimated_occupancy_l365d` | Inside Airbnb's estimate of nights booked in the last year, built from reviews |
| Snapshot | `last_scraped` | The day that listing page was visited |

## Before you trust a number

The data is real, so it is messy: text where you want numbers, missing values, extreme values, placeholders. Every cleaning step changes the answer, so every cleaning step is **your decision**.
