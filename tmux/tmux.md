



## **tmux notes**

Send commands:



*   from command line such as “tmux attach”
*   from shortcuts using the default prefix ctrl-b then the shortcut
*   from command mode by entering prefix : then typing the word command

Change the default prefix from ctrl-b

add the following to .tmux.conf

The default tmux server name is default, which is stored in /tmp/tmu-1000 directory

Windows shortcuts


<table>
  <tr>
   <td>create new window
   </td>
   <td>Prefix + c
   </td>
  </tr>
  <tr>
   <td>previous window
   </td>
   <td>Prefix + p
   </td>
  </tr>
  <tr>
   <td>next windows
   </td>
   <td>Prefix + n
   </td>
  </tr>
  <tr>
   <td>rename window
   </td>
   <td>Prefix + ,
   </td>
  </tr>
  <tr>
   <td>choose windows from a list
   </td>
   <td>Prefix + w
   </td>
  </tr>
  <tr>
   <td>named command
   </td>
   <td>Prefix + :
   </td>
  </tr>
  <tr>
   <td>resize window
   </td>
   <td>Prefix + arrow key
   </td>
  </tr>
  <tr>
   <td>switch to window by index number
   </td>
   <td>Prefix + 0-9
   </td>
  </tr>
  <tr>
   <td>close a window
   </td>
   <td>exit
   </td>
  </tr>
  <tr>
   <td>force kill-all processes in unresponseive window
   </td>
   <td>Prefix + &
   </td>
  </tr>
</table>


Panes


<table>
  <tr>
   <td>split horizontally
   </td>
   <td>Prefix + %
   </td>
  </tr>
  <tr>
   <td>split vertically
   </td>
   <td>Prefix + “  or  split-window
   </td>
  </tr>
  <tr>
   <td>switch to another pane
   </td>
   <td>Prefix + arrow key
   </td>
  </tr>
  <tr>
   <td>resize active pane
   </td>
   <td>Prefix + ALT+arrow
   </td>
  </tr>
  <tr>
   <td>resize all panes
   </td>
   <td>hold Prefix + arrow
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>


Sessions


<table>
  <tr>
   <td>create session
   </td>
   <td>tmux new -s backupsession
   </td>
  </tr>
  <tr>
   <td>detach from session
   </td>
   <td>Prefix + d
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>list sessions
   </td>
   <td>tmux list-sessions
   </td>
  </tr>
  <tr>
   <td>reattach to session
   </td>
   <td>tmux attach backupsession
   </td>
  </tr>
  <tr>
   <td>switch to previous session
   </td>
   <td>Prefix + (
   </td>
  </tr>
  <tr>
   <td>switch to next session
   </td>
   <td>Prefix + )
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>


Commands


<table>
  <tr>
   <td>list available sessions
   </td>
   <td>tmux ls
   </td>
  </tr>
  <tr>
   <td>destroy all sessions and kill all processes
   </td>
   <td>tmux kill-server
   </td>
  </tr>
  <tr>
   <td>start multiple servers
   </td>
   <td>tmux -L moo  (socket is moo)
   </td>
  </tr>
  <tr>
   <td>list clients
   </td>
   <td>tmux list-clients
   </td>
  </tr>
  <tr>
   <td>change windows layout
   </td>
   <td>Prefix + space  (cycles through layouts)
   </td>
  </tr>
  <tr>
   <td>reread .tmux.conf
   </td>
   <td>:source-file ~/.tmux.conf   or   tmux source-file ~/.tmux.conf
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>


.tmux.conf

Pane switching with Alt+arrow

bind -n M-Left select-pane -L \
bind -n M-Right select-pane -R \
bind -n M-Up select-pane -U \
bind -n M-Down select-pane -D

Activity Monitoring

setw -g monitor-activity on \
set -g visual-activity on

Highlighting Current Window Using Specified Colour

set-window-option -g window-status-current-bg yellow

tmux tries to read .bash_profile instead of .bashrc.

source ~/.bashrc
