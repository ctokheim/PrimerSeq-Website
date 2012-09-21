---
layout: page
title: "Vim"
description: "Vim tricks"
tagline: "{keyboard tricks}"
---
{% include JB/setup %}
<img src="http://www.viemu.com/vi-vim-cheat-sheet.gif" />

## Tabular Vim Cheat Sheet

<table class="table table-striped">
    <thead>
        <tr>
            <th>command</th>
            <th>description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>ci <code>char</code> </td>
            <td>delete contents within surrounding <code>char</code> </td>
        </tr>
        <tr>
            <td><code>num</code> dd</td>
            <td>delete <code>num</code> (optional) # of lines</td>
        </tr>
        <tr>
            <td>? <code>str</code> </td>
            <td>search for <code>str</code> before the current position </td>
        </tr>
        <tr>
            <td>/ <code>str</code> </td>
            <td>search for <code>str</code> after the current position</td>
        </tr>
        <tr>
            <td>:x </td>
            <td>save and quit</td>
        </tr>
        <tr>
            <td>o</td>
            <td>go to the next line and then enter insert mode</td>
        </tr>
        <tr>
            <td>A </td>
            <td>go to end of line and then enter insert mode</td>
        </tr>
        <tr>
            <td><code>num</code> gg</td>
            <td>go to line <code>num</code></td>
        </tr>
        <tr>
            <td>G</td>
            <td>go to last line</td>
        </tr>
        <tr>
            <td>:%! <code>cmd</code></td>
            <td>run the <code>cmd</code> line argument on the vim buffer</td>
        </tr>
        <tr>
            <td>*</td>
            <td>find the next occurence of a word </td>
        </tr>
        <tr>
            <td>#</td>
            <td>find the previous occurence of a word </td>
        </tr>
        <tr>
            <td>:zo</td>
            <td>open a single fold</td>
        </tr>
        <tr>
            <td>:zc</td>
            <td>close a single fold</td>
        </tr>
        <tr>
            <td><code>num</code> yy</td>
            <td>yank (copy) <code>num</code> lines of text</td>
        </tr>
        <tr>
            <td>p</td>
            <td>paste yanked/deleted text</td>
        </tr>
    </tbody>
</table>
