## GO(lang)
    - compiled statically typed language
    - has garbage collection
    - built in concurrency
    - mascot is a gopher
    - interpreted vs compiled
    - 2.5 times faster than PHP
    - go formatter
    #### Go Structure
        - package (like namespace)
        - import (like use statement)
        - main (every go has to have)
        - Studly is public
    #### build steps
        - go build <file>
    #### run Go code
        - go run <file>
    #### GOPATH
        - 
        - going away Modules added in 1.11+
            - no more $GOPATH
            - projects can live anywhere on disk
            - package management integrated directly into the Go toolchain
            - requires semver
            - converts from dep Gopkg.lock file or 9 other dependecy formats
    #### What can you build with GO?
        - command line apps
        - bash scripts
        - PHP accells at the web lever GO accells at anything below that
        - Its possible to build websites with GO
    #### Concurrency vs Parrallelism
        - concurrency: two threads are making progress
        - Parrelism: two threads are executing simultaneously
    
    #### Go routines
        - `go myFunction`
        - can use wait groups to manage concurrent thread finishing
        ##### Channels
            - pipes or ques you send and receive data
            - `
