# How to layout a Javascript project
A guide for the uninitiated

## CSS/LESS/SCSS/STYLUS

Bootstrap framework is a great example on how to layout your css files


Below is a basic example

```
forms.scss
mixins/
	grid.scss
	border-radius.scss
	gradients.scss
buttons.scss
type.scss
print.scss
alerts.scss
modals.scss
variables.scss
responsive.scss
utilities.scss

```

**Do not to start a new project without using bootstrap or another css framework, you will be creating more work for yourself and others.**

## Componentising

### Grouping by components or features

This allows others to find specific files associated with your feature and keep the stylesheets clean and namespaced

```
\myFeature
	myFeature.html
	myFeatureModel.js
	myFeatureView.js		
	myFeature.scss

```


## anti-patterns

MVC is an architecture not a folder structure

```
\myApp
	views\
		view1.html
		view2.html
	models\
		view1Model.js
		view2Model.js

```

Although this may look good now, times those files by 10 and it becomes a big mess!

This might have worked for Java but it doesn't work with web based projects
