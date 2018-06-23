# Matroska EBML Parser - mkinfo.js #
An offline JavaScript parser for [matroska](https://matroska.org/) files (up-to-date mk-parser).  
This is not a substitute for the amazing [MediaInfo](https://mediaarea.net/en/MediaInfo) program.

#### Coming soon™

## Installation ##

``` javascript
// At the moment, there is no named export
import mkinfo from "./lib/mkParser.mjs"
```

:warning: The sources heavily rely on **ES6**. It should work on modern browsers.  
:information_source: For older browsers, a Babel-transpiled bundle is shipped in Releases.

## How to use ##

The main function is `new()` (I have to find a better name).  
It receives a *Blob* (the matroska file) as a single argument and returns a *Promise* resolving with the infos (graph below).

``` javascript
// e.g. <input type='file' multiple>
document.querySelector('input[type="file"]').addEventListener(
  'change',
  function () {
    filesArray = [...this.files]

    Promise.all(filesArray.map(f => mkinfo.new(f)))
    .then(
      resolvedInfos => {

        for (file of resolvedInfos)
          console.log(file.infos)

      },
      console.error
    )
  },
  false
)
```

## Graph ##

Soon™

## License ##

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">mkinfo.js</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/Phoenix35/mkinfo.js" property="cc:attributionName" rel="cc:attributionURL">Phoenix35</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
