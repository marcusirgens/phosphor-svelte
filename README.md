<img src="./meta/phosphor-mark-tight-yellow.png" width="128" align="right" />

# phosphor-svelte

Phosphor is a flexible icon family for interfaces, diagrams, presentations — whatever, really. More icons at [phosphoricons.com](https://phosphoricons.com).

## Installation

```bash
yarn add --dev phosphor-svelte
```

or

```bash
npm install --save-dev phosphor-svelte
```

## Usage

```html
<script>
  import { Horse, Heart } from "phosphor-svelte";
  // or
  import Cube from "phosphor-svelte/lib/Cube"; // for faster compiling
</script>

<Horse />
<Heart color="#AE2983" weight="fill" size="{32}" />
<Cube color="teal" weight="duotone" />
```

### Props

- **color?**: `string` – Icon stroke/fill color. Can be any CSS color string, including `hex`, `rgb`, `rgba`, `hsl`, `hsla`, named colors, or the special `currentColor` variable.
- **size?**: `number | string` – Icon height & width. As with standard React elements, this can be a number, or a string with units in `px`, `%`, `em`, `rem`, `pt`, `cm`, `mm`, `in`.
- **weight?**: `"thin" | "light" | "regular" | "bold" | "fill" | "duotone"` – Icon weight/style. Can also be used, for example, to "toggle" an icon's state: a rating component could use Stars with `weight="regular"` to denote an empty star, and `weight="fill"` to denote a filled star.
- **mirrored?**: `boolean` – Flip the icon horizontally. Can be useful in RTL languages where normal icon orientation is not appropriate.

### Composability

<img src="./meta/cube-rotate.svg" width="128" align="right" />

Components can accept arbitrary SVG elements as children, so long as they are valid children of the `<svg>` element. This can be used to modify an icon with background layers or shapes, filters, animations and more. The children will be placed _below_ the normal icon contents.

The following will cause the Cube icon to rotate and pulse:

```html
<Cube color="darkorchid" weight="duotone">
  <animate
    attributeName="opacity"
    values="0;1;0"
    dur="4s"
    repeatCount="indefinite"
  ></animate>
  <animateTransform
    attributeName="transform"
    attributeType="XML"
    type="rotate"
    dur="5s"
    from="0 0 0"
    to="360 0 0"
    repeatCount="indefinite"
  ></animateTransform>
</Cube>
```

> **Note:** The coordinate space of slotted elements is relative to the contents of the icon `viewBox`, which is a 256x256 square. Only [valid SVG elements](https://developer.mozilla.org/en-US/docs/Web/SVG/Element#SVG_elements_by_category) will be rendered.

## License

MIT © [Phosphor Icons](https://github.com/phosphor-icons)

## Inspiration

- [Phosphor React](https://github.com/phosphor-icons/phosphor-react/)
- [Carbon Icons Svelte](https://github.com/IBM/carbon-icons-svelte/)