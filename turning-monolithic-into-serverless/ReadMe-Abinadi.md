# Adding Serverless to a Legacy/Monolithic PHP App

## How to modernize
* Complete Rebuild
* Iterative


## What is "Serverless"
* Running without caring where the code is run
* Containers, but you don’t have to worry about them

## Why bother?

## Ways to get going
* Events
	* HTTP requests
	* Scheduled events
	* Platform-specific
* Biggies (AWS, GC, Azure)
* Others

## Serverless.com
* YAML-based
* Provider-agnostic
* Greate ecosystem
* Local dev options
* Open Source & enterprise

## Good, Bad, Ugly
* Good
	* Hugely reduced infrastructure overhead & costs (maybe)
	* Can encourage better programming & encapsulation
	* Easier path towards modernization
	* Scalability (huge)
	* Security
	* Separation from legacy environment
* Bad
	* Overhead (more stuff)
	* Languages & PHP support
	* Incorporating with deployment procedures
	* Figuring out local dev
	* Additional overhead for logging * monitoring
	* New ways of thinking
* Ugly
	* Vendor lock-in
	* Cold starts VPCs
	* Output formatting
	* SO MANY SERVICES (and their learning curves)
	* Balanciing disparate systems
	* "Whoopsies" moments

## Logs
* Easiest place to start
* Start with logs, don’t even touch the legacy app.
* Parsing logs to block abusive users and fraudsters.
* HTTP event. File (S3) event. Database (DDB) event.

## Moar Logs
* Let’s finally have Legacy actually talk to serverless
* Tidying up - Let’s get a cron going to periodically remove offending IPs

## Going Big
* Replacing a core component of the legacy app.

## Running user-supplied code
* User code. On our servers? Within our app?!?!?!!
* How to allow enough flexibility? How about allowing straight js?

## Robust documentation and helpers are a good idea.