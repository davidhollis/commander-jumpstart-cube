---
title: "{{ replace (replaceRE "^[0-9]+-" "" .Name) "-" " " | title }}"
deckId: "{{ index (split .Name "-") 0 }}"
commander: The Prismatic Piper
colors: wubrg
cards:
    - Black Lotus
status: in-progress
draft: true
---

This is a description of a new deck.