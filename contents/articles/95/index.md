---
title: Setting up Thunk with Redux and React
author: saumya
date: 2020-07-07
template: article.pug
---


This is one of the reasons why getting up and running with [Redux][r3] may take sometime. The setting up of the whole thing takes time. And it may take more time, if you want to setup this after you have a working [React][r1] project. To start a [React][r1] project today, it is easy to get up and running with [Create-React-App][r2]. But gluing up [Redux][r3] after that point is a very difficult and confusing process. And then comes [Thunk][r5] which will take some more involvement into it.

<span class="more"></span>

> Do not be carried away by the words. 

The simple meaning of the words are as follows.

 - [Redux][r3] allows the application to use a single central Data Object(ususally called Store)
 - [Thunk][r5] is an addition to [Redux][r3] for Asynchronous calls ( The API calls )

For working with [Redux][r3] inside [React][r1] we need two things.

 - [Redux][r3]
 - [React-Redux][r4]

While [Redux][r3] manages the data in the central data object (Root Store), the [React-Redux][r4] helps wiring-up [React][r1] with [Redux][r3]. The point is, [Redux][r3] could be used in any project where we need a central data management functionality. It is a general purpose library. To use it easily inside [React][r1] applications we need [React-Redux][r4].

```
npm install redux
npm install react-redux
```

That is all for setting up the [Redux][r3] in our application. The `Code` looks like this.

```
//index.js
//The application entry file

import { createStore } from 'redux'
import { Provider } from 'react-redux'

import allInOneReducer from './reducers'

const theAppStore = createStore( allInOneReducer )

ReactDOM.render(
  <Provider store={ theAppStore }>
  <React.Fragment>
    <AppContainer />
  </React.Fragment>
  </Provider>,
  document.getElementById('root')
);
```

Now to interact with the central Store we need to `dispatch` actions from our components and `useSelector` to get data to our component. These are provided by [React-Redux][r4]

```
//AppContainer.js

import { useDispatch, useSelector } from 'react-redux'

let AppContainer = ()=>{
	const dispatch = useDispatch()
	dispatch( changeStatusMessage('Inside AppContainer') )

	const appMessages = useSelector( state=> state.messages )
	return( <div> My Component </div> )
}
export default AppContainer
```

The central Store is stored inside `Reducers` folder in 'index.js'. One of the stores in the central store is 'message'. This is like dividing the central store into small stores of their own.

```
//messages.js inside 'reducers' folder

const initialState = {
    message_string: 'Nothing'
}
const messages = (state = initialState, action )=>{
    switch(action.type){
        case 'NEW_MESSAGE' :
            return { ...state, message_string: action.payload}
        default :
            return state
    }
}

export default messages
```

To complete the Store setup, we need one more thing inside 'reducers' folder, the 'index.js'.

```
//index.js inside 'reducers' folder

import { combineReducers } from 'redux'

import messages from './messages'
import loginReducer from './login_reducer'


const theReducer = combineReducers({
    messages: messages,
    loginData: loginReducer
})
export default theReducer
```


The actions looks like this.

```
//index.js inside 'actions' folder

export const changeStatusMessage = message=> {
    return ({
        type: 'NEW_MESSAGE',
        payload: message
    })
}

```

We are done with [React][r1], [Redux][r3] and [React-Redux][r4]. :) I know.

### Thunk

As it is called the middleware of Redux, we need to initialise it where we are initialising the Redux store. That is the main application entry file.

First install the library in the project.

```
npm install redux-thunk
```

Now setting up the Store in the application entry is modified as this. Notice the use of `applyMiddleware` from 'redux' here.

```
//index.js
//The application entry file

//import { createStore } from 'redux'
import { createStore, applyMiddleware } from 'redux'
import { Provider } from 'react-redux'
import thunk from 'redux-thunk';

import allInOneReducer from './reducers'

//const theAppStore = createStore( allInOneReducer )
const theAppStore = createStore( allInOneReducer, applyMiddleware(thunk) )

ReactDOM.render(
  <Provider store={ theAppStore }>
  <React.Fragment>
    <AppContainer />
  </React.Fragment>
  </Provider>,
  document.getElementById('root')
);
```

The components in the application have to be updated as this. Notice the use of `connect` from 'react-redux' while exporting the component.

```
//AppContainer.js

//import { useDispatch, useSelector } from 'react-redux'
import { connect, useDispatch, useSelector } from 'react-redux'

let AppContainer = ()=>{
    const dispatch = useDispatch()
    dispatch( changeStatusMessage('Inside AppContainer') )

    // This action will use Thunk
    dispatch( someAsyncCall('data') )

    const appMessages = useSelector( state=> state.messages )
    return( <div> My Component </div> )
}

//export default AppContainer
export default connect()(AppContainer)
```

Now we can write Async calls inside our actions. Here is an example.

```
//index.js inside 'actions' folder

export const changeStatusMessage = data=> {
    return ({
        type: 'NEW_MESSAGE',
        payload: data
    })
}


// This is possible because of Thunk.
// Calling an API and changing the state depending upon Success or Fail

export const someAsyncCall = data=>{
	return function (dispatch) {
		call_RestAPI(data).then( 
				function(success){
						dispatch( changeStatusMessage('API call Success') )
					}, 
				function(error){
						dispatch( changeStatusMessage('API call Fail') )
				} 
			)
	}
}

const call_RestAPI = (data) => {
  const url_1 = 'https://some_api_endpoint'
  const fetch_data = {
    method: 'POST', 
    mode: 'cors', 
    headers: new Headers({ 'Content-Type': 'application/json' }),
    body: JSON.stringify(data)
  }
  return fetch(url_1, fetch_data)
}
```

Most important things to remember here are to use `applyMiddleware`, `connect`. One is used while setting up the Store and one is used inside the components. And finally keep an eye on how to write an Async action and call the APIs.




Happy coding.


























[r1]: https://reactjs.org/
[r2]: https://create-react-app.dev/
[r3]: https://redux.js.org/
[r4]: https://react-redux.js.org/
[r5]: https://github.com/reduxjs/redux-thunk







