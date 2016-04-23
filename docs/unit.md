[Table of Contents](./index.md)

### Translation Unit

A translation unit consists of a header including translation unit options
and one or multiple translations.

*Example*

```
# (c) 2016 coldrye
# ...

#= lang en-US
#= ns translation

#! fred
yabba dabba doo!

#@ name
Fred Flintstone

#@ wilma
Wilmaaaaa!

#@ barney
Barney, get the bowlders!

#! barney

#@ name
Barney Rubble

#@ fred
huh huh... OK, Fred!
```

The above example translates to the i18next format like this

```
{
  "fred": "yabba dabba doo!",
  "fred_name": "Fred Flintstone",
  "fred_wilma": "Wilmaaaa!",
  "barney_name": "Barney Rubble",
  "barney_fred": "huh huh... OK, Fred!"
}
```


#### Translation Unit Options


##### Language Option

The language option corresponds directly to the standard folder naming scheme
imposed by i18next. While mostly the language option can considered redundant,
it is a mandatory requirement.

```
#= lang <lcid>
```

*Examples*

```
#= lang en
#= lang en-US
```


##### Namespace Option

The namespace option corresponds directly to the i18next translation file name.
While mostly the namespace option can be considered redundant, it is required for
processes where the originating file name ``*.ypo`` does not match the target
i18next JSON file name and thus is a mandatory requirement.

Namespace ids must be simple identifiers and are limited to alpha numeric ASCII
strings including ``$``, ``.``, ``_`` and ``-``. Namespace ids must not contain
any whitespace.

The default namespace is ``translation`` and it can be overridden.

```
#= ns <id>
```

*Examples*

```
#= ns translation
#= ns config-ui
#= ns ui.config.general
``` 


Next in line: [Translation](./translation.md)

