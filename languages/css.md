CSS, HTML, and JS are a pain to manage.
There are many tools to manage them.
There are many _good_ tools to mangage them.
Why more?
There is no good answer, more just means more options and dependencies.

I love the style of CSS, I don't entirely love HTML, but I do like it.
JS is JS, I'll let people use Wasm to fix that...


```cr
begin div
  {
    |container : Class|
    color: red;
    background: blue;
  }
  begin p 
    {
      |p : Element|
      font-size: 0.75em
    }
    Hello World!
  end p
end div
```

Translates to

```html
<div class="container">
  <p>
    Hello World!
  </p>
</div>
```

```css
div .container {
  color: red;
  background: blue;
}

div .container p {
  font-size: 0.75em
}
```
