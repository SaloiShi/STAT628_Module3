# STAT628_Module3

## Assignments：
- Flight cancellation: Binary classification; output the probability of cancellation.
- Departure delay: Predict the delay in minutes, allowing negative values to indicate an early departure.
- Arrival delay: Predict the delay in minutes, allowing negative values to indicate an early arrival.
- Excessive taxi time: Binary classification based on a predefined threshold for “excessively long” taxi time; this reflects taxi-related risk.
For a passenger flying with one of our selected airlines from a busy origin city, how reliable is the flight, and what kinds of delays should they expect?


## Plan for scoping the data：
### Date Range
- September–December 2023;
- September–December 2024;
- September–November 2025.

### Flight Corp Range
We selected four airlines—**Frontier, American, Delta, and United（F9, AA, DL, and UA）**—and combined their data across all three years. We excluded rows where Diverted = 1, then selected the top 10 origin cities with the highest record counts in the remaining data for these four airlines.

## Our data plan is as follows:
We use a chronological split shared across the cancellation, delay, and taxi-time analyses:

- **Training set:** September–December 2023, September–December 2024, and September 2025.
- **Validation set:** October 2025, used to select predictors, model specifications, and tuning parameters.
- **Test set:** November 2025, held out from model fitting and selection for the final historical evaluation.

This split includes both historical December periods in training and evaluates predictions on later months. In the current cleaned dataset, the training, validation, and test sets contain approximately 80.85%, 9.91%, and 9.24% of flight records, respectively. Each analysis applies its own outcome eligibility rules while retaining the same split
assignment for each flight.

The final prediction target is December 2025. 

After model selection and historical test evaluation are complete, the selected model can be refitted using all eligible available records before generating predictions for December 2025.

## Data cleaning：
Check for duplicate records and validate airport codes, airline codes, and scheduled dates and times. Add airport time zones and elevations, and standardize timestamps to account for UTC conversion, date rollovers, and daylight saving time.

## Main Purpose
(Do some data exploration first)

- whether their flight will be canceled
- whether their flight will depart on-time and, if not, the length of the departure delay (which may be negative for early departure)
- whether their flight will arrive on-time and, if not, the length of the arrival delay (which may be negative for early arrival)
- whether taxi-out or taxi-in is a big factor in departure or arrival delay

## Focus on...
- Factors Affecting Flight Delays：Does an airport’s location in an airline’s headquarters city affect flight delays?
- How does operational efficiency vary across airlines, and what factors contribute to these differences, particularly at airports in their headquarters cities?
- What patterns do departure and arrival delays exhibit across years, seasons, and weekdays versus weekends?
- the associated uncertainty for each prediction.

## Mainly Used Variables (so far, may change in the future)
- day of week
- flight date
- reporting airline
- originAirportID
- Origin origincityname
- dest destcityname
- Depdelay
- taxiout
- taxiin
- Arrdelay
- cancelled
- cancellationcode
- AirTime
- ActualElapsedTime CRSElapsedTime
- DistanceGroup
- CarrierDelay WeatherDelay NASDelay SecurityDelay LateAircraftDelay TotalAddGTime
