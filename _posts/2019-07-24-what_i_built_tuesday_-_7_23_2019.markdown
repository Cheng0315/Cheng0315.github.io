---
layout: post
title:      "What I Built Tuesday - 7/23/2019"
date:       2019-07-24 06:22:58 +0000
permalink:  what_i_built_tuesday_-_7_23_2019
---


This week, I added redux to my Movie-TV-Hub application. First, I installed redux.

```
npm install --save redux
```

Then I installed redux-thunk.

```
npm install redux-thunk
```

Then I added the store file, which contains the create store function from redux and thunk from redux-thunk.

```
import { createStore, applyMiddleware, compose} from 'redux';
import thunk from 'redux-thunk';

const initialState = {};

const middleware = [thunk];

const store = createStore(
  rootReducer,
  initialState,
  compose(
    applyMiddleware(...middleware)
  )
)

export default store;
```

After that, I updated the index.js file to utilize the store variable.

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import store from './store'
import { Provider } from 'react-redux'
import * as serviceWorker from './serviceWorker';

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>, 
  document.getElementById('root')
);
```

And that was what I worked on this week. For next week, I'd like to add in The Movie Database API.
