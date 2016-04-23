[Table of Contents](./index.md) - [Translation Unit](./unit.md) - [Translation](./translation.md)

### Variation

Each translation consists of one or multiple variations. A variation without a
context and without a pluralization option is considered the default variation.
The default variation must immediately follow the translation id.

Optionally, one can define a context for either of the available variations.
Again, optionally, one can define a pluralization directive for either of the
available variations.

Apart from that, a variation consists of one or multiple lines of text, which
is discussed in the following chapter.

*Example*

```
#! child

# default variation
a child

# male child
#@ male
a boy

# female child
#@ female
a girl

# plural variation for a single child
#+ 1
one child

# plural variation for two children
#+ 2
two children

# ranged plural
#+ 3..100
some children

# indefinite plural
#+ [inf]
a lot of children
```

TODO:refactor to pluralization

The above example translates to the i18next format like this

```
{
  "child": "a child",
  "child_male": "a boy",
  "child_female": "a girl",
  "child_1": "one child",
  "child_2": "two children",
  "child_3": "some children",
  "child_101": "a lot of children",
  "child_plural": "a lot of children"
}
```


#### Variation Context

In order to associate a given variation with a specific context, one can use the
context directive.

Context ids must be simple identifiers and are limited to alpha numeric ASCII
strings without any whitespace or similar such separators/delimiters.

```
#@ <id>
```

*Examples*

```
#@ TheContext
#@ 123
#@ 123context
#@ CONTEXT123
```


#### Variation Options

##### TBD:Plural Directive

```
#+ [<cardinality>]
```


Next in line: [Text](./text.md)

