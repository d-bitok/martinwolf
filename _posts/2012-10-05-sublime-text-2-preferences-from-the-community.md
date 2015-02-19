---
title: Sublime Text 2 Preferences from the Community
author: Martin Wolf
layout: post
permalink: /2012/10/05/sublime-text-2-preferences-from-the-community/
categories:
  - Articles
tags:
  - configuration
  - editor
  - list
  - preferences
  - sublime text 2
---
**A few days ago I asked you to share your [Sublime Text 2 Preferences][1] and you did. That&#8217;s really cool – thanks!**

So today I want to share these configurations with you.

I also got some feedback on my preferences and it seems like `line_padding_bottom` was something a lot of people didn&#8217;t know about but liked very much. But now let&#8217;s see what you&#8217;ve got:

[Ingo Wennemaring][2]:

<pre class="language-javascript"><code class="language-javascript">{
    "bold_folder_labels": true,
    "highlight_modified_tabs": true,
    "color_scheme": "Packages/User/Espresso Soda.tmTheme",
    "find_selected_text": true,
    "font_size": 13,
    "line_padding_bottom": 1,
    "font_face": "SourceCodePro-Regular",
    "highlight_line": true,
    "match_brackets_angle": true,
    "spell_check": true,
    "theme": "Soda Light.sublime-theme",
    "soda_classic_tabs": true,
    "translate_tabs_to_spaces": true,
    "trim_trailing_white_space_on_save": false,
    "word_wrap": true
}</code></pre>

[Alexander Plavinski][3]:

<pre class="language-javascript"><code class="language-javascript">{
    "color_scheme": "Packages/Tomorrow Color Schemes/Tomorrow-Night.tmTheme",
    "draw_white_space": "all",
    "ensure_newline_at_eof_on_save": true,
    "font_face": "Source Code Pro",
    "font_size": 13.0,
    "highlight_line": true,
    "highlight_modified_tabs": true,
    "tab_completion": false,
    "tab_size": 2,
    "translate_tabs_to_spaces": true,
    "trim_trailing_white_space_on_save": true
}</code></pre>

[Felix Triller][4]:

<pre class="language-javascript"><code class="language-javascript">{
    // theme
    "color_scheme": "Packages/Tomorrow Color Schemes/Tomorrow-Night.tmTheme",
    "theme": "Soda Light.sublime-theme",

    // font
    "font_face": "Menlo",
    "font_size": 12.0,
    "font_options": ["subpixel_antialias"],

    // layout
    "bold_folder_labels": true,
    "highlight_line": true,
    "highlight_modified_tabs": true,
    "line_padding_bottom": 2,

    // usage settings
    "draw_white_space": "all",
    "translate_tabs_to_spaces": true,
    "word_wrap": true,

    "spell_check": true,

    "ignored_packages":
    [
        "Vintage"
    ]
}</code></pre>

[@prop79][5]:

<pre class="language-javascript"><code class="language-javascript">{
    "theme": "Soda Dark.sublime-theme",
    "color_scheme": "Packages/Color Scheme - Default/Railscasts.tmTheme",
    "font_face": "Inconsolata",
    "font_size": 14.0,
    "open_files_in_new_window": false,
    "highlight_line": true,
    "word_wrap": false,
    "tab_size": 2,
    "translate_tabs_to_spaces": true,
    "trim_trailing_white_space_on_save": true,
    "ensure_newline_at_eof_on_save": true
}</code></pre>

[Matthias Slovig][6]:

<pre class="language-javascript"><code class="language-javascript">{
    "font_face": "Consolas",
    "font_size": 15.0,
    "word_wrap": "true",
    "highlight_line": true,
    "tab_size": 4,
    "translate_tabs_to_spaces": false,
    "line_padding_bottom": 1
}</code></pre>

[Daniel Ehniss][7]:

<pre class="language-javascript"><code class="language-javascript">{
    "color_scheme": "Packages/Color Scheme - Default/iPlastic.tmTheme",
    "font_face": "Source Code Pro",
    "font_size": 15,
    "word_wrap": true,
    "highlight_line": true,
    "caret_style": "phase",
    "translate_tabs_to_spaces": true,
    "open_files_in_new_window": false
}</code></pre>

 [1]: http://theamazingweb.net/2012/10/02/my-sublime-text-2-preferences/
 [2]: http://wennemaring.de/
 [3]: https://gist.github.com/3817363
 [4]: https://github.com/felixtriller/sublime2-settings/blob/master/Preferences.sublime-settings
 [5]: https://twitter.com/prop79
 [6]: http://50north.de/sublime-text-2-settings/
 [7]: http://depone.danielehniss.de/2012/10/04/sublime-text-2/