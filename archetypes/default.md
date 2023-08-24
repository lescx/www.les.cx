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

tags = []
categories = []
series = []

keywords = []

publishDate = {{ .Date }}
#lastmod = {{ .Date }} # should be based on git commit and then format it in HTML with functions

#outputs =

#
# Custom Params
#

#subtitle = ''
includeToc = true
#hiddenFromHomePage = false
#hiddenFromSearch = false
+++
