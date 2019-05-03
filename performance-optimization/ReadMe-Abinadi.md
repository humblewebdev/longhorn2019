# Performance Optimi$ation: How Do I Go About It? by Kat Zien

https://joind.in/talk/09F01
@kasiazien

## Why
* fast is better than slow (duh)
* memory efficient is good
* saving money is good
* running out of memory in production is bad
* suddenly running out of memory in production is really BAD
* language and hardware only take you so far

## When
* development
* load testing
* monitoring production

## What
* execution time/no. of operations
* memory usage/allocation
* design (concurrency)
* server (eg. opcache settings)
* hardware (throwing money at the problem)

## Issues
* Memory leaks
* timeouts
* if concurrency: race conditions, deadlocks/livelocks
* redundancy/inefficiency

## Micro Optimisations (99% of the time, ignore them every time)
* Watch out for DB queries inside loops
* use `empty($array)` instead of `count($array) === 0`
* use $a === $b instead of `strcmp`
* use single quotes instead of double
* foreach vs array_walk
* use regex/don’t use regex

## How (what most people get stuck on)
* Do I know what to improve?
* Do I know what my app is doing?
* Do I know what my app can handle?
* Measure
	* Do I measure?
	* Do I know how to measure?

## Tools
* Monitoring
* Load testing/benchmarking
	* eg. go-wrk, k6, pewpew, jmeter, gatling+taurus, ApacheBench, curl-loader, httperf, vegeta, a really loop in your code...
* Profiling
* Visualising
* Off the shelf
	* blackfire.io
	* datadog
	* New Relic

## Tools for PHP
* Not built into language :(
* Roll your own?
	* `$start_time ... $end_time`
* Extensions
	* package managers: brew/yum/apt
	* PEAR/PECL: pecl install <name>
	* Compile from source
* Profilers
	* xdebug
		* + qcachegrind/kcachegrind for GUI
	* xhprof
		* PHP 7 forks from tideways, patrickallaert, or longzinH
	* adsr/phpspy (linux only)
	* php-meminfo

## Diagnostics before Diagnosis
* github.com/brunty/cigar
* Baseline first
* Setup xhprof
* View results (baseline)
* setup xdebug
* install qcachegrind/kcachegrind
* run... look at time breakdown
* Look for big empty sqares in Callee Map
* View Call Graph
* View source code within qcachegrind/kcachegrind

## Memory leaks
* php-meminfo
* Comes with own command line analyser `summary`

## Generating flamegraphs
* phpspy
* xhprof_sample_enable() / xhprof_sample_disable()

## Takeaways
* Do I need to do this? (The best possible optimization.)
* Prioritise (Gains vs Effort)
	* design changes trump code changes, usually
* Customise to your needs
* Measure everything. Use data to prove your guesses. (careful in prod)
* Iterate. Optimization is an iterative process.
