1. What is flex?: The **`flex`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties) sets how a flex _item_ will grow or shrink to fit the space available in its flex container.
2. flex-grow, flex-shrink, flex-basis를 한 번에 쓸 수 있는 축약형 속성
3. Flex is a CSS layout mode that arranges elements within a container so that they use the available space efficiently. It allows elements to be aligned horizontally or vertically, and distributed evenly within the container. Flex elements can be resized dynamically based on the available space.

- 보충 더 필요..


```css
.item { 
flex: 1; 
/* flex-grow: 1; 
flex-shrink: 1; 
flex-basis: 0%; */ 
flex: 1 1 auto; 
/* flex-grow: 1; 
flex-shrink: 1; 
flex-basis: auto; */ 
flex: 1 500px; 
/* flex-grow: 1; 
flex-shrink: 1; 
flex-basis: 500px; */ 
}
```