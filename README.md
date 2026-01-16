![American Airlines Hack-a-thon 2024](https://github.com/RakeshsarmaKarra/American-Airlines-Hack-a-thon-OR-AA-/blob/main/Picture.jpg)

# ✈️ Destination Recommendation Engine – Customer Travel Behavior Modeling
## Project Overview
This project implements a destination recommendation prototype built during an airline analytics hackathon. It uses multi-table customer travel behavior data to predict likely future destinations and lay the groundwork for a top‑N recommendation engine.
​
## Goal
Learn from historical searches and bookings to recommend a small set of likely destinations for each loyalty customer.

## Impact
A data‑driven recommendation layer can support better personalization, marketing efficiency, and customer experience in flight planning.
​
## Data Overview
The solution works with de‑identified, structured data representing customer travel behavior across several relational tables. 

## Abstracted tables (conceptual):
Origins: Customer home or “base” location keyed by a loyalty identifier.                                                                                                                                                                     
Searches: Historical flight search behavior with season and searched destination.                                                                                                                                    
Bookings: Completed trips with destination and season of travel.                                                                                                                                                                     
Airport Info: Metadata describing airport codes, geography, and region groupings.                                                                                                                                    
Targets: Future destination labels used to train and evaluate supervised models.                                                                                                                                    
All tables are joined using an abstracted customer key (loyalty ID) to build a unified behavior view.                                                                                                                                    

## Feature Engineering
The project focuses on customer‑level behavioral features that summarize past interactions and preferences, suitable for destination prediction and recommendation.
​
## Examples of engineered features:
Engagement intensity: Counts of past bookings and search events per customer.                                                                                                                                            
Destination diversity: Number of distinct destinations searched or booked.                                                                                                                                            
Seasonality preferences: Most common seasons for searches and trips.                                                                                                                                            
Home–destination patterns: Relationships between home location and historical destinations.                                                                                                                                            

These signals are aggregated into a single feature matrix keyed by the customer identifier, ready for supervised learning.

## Modeling Approach
The recommendation prototype is framed as a multiclass classification problem: predict a future destination label given engineered behavioral features.
​
## Preprocessing:
Type casting and cleaning across all tables.                                                                                                                                                                               
Encoding of categorical features and scaling of numerical features via scikit‑learn pipelines.                                                                                                                                            
Models explored (high level):                                                                                                                                                                               
Tree‑based classifiers (e.g., random‑forest–style models).                                                                                                                                                                               
Gradient‑boosted approaches for stronger nonlinear performance.                                                                                                                                                                               
​
## Evaluation:
Train/test split at the customer level.                                                                                                                                            
Accuracy and related metrics used for baseline assessment, with the intent to extend toward top‑N recommendation quality metrics.
