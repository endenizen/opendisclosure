opendisclosure
==============

## Overview

The goal of the project is to produce useful visualizations and statistics for Oakland's campaign finance data, starting with the November 2014 mayoral race.

Meeting notes can be found in [this Google Doc](https://docs.google.com/document/d/11xji54-RiszyFBQnSBOI5Ylmzn2vC9glwAoU6A8CM_0/edit?pli=1#).


## Technical Details

The raw data can be found on Oakland's "NetFile" site here:
http://ssl.netfile.com/pub2/Default.aspx?aid=COAK

Current technology choices to-date:
- Javascript/HTML/CSS
- D3.js for visualization
- Ruby (probably) for backend data acquisition and processing

The raw data needs to be cleaned. A few common problems are:
- Misspellings
- Mischaracterized/vague occupation

## Development Process

Trying out an "agile" approach, with a basic first version:

- Clean a sample dataset (for one point in time) using a list of rules we come up with
- Use cleaned dataset to answer the below 5 key questions
- Then try to automate the cleaning to the extent possible for automatic updates/dynamic data

## 5 Key Questions from the Public Ethics Commission

(Click a question to be taken to the GitHub Issue for that question.)

[1. Who are the top 5-10 contributors to each campaign? (people or company)](https://github.com/openoakland/opendisclosure/issues/3)

[2. Which industries support each candidate? (top 5 industries, aggregate amount given from this industry to each candidate, percentage that this contribution makes in the committee’s entire fundraising efforts for this reporting period)](https://github.com/openoakland/opendisclosure/issues/4)

[3. Bar graph showing how much campaign committee has raised so far versus how much that committee has spent in expenditures on the campaign.](https://github.com/openoakland/opendisclosure/issues/5)

[4. What percentage of campaign contributions to each mayoral candidate are made from Oakland residents vs. others?](https://github.com/openoakland/opendisclosure/issues/6)

[5. Evaluate any overlap between corporations and industries that employ and register a lobbyist with the City of Oakland and campaign contribution and expenditure data.](https://github.com/openoakland/opendisclosure/issues/7)


TABLETOP CODE

## Initialize Tabletop

    var gsheet = "https://docs.google.com/spreadsheet/pub?key=0AnZDmytGK63SdDVyeE9ONFctMnRSU2VjanhZTUJsN1E&output=html";
		$(document).ready(function(){
				Tabletop.init( { key: gsheet,
			                     callback: setTheScene,
			                     proxy: IF USING PROXY,
			                     wanted: ["SHEETi"], ##can haz multiple sheets
			                     debug: true } );
		});
		
		function setTheScene(data, tabletop){
			$.each( tabletop.sheets("SHEETi").all(), function(i, sheeti) {
				var insertRow = [];
				insertRow[0] = sheeti.columnname; #enter column name here
				ARRAY.push(insertRow); ## push to array of choice
			});
		
		}


