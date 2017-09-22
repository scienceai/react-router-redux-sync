# react-router-redux-sync

Sync params and location from react-router (v3) to a redux store.

## Usage

```js
import {
  SyncRouting,
  locationReducer,
  paramsReducer
} from 'react-router-redux-sync';
import React from 'React';
import { render } from 'react-dom';
import { createStore, combineReducers } from 'redux';
import { Provider } from 'react-redux';
import { Router, Route, browserHistory } from 'react-router';

import App from './App';
import reducers from './reducers';

const store = createStore(
  combineReducers(
    Object.assign(
      { location: locationReducer, params: paramsReducer },
      reducers
    )
  )
);

render(
  <Provider store={store}>
    <Router history={browserHistory}>
      <Route path="/" component={SyncRouting(App)}>
        // Your store will now have have access to synced `location` and `params`
        // ...
      </Route>
    </Router>
  </Provider>,
  document.body
);

```
