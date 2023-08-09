# Accordion Component

## Components

### Accordion.Container

Used to encapsulate the Accordion components. Required for the Accordion to work.

| Args         | Explaination                                                                                                                                  | Type                      | Required |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- | -------- |
| children     | One or More Accordion Components components                                                                                                   | ReactNode[ ] or ReactNode | Yes      |
| className    | Class Name                                                                                                                                    | string                    | No       |
| global       | Whether global controls are enabled. Not suitable to be used with separate Tabs and Panels. Only use Items as children. Default value = false | boolean                   | No       |
| title        | Title of the Accordion. Displayed with the global controls button                                                                             | String                    | No       |
| single       | Whether only one item can be open at a time. Default value = false                                                                            | boolean                   | No       |
| scroll       | Whether the container should scroll when the panel is opened. Default value = false                                                           | boolean                   | No       |
| scrollHeight | Height of the container when the panel is opened. Default value = 300 (300px)                                                                 | string or number          | No       |
| alwaysOpen   | Whether there should always be at least 1 panel open. Only works with single = true. Default value = false                                    | boolean                   | No       |

### Accordion.Item

Item Included both Accordion.Tab and Accordion.Panel. Includes spacing for the panel. Not to be used with Accordion.Tab or Accordion.Panel.

| Args        | Explaination                                                         | Type                      | Required |
| ----------- | -------------------------------------------------------------------- | ------------------------- | -------- |
| index       | Index of the item. Used to identify the item                         | string                    | Yes      |
| children    | Components inside the collapsable panel                              | ReactNode[ ] or ReactNode | Yes      |
| className   | Class Name                                                           | string                    | No       |
| title       | Title of the Accordion Item. Displayed in the button                 | ReactNode or String       | Yes      |
| subtitle    | Subtitle of the Accordion Item. Displayed in the button under title. | ReactNode or String       | No       |
| defaultOpen | Whether the item is open by default. Default value = false.          | boolean                   | No       |

### Accordion.Tab

Tab is the button that is used to open the panel. It is a child of Accordion.Item buyt can be used seperately. To ensure functionality, the index of the tab must match the index of the panel.

| Args     | Explaination                                                         | Type                | Required |
| -------- | -------------------------------------------------------------------- | ------------------- | -------- |
| index    | Index of the item. Used to identify the item                         | string              | Yes      |
| title    | Title of the Accordion Item. Displayed in the button                 | ReactNode or String | Yes      |
| subtitle | Subtitle of the Accordion Item. Displayed in the button under title. | ReactNode or String | No       |

### Accordion.Panel

Panel is the collapsable panel that is opened when the tab is clicked. It is a child of Accordion.Item but can be used seperately. To ensure functionality, the index of the panel must match the index of the tab.

| Args     | Explaination                                 | Type                      | Required |
| -------- | -------------------------------------------- | ------------------------- | -------- |
| index    | Index of the item. Used to identify the item | string                    | Yes      |
| children | Components inside the collapsable panel      | ReactNode[ ] or ReactNode | Yes      |

## Example

```jsx
import React from 'react'
// Import as one component
import Accordion from '@components'
// Import as seperate components
import { Container, Item, Tab, Panel } from '@components'

const Example = () => {
  return (
    <Accordion.Container>
      // as one component
      <Accordion.Item index="1" title="Item 1">
        <p>Panel 1</p>
      </Accordion.Item>
      // or seperately
      <Accordion.Tab index="2" title="Item 2" />
      <Accordion.Panel index="2">
        <p>Panel 2</p>
      </Accordion.Panel>
    </Accordion.Container>
  )
}
```

## Styling

The Accordion component uses the following classes:

- Container

  - flex w-full flex-col flex-auto overflow-y-scroll

- Item

  - flex w-full flex-col items-center justify-start

- Tab

  - flex w-full flex-row items-center justify-between border-b py-6

- Panel
  - flex w-full origin-top flex-col justify-start gap-4 overflow-hidden
