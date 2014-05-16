grails-yeoman-angularjs-integration
===================================

grails integrate with yeoman angularjs

#environment setting
install [node.js](http://nodejs.org/)
install [yeoman](http://yeoman.io)

#git clone and test
```
git clone https://github.com/makersu/grails-yeoman-angularjs-integration.git
cd grails-yeoman-angularjs-integration/
npm install
grunt serve
grails run-app
```

#create grails application
`grails create-app grails-yeoman-angularjs-integration`

#integrate with yeoman angularjs
##create yeoman angularjs app
```
cd grails-yeoman-angularjs-integration/
yo angular
bower install bootstrap-css --save
bower install angular-bootstrap --save
grunt serve (test yeoman)
```
##integrate with grails
###move resources
```
mv app/* web-app/
mv app/images/* web-app/images/ 
```
###edit .bowerrc
```
{
    "directory": "web-app/bower_components"
}
```
###edit Gruntfile.js
```
...
yeoman: {
      // configurable paths
      app: require('./bower.json').appPath || 'web-app',
      dist: 'dist'
    },
...
```
###edit bower.json
```
...
,"appPath": "web-app"
```
###edit grails-app/conf/UrlMappings.groovy
```
...
"/"(uri:"/index.html")
...
```

#test grails and yeoman
```
grunt serve
grails run-app
```
