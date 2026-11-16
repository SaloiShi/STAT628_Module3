# STAT628_Module3

## Assignments：
1 Flight cancellation: Binary classification; output the probability of cancellation.
2 Departure delay: Predict the delay in minutes, allowing negative values to indicate an early departure.
3 Arrival delay: Predict the delay in minutes, allowing negative values to indicate an early arrival.
4 Excessive taxi time: Binary classification based on a predefined threshold for “excessively long” taxi time; this reflects taxi-related risk.

## Plan for scoping the data：
September–December 2023;
September–December 2024;
September–November 2025.

We selected four airlines—WN, AA, DL, and UA—and combined their data across all three years. We excluded rows where Diverted = 1, then selected the top 10 origin cities with the highest record counts in the remaining data for these four airlines.

Our data plan is as follows:
- Training set: Combine September–November data from 2023 and 2024 to train the baseline model.
- Validation set: Use December data from 2023 and 2024 for model tuning and validation.
- Test set: Use September–November 2025 data to evaluate model performance on unseen data.
The final goal is to predict flight outcomes for December 2025.

## Data cleaning：
Check for duplicate records and validate airport codes, airline codes, and scheduled dates and times. Add airport time zones and elevations, and standardize timestamps to account for UTC conversion, date rollovers, and daylight saving time.

## Main Purpose
- whether their flight will be canceled
- whether their flight will depart on-time and, if not, the length of the departure delay (which may be negative for early departure)
- whether their flight will arrive on-time and, if not, the length of the arrival delay (which may be negative for early arrival)
- whether taxi-out or taxi-in is a big factor in departure or arrival delay
- the associated uncertainty for each prediction.

## Focus on...
- Factors Affecting Flight Delays：Does an airport’s location in an airline’s headquarters city affect flight delays?
- How does operational efficiency vary across airlines, and what factors contribute to these differences, particularly at airports in their headquarters cities?
- What patterns do departure and arrival delays exhibit across years, seasons, and weekdays versus weekends?

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
