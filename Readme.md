Objective
Build a small working prototype that accepts a natural language query about vessel movement and returns an analytical or predictive output using a provided AIS dataset.

Dataset – Open Source Dataset link 
	https://datasetsearch.research.google.com/search?query=ais%20vessel%20data

https://coast.noaa.gov/htdata/CMSP/AISDataHandler/2020/index.html

Task Requirements
1. NLP Interpretation
•	Accept a natural language query such as:
o	“Show the last known position of INS Kolkata.”
o	“Predict where MSC Flaminia will be after 30 minutes.”
o	“Check if the latest position of Ever Given is consistent with its past movement.”
•	Parse the query to extract:
o	Intent (show, predict, verify)
o	Vessel name
o	Time horizon (if applicable)
(Can use simple keyword mapping or a lightweight NLP model like spaCy; no need for heavy LLM integration.)
2. Data Query & Processing
•	Read the AIS CSV into a dataframe.
•	Based on extracted intent:
o	If “show” → return the latest known lat/lon for that vessel.
o	If “predict” → estimate the vessel’s next position after X minutes assuming constant speed and course.
o	If “verify” → check if the vessel’s movement between the last 3 points is smooth and consistent (no sudden jump or unrealistic turn).
3. Output
•	Print or return a short textual response like:
•	INS Kolkata was last seen at 13.01N, 80.27E moving SE at 15 knots.
•	Predicted position after 30 minutes: 12.92N, 80.55E.
•	Optional bonus: plot vessel track on a simple map (using Folium or Matplotlib).
4. Evaluation Criteria
Skill Area	What You’re Looking For
Data Handling	Clean reading and processing of AIS data.
Logic & Algorithms	Correct computation of vessel heading, position prediction, and movement validation.
NLP Understanding	Ability to extract intent and entities from text (even with simple logic).
Code Structure	Modular, readable, and documented code.
Domain Sense	Awareness of realistic vessel speeds and behaviors.
