# Setting up a NodeJS server
### npm init
```
npm init
```
> Initiates Project, Creates packages.json , ...
### npm install
```
npm istall
```
> installs dependencies listen in packages.json
```
npm install ...
```
> install ..., Adds to packages.json
```
npm install -g ...
```
> install dependencies globally
```
npm install -D ...
```
> install DEV dependency, also installs dependencies and their dependencies.
### npm Packages
```
nodemon 	(auto restart server on changes)
```
### Node Console
```
node
```
> go into javascript console
```
ctrl+C
```
> exit javascript console

# IMPORT REQUIRE
### Make a file `people.js` with an object
```
const person = {
	name: 'john',
	age: 30
};

module.exports = person
```
### require `person` in `index.js` and use object in other file.
```
const person = require('./person');
console.log(person);
```
> {name: 'john',age: 30}
# OBJECT CONSTRUCTOR
```
class Layer {
	constructor(name,age){
		this.name = name;
		this.age  = age;
	}

	greeting(){
		console.log('my name is ${this.name} and i am ${this.age}');
	}
}
```
> my name is john and i am 30
# Path
#### Full Path + filename
```
__filename
```
> path/directory/filename.js

#### Base Filename
```
path.basename(__filename)
```
> filename.js

#### File Extention
```
path.extname(__filename)
```
> .js

#### Directory Path
```
__dirname
```
> path/directory

#### Directory name
```
path.dirname(__filename)
```
> directory

#### Object with all info
```
path.parse(__filename)
```
> {
root: '/',
dir: 'path/directory',
base: 'filename.js',
ext: '.js',
name: 'filename'
}
#### Part of the object
```
path.parse(__filename).base
```
> filename.js
#### Create a path  			(Avoid / \ problems)
```
path.join(__dirname,'test','test.js')
```
> path/dirname/test/test.js
# FileSystem
```
const fs = require('fs');
const path = require('path');
```

#### Create Folder
```
fs.mkdir(path.join(__dirname,'/test'),{}, function(err){
	if (err) throw err;
		console.log('Folder created');
});
```
#### Write File (ASYNC)
```
fs.writefile(path.join(__dirname,'/test','hello.txt'),'Hello World!', function(err){
	if (err) throw err;
		console.log('File OverWritten');

	//Append File (ASYNC)
	fs.appendfile(path.join(__dirname,'/test','hello.txt'),'Add stuff!', function(err){
		if (err) throw err;
			console.log('File Appended');
	});

});
```
## Append File (ASYNC)
```
fs.appendfile(path.join(__dirname,'/test','hello.txt'),'Add stuff!', function(err){
	if (err) throw err;
		console.log('File Appended');
});
```
## Read File
```
fs.readFile(path.join(__dirname,'/test','hello.txt'),'utf8', function(err,data){
	if (err) throw err;
		console.log(data);
});
```
## Rename File
```
fs.rename(path.join(__dirname,'/test','hello.txt'),path.join(__dirname,'/test','renamedfile.txt'), function(err,data){
	if (err) throw err;
		console.log('file renamed');
});
```















