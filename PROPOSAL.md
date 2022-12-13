# Cloud Computing Project WS22

## Logging statistics from an ETA PU15 (Holz-Pellet Heizung / wood pellet heating unit) using Microservices

### Problem
The ETA PU15 unit can deliver various infos to the user,
like heating status, if an external heating-devices delivers heat,
which temperatures radiators, water heating buffer tank
or warm water exchanger have currently.

All those infos can be shown live via the built-in display.
But there is also an option to enter a developer menu
and export all current infos to a USB-Stick as an CSV-file
or read out the values via a Webserver.

If one wants to track usage of pellets for example,
it is possible to save the CSV-files on to a USB-stick
and get back to the ETA PU15 (referred to as heating-unit)
at any time to view changes and usage statistics from file to file
from inside the developer menu.

This requires physical access to the heating-unit.

### Proposal
The user should get an easier way to those statistics.
To achieve this, a Docker-Microservice-Architecture should replace the need
to physically go to the heating-unit. The main goal is
to automatically retrieve the infos via the built-in Webserver,
log it into a database and show the user the info nicely formatted
on a webpage accessible on every device in the network.

#### Details for Implementation
One Docker Container should contain a way to retrieve the needed infos
from the heating-unit.

A second one hosts a database to write logs with the needed data into.

A third one should host a webpage the user can access
with some nicely formatted and user-readable live-infos
and also some usage-statistics for the last month for example
(mean pellet usage per day, overal pellet usage).

### Planning
#### Milestones
Milestone 1: Retrieving infos from the heating-unit is working

Milestone 2: Logging infos in database is working

Milestone 3: Displaying live-data via webpage is working

Milestone 4: Displaying usage-statistics over time-period is working

