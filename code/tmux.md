---
layout: page
title: "Tmux"
description: "tmux"
tagline: "{like screen but better}"
---
{% include JB/setup %}

Tmux is a relatively recent replacement for GNU screen. It can perform many of the tasks
screen is typically is used for:

* Running code while logged off from a server
* Split screen
* Pair-programming

However tmux is easily configureable especially compared to screen. Tmux has a `.tmux.conf` file in your home directory
where you can change key bindings and other options. Also, unlike screen, tmux is still under active development.

The typical tmux command is done using `<Cntrl-b>` then a following letter. Since this is hard to type (and is different then screen),
I changed the command prefix to `<Cntrl-a>` in my [.tmux.conf](https://github.com/ctokheim/dotfiles/blob/master/.tmux.conf).
In addition I actually remap my Caps Lock key to Cntrl so that I can hit `Cntrl-a` by pressing `CapsLock-a`.

## Tmux tricks

The tmux hierarchy is the following:

    1. session - holds all the windows, you can detach sessions
        2. window - everything that you can see at one time
            3. pane - one part of your split screen

### Command line

To just start tmux type `tmux`.
Use `tmux ls` to list available tmux sessions to reattach to. The first number
on each line will be the session number. To attach to a specific session type `tmux att -t num`.

### Keyboard

Remember all the following commands should be prefixed with `cntrl-a` instead
of `Cntrl-b` since I use a custom mapping. I try to note when my custom mappings
differ between the default.

<table class="table table-striped">
    <thead>
        <tr>
            <th>command</th>
            <th>description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>d</td>
            <td>detach tmux session </td>
        </tr>
        <tr>
            <td>"</td>
            <td>split your window vertically</td>
        </tr>
        <tr>
            <td>%</td>
            <td>split your window horizontally</td>
        </tr>
        <tr>
            <td>c</td>
            <td>create a new window in your session</td>
        </tr>
        <tr>
            <td>n</td>
            <td>go to the next window</td>
        </tr>
        <tr>
            <td>j</td>
            <td>go to the pane below your current pane (custom mapping)</td>
        </tr>
        <tr>
            <td>h</td>
            <td>go to the pane to the left of your current pane (custom mapping)</td>
        </tr>
        <tr>
            <td>k</td>
            <td>go to the pane above your current pane (custom mapping)</td>
        </tr>
        <tr>
            <td>l</td>
            <td>go to the pane to the right of your current pane (custom mapping)</td>
        </tr>
        <tr>
            <td>ampersand</td>
            <td>kill current window</td>
        </tr>
        <tr>
            <td>x</td>
            <td>kill current pane</td>
        </tr>
        <tr>
            <td>alt-<code>arrow-key</code></td>
            <td>reisize the pane</td>
        </tr>
        <tr>
            <td><code>Cntrl-d</code> (without <code>Cntrl-a</code>)</td>
            <td>logout of whatever your in</td>
        </tr>
    </tbody>
</table>
