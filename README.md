# YPO File Format Specification

This is the repository for the YPO file format specification.

See the [specification](https://github.com/coldrye-es/ypo-specification/blob/master/docs/index.md) for more information on the file format.


## Releases

See the [changelog](https://github.com/coldrye-es/ypo-specification/blob/master/CHANGELOG.md) for more information.


## Motivation

For my ECMAScript based tools and applications, both in the browser and on the
server, I needed a simple to use and capable t10n/i18n framework.

So, after having reviewed some of the available frameworks, I opted for gettext
and i18next. And, while both gettext and i18next do a great job, both their file
formats put me off.

JSON, while simple to author and read, becomes a major pain in the behind as
soon as the document becomes bigger. Existing editors I use, VI that is, do not
support it well and the overhead induced by the JSON format soon freaked me out.

PO on the other hand is plain text, so this is good and can be handled very well
in my favourite editor. Yet, the PO format does not support the ECMAScript 
domain in combination with i18next very well, so one needs to take short cuts
when it comes to message ids. And while PO is a very good format, it still adds
some noise that I found counter productive when dealing with i18next.

Consequently, the YPO plain text format was born, which is somewhat similar to
the PO format but leaning itself heavily on the i18next specification, while it
gets rid of any notational overhead and sets its focus on simple use and easy
maintenance.


## Project Site

The project site, see (2) under resources below, provides more insight into the project,
including test coverage reports and API documentation.


## Contributing

You are very welcome to propose changes and report bugs, or even provide pull
requests on [github](https://github.com/coldrye-es/ypo-specification).

See the [contributing guidelines](https://github.com/coldrye-es/ypo-specification/blob/master/CONTRIBUTING.md) for more information.


### Contributors

 - [Carsten Klein](https://github.com/silkentrance) **Maintainer**


## Resources

 - (1) [Github Site](https://github.com/coldrye-es/ypo-specification)
 - (2) [Project Site](http://ypo.es.coldrye.eu)

