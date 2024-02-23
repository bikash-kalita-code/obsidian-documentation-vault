It is recommended to install `docsify-cli` globally, which helps initializing and previewing the website locally.
`npm i docsify-cli -g`

### Initialize
`docsify init ./docs`

### Preview your site
Run the local server with docsify serve. You can preview your site in your browser on http://localhost:3000.
`docsify serve docs`

### Manually preview your site
If you have Python installed on your system, you can easily use it to run a static server to preview your site.
```bash
cd docs && python -m SimpleHTTPServer 3000
```
```bash
cd docs && python -m http.server 3000
```


## References
- https://docsify.js.org/