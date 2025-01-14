___
**Note du traducteur**

C'est la traduction du fichier [use-true-false.md](https://github.com/avajs/eslint-plugin-ava/blob/master/docs/rules/use-true-false.md). Voici un [lien](https://github.com/avajs/eslint-plugin-ava/compare/7542453058c30ebbc79c7bfeb689492fce226d8f...main#diff-ddb8eec6553e62e35444366d67672f38) vers les différences avec le master de eslint-plugin-ava (Si en cliquant sur le lien, vous ne trouvez pas le fichier `use-true-false.md` parmi les fichiers modifiés, vous pouvez donc en déduire que la traduction est à jour).
___
# S'assurer que `t.true()`/`t.false()` sont utilisés à la place de `t.truthy()`/`t.falsy()`

Traductions : [English](https://github.com/avajs/eslint-plugin-ava/blob/master/docs/rules/use-true-false.md)

`t.true()` et `t.false()` sont plus strict que `t.truthy()` et `t.falsy`.
Par exemple : si vous avez une fonction `foo()` qui retourne normalement `true`, mais retourne soudainement à la place `1`, `t.truthy(foo())` ne pourra pas attraper ce changement, alors que ce serait le cas avec `t.true(foo())`.
Cette règle impose l'utilisation de `t.true()`/`t.false()` lorsque l'expression testée est connue pour retourner une valeur booléenne.

### Échoue

```js
const test = require('ava');

test(t => {
	t.truthy(value < 2);
	t.truthy(value === 1);
	t.truthy([1, 2, 3].includes(value));
	t.falsy(!value);
	t.truthy(!!value);
	t.truthy(Array.isArray(value));
});
```

### Passe

```js
const ava = require('ava');

test(t => {
	t.true(value < 2);
	t.true(value === 1);
	t.true([1, 2, 3].includes(value));
	t.false(!value);
	t.true(!!value);
	t.true(Array.isArray(value));
});
```
