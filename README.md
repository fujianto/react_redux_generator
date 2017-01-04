# Redux Generator

This generator helps to create all the necessary files for react-redux application. It follows the file structure below. The `frontend` folder is stored at the root directory of the application.

```
// example file structure

frontend
  |- actions
    |- session_actions.js
  |- components
    |- session_form
      |- session_form.jsx
      |- session_form_container.jsx
  |- reducers
    |- root_reducer.js
    |- session_reducer.js
  |- store
    |- store.js
  |- util
    |- api_util.js
  |- app.jsx
```

### Store

To generate a store, run

```
redux generate store
```

or

```
redux g store
```

This will generate `store.js` inside the store folder in the format of:

```js
import { createStore, applyMiddleware } from 'redux';
import rootReducer from '../reducers/root_reducer.js';

const configureStore = (preloadedState = {}) => (
  createStore(
    rootReducer,
    preloadedState,
    applyMiddleware()
  )
);

export default configureStore;
```

### Reducers

**Root Reducer**

To generate a root reducer, run

```
redux g reducer root
```

This will generate a file `root_reducer.js` with the following code:

```js
import { combineReducers } from 'redux';

const rootReducer = combineReducers(
);

export default rootReducer;
```

**Other Reducers**

To generate a reducer, run

```
redux g reducer session
```

This will generate a file `session_reducer.js`. It will have a format of:

```js
import { merge } from 'lodash';

const sessionReducer = (state, action) => {
  Object.freeze(state);
  switch(action.type) {
    default:
      return state;
  }
}

export default sessionReducer;
```