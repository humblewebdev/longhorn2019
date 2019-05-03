### WHY
    - faster is better
    - memory efficient is good
    - 

### When
    - development
    - load testing
    - monitoring production

### What
    - exection time / no of operations
    - memory usage / allocation
    - design (concurrency)
    - server (e.g. opcache settings)
    - hardware

### Goal of performance optimization
    - use as little memory as fast as possible with as little code as possible

### potential issues
    - memory leak
    - timeouts
    - concurrency: race conditions, deadlocks/livelocks
    - redundancy/inefficiency

### sane advice
    - dont evaluate  in your loop condition, do it once before the loop
        - `for($i=0, $count = count($array)

### micro optimizations (99% of the time, ignore them every time)
    - use empty instead of count($array) === 0
    - ues $a===$b instead of strcmp($a, $b) === 0
    - use single quotes
    - foreach vs array_walk
    - use regex
### How
    - do I know what to improve?
    - do I know what my app is doing?
    - do I know what my app can handle?
    #### Measure
        - do I measure?
        - 
    ### Tools
        - monitoring
        - load testing/benchmarking
            - go-wrk, k6, pewpew, jmeter, gatling+taurus, 
            ApacheBench, curl-loader, httpperf, vegeta a really big loop in your code
        - profiling
        - visualising
        #### Off the shelf
            - backfire.io
            - datadog
            - new relic

        #### Tools for PHP
            - not built into the language
            - roll your own?
                $start_time = microtime(true)
                //do stuff
                $end_time = microtime(true);
        
        #### profiler
            - xdebug
                - qchachegrind/kcachefrint for gui
            - xhprof
                - pgp 7 forms from tideways, patrickallaert or longxinH
            - adsr/phpspy (Linux only at the momoent, WIP)
            - php-meminfo
        #### Diagnostics
        
        #### Capture Baseline
            - setup xhprof
            - setup xdebug
            - install qcachegrind(mac)/kcachegrind
                - visualition tool
                    
        #### Generate flamegraphs
            - phpspy or
            - 
