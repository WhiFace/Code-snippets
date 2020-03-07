# Code-snippets
Code snippets for coding works

This code should be placed before the author line in the node JSON file


Sctipt for liveserver and sass watching, autoprefixer and compressor

"scripts": {
    //Sass and css files are created at this stage
    "watch:sass": "node-sass sass/main.scss css/style.css -w",
    
    //Runs the live server plugin
    "devserver": "live-server",
    
    //watches for sass file changes
    "start": "npm-run-all --parallel devserver watch:sass",
    
    //compiles sass file and add new code to css file (compiled)
    "compile:sass": "node-sass sass/main.scss css/style.comp.css",
    
    //Add web prefixes to css attributes to use in older browsers las ten versions
    "prefix:css": "postcss --use autoprefixer -b 'last 10 versions' css/style.comp.css -o css/style.prefix.css",
    
    //File is compressed at this point
    "compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed",
    
    //A build process is activated when this command is called in the terminal
    "build:css": "npm-run-all compile:sass prefix:css compress:css"
  }
