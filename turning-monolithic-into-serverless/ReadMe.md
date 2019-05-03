### How to modernize
    - Lots of options, but basically:
        - complete rebuild
        - patrial rebuild

    - What is "serverless"?
        
    - How to actually tun a serverless app
        - http requests
        - cron
        - platform specific items like
            - s3
            - sns & sqs
            - cloudwatch logs
     - Make serverless easy with serverless.com
        - YAML-based
        - provider agnostic
        - great ecosystem
        - local dev options
        - open source & enterprise
    - Let's focus on lambda
    
    - The Good
        - Hugely reduced infrastructure overhead & costs
        - can encourage better programming & encapsulation
        - easier path towards modernization
        - Scalability
        - Security
        - Isolation from legact app environment
    - Tha Bad
        - Overheard of "more stuff"
        - Langagues & PHP support
        - Incorporating with deployment procedures
        - Figure out local dev
    - The Ugly
        - Vendor lock-in
        - Cold starts, VPCs & database access
        - output formatting
        - So Many Services
        - Balancing
### Best way to start with serverless is Logs
    - start with handling logs. Don't event touch the legacy app.
    - parsing logs to block abusive users & fraudsters
    - 
