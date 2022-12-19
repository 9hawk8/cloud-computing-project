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
to automatically retrieve the infos via the built-in Webserver
with help of a log-aggregation-tool and transfer them to a monitoring-tool
to show some nice graphs.

#### Details for Implementation
One Docker Container should contain a way to retrieve the needed infos
from the heating-unit. This could be done by setting up a fluentd instance.
With help of fluentd the heating-units built-in webserver can be contacted
at certain intervals to retrieve the statistics.

A second one could host a Grafana Loki instance, which can be accessed
by the user with some nicely formatted graphs for live-infos
and also some usage-statistics for the last month for example.

### Planning
#### Milestones
Milestone 1: set up fluentd in Docker-Container

Milestone 2: Retrieving infos from the heating-unit via fluentd is working

Milestone 3: set up Grafana Loki in Docker-Container

Milestone 4: Transferring logs from fluentd to Grafana Loki is working

Milestone 5: Displaying usage-statistics and data with Grafana is working

