# pen

I love using Codepen to hack around with frontend code, but sometimes my pens become too large for something I want to edit in a browser window. This repo is just a boilerplate for a project with ES6 (Babel) and Sass so I can hack around locally. 

In order to easily have multilpe pens on the file system, a couple node modules should be installed globally. Install Babel and Sass globally:

`npm install babel-cli node-sass -g`

Then, add this to `~/.bash_profile`

```
pen() {
    if [ $1 ]
    then
        git clone git@github.com:jsakas/pen.git $1;
        cd $1;
        npm install babel-preset-es2015;
    fi
    node-sass sass --output css --resursive
    babel babel -d js --watch & \ 
    node-sass sass --output css --watch --recursive & \ 
    python -m SimpleHTTPServer 3000;
}
```

### commands

Create pens with `pen <name>` (`pen awesome-pen`)

Edit existing pens with `pen`

### directories

ES6 is written in `babel/` and output to `js/`

Sass is written in `sass/` and output to `css/`

# Happy hacking! ^_^
