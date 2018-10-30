# Reusing selectors

Common problem when creating Strudel components is too have same selectors present in both
`@El` and `@Evt` decorators. Thanks to template strings this could be simplified, so you can
have a selector in single place (single source of truth).

## Example

```
import { Component, El, Evt } from 'strudel';

const refs = {
    btn: '.button'
}

@Component('.cta')
class CallToAction {
    @El(`${refs.btn}`) button

    @Evt(`click ${refs.btn}`)
    onClick() {
        this.button.text('Clicked');
    }
}
```