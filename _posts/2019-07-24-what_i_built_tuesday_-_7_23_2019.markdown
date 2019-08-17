---
layout: post
title:      "What I Built Tuesday - 7/23/2019"
date:       2019-07-24 02:22:59 -0400
permalink:  what_i_built_tuesday_-_7_23_2019
---


To add redux to my application, I used the following command.

`
npm install --save redux
`

And to add redux-thunk, I used the following command.

`
npm install redux-thunk
`

After that, I added the store file, which contains the 'createStore()' function and the middleware 'thunk'.

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

Then, I updated the index.js file to utilize the store variable.

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
