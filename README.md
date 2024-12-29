# Making Changes

## Content

The simple layout should make this straightforward. Add/delete content following the general structure of the HTML.

### Adding an Abstract

Abstracts use a `details` container. These come immediately after the `paragraph` tag they're meant for. There are a couple of examples in the research page.

The structure is as follows:

```
<details class="abstract">
    <summary>WHAT'S VISIBLE WHEN THE CONTAINER IS COLLAPSED, 'Abstract' SHOULD DO.</summary>
    PUT THE ACTUAL CONTENT OF THE ABSTRACT HERE.
</details>
```

### HTML Validation

Validate any HTML using the W3C validator [here](https://validator.w3.org/nu/#textarea) before publishing. Fix any errors -- you can ignore warnings if you have to.

## Styling

Styling changes will involve either editing `assets/css/styles.css` or adding one or multiple utility classes (declared in `assets/css/utils.css`) to the HTML.

There are utility classes covering most common styling cases. Ideally the `utils` file should not be edited. If for some reason you want to make changes to a utility class, duplicate it in `styles.css`. Things are set up so that any conflicting rules in `styles.css` automatically override their counterparts in `utils.css`.

```html
<p>This is just a paragraph.</p>

<p class="text-center">
  This is a paragraph with one util class centering the text.
</p>

<p class="text-center uppercase">
  This is a paragraph with two util classes. Any number of classes can be added
  as a space-separated list. If an element already has classes just tack on any
  additional ones you need to.
</p>
```

For now, the most straightforward to use are the text-related utils (look at `utils.css`), and the following:

- `hidden` makes it possible to remove something (temporarily) without deleting its HTML.

  ```html
  <p class="hidden">This is a paragraph that is not visible.</p>
  ```

- `invisible` is similar to `hidden`, in that the element becomes invisible, however `hidden` removes the element from the document, while `hidden` leaves it occupying the same space it occupied, just not visible. This is useful for when you want to hide something without creating a "vacuum" where it used to be. Experiment with both to see the difference.

  ```html
  <p class="invisible">
    This paragraph is not visible, but still takes up space.
  </p>
  ```

More utils can be added depending on commonly made changes.

### Colours

The main colour scheme can be changed by updating the variables declared at the top of `styles.css`.

Unambiguous colours (e.g. black, white) can be declared by name. For other colours, you can find hex codes online. [colorhunt.co](https://colorhunt.co) is great for this.

### Other

Font weight is represented by a number (more precise than just saying `bold` or `regular` -- still OK to use, just less precise). The values for the current font are:

```css
font-weight: 300; /* light */
font-weight: 400; /* regular */
font-weight: 500; /* medium */
font-weight: 700; /* bold */
```

### CSS Validation

Validate your CSS [here](https://jigsaw.w3.org/css-validator/#validate_by_input).

## Notes

- To make a link open in the background add the `target="_blank"` attribute. See the CV link for example.
