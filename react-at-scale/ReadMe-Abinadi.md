# React @ Scale by Daniel Cousineau

@dcousineau

Scalability means something different to frontend eng. than to backend eng.

On frontend, you can’t horizontally scale the same way. 

## Don’t avoid local state

* Valuable tool
* You are building state apps

## Hoist local state early and often

* components are like a tree, it is okay to pull state changes up the tree, because as app evolves, you will eventually put things into a store.

## Use hooks (on new components)

* Don’t rewrite everything in hooks (classes are not going away)
* Do use hooks with new components
* Replace lifecycle things and do new things
	* useState <= this.setState()
	* useEffect <= componentDidUpdate()
	* useRef <= React.createRef
	* useContext
* Run eslint: eslint-plugin-react-hooks

## Use Suspense (and React.lazy)

* For async DOM updates
* Don’t load what you don’t need

## Don’t avoid Redux (hooks are not a replacement)

## Be judicious about what you store in Redux

* API Responses ("shared cache")
* Data required at deeply nested levels
* Truly global layout state (menu open, etc)

## Use "selector" function to read Redux store

* github.com/reduxjs/reselect

## Normalize API responses based on Domain model

* When you pull in API data, redux is good place to centrally store unique whatever (posts, comments, etc). Then combine all later in component layer

## Use webpack

* Have a discrete step for asset build pipeline
* Webpack is not as painful as it used to be 
* entry -> module -> optimization -> output
	* at each "->" can go to "plugins"

## Use webpack-dev-server 

* Has built-in change/watch mode to speed builds
* Has hot reloading
* Can have local web server

## Optimize fresh starts for new developers

* How fast can you deploy?
	* How fast you can deploy is how fast a new person can get going
	* First place to optimize

## Use feature flags

* You can never guarantee a user is using latest version of you app
* React makes using feature flags simple for display related stuff
* You are never blocked by deploy as you can fix a feature by turning it off while you keep working

## Can you optimize your directory structure around team responsibilities?

* If teams are organized by "product domain," can you organize code around product domain?

## Final thoughts

* If you’re struggling, they’re struggling.
	* Focus on developer ergonomics first, performance later
* You will not get it perfect the first time.
	* Optimize your code for easier refactoring.
