[Table of Contents](./index.md) - [Translation Unit](./unit.md) - [Translation](./translation.md)

### Variation

Each translation consists of one or multiple variations. A variation without a
context and without a pluralization option is considered the default variation.
The default variation must immediately follow the translation id.

Optionally, one can define a context for either of the available variations.
Again, optionally, one can define a pluralization option for either of the
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
#= plural 1
one child

# plural variation for two children
#= plural 2
two children

# infinite/indefinite plural variation
#= plural
some children
```

The above example translates to the i18next format like this

```
{
  "child": "a child",
  "child_male": "a boy",
  "child_female": "a girl",
  "child_1": "one child",
  "child_2": "two children",
  "child_plural": "some children"
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

##### TBD:Plural Option

```
#= plural [<cardinality>]
```


Next in line: [Text](./text.md)

