# YPO Format Specification

The YPO file format makes it rather easy to author translations to be used with i18next2.







#### Translation ID

Translation ids are alpha numeric identifiers.

**Examples**

```
#! message
#! hierarchical.message.id
#! 1
```


#### Variation 

A variation is introduced by optional variation options such as plural, followed by plain text,
either a single line or multiple lines.

Leading '#' must be escaped using the standard escape character '\'. Remember 'C:\'
or 'namespace foo\bar;'? Well, these are weird, but here it makes sense as you do not
want your messages to be interpreted as comments, or, even worse, as directives.

You may use line continuation. In order to introduce forced new lines, use ``\n`` at the
start of the line.

**Example**

```
# Comment
#! msg.child
child

# Comment
#= plural
children \
and more to come

#= plural 2
two children

# Comment
#= plural 3
three children

#= plural 4
many children
\n
any other hobbies?
```


### Production Rules


```
TRANSLATION_UNIT ::= NEWLINE* COMMENT* NEWLINE* COMMENT* order_independent(OPT_LANG OPT_NS?) AUTHORSHIP* NEWLINE* TRANSLATION+ NEWLINE*

TRANSLATION ::= COMMENT* TRANSLATION_ID VARIATION*

AUTHORSHIP ::= DIR_AUTHORSHIP AUTHOR_INFO NEWLINE

COMMENT ::= DIR_COMMENT TEXT NEWLINE

TRANSLATION_ID ::= DIR_TID QNAME NEWLINE

VARIATION ::= CONTEXT? OPT_PLURAL? TEXT+

OPT_NS ::= DIR_OPTION WHITESPACE* 'ns' WHITESPACE+ NSNAME WHITESPACE* NEWLINE

OPT_LANG ::= DIR_OPTION WHITESPACE* 'lang' WHITESPACE+ LANGID WHITESPACE* NEWLINE

OPT_PLURAL ::= DIR_OPTION WHITESPACE* 'plural' (WHITESPACE+ (NUMBER))? WHITESPACE* NEWLINE

AUTHOR_INFO ::= one_or_all_of(AUTHOR_NAME, AUTHOR_ALIAS, AUTHOR_EMAIL) AUTHOR_URL?

AUTHOR_NAME ::= <word> (WHITESPACE+ <word>)*

AUTHOR_ALIAS ::= ['"] <word> ['"]

AUTHOR_EMAIL ::= '<' <email-address> '>'

AUTHOR_URL ::= '(' <url> ')'

CONTEXT ::= DIR_CONTEXT WHITEPSPACE* QNAME NEWLINE

TEXT ::= ESCAPED_DIRECTIVE? <text> NEWLINE|LINE_CONTINUATION

LINE_CONTINUATION ::= '\'

NEWLINE ::= '\r\n' | '\n' | '\r'

NUMBER ::= [0-9]+

NSNAME ::= QNAME ('.' QNAME)*

QNAME ::= [a-zA-Z0-9$]+

DIR_AUTHORSHIP ::= '#~'

DIR_COMMENT ::= '#'

DIR_CONTEXT ::= '#@'

DIR_TID ::= '#!'

DIR_OPTION ::= '#='

ESCAPED_DIRECTIVE ::= '\#'

WHITESPACE ::= <single-character-whitespace>
```


```
<text> : text including whitespace and escape sequences such as \n and so on

<word> : alpha-numerical excluding any whitespace

<email-address> : should be a valid email address

<url> : needs to be a url with the http(s) scheme, other schemes will be rejected

<single-character-whitespace> : [ \t]
```

