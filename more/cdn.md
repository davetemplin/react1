# How to load React libraries from CDN

## Edit `webpack.config.js` adding the following `externals` definitions...

```js
  externals: {
    "react": "React",
    "react-dom": "ReactDOM",
    "react-router": "ReactRouter"
  }
```

## Edit `index.html` adding the following script tags before the script tag for the app...
```html
    <script src="//cdnjs.cloudflare.com/ajax/libs/react/16.2.0/umd/react.production.min.js"></script>
    <script src="//cdnjs.cloudflare.com/ajax/libs/react-dom/16.2.0/umd/react-dom.production.min.js"></script>
    <script src="//cdnjs.cloudflare.com/ajax/libs/react-router-dom/4.2.2/react-router-dom.min.js"></script>    
```
