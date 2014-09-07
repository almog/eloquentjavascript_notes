# Language
  * [Function declaration inside a function expressions](http://eloquentjavascript.net/11_language.html#c_3Dn8ryI9i3)
  * Will the [evaluate](http://eloquentjavascript.net/11_language.html#c_dCjY/Lr6Wt) ever encounter an `apply` expression whose operator type isn't 'word'?
  * Why did [run](http://eloquentjavascript.net/11_language.html#c_hH6wAg7pwu) had to use slice before joining the arguments into string? What's wrong with the following code:

```
  function run() {
    var env = Object.create(topEnv);
    var program = Array.prototype.join.call(arguments, "\n");
    return evaluate(parse(program), env);
  }
```
