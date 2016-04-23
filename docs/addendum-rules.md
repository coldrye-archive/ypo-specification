[Table of Contents](./index.md)

### TBD:Production Rules

```
TRANSLATION_UNIT ::= NEWLINE* COMMENT* NEWLINE* COMMENT* order_independent(OPT_LANG OPT_NS?) AUTHORSHIP* NEWLINE* TRANSLATION+ NEWLINE*

TRANSLATION ::= COMMENT* TRANSLATION_ID VARIATION*

AUTHORSHIP ::= DIR_AUTHORSHIP AUTHOR_INFO NEWLINE

COMMENT ::= DIR_COMMENT TEXT NEWLINE

PLURAL ::= DIR_PLURAL CARDINALITY

TRANSLATION_ID ::= DIR_TID QNAME NEWLINE

VARIATION ::= CONTEXT? OPT_PLURAL? TEXT+

OPT_NS ::= DIR_OPTION WHITESPACE* 'ns' WHITESPACE+ NSNAME WHITESPACE* NEWLINE

OPT_LANG ::= DIR_OPTION WHITESPACE* 'lang' WHITESPACE+ LANGID WHITESPACE* NEWLINE

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

NSNAME ::= NSQNAME ('.' NSQNAME)*

NSQNAME ::= [a-zA-Z0-9$-_]+

QNAME ::= [a-zA-Z0-9$.]+

DIR_AUTHORSHIP ::= '#~'

DIR_COMMENT ::= '#'

DIR_CONTEXT ::= '#@'

DIR_PLURAL ::= '#+'

DIR_TID ::= '#!'

DIR_OPTION ::= '#='

CARDINALITY ::= FIXME

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

