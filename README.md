## Правила написания кода

### БЭМ

Для именования классов рекомендуется использовать [БЭМ-нотацию](https://ru.bem.info/methodology/naming-convention/).

```scss
.block {
    &__element {
        &--modificator {
            // ...
        }
    }
}
```
### Классы состояний

Классы состояний рекомендуется записывать кратко:

```scss
.is-active {
    // ...
}

.is-current {
    // ...
}

.is-open {
    // ...
}

.is-hidden {
    // ...
}
```

### Вендорные префиксы

В SCSS-коде не должно присутствовать вендорных префиксов. Они автоматически расставляются в процессе сборки. Однако существуют исключения и некоторые префиксы необходимо добавлять вручную.

Желательно использовать mixin для решения проблемы и подключать в нужном месте через @include [name]. 

**Неправильно:**

```scss
input {
    -webkit-transition: border-color 0.3s;
    transition: border-color 0.3s;

    &::-webkit-input-placeholder {
        color: #000;
    }

    &:-moz-placeholder {
        color: #000;
    }

    &::-moz-placeholder {
        color: #000;
    }

    &:-ms-input-placeholder {
        color: #000;
    }

    &::placeholder {
        color: #000;
    }
}
```

**Правильно:**

```scss
input {
    transition: border-color 0.3s;

    &::placeholder {
        color: #000;
    }
}
```

##Если же SCSS код не используется в проекте, то использование вендорных префиксов допускается
