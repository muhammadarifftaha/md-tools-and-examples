# Button Component

## Components

### Button

| Args          | Explaination                                             | Type                           | Required |
| ------------- | -------------------------------------------------------- | ------------------------------ | -------- |
| label         | Label of the button                                      | String                         | No       |
| icon          | Icon of the button                                       | ReactNode                      | No       |
| iconPlacement | Placement of the icon. Default = "right"                 | "left" or "right               | No       |
| variant       | Variant of the button. Default = "primary"               | "primary", "secondary", "text" | No       |
| onClick       | Function to run when the button is clicked               | Function                       | No       |
| href          | Link to go to when the button is clicked                 | String or UrlObject            | No       |
| target        | Target of the link. Default = "\_blank"                  | String                         | No       |
| shallow       | Shallow routing. Default = false                         | Boolean                        | No       |
| aria_label    | Aria label of the button. For use with Icon only buttons | String                         | No       |

## Example

```tsx
import React from 'react'
import { Button } from '@/components/Button'

const ExampleWithLink = () => {
  return (
    <Button
        label="button"
        icon={Icon}
        iconPlacement='right'
        variant="primary"
        href="https://www.google.com"
        target="_blank"
        shallow
        />
    )
}

const ExampleWithOnClick = () => {
  return (
    <Button
        label="button"
        icon={Icon}
        iconPlacement='right'
        variant="primary"
        onClick={function}
        />
  )
}
```

## Styles

Primary :

```js
 initial: {
        background: 'linear-gradient(130deg, #D263DC 0%, #8A58B1 100%)',
        color: 'white',
        backgroundSize: '100% 200%',
    },
  hover: {
        background: 'linear-gradient(490deg, #D263DC 0%, #8A58B1 100%)',
        color: 'white',
        transition: {
            duration: 3,
            bounce: 0,
            damping: 0,
            delay: 0,
            easings: cubicBezier(1, 0, 1, 0),
            repeatDelay: -0.4,
            repeat: Infinity,
            repeatType: 'loop',
        },
    },
```

Secondary :

```js
initial: {
    background: '#F6F1F7',
    color: '#913493',
    transition: { duration: 0.3 },
},
hover: {
    background: '#913493',
    color: 'white',
},
```

Text :

```js
initial: {
    background: 'transparent',
    color: '#913493',
},
hover: {
    background: 'transparent',
    color: '#BC8CBF',
},

```

Primary & Secondary with and without icon :

`rounded-full px-6 py-3 md:py-[18px]`

Primary & Secondary icon only :

`aspect-square rounded-full p-3 md:p-5`

Text with and without icon and Icon only:

`py-3 md:py-[18px]`
