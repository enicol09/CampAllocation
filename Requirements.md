# Scout Troop Camp Allocation Details

When preparing for scout-camp allocation, the following details should be provided:

1. **Scout Troop Number**  
   Example: `297`, `76` (Integer)
2. **List of Associated Scout Troops**  
   A list of other scout troops planning to camp together.  
   Example: `[99, 283]` (Integer List)
3. **Preferred Campsite Location**  
   Example: `Platania` (String)
4. **Secondary Campsite Location**  
   Example: `Kapparis` (String)
5. **Previous Year's Camp Location**  
   Example: `Platania` (String)
6. **Preferred Dates**  
   - **Primary Date**: Selected from a provided list. (Date)  
   - **Secondary Date**: Selected from a provided list. (Date)
7. **Scout Group Type**  
   Specify the group type: `Cubs`, `Scouts`, `Rovers` (String)
8. **Number of Participants**  
   - **Campers**: Total number of scouts attending.  
   - **Leaders**: Total number of leaders attending.
9. **Notes**  
   Provide any additional information. Notes will be reviewed during the preparation phase and assigned a priority number if necessary.

# Restrictions for Scout Camp Allocation

1. **Participant Limit**  
   The number of scouts attending must not exceed the number of spaces allocated at the campsite.
2. **Date Selection**  
   The **primary date** and **secondary date** must be different.
3. **Location Preference**  
   The same campsite location may be chosen as the previous year's camp also as a secondary choice.
4. **Leader Allocation**  
   The number of leaders must meet logical requirements based on hygiene and safety standards.

# Priority Specifications for Scout Camp Allocation

1. **Previous Camp Location**  
   If two candidate troops have a similar number of scouts:  
   - Priority is given to the troop whose previous camp location matches the requested location for the upcoming camp.
2. **Assigned Priority Value**  
   Troops assigned a higher priority value during the preparation phase will be allocated first.
3. **Participant Count**  
   If two candidate troops request the same location and date, and no priority value is assigned:  
   - The troop with the higher number of participants (scouts only, excluding leaders) will be given priority.
4. **Associated Scout Troops**  
   If two candidate troops request the same location and time and differ in participant count by no more than 5 scouts:  
   - Priority is given to the troop with the greater number of associated scout troops planning to camp together.
5. **Balance Between Campsites**  
   - Troops requesting a less frequently chosen campsite for the current year are given priority to ensure balanced usage of available facilities.
6. **Troop History at Requested Campsite**  
   - Troops that have not camped at their requested location in the past 3 years receive a slight priority boost, promoting equitable rotation among campsites.
7. **Leader-to-Scout Ratio**  
   - Troops maintaining an optimal leader-to-scout ratio (e.g., 1 leader for every 10 scouts) receive higher priority.
8. **Seasonal Considerations**  
   - Troops requesting less popular or challenging dates (e.g., early summer or wetter months) are given priority for their flexibility.
9. **Event-Specific Requests**  
   - Troops requesting allocation during regional or national scouting events (e.g., jamborees, roverway) are prioritized for relevant locations and dates.
  
# Algorithms Suggestion
1. Based on a weighted priority scoring system: (very objective) - favourite by far easy to be implemented
Assign a weighted score to each troop based on key criteria:
   - **Previous Location Match**: +X points  
   - **Priority Value**: +Y points  
   - **Participant Count**: +Z points for every 5 or 10
   - **Associated Troops**: +W points per troop in the list
  
** need to define tie-breaker 

2. Using a Hierarchical Ranking System: (suggesting tiers)
    1. **Priority-Based Sorting**
    2. **Location Matching**   
    3. **Participant Count**
    4. **Associated Troops**
    5. **Campsite Balancing**
    6. **Historical Considerations**
    7. **Leader-to-Scout Ratio**
    8. **Final Tier: Randomized Tie-Breaker**
  
3. Constraint Satisfaction & Optimization.
   1. Hard Constraints - restrictions
   2. Soft Constraints with weights
   3. Weighted Optimization
   4. Rebalancing
  
# Proposed Phases:
   1. Verification - that hard constraints are being satisfied/
   2. Preparation
   3. Allocation

