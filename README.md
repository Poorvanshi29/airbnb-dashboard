# airbnb-dashboard
An interactive Power BI dashboard analysing Airbnb listings, ratings, hosts and review behaviour across global cities.

📌 Overview

This project explores Airbnb's marketplace through two datasets, **Listings** and **Reviews**, and turns them into a three-page interactive report. It answers questions such as:

- How has the number of new listings grown over time, and how did COVID-19 affect it?
- Which cities dominate the market, and how do they compare on price and ratings?
- How trustworthy are hosts, and how often do guests come back to review?
- When does review activity peak in each city?

🗂️ Dashboard Structure

The report has **3 pages**, designed to be read in order.

1. Overview: platform growth story
- KPI cards for listings, reviews, property types, hosts and cities
- Line chart of new listings by year, split by room type
- Lifecycle phases: *Introduction → Growth → Maturity → Decline → COVID-19 → Reinvention*

2. Ratings: market share, pricing and quality
- Pareto-style combo chart of market share by city with cumulative %
- Average price by room type
- Average rating by city
- Detailed rating matrix (accuracy, cleanliness, communication, location, value)

3. Reviews: guest behaviour and trust
- Review-frequency chart with cumulative %
- Host trust cards (identity verified × profile picture)
- Ribbon chart of monthly review seasonality by city

🛠️ Tech Stack

- Visualisation and reporting: Power BI Desktop
- Data loading and cleaning (ETL): Power Query (M), with type transformations and header promotion
- Data modelling: one-to-many relationship from `Listings[listing_id]` to `Reviews[listing_id]`
- Calculations: DAX measures for ranking, cumulative %, segmentation and ratios

📊 Data Source

Two CSV files from the Airbnb dataset used in this project:

**Listings** (33 columns): one row per listing. Key fields include `listing_id`, `host_id`, `host_since`, `city`, `neighbourhood`, `property_type`, `room_type`, `price`, `accommodates`, `bedrooms`, `host_is_superhost`, `host_identity_verified`, `host_has_profile_pic`, `instant_bookable` and the `review_scores_*` columns.
**Reviews** (4 columns): one row per review, with `listing_id`, `review_id`, `date` and `reviewer_id`.
**Relationship:** `Reviews (many) → Listings (one)` on `listing_id`.


✨ Features & Highlights

- Business-lifecycle storytelling:** the Overview page frames listing growth as phases (Introduction, Growth, Maturity, Decline, COVID-19, Reinvention).
- Pareto / cumulative market-share analysis:** a custom DAX ranking (`RANKX`) with cumulative listing % shows how concentrated the market is across cities.
- Superhost vs. non-superhost comparison** per city.
- Multi-dimensional ratings:** a drill-down matrix across accuracy, cleanliness, communication, location and value, with a selector for overall vs. detailed rating.
- Host trust matrix:** hosts segmented into four groups (identity verified × profile picture) with percentage cards.
- Review-frequency analysis:** cumulative distribution of reviews per reviewer.
- Seasonality:** ribbon chart ranking cities by share of monthly reviews.
- Consistent design:** branded header, logo and themed layout across all pages.


💡 Key Insights

1. The market is concentrated.** Paris, New York and Sydney account for almost half of all listings and about **48% of total reviews**. Paris leads in both listings and reviews.
2. Guests rarely review more than once.** About **98.8%** of reviewers wrote 3 reviews or fewer, and one reviewer wrote **283**.
3. Trust signals are strong.** Over two-thirds of hosts are fully verified (identity + profile picture), and almost all provide at least one trust signal.
4. Reviews are seasonal.** Paris and Rome dominate review share from **April to August** (European summer travel), while New York rises in **November and December** (holiday season).


🎯 Business Impact

- Market expansion:** identifies the cities that drive most of the volume, helping prioritise acquisition and marketing spend.
- Pricing strategy:** comparing average price by room type and city supports price-benchmarking for hosts.
- Quality control:** the detailed rating breakdown highlights which experience factors (cleanliness, accuracy, value, etc.) pull ratings down.
- Trust & safety:** the verification matrix shows where nudging hosts to verify identity or add a photo would raise platform trust.
- Demand planning:** seasonality by city informs staffing, promotions and host availability ahead of peak months.
- Retention opportunity:** since most guests review only once, there is room to improve repeat-booking and loyalty programmes.

✨ Screenshot: 
Link: 
