# airbnb_data_analytics

This project analyzes modified Airbnb data for Sydney, Australia, focusing on data cleaning, merging, exploratory data analysis (EDA), visualization, and business insights.
The dataset includes Listings, Reviews, and Neighbourhood GeoJSON files, processed using Python.

# Dataset Description

This project uses a modified Airbnb dataset consisting of:

- `listings.csv`: Listing information to help people book stays.
- `reviews.csv`: Review data from guests, including comments and reviewer info.
- `neighbourhoods.geojson`: Geographic boundary data for Sydney neighbourhoods.


# Step 1: Data Cleaning & Preprocessing

## Cleaning Listings Data

- Standardized column names (lowercase, trimmed whitespace)

- Selected key columns (price, room type, amenities, host info, coordinates, etc.)

- Removed empty columns and duplicate rows

- Cleaned price and host_response_rate formats

- Converted date fields to datetime

- Ensured id is unique and set as index

## Cleaning Reviews Data

- Standardized column names

- Kept essential fields (listing_id, date, reviewer info, comments)

- Removed duplicates and rows missing listing_id/date

- Ensured id is unique and set as index

# Step 2: Merging Listings, Reviews & Neighbourhoods

Steps:

- Calculated centroid coordinates for each neighbourhood

- Merged reviews_df with listings_df using listing_id

- Merged with neighbourhood GeoJSON using neighbourhood names

- Removed rows missing coordinates

- Final merged dataset: 611,463 rows × 30 columns

# Step 3: Host Performance by Amenity & Portfolio Size

Host Portfolio Segments
- Small Portfolio: 1 listing
- Medium Portfolio: 2–5 listings
- Large Portfolio: 6–10 listings
- Enterprise Portfolio: 10+ listings

Key Amenities Analyzed
- Wifi
- Kitchen
- Air conditioning
- Heating
- TV
- Washer
- Free Parking

Metrics Calculated (Pivot Table)
For each host segment × amenity:

- Average nightly price

- Average availability in next 30 days

- Average review score rating

# Key Insights

- Enterprise hosts charge the highest prices but receive the lowest ratings
Prices often exceed $240–$257

Ratings fall between 4.69–4.71, the lowest among all segments

- Small hosts receive the highest ratings
Ratings consistently 4.85–4.86

Suggests more personalized guest experiences

- Free parking is a high‑value amenity
Across all host segments, listings with Free parking have higher prices.

- High-demand amenities: Air conditioning, Free parking, Wifi
Enterprise hosts show lower availability_30, indicating higher booking demand

- Large hosts show higher availability_30, possibly due to oversupply or lower demand

# Step 4 — Visualization: Price vs Rating

The scatter plot highlights:

- Free parking and Air conditioning (bold markers) are consistently associated with strong ratings

- Small hosts maintain high ratings across all amenities

- Enterprise hosts tend to have high prices but lower ratings

- Medium hosts achieve a balanced price–rating performance
# Recommendations

For New Hosts
- Offer Free parking and Air conditioning first

- Low cost, high impact on guest satisfaction and review scores

For Existing Hosts
- Review pricing strategy relative to portfolio size

- Enterprise hosts should focus on improving guest experience

- Avoid high-priced listings with low ratings

- Medium hosts can strengthen performance with amenities like Kitchen or Heating

# Step 5 — Review Timing & Engagement Analysis

Additional Columns Created
- day_of_week
- is_weekend
- is_holiday (NSW public holidays)
- day_type (Holiday / Weekend / Weekday)

# Heatmap Analysis

## Grouped by:
- Review score rating (binned)
- Host response rate (binned)

## Calculated verage number of reviews per group

Review Timing Insights
- Reviews increase significantly on weekends and public holidays
→ Supports the claim that review activity is higher during these periods.

-  Listings with high ratings and high host response rates receive the most reviews
→ Strongly supports the claim that quality listings attract more engagement.

-  High response rate is a major driver of review volume
→ Hosts with 90–100% response rate consistently receive more reviews.

# Summary of Insights
- Small hosts deliver the best guest experience (highest ratings)

- Enterprise hosts charge more but receive lower ratings

- Free parking and Air conditioning are the most valuable amenities

- Review activity is higher on weekends and holidays

- High ratings + high response rate = more reviews and visibility
