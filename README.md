# Events sidebar widget for r/GTAV_Cruises

Tampermonkey/Greasemonkey userscript that lists upcoming, in progress and recent online events for the GTAV subredit [r/GTAV_Cruises](https://www.reddit.com/r/GTAV_Cruises/)


## Installation

1. First install **[Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)** (Google Chrome) or **[Greasemonkey](https://addons.mozilla.org/en-us/firefox/addon/greasemonkey/)** (Firefox).

2. Then **[click here to open the script](https://github.com/qlimax5000/GTAV_Cruises_Events/raw/master/GTAV_Cruises%20Events%20Magic.user.js)** and click the `install` button.

That's it! Just reload the subreddit page and you'll see the cruises/events box appear on the sidebar after a couple of seconds.


## Features

* Displays ALL upcoming and in-progress events/cruises in right-sidebar above Welcome section, on all pages of our subreddit.

* Event posted time converted to your local time.

* Automatic chronological sorting of events, soonest event(s) first.

* Countdown timers for each event.

* Countdown timers automatically update ever 30 seconds.

* Your local date and time of event shown underneath countdown timer.

* Event(s) convert to "In Progress" status, with custom GUI styling, when countdown timer reaches zero.

* Event(s) convert to "Finished" status, which hides the entire event, if countdown timer has been in "In Progress" status for 2 hours.

* Error handling for invalid event titles (which are not formatted correctly). Invalid event titles are displayed at the bottom, indicating the number of events omitted as well as their title(s) and link(s) to event(s).

![screenshot](http://i.imgur.com/agvyvbd.png)


## Notes for event hosts

**NOTE - If you are hosting an event, your event title MUST follow this pattern:**

**[Region] | [Date] | [Title] | [GMT] | [Time]**

* **DATE:** Must be in day/month/year format (ex: 17/8/2015 for August 17, 2015) **DO NOT USE** month/day/year, or written out like, "August 17th 2015".

* **GMT Timezone:** Please post in GMT format (ex: GMT4). The script will also convert PST/PDT/CST/CDT/EST/EDT/AEST/AEDT, but if you use those, you MUST use the right one. If you use PST yet pacific time is currently in PDT, your event will show as 1-hour off.

* **TIME:** Please use 24 hour time. The script will do its best to convert 12 hour format to 24, but just use 24 hour to mitigate edge case issues.

* The script does have other fixes to attempt to resolve human formatting errors, but plase follow these guideline to minimize possible issues. **The most important thing is to always use day/month/year for your date.**


## How it works

For those who are interested, the script does the following (and ONLY the following):

1. Load our upcoming events via search page JSON request.

2. Parse through the event titles and urls.

3. For each event found, break up the title line for all necessary information, then perform calculations on the dates/times/etc to convert the event time(s) and date(s) to true UTC time.

4. Compares the future epoch of that UTC time to the current UTC epoch, which creates a difference, and uses that as the countdown.


## Credits

* **Original code by** [PapaSyntax](https://www.reddit.com/user/PapaSyntax).
* **Maintained by** [qlimax5000](https://www.reddit.com/user/qlimax5000).
* **UI created by** [Yogensya](https://www.reddit.com/user/Yogensya).
