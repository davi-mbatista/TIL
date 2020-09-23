# CSS: Content visibility

The `content-visibility` property allows you to control the visibility of elements on the page in a way that gives you actual performance benefits when compared to other properties that achieve the "same" visual effect. This property will tell the browser which elements/content it can skip the rendering phase. There are many values that can be used with `content-visibility`: `auto`, `layout`, `style`, `paint`, `size`, `hidden`. For example, you chunk content in a way that makes sense to your application and then apply the following property:

```css
.element {
  content-visibility: auto;
}
```

In shorts: This will effectively tell the browser do the rendering job of the object once it approaches the visible area.

**Note:** One thing to keep in mind is that this can cause shifting on the page if the element depend on content for its size. So, to avoid any jump, you should couple `content-visibility: auto` property along with `contain-intrinsic-size` because it will "act as a placeholder size in lieu of rendered content."

```css
.element {
  content-visibility: auto;
  contain-intrinsic-size: 200px;
}
```

> contain-intrinsic-size: "...effectively specifies the natural size of the element if the > element is affected by size containment"

There is also `content-visibility: hidden` that will give you more control over when the element should be actually rendered. Neat!

For more follow the [web.dev article about the content-visibility property](https://web.dev/content-visibility/)
