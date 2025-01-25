# Moodle question bank multi language preview

This plugin adds the convenience of easily selecting other languages when previewing quiz questions. There will be no effect if a quesiton text does not contain any language tags. It will work from anywhere a question can be previewed and has no settings option. it can be enabled and disabled from

It supports three types of language tags and associated filters

* Core Moodle
* Mlang2
* STACK

It makes no changes to core Moodle and it uses the callbacks api. When  quiz question is previewed it makes a database query to search through the quesiton text. If it finds any one of three types of language tags it will create a new dropdown with a list of the languages that are available in the question according to the tags.

When one of the languages is selected. the URL of the preview screen will be updated to include the language code, e.g. &lang=de would be added if German was selected. The current users preferred language is always added to the list of languages.

## Mlang2 tags

https://github.com/iarenaza/moodle-filter_multilang2/blob/master/README.md

```
{mlang de}MLang2 German{mlang}
{mlang es}MLang2 Spanish{mlang}
{mlang no}MLang2 Norweigian{mlang}
```
(remove carriage returns to avoid unwanted blanks when rendered)


## Core Mlang tags
https://docs.moodle.org/405/en/Multi-language_content_filter

```
<span lang="de" class="multilang">Core German</span>
<span lang="es" class="multilang">Core Spanish</span>
<span lang="no" class="multilang">Core Norweigian</span>
```
## STACK (maths) tags
https://docs.stack-assessment.org/en/Authoring/Languages/
```
[[lang code='de']]STACK German[[/lang]]
[[lang code='es']]STACK Spanish[[/lang]]
[[lang code='no']]STACK Norweigian[[/lang]]

```

If the selected language is not reverted to the preferred language before closing the preview screen the users preferred language will be set to what has been selected for the rest of the session.

If a tag references a language that does not have a matching installed language pack the language abbreviation will be shown. For example if the tag no is included but Norwegian, it will show No in the dropdown rather than Norweigian.

