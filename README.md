# Fluid SASS Library

Fluid is a SCSS mixin library based on brilliant work from the individuals at  [utopia.fyi](https://utopia.fyi/)

Add fluid settings into your desired file. We recommend using a _variables.scss file for this.

## Usage

### Sass (<code>.scss</code> syntax)

```text
project/
├── node_modules/
│   └── rfs
│        └── ...
└── scss/
    └── main.scss
```

#### Setup

```scss
// scss/main.scss

@import "../node_modules/fluid/scss";

$fluid-settings: (
  minViewportWidth: 320,
  minFontSize: 21,
  minTypeScale: minorThird,
  maxViewportWidth: 880,
  maxFontSize: 24,
  maxTypeScale: majorThird,
  positiveSteps: 5,
  negativeSteps: 2,
);

@include  ft-generate-classes($fluid-settings);
```

If you're using Webpack, you can simplify the `@import` using the `~` prefix:

```scss
@import "~fluid/scss";
```

#### Generating classes
Fluid automatically generates classes for you. They can be used in the following way:

```scss
// scss/main.scss

@include  ft-generate-classes($fluid-settings);

// Outputs classes based on the $fluid-settings params. 
// By default, it outputs 8 classes: 
// .fluid-step--2,
// .fluid-step--1,
// .fluid-step-0,
// .fluid-step-1,
// .fluid-step-2,
// .fluid-step-3,
// .fluid-step-4,
// .fluid-step-5,
```
