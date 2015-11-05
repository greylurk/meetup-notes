# Angular Meetup at Virtuwell

## Agenda
* Sponsors
    - Virtuwell supplies the space
    - SDG supplies the food and beer 
* LFH/LFJ
    - Robert Half is in the house.
* Lighting Talks
	- Commitizen
* Main presentation
	- http://slides.com/jimthedev/getting-started-with-angular-2-and-typescript#/live

## Commitizen - Format your commit messages in git, so you can pull tags and stuff out of git

```
$ npm init
$ git init
$ touch myfile.js
$ ls 
myfile.js package.json
$ git add .
$ git status
On branch master

Initial commit
...
$ git commit -m "I made some changes" 
...
or
... 
$ commitizen init cz-conventional-changelog --save-dev
.... 
$ git cz 
```

Allows project owner to determine what commit formating they want to see their commit messages in

http://github.com/comitizen/cz-cli/

### further investigation
Kent C Dodds.
Validate Commit msg. 
Inquirer? 
Yeoman? 
Semantic Release?

## Main Presentation - Angular 2 & Typescript 1.6 + 
http://slides.com/jimthedev/getting-started-with-angular-2-and-typescript#/live

@JimTheDev Jim Cummins

What we won't cover: 
* Advanced Typescript
* Angular 1 -> Angular 2 Migration
* Animations
* i18n
* Services/Providers
* Form Building (2 way binding)
* Routing - Check out a talk by Brian Ford ( check notes for details)

## Web in 1996 (Or more like 2005)
CSS selectors 

## Web in 2015 - 
Web Components are what Angular 2 uses to modularize CSS and the like. 

TypeScript = JavaScript + Types (but they're duck types) (quack)

Better overall readability in TypeScript
Better Refactoring. 

Some new ES6 Features included. (whoo)

Intellisense is available with TypeScript

Typescript is a superset of JavaScript (ES6).  Rename *.js -> *.ts and you're on your way.

IDEs and compilers can give warnings,

```
var name = "Annabelle";

console.log("Hello " + name);
```

Becomes
```
var name : string = "Annabelle";
console.log("Hello " + name );
```

TypeScript has:
- ES6 Classes, 
- Adds Private variables and methods. (ActionScript style syntax)
- Type inference ( but it can be disabled on the compiler)
- Fun syntactic sugar to add properties by arguments to constructor
	 
Getting bogged down in TypeScript

TypeScript has interfaces (whoo)

TypeScript has Modules. Uses systemjs module style.

### Installing Typescript

```
$ brew install git
$ brew install npm
$ npm install -g typescript tsd
```

TSD describes non-typescript modules and annotates them with types

### Editors
- Adobe Brackets
- Github Atom
- Sublime Text
- JetBrains (WebStorm!)
- Microsoft VS Code

### Typescript in the dev pipeline

* Gulp/Grunt (Broccoli?)
* Webpack / SystemJS / (JSPM?)

### Angular 2 == Components

Annotations?  
Metadata about the class
Components are based off of CSS Selectors 
```
import {Component} from 'angular2/angular2';
import {HairComponent} from '../hair/hair.component';
import {EyesComponent} from '../eyes/eyes.component';

@Component({ 
	selector: 'person',
	template: '
		<hair [color]="'Black'"></hair>
		<eyes [color]="'Brown'" (blink)="blinked($event)"></eyes>',
	directives: [
		HairComponent,
		EyesComponent
	],
	styles: '
	  hair { height: 150px; }
	  eyes { border-radius: 50%; }
	'
})
export class Person{
	blinked(eyeColor: string) {
		
	}
}
```

```
import {Component} from 'angular2/angular2';

@Component({
	selector: 'eyes',
	outputs: ['blink'],
	inputs: ['color'],
	template: '
	  <eye (click)="blink('Blue')">
	'
})
export class EyeComponent{
}
```
We have both types of Brackets, Square *and* round


### Further Reading
Check out the starter projects: 
https://github.com/pkozlowski-opensource/ng2-play
https://github.com/pkozlowski-opensource/ng2-play.ts
https://github.com/angular-class/angular2-webpack-starter

Check the slides for more. Lots of good learning, community, refs to Jim Cummins' dox.
