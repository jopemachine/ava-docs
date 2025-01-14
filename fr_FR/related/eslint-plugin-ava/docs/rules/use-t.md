___
**Note du traducteur**

C'est la traduction du fichier [use-t.md](https://github.com/avajs/eslint-plugin-ava/blob/master/docs/rules/use-t.md). Voici un [lien](https://github.com/avajs/eslint-plugin-ava/compare/7542453058c30ebbc79c7bfeb689492fce226d8f...main#diff-17ed83dfe5d8198bdea74504bceedceb) vers les différences avec le master de eslint-plugin-ava (Si en cliquant sur le lien, vous ne trouvez pas le fichier `use-t.md` parmi les fichiers modifiés, vous pouvez donc en déduire que la traduction est à jour).
___
# S'assurer que les fonctions de test utilisent `t` comme paramètre

Traductions : [English](https://github.com/avajs/eslint-plugin-ava/blob/master/docs/rules/use-t.md)

La convention veut que le paramètre dans la fonction de test de AVA soit nommé `t`. La plupart des règles dans `eslint-plugin-ava` sont basées sur cette hypothèse.

### Échoue

```js
const test = require('ava');

test(foo => { // Nom incorrect
	t.pass();
});

test((t, bar) => { // trop d'arguments
	t.pass();
});

test((bar, t) => { // trop d'arguments
	t.pass();
});
```

### Passe

```js
const test = require('ava');

test(() => {
	// ...
});

test(t => {
	t.pass();
});
```
