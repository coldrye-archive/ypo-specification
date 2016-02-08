[Table of Contents](./index.md) - [Translation Unit](./unit.md)

### Translation

Each translation in a translation unit is made up of one or multiple variations.

A translation is introduced by a translation id, followed directly by its variations.

*Example*

```
#! fred
yabba dabba doo!

#@ wilma
Wilmaaaa!
```

In the above example ``fred`` is the translation id and ``yabba dabba doo!`` the
default variation. The second variation ``Wilmaaaa!`` is applied only in context,
namely whenever the context id ``wilma`` is passed to i18next.


#### Translation Id

Translation ids must be simple identifiers and are limited to alpha numeric ASCII
strings without any whitespace or similar such separators/delimiters.

```
#! <id>
```

*Examples*

```
#! TheID
#! 123
#! 123id
#! ID123
```


Next in line: [Variation](./variation.md)

