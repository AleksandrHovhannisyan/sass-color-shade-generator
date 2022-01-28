# sass-color-shade-generator

A function to generate shades of a color in Sass.

## Installation

Install the package using npm/yarn/whatever:

```
npm install sass-color-shade-generator
```

## Usage

Import the function into any Sass file:

```scss
@import "../node_modules/sass-color-shade-generator/generateShades";
```

> Note: You may need to adjust the relative path accordingly depending on where your partial is located relative to your project root.

And use it like so:

```scss
generate-shades($color: hsl(0, 0%, 100%), $n: 10, $type: "darker");
```

This returns a list of `10` colors, each `10%` darker than the provided color:

```
hsl(0deg 0% 90%)
hsl(0deg 0% 80%)
hsl(0deg 0% 70%)
hsl(0deg 0% 60%)
hsl(0deg 0% 50%)
hsl(0deg 0% 40%)
hsl(0deg 0% 30%)
hsl(0deg 0% 20%)
hsl(0deg 0% 10%)
hsl(0deg 0% 0%)
```

**Note**: Duplicates will NOT be removed. So if you want to generate `n` darker shades of `black`, you're going to get `10` copies of `black`. Similarly, for colors that are already quite dark, you may get some colors repeated at the tail end. Same goes for lighter shades.

## API

### `generate-shades`

| Argument | Type                      | Description                                                                  | Required                 |
| -------- | ------------------------- | ---------------------------------------------------------------------------- | ------------------------ |
| `color`  | `Color`                   | The color from which to generate shades. Any valid color format is accepted. | Yes                      |
| `n`      | `Number`                  | The number of shades to generate. Must be a positive integer.                | No (default: `1`)        |
| `type`   | `"darker"` or `"lighter"` | Whether to generate darker or lighter shades of the color.                   | No (default: `"darker"`) |

Returns: a `List` of colors.
