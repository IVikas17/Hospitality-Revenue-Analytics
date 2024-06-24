# Hospitality Revenue Analytics

AtliQ Grands, a chain of five-star hotels across India, is experiencing a decline in market share and revenue in the luxury/business hotel sector. To address this, they have sought insights from historical data to inform strategic decisions. This project involves creating metrics, a dashboard, and additional insights to help the company regain its market share.

## Table of Contents
- [Project Overview](#project-overview)
- [Power BI Dashboard](#power-bi-dashboard)
- [Installation and Usage](#installation-and-usage)
- [Conclusion](#conclusion)

## Project Overview

AtliQ Grands owns multiple five-star hotels across India. They have been in the hospitality industry for the past 20 years. Due to strategic moves from other competitors and ineffective decision-making in management, AtliQ Grands are losing their market share and revenue in the luxury/business hotels category. As a strategic move, the managing director of AtliQ Grands wanted to incorporate “Business and Data Intelligence” to regain their market share and revenue. However, they do not have an in-house data analytics team to provide them with these insights.

Their revenue management team decided to hire a 3rd party service provider to provide them with insights from their historical data.

### Key Findings and Results
1. **Pricing Strategy**: Hotels are not using dynamic pricing effectively.
2. **Average Rating**: Some hotels have low average ratings, resulting in a low occupancy rate of 44%.
3. **Booking Platforms**: Inefficient use of different booking platforms. Recommendations include offering discount coupons and promotions on their own website to increase direct bookings.



## Power BI Dashboard

The Power BI dashboard includes the following KPIs and visualizations:

![Atliq Hotel Dashboard](https://github.com/IVikas17/Hospitality-Revenue-Analytics/assets/116329070/802ce1ec-7e93-4a86-93fb-16cc72e199f6)


### KPIs
- **Revenue**: Total revenue realized from bookings.
- **Occupancy %**: Percentage of occupied rooms out of the total available capacity.
- **Average Rating**: Average rating given by customers.
- **Total Bookings**: Total number of bookings made.
-  **Revenue WoW Change %:** Week-over-week percentage change in revenue.
-  **Occupancy WoW Change %:** Week-over-week percentage change in occupancy rate.
-  **ADR WoW Change %:** Week-over-week percentage change in Average Daily Rate.
-  **RevPAR WoW Change %:** Week-over-week percentage change in Revenue Per Available Room.
-  **Realisation WoW Change %:** Week-over-week percentage change in realization.
-  **DSRN WoW Change %:** Week-over-week percentage change in Daily Sellable Room Nights.

### Filters
- **Category:** Filter data by specific categories of hotels.
- **City:** Filter data by specific city.
- **Room type:** Filter data by room types.

### Visualizations
1. **Line Chart for Daily Trends**:
   - Shows the daily trends of Revenue, Occupancy, and Average Rating.
   - Set the x-axis to the date.
   - Added Revenue, Occupancy, and Average Rating as values.


2. **Bar Chart for Room Class Analysis**:
   - Displays the revenue and bookings by room class.
   - Set the x-axis to room class.

3. **Pie Chart for Booking Platform Distribution**:
   - Shows the distribution of bookings across different platforms.
   - Set the legend to booking platform.
   - Set values to the count of bookings.

4. **Table with Booking Details**:
   - Includes columns such as booking_id, revenue_realized, booking_status, ratings_given, and booking_platform.

### Steps to Implement Visualizations

1. **Revenue KPI**:
   - Used a Card visualization.
   - Created a measure for total revenue.
   ```DAX
   Total Revenue = SUM(FactBookings[revenue_realized])


2. **Occupancy % KPI**:
- **Visualization:** Used a Card visualization.
- **Measure:** Created a measure for occupancy percentage.
- **DAX:**
    ```
    Occupancy % = 
    DIVIDE(
       COUNTROWS(FactBookings),
       CALCULATE(
          COUNTROWS(FactBookings),
          FactBookings[booking_status] = "Checked Out"
       )
    ) * 100
    ```

3. **Average Rating KPI**:
- **Visualization:** Used a Card visualization.
- **Measure:** Created a measure for average rating.
- **DAX:**
    ```
    Average Rating = AVERAGE(FactBookings[ratings_given])
    ```

4. **Total Bookings KPI**:
- **Visualization:** Used a Card visualization.
- **Measure:** Created a measure for total bookings.
- **DAX:**
    ```
    Total Bookings = COUNTROWS(FactBookings)
    ```

# Conclusion

## Project Overview
This project highlights the deployment of a Power BI-based business intelligence solution for AtliQ Grands, aimed at leveraging historical data to optimize operations and regain market share in luxury/business hotels. By analyzing occupancy rates, average ratings, and booking platform efficiencies, the dashboard offers actionable insights to enhance pricing strategies, improve customer satisfaction, and drive direct bookings. This initiative underscores the importance of data-driven decision-making in maintaining competitiveness and achieving strategic goals in the hospitality sector.
