# Reach at Scale

The problem with application tutorials is they are usually terrible because it's either todo or The Mona Lisa.

*Scalability*: How do I respond to bugs for an "unlimited" number of devices.

## Don't avoid local state
    
- Release there is a callback as a second argument for `setState()`

## Hoise local state early and often

- When a child modifies state that is shared, move that state to the parent component and make the child stateless.
- Be constantly evolving application structure / architecture over time.

## Use hooks (on new components)
  
- Classes are not going away, so don't rewrite everything in hooks
- Essentially replace lifecycle events
    - useState => this.setState
    - useEffect => componentDidUpdate
    - useRef => React.createRef
    - eslint-plugin-react-hooks

## Use Suspense (and React.lazy)
- Allows dynamically loading components
- You will want to combine with Webpack

## Don't avoid Redux (hooks are not a replacement)

## Be judicious about what you store in Redux
- API responses
- Data required at nested levels
- Truly global layout state

## Use "selector" functions to read Redux store
- use "Reselect" if you have no strong opinions on how selectors should work.

## Normalize API responses

## Use Webpack
- Use webpack-dev-server (has a built-in change watch mode)

## Optimize fresh starts for new developers
- Determines the most of how fast you can deploy

## Use feature flags
- Never blocked by deploys

```jsx
<Feature fallback={OlfFeature}></Feature>
```

"Can I optimize my directory structure around team responsibilities?"

You will not get it right the first time. Continuous iterating.