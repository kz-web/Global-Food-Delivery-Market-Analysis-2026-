

# Global Food Delivery Market Analysis (2026)

## Project Overview

An end-to-end exploratory data analysis and interactive spreadsheet dashboard built in **Google Sheets** using a global food delivery dataset (`global_food_delivery_enriched_market_2026`, **8,000 orders**). The project transforms raw transaction records into cleaned data tables, pivot summaries, dynamic slicers, and executive charts designed to surface operational bottlenecks, city-level revenue patterns, pricing/basket dynamics, and satisfaction drivers.

---

## Workbook Architecture (`Tabs`)

* **`cleaneddata`** — Standardized analytical dataset (`8,000` order records) serving as the source of truth for KPI calculations and slicer filtering.
* **`Customer Cuisines Summary`** — Pivot table analyzing average net order price (`net_effective_order_price`) and discount patterns (`discount_percentage`) across `cuisine_category` and `restaurant_price_tier`.
* **`OrderDrives_Summary`** — Pivot table evaluating order volume (`COUNTA` of `order_id`) and customer satisfaction (`AVERAGE` of `customer_rating`) across satisfaction/delay drivers.
* **`WeatherImpact`** — Pivot table comparing average fulfillment time (`AVERAGE` of `total_fulfillment_time_min`) and customer ratings across `weather_condition` and peak-hour status (`is_peak_hour`: Off-Peak vs. Peak Hour).
* **`Metrocity_summary`** — Pivot table aggregating total net revenue (`SUM` of `net_effective_order_price`) across **12 metro cities**.
* **`DASHBOARD`** — Executive summary view featuring KPI cards, interactive slicers (`metro_city`, `weather_condition`, `is_peak_hour`, `restaurant_price_tier`), a 2×2 chart grid, and actionable recommendations.

---

## Headline Metrics (`KPIs`)

* **Total Orders:** `8,000`
* **Net Revenue:** `$238,854.63`
* **Average Customer Rating:** `4.28` / `5.00`
* **Average Net Order Value:** `$29.86`

---

## Key Analytical Findings

1. **Peak Hours + Severe Weather Create the Longest Fulfillment Delays:** Across weather conditions, peak-hour deliveries take noticeably longer than off-peak deliveries, with **`Heavy Rain / Storm` during Peak Hours** pushing average fulfillment toward **~40 minutes** (~`39.70` min).
2. **Weather Delays Drive the Sharpest Rating Drops:** While routine order volume is heavily supported by fast fulfillment and promotional discounts, weather-induced delays correlate with noticeably lower ratings (around **`3.24`** in delay cohorts and **`3.90`** during peak heavy rain/storms), showing that customer frustration spikes when severe weather compounds wait times.
3. **Revenue Is Top-Heavy Across Global Metros:** **New York**, **Tokyo**, and **London** lead net revenue generation, while secondary or distinct markets show different trade-offs between order volume, basket size, and rating performance (such as lower ratings in São Paulo and distinct volume/value profiles in Mumbai and Toronto).
4. **Basket Sizes Scale Across Restaurant Price Tiers:** Average net order values increase substantially across restaurant price tiers, while lower-priced tiers rely more heavily on promotional discounts to sustain order flow.

---

## Strategic Recommendations

* **Target Operational Buffers & Courier Incentives on Peak Storms:** Concentrate dynamic ETA buffers, proactive delay notifications, and courier incentives on `Heavy Rain / Storm` + `Peak Hour` windows rather than applying broad operational friction during clear or mild weather.
* **Refine Discounting on High-Performing Budget Cuisines:** Review discount caps where basket sizes and demand already hold strong so promotions protect restaurant and marketplace margins instead of subsidizing baseline orders.
* **Tailor Growth & Quality Playbooks by Metro City:** Pair service and fulfillment audits in lower-rating markets (such as São Paulo) with targeted demand or basket-size initiatives in markets with room to expand (such as Mumbai and Toronto).

---

## How to Use & Explore the Workbook

1. Open the **`DASHBOARD`** tab to review headline KPIs, the 2×2 visual grid, and the **Recommendations** block.
2. Use the **Slicers** (`metro_city`, `weather_condition`, `is_peak_hour`, `restaurant_price_tier`) to slice performance by city, weather state, peak timing, or price tier.
3. Inspect the underlying Pivot Tables (`Customer Cuisines Summary`, `OrderDrives_Summary`, `WeatherImpact`, `Metrocity_summary`) or `cleaneddata` to audit exact breakdowns and formulas.
