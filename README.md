# Quadz-Template
This is an example template that can be used in [Quadz](https://github.com/LazuriteMC/Quadz).

## Creating a custom template
There are four components needed in order to create a quadcopter template:
* A model file
  * Must be a geckolib model
  * Name format: `template.geo.json`
* An animation file
  * Must be a geckolib animation
  * Name format: `template.animation.json`
* A texture file
  * Name format: `template.png`
* A settings file
  * Contains metadata related to flight characteristics
  * Name format: `template.settings.json`

## Template ID
Your template ID is the only way that Quadz distinguishes between templates. If you name your template
the same as one of the built in quadcopters, yours will not be loaded. That is why it's important to
make your template ID unique. It must also be completely lowercase.

Additionally, each file within your template must have the template ID in its name. For example, if I created
a template with the ID `rayon-racer`, I would need to name all of my files like so: `rayon-racer.geo.json`, `rayon-racer.animation.json`, `rayon-racer.png`, `rayon-racer.settings.json`.
  
## Animations
You're able to set up your animation however you like. The only constraint is that the animation
must be named `armed`, otherwise it will not play. If you don't want to use an animation for whatever
reason, just create an empty animation and name it `armed`.
  
## Settings
Your settings JSON file should look like the following:
```
{
	"id" : "template",
	"name" : "Example Template",
	"author" : "Joshua Bardwell",
	"width" : 0.6,
	"height" : 0.1,
	"cameraX" : 0.15,
	"cameraY" : 0.1,
 	"mass" : 0.5,
	"dragCoefficient" : 0.04,
	"thrust" : 50,
	"thrustCurve" : 1.0,
	"cameraAngle" : 30
}
```
This template represents a medium sized quadcopter (such as one with 5" propellers). For smaller or larger quadcopter examples, here are some of the settings for Pixel and Voyager:

Pixel:
```
"width" : 0.225,
"height" : 0.125,
"cameraX" : 0.025,
"cameraY" : 0.1,
"mass" : 0.01,
"dragCoefficient" : 0.2,
"thrust" : 0.4,
"thrustCurve" : 1.0,
"cameraAngle" : 5
```

Voyager:
```
"width" : 0.9,
"height" : 0.2,
"cameraX" : 0.43,
"cameraY" : 0.05,
"mass" : 1.2,
"dragCoefficient" : 0.01,
"thrust" : 65,
"thrustCurve" : 0.9,
"cameraAngle" : 20
```

## Creating Models
I recommend using [BlockBench](https://blockbench.net/) for creating custom models. Additionally, you will need to install the Geckolib plugin that comes with BlockBench in order to generate a geckolib geo model and animation file.

## Finishing Up
Your template can either be inside of a folder or a zip file. In either case, it must be placed in the `.minecraft/quadz` directory and it must be named using your template ID. For example, `rayon-racer` or `rayon-racer.zip`.
