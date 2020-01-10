TOPICS: ChildNode.after
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ChildNode.after()`

The **`ChildNode.after()`** method inserts a set of `Node` or `DOMString` objects in the children
list of this `ChildNode`'s parent, just after this `ChildNode`. `DOMString` objects are inserted
as equivalent `Text` nodes.

## Syntax

```javascript
[Throws, Unscopable]
void ChildNode.after((Node or DOMString)... nodes);
```

| parameter | Description |
| :-- | :-- |
| `nodes` | A set of `Node` or `DOMString` objects to insert. |

### Exceptions

- `HierarchyRequestError`: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Inserting an element

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.after(span);

console.log(parent.outerHTML);
// "<div><p></p><span></span></div>"
```

### Inserting text

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);

child.after("Text");

console.log(parent.outerHTML);
// "<div><p></p>Text</div>"
```

### Inserting an element and text

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.after(span, "Text");

console.log(parent.outerHTML);
// "<div><p></p><span></span>Text</div>"
```

### `ChildNode.after()` is unscopable

The `after()` method is not scoped into the with statement. See `Symbol.unscopables` for more information.

```javascript
with(node) {
  after("foo");
}
// ReferenceError: after is not defined
```

## Polyfill

You can polyfill the `after()` method in Internet Explorer 9 and higher with the following code:

```javascript
// from: https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/after()/after().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('after')) {
      return;
    }
    Object.defineProperty(item, 'after', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function after() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.parentNode.insertBefore(docFrag, this.nextSibling);
      }
    });
  });
})([Element.prototype, CharacterData.prototype, DocumentType.prototype]);
```

### Another polyfill

```javascript
// from: https://github.com/FabioVergani/js-Polyfill_Element.prototype.after/blob/master/after.js

(function(x){
 var o=x.prototype,p='after';
 if(!o[p]){
    o[p]=function(){
     var e, m=arguments, l=m.length, i=0, t=this, p=t.parentNode, n=Node, s=String, d=document;
     if(p!==null){
        while(i<l){
         e=m[i];
         if(e instanceof n){
            t=t.nextSibling;
            if(t!==null){
                p.insertBefore(e,t);
            }else{
                p.appendChild(e);
            };
         }else{
            p.appendChild(d.createTextNode(s(e)));
         };
         ++i;
        };
     };
    };
 };
})(Element);



/*
minified:

(function(x){
 var o=x.prototype;
 o.after||(o.after=function(){var e,m=arguments,l=m.length,i=0,t=this,p=t.parentNode,n=Node,s=String,d=document;if(p!==null){while(i<l){((e=m[i]) instanceof n)?(((t=t.nextSibling )!==null)?p.insertBefore(e,t):p.appendChild(e)):p.appendChild(d.createTextNode(s(e)));++i;}}});
}(Element));
*/
```
