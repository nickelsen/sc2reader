CHANGELOG
============

0.5.2 -
--------------------

* Adds experimental SC2Map.MapInfo parsing support. Replaces the useless MapInfo resource from before.
* Summary.teams is now summary.team; summary.team is now summary.teams. To conform with replay name conventions
* Fixed #136, unit types from tracker events are used when available.
* Deprecated player.gateway for player.region
* Reorganized the person/player/observer hierarchy. Top level classes are now Computer, Participant, and Observer. Participant and Computer are both children of player so any isinstance code should still work fine.
* Player.uid now means something completely different! Use player.toon_id instead
* Player.uid is now the user id of the player (was player.cid)
* PersonDict can no longer be constructed from a player list and new players cannot be added by string (name). Only integer keys accepted for setting.
* Added a sc2json script contributed by @ChrisLundquist
* Hooked up travis-ci for continuous testing. https://travis-ci.org/GraylinKim/sc2reader
* Switched to built in python unittest module for testing.
* Log a warning instead of throwing an exception when using an unknown colors.
    * An unknown hex value will use the hex value as the name.
    * An unknown color name will use 0x000000 as the color.


0.5.1 - June 1, 2013
--------------------

* Fixes several game event parsing issues for older replays.
* Propperly maps ability ids for armory vehicle & ship armor upgrades.
* Uses the US depot for SEA battle.net depot dependencies.
* ``PlayerStatEvent.food_used`` and ``food_made`` are now properly divided by 4096
* ``AbilityEvent.flags`` are now processed into a dictionary mapping flag name to True/False (``AbilityEvent.flag``)
* Fixed error preventing UnitOwnerChangeEvents from being processed
* Fixed the toJSON plugin and adds new fields
* Fixed error preventing parsing of MapHeader (s2mh) files
* APMTracker now properly calculates average APM to the last second played by each player instead of using the number of replay minutes in the denominator.

0.5.0 - May 7, 2013
--------------------

* Support for all replays (arcade replays now parse!) from all versions
* Support for the new replay.tracker.events added in 2.0.8
    * Units now have birth frame, death frame, and owner information
    * New events for (roughly) tracking unit positions
    * New events for tracking player resource stockpiles and collection rates
    * More!
* Much more comprehensive documentation.
* New unit model
    * SiegeTank and SiegeTankSieged (and others with different forms) are no longer separate units.
    * Units that can transform maintain a full type history.
    * Units are correctly and uniquely identified by unit_id alone.
* Updated unit meta data:
    * Mineral Cost
    * Vespene Cost
    * Supply Cost
    * Flags for is_worker, is_army, is_building
* Added ability meta data:
    * is_build flag marking abilities that create units
    * build_unit indicating the unit type that is built
    * build_time indicating the build time for the ability

0.4.0 - ???
--------------------

...

