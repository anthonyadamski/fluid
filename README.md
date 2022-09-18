# Liquid Type SASS Plugin

Liquid is a SCSS mixin library based on brilliant work from the individuals at [utopia.fyi](https://utopia.fyi/)

Add liquid settings into your desired file. I recommend using a _variables.scss file for this.

## Usage

#### Setup

```scss
// scss/app.scss

@import "liquid-type.scss";

$liquid-type-settings: (
  baseFontSize: 16px,
  minViewportWidth: 320px,
  minFontSize: 21px,
  minTypeScale: minorThird,
  maxViewportWidth: 1140px,
  maxFontSize: 24px,
  maxTypeScale: majorThird,
  singleStep: null,
  negativeSteps: 3,
  positiveSteps: 4,
);

@include liquid-type-generate-classes($liquid-type-settings);

h1 { @extend .lt-4; }
h2 { @extend .lt-3; }
h3 { @extend .lt-2; }
h4 { @extend .lt-1; }
h5 { @extend .lt-0; }
p { @extend .lt-0; }
h6 { @extend .lt--1; }
small { @extend .lt--2; }

// You can also use these directly in your markup. For example:
// <h1 class="lt-4">Hello</h1>
```

#### Generating classes
Liquid type automatically generates classes for you. They can be used in the following way:

```scss
// scss/main.scss

@include liquid-type-generate-classes($liquid-type-settings);

// Outputs classes based on the $liquid-type-settings params. 
// By default, it outputs 8 classes to create a complete typographical octave: 
// .lt--2,
// .lt--1,
// .lt-0,
// .lt-1,
// .lt-2,
// .lt-3,
// .lt-4,
// .lt-5,
```
