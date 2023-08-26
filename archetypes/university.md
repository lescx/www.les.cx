+++

#
# important websites
# https://gohugo.io/content-management/front-matter/
# https://gohugo.io/variables/page/
#

draft = true

#
# Front matter
#

title = '{{ replace .Name "-" " " | title }}'
description = ''
summary = ''

semesters = 1
modules = ''

keywords = []

publishDate = {{ .Date }}

#outputs =

#
# Custom Params
#

includeToc = true
+++
