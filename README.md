# Real-Estate-Market-Analytics

Analyze property prices, market liquidity, and investment potential across European countries and cities to support data-driven real estate decisions.

## I. Introduction

### 1. Dataset

The dataset represents a European real estate listing platform, containing 5,000 property listings across 10 countries (France, Netherlands, Germany, Spain, Italy, Austria, Portugal, Poland, Czech Republic, Belgium) and their major cities.

#### Real Estate Listings Table

| Column Name | Data Type | Description |
|---|---|---|
| property_id | STRING | Unique property identifier |
| country / city | STRING | Property location |
| property_type | STRING | Apartment, Office, Retail, Villa, Townhouse, Warehouse, Mixed-Use |
| listing_type | STRING | Sale or Rental |
| sale_price_eur | FLOAT | Sale price in EUR |
| monthly_rent_eur | FLOAT | Monthly rent in EUR |
| price_per_sqm | FLOAT | Price per square meter |
| square_meters | FLOAT | Property size |
| bedrooms / bathrooms | INTEGER | Room counts |
| furnishing_status | STRING | Furnished, Semi-Furnished, Unfurnished, Unspecified |
| energy_rating | STRING | Energy efficiency rating (A-G) |
| elevator / gym / swimming_pool | STRING | Amenity flags (Yes/No) |
| floor_number | INTEGER | Floor level |
| parking_spots | INTEGER | Number of parking spots |
| year_built | INTEGER | Construction year |
| days_on_market | INTEGER | Days the listing has been active |
| Capital Gain % | FLOAT | Pre-calculated capital appreciation estimate |

### 2. Problem to Be Solved

Build a decision-making report for real estate analysts, property investors, and marketplace product teams to:
- Understand how prices vary across locations and property characteristics
- Identify which properties stay longest on the market and why
- Spot locations with high value but weak liquidity
- Rank cities by investment attractiveness (yield and capital growth combined)
Key Questions to Explore
-	How do property prices and price per square meter vary across countries and cities?
-	Which locations and property types have the highest average listing values?
-	How do property characteristics such as size, bedrooms, bathrooms, and building age influence pricing?
- Do properties with premium amenities (parking, elevators, gyms, pools) command higher prices?
- Which properties stay longest on the market ?
- Are there locations that show high property values but lower market activity?
- Which cities might present the most attractive opportunities for real estate investors?


## II. Design Thinking

### STEP 1: Empathize

Three personas were considered: the analyst needing market-wide patterns, the investor needing yield and growth comparisons, and the buyer/agent needing to understand what drives a specific property's price and time-to-sell.

### STEP 2: Define POV

North star metric
- Summary: Total Listing
- Market Liquidity: Average days on market
- Investor Opportunities: Perccentage of Average Capital Gain (%), Percentage of Gross Rental Yield (%)
- Property value drivers: Price per square meter

### STEP 3: Ideate

Four report pages were planned: Overview (market pulse), Price Drivers (what influences value), Market Liquidity (what slows sales down), Investor Opportunities (where to invest) and Property Deepdive (Explorer - find and compare properties easily)

### STEP 4: Prototype and Review

Chart types were chosen to match each question's data structure: bar charts for mutually exclusive categories, matrix/heatmap for two-dimensional combinations, scatter plots for continuous relationships, and composite scoring tables for investment ranking.

## III. Visualization

### OVERVIEW

Overview - what does the Market Look Like?
- How listings have changed over time
- Are there locations that show  high property values bur lower market activity ?
- What types of properties dominate the market?
- Which Property Size Band have the highest Sale Listings and Rental Listings ?
- How features like amenities and furnishing show up across listings ?
<img width="1226" height="745" alt="image" src="https://github.com/user-attachments/assets/546aa9cc-4475-4214-9ada-2e79fbd7c9d4" />


### PRICE DRIVERS

Price Drivers - what Influences Property Value?
- Do amenities like gyms or pools really increase value?
- Do Properties size band influences price ?
- Are bigger properties always more expensive per square meter?
- Does age influences price ?
- Does floor level make a difference?
- How do bedrooms and bathrooms combine to influence price?
<img width="1415" height="707" alt="image" src="https://github.com/user-attachments/assets/192a46fa-6f75-4b3d-b4f9-819824e0d088" />

### MARKET LIQUIDITY
How fast a property selling ?
- How many listing each day-on-market band has ?
- which countries sell property fastest, and what price level comes with that speed?
- Which properties stay longest on the market ?
<img width="1222" height="592" alt="image" src="https://github.com/user-attachments/assets/51fc4b7a-3478-4958-916b-e06c8e42b6ec" />

### INVESTOR OPPORTUNITIES
Investor opptunities finder
- Which cities might present the most attractive opportunities for real estate investors?
- Highest Avg Capital Gain % by Country ?
- Which property type offers the best mix of rental income and price growth?
- Which cities offer both high rental yield and strong capital growth?
<img width="1206" height="612" alt="image" src="https://github.com/user-attachments/assets/ac588967-5af3-42f5-818e-26e90a8abdef" />

### EXPLORE - FIND AND COMPARE PROPERTIES EASILY .

Browse and comapre individual property in every dimension 
<img width="1035" height="585" alt="image" src="https://github.com/user-attachments/assets/a572de84-b365-4565-8b4b-f3c353dfc7de" />


## IV. Insight and Recommendation

### 1. Price Drivers

**Price per sqm rises with property size .** Medium has the most listings but lower price/sqm; Extra Large has the fewest listings but highest price/sqm. 
The majority of listings fall within small to mid-sized ranges (50–200 sqm), reflecting the core of market supply and demand.  

**Age influence price** Properties built within the last 50 years achieve above-average rental income, indicating stronger tenant demand for modern housing

**Amenities do not add value cumulatively.** Properties with all three amenities (elevator, gym, pool) average the lowest price per sqm (€2.5K) of any amenity combination, lower than having none (€3.0K). Elevator+Pool is the most valuable pairing (€3.5K). Amenities appear to signal a market segment rather than directly cause price increases.

**Bedroom-bathroom combinations follow standard real estate economics.** 1-bedroom/1-bathroom properties command the highest price per sqm (€3.01K), decreasing as room count rises, consistent with fixed costs being spread over more area in larger configurations. This is the cleanest, most theory-consistent result in the dataset.

### 2. Market Liquidity

**Market-wide slowdown:** All 10 countries average 162-183 days on market, nearly double the 90-day benchmark.

**Country and property type matter little:** Fastest vs. slowest country differs by only ~21 days (Czech Republic 162, Netherlands 183). Property types differ by ~14 days (Villa 164, Retail 178).

**Long-tail listings drive the problem:** ~44% of listings sit 180+ days; only ~28% sell within 90 days.

**Price doesn't track speed:** Cheap markets (Czech Republic) and expensive ones (Netherlands) show no consistent relationship with days on market.

### 3. Investor Opportunities

**Vienna and Berlin rank highest** on rental yield (5.2%, 5.0%) and on the custom Investor Score (60 each).

**Higher price does not mean higher yield** in this dataset. Paris (€5.2K/sqm, 3.6%) and Amsterdam (€4.8K/sqm, 4.0%) are the most expensive but have among the lowest yields.

**Brussels has the highest capital gain** (116.9%) with a 4.6% yield.

**Residential has the highest capital gain** (~100%) with a 4.5% yield.

**Mixed Use has the highest yield** (4.8%) but the lowest capital gain. It is also the smallest segment (~7% of listings).

