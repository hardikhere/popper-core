# Detect Overflow

The detectOverflow modifier can signal other modifiers when
a popper element is scheduled to be positioned outside a given
boundary, or container element.

By default, the boundary element is set to the closest scrolling
clipping container, which, in other words, is a container with
scrollbars, that can potentially hide the popper if the latter
is positioned outside of the visible container area.

If none of these containers is found, it will fallback to the
page viewport, which is the visible document area.

We can define an arbitrary boundary element, we just need to
make sure the custom element is a parent of the popper element.

```js
new Popper(reference, popper, {
  modifiers: [
    {
      name: 'detectOverflow',
      options: {
        boundaryElement: document.querySelector('#custom'),
      },
    },
  ],
});
```