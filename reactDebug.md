1.react 刷新 Cannot GET
解决：
```
 devServer: {
        contentBase: devPath,
        historyApiFallback: {
            // Paths with dots should still use the history fallback.
            // See https://github.com/facebookincubator/create-react-app/issues/387.
            disableDotRule: true,
          },
        hot: true
    },
```
