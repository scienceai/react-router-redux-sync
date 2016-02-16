# react-router-redux-sync

Sync params and location from react-router to a redux store.

## Usage

### Higher order component

```js
import { SyncRouting } from 'react-router-redux-sync';
import { Router, Route, browserHistory } from 'react-router'
import { Provider } from 'react-redux';
import App from './App';

render(
  <Provider store={store}>
    <Router history={browserHistory}>
      <Route path="/" component={SyncRouting(App)}>
         ...
      </Route>
    </Router>
  </Provider>,
  document.body
);

```

### Reducers


```js
import { locationReducer, paramsReducer } from 'react-router-redux-sync';
```
