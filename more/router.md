# How to setup React Router
```
$ npm install react-router-dom --save
$ npm install @types/react-router-dom --save-dev
```

## Add file `src/Home.tsx`...
```jsx
import React from 'react';
const Home = () => <h2>Home</h2>;
export default Home;
```

## Add file `src/Dashboard.tsx`...
```jsx
import React from 'react';
const Dashboard = () => <h2>Dashboard</h2>;
export default Dashboard;
```

## Add file `src/App.tsx`...
```jsx
import React from 'react';
import {BrowserRouter as Router, Switch, Route, Link} from 'react-router-dom';
import Home from './Home';
import Dashboard from './Dashboard';

const App = () => 
    <Router>
      <Switch>
          <Route exact path='/' component={Home} />
          <Route path='/dashboard' component={Dashboard} />
      </Switch>
    </Router>;

export default App;
```

## Replace file `src/index.tsx`...
```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render((<App />), document.getElementById('app'));
```

## Refereces
* [React Router Tutorial Example From Scratch by Krunal](https://appdividend.com/2017/09/12/react-router-tutorial-example-scratch/)