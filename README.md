# animate-css-styled-components

simple port of animate css for styled-components

[![Build Status](https://travis-ci.org/dielduarte/animate-css-styled-components.svg?branch=master)](https://travis-ci.org/dielduarte/animate-css-styled-components)

----------

## instalation

install animate-css-styled-components

```
[sudo] npm i --save animate-css-styled-components
```

## How to use

import animate-css-styled-components module calling global animations

```
import { Wobble, FadeIn, FadeOut } from 'animate-css-styled-components';
```

###### See how import specifics animations [here](https://github.com/dielduarte/animate-css-styled-components/tree/master/docs/specific-animations).

Now, this animation is a component and you can encompassing the desired content within the component.

Example:

```
  <Wobble duration="0.8s" delay="1s">
    <Card>
      card content...
    </Card>
  </Wobble>
```

## Props

 - duration
	 - prop for represent animation-duration
	 - default `1s`
 - delay
	 - prop for represent animation-delay
	 - default `0s`
 - timingFunction
	 - prop for represent  animation-timing-function
	 - default `ease`
 - iterationCount
	 - prop for represent animation-iteration-count
	 - default `1`
 - direction
	 - prop for represent animation-direction
	 - default `normal`
 - fillMode
	 - prop for represent animation-fill-mode
	 - default `both`
 - playState
	 - prop for represent animation-play-state
	 - default `running`
 - display
	 - prop for represent display css property
	 - default `block`

## Examples

See all examples [here](https://dielduarte.github.io/animate-css-styled-components/)

## How to create custom styled animations

You can import BaseAnimation component and create your custom animation

Example:

```
  import { BaseAnimation } from 'animate-css-styled-components';

  //create your custom animation
  const SlideOutDownAnimation = keyframes`
    from {
      transform: translate3d(0, 0, 0);
    }

    to {
      visibility: hidden;
      transform: translate3d(0, 100%, 0);
    }
  `;

  //extend BaseAnimation component and create
  //your custom styled animation
  const SlideOutDown = styled(BaseAnimation)`
    animation-name: ${SlideOutDownAnimation};
  `;

  //export your custom styled animation  
  export default SlideOutDown;
```

now your animation is a styled-component and you can use this like any other styled-component,
passing the all BaseAnimation [props](https://github.com/dielduarte/animate-css-styled-components#props).

# WIP
 - `animate` component, wrapper for all animations with a only component.
