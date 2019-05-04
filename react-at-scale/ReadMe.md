### State is good in front end
    - use the callback when changing state
    - hoist state early and often
    - move state to the parent
    - use hooks (on new components) do not rewrite everything in hooks
    #### Big 4 hooks
        - useState
        - useEffect
        - useRef
        - useContext
    #### Use eslint-plugin-react-hooks
    #### lazyComponents
        - take advantage to dynamically loaded components
    #### Dont avoid redux (hooks are not a replacement)
    #### Be judicious about what you load in redux
        - API responses
        - Data required at deeply nested levels
        - truly global
    #### Use selector functions to read Redux store
        - gives you a nice level of abstraction
    #### Reselect
        - how to structure selectors
    #### Normalize APi responses based on 
    #### Webpack
        - have a discrete (FE) asset build pipeline
        - webpack has 3 config rewquirements mode, entry, output
        - use create react app to look at a complex webpack config
    #### Use Webpack-dev-server
        - has a built in change watch mode
        - allows you to easily code live
    #### html-webpack-plugin
    #### Optimize fresh starts for new developers
        - how quickly can new developers can get setup
        - also is how long it takes to deploy the application
    #### use feature flags
        - never blocked by deploys
        - unblocks forward development progress
    #### optimize directory structure around team responsibilities
### Final thoughts
    - if youre struggling, they're struggling. Focus on developer ergonimics first
        performance later.
    - You will not get it perfect the first time.
        optimize youre code for easier refactoring
    - 
