<!DOCTYPE html>
<html data-markdown-preview-plus-context="html-export">
  <head>
    <meta charset="utf-8" />
    <title>tmux</title>
    <style>.emoji {
  max-width: 1em !important;
}
del {
  text-decoration: none;
  position: relative;
}
del::after {
  border-bottom: 1px solid black;
  content: '';
  left: 0;
  position: absolute;
  right: 0;
  top: 50%;
}
ul.contains-task-list li.task-list-item {
  position: relative;
  list-style-type: none;
}
ul.contains-task-list li.task-list-item input.task-list-item-checkbox {
  position: absolute;
  transform: translateX(-100%);
  width: 30px;
}
span.critic.comment {
  position: relative;
}
span.critic.comment::before {
  content: '\1f4ac';
  position: initial;
}
span.critic.comment > span {
  display: none;
}
span.critic.comment:hover > span {
  display: initial;
  position: absolute;
  top: 100%;
  left: 0;
  border: 1px solid;
  border-radius: 5px;
  max-height: 4em;
  overflow: auto;
}
span.critic.comment:focus > span {
  display: initial;
  text-decoration: underline;
  position: initial;
  top: auto;
  left: auto;
  border: initial;
  border-radius: initial;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
  background-color: transparent;
}

body {
  padding: 2em;
  font-size: 1.2em;
  color: #c5c8c6;
  background-color: #1d1f21;
  overflow: auto;
}
body > :first-child,
body > div.update-preview > :first-child {
  margin-top: 0;
}
body > p,
body > div.update-preview > p {
  margin-top: 0;
  margin-bottom: 1.5em;
}
body > ul,
body > div.update-preview > ul,
body > ol,
body > div.update-preview > ol {
  margin-bottom: 1.5em;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  line-height: 1.2;
  margin-top: 1.5em;
  margin-bottom: 0.5em;
  color: #ffffff;
}
h1 {
  font-size: 2.4em;
  font-weight: 300;
}
h2 {
  font-size: 1.8em;
  font-weight: 400;
}
h3 {
  font-size: 1.5em;
  font-weight: 500;
}
h4 {
  font-size: 1.2em;
  font-weight: 600;
}
h5 {
  font-size: 1.1em;
  font-weight: 600;
}
h6 {
  font-size: 1em;
  font-weight: 600;
}
strong {
  color: #ffffff;
}
del {
  color: #9ba09d;
}
a,
a code {
  color: white;
}
img {
  max-width: 100%;
}
blockquote {
  margin: 1.5em 0;
  font-size: inherit;
  color: #9ba09d;
  border-color: #43484c;
  border-width: 4px;
}
hr {
  margin: 3em 0;
  border-top: 2px dashed #43484c;
  background: none;
}
table {
  margin: 1.5em 0;
}
th {
  color: #ffffff;
}
th,
td {
  padding: 0.66em 1em;
  border: 1px solid #43484c;
}
code {
  color: #ffffff;
  background-color: #303337;
}
pre.editor-colors {
  margin: 1.5em 0;
  padding: 1em;
  font-size: 0.92em;
  border-radius: 3px;
  background-color: #27292c;
}
kbd {
  color: #ffffff;
  border: 1px solid #43484c;
  border-bottom: 2px solid #35393c;
  background-color: #303337;
}

.bracket-matcher .region {
  border-bottom: 1px dotted lime;
  position: absolute;
}
.line-number.bracket-matcher.bracket-matcher {
  color: #c5c8c6;
  background-color: rgba(255, 255, 255, 0.14);
}

.spell-check-misspelling .region {
  border-bottom: 2px dotted rgba(255, 51, 51, 0.75);
}
.spell-check-corrections {
  width: 25em !important;
}

pre.editor-colors {
  background-color: #1d1f21;
  color: #c5c8c6;
}
pre.editor-colors .invisible-character {
  color: rgba(197, 200, 198, 0.2);
}
pre.editor-colors .indent-guide {
  color: rgba(197, 200, 198, 0.2);
}
pre.editor-colors .wrap-guide {
  background-color: rgba(197, 200, 198, 0.1);
}
pre.editor-colors .gutter {
  background-color: #292c2f;
}
pre.editor-colors .gutter .cursor-line {
  background-color: rgba(255, 255, 255, 0.14);
}
pre.editor-colors .line-number.cursor-line-no-selection {
  background-color: rgba(255, 255, 255, 0.14);
}
pre.editor-colors .gutter .line-number.folded,
pre.editor-colors .gutter .line-number:after,
pre.editor-colors .fold-marker:after {
  color: #fba0e3;
}
pre.editor-colors .invisible {
  color: #c5c8c6;
}
pre.editor-colors .cursor {
  border-color: white;
}
pre.editor-colors .selection .region {
  background-color: #444;
}
pre.editor-colors .bracket-matcher .region {
  border-bottom: 1px solid #f8de7e;
  margin-top: -1px;
  opacity: .7;
}
.syntax--comment {
  color: #8a8a8a;
}
.syntax--entity {
  color: #FFD2A7;
}
.syntax--entity.syntax--name.syntax--type {
  text-decoration: underline;
  color: #FFFFB6;
}
.syntax--entity.syntax--other.syntax--inherited-class {
  color: #9B5C2E;
}
.syntax--keyword {
  color: #96CBFE;
}
.syntax--keyword.syntax--control {
  color: #96CBFE;
}
.syntax--keyword.syntax--operator {
  color: #EDEDED;
}
.syntax--storage {
  color: #CFCB90;
}
.syntax--storage.syntax--modifier {
  color: #96CBFE;
}
.syntax--constant {
  color: #99CC99;
}
.syntax--constant.syntax--numeric {
  color: #FF73FD;
}
.syntax--variable {
  color: #C6C5FE;
}
.syntax--invalid.syntax--deprecated {
  text-decoration: underline;
  color: #FD5FF1;
}
.syntax--invalid.syntax--illegal {
  color: #FD5FF1;
  background-color: rgba(86, 45, 86, 0.75);
}
.syntax--string .syntax--source,
.syntax--string .syntax--meta.syntax--embedded.syntax--line {
  color: #EDEDED;
}
.syntax--string .syntax--punctuation.syntax--section.syntax--embedded {
  color: #00A0A0;
}
.syntax--string .syntax--punctuation.syntax--section.syntax--embedded .syntax--source {
  color: #00A0A0;
}
.syntax--string {
  color: #A8FF60;
}
.syntax--string .syntax--constant {
  color: #00A0A0;
}
.syntax--string.syntax--regexp {
  color: #E9C062;
}
.syntax--string.syntax--regexp .syntax--constant.syntax--character.syntax--escape,
.syntax--string.syntax--regexp .syntax--source.syntax--ruby.syntax--embedded,
.syntax--string.syntax--regexp .syntax--string.syntax--regexp.syntax--arbitrary-repetition {
  color: #FF8000;
}
.syntax--string.syntax--regexp.syntax--group {
  color: #C6A24F;
  background-color: rgba(255, 255, 255, 0.06);
}
.syntax--string.syntax--regexp.syntax--character-class {
  color: #B18A3D;
}
.syntax--string .syntax--variable {
  color: #8A9A95;
}
.syntax--support {
  color: #FFFFB6;
}
.syntax--support.syntax--function {
  color: #DAD085;
}
.syntax--support.syntax--constant {
  color: #FFD2A7;
}
.syntax--support.syntax--type.syntax--property-name.syntax--css {
  color: #EDEDED;
}
.syntax--source .syntax--entity.syntax--name.syntax--tag,
.syntax--source .syntax--punctuation.syntax--tag {
  color: #96CBFE;
}
.syntax--source .syntax--entity.syntax--other.syntax--attribute-name {
  color: #FF73FD;
}
.syntax--entity.syntax--other.syntax--attribute-name {
  color: #FF73FD;
}
.syntax--entity.syntax--name.syntax--tag.syntax--namespace,
.syntax--entity.syntax--other.syntax--attribute-name.syntax--namespace {
  color: #E18964;
}
.syntax--meta.syntax--preprocessor.syntax--c {
  color: #8996A8;
}
.syntax--meta.syntax--preprocessor.syntax--c .syntax--keyword {
  color: #AFC4DB;
}
.syntax--meta.syntax--cast {
  color: #676767;
}
.syntax--meta.syntax--sgml.syntax--html .syntax--meta.syntax--doctype,
.syntax--meta.syntax--sgml.syntax--html .syntax--meta.syntax--doctype .syntax--entity,
.syntax--meta.syntax--sgml.syntax--html .syntax--meta.syntax--doctype .syntax--string,
.syntax--meta.syntax--xml-processing,
.syntax--meta.syntax--xml-processing .syntax--entity,
.syntax--meta.syntax--xml-processing .syntax--string {
  color: #8a8a8a;
}
.syntax--meta.syntax--tag .syntax--entity,
.syntax--meta.syntax--tag > .syntax--punctuation,
.syntax--meta.syntax--tag.syntax--inline .syntax--entity {
  color: #FF73FD;
}
.syntax--meta.syntax--tag .syntax--name,
.syntax--meta.syntax--tag.syntax--inline .syntax--name,
.syntax--meta.syntax--tag > .syntax--punctuation {
  color: #96CBFE;
}
.syntax--meta.syntax--selector.syntax--css .syntax--entity.syntax--name.syntax--tag {
  text-decoration: underline;
  color: #96CBFE;
}
.syntax--meta.syntax--selector.syntax--css .syntax--entity.syntax--other.syntax--attribute-name.syntax--tag.syntax--pseudo-class {
  color: #8F9D6A;
}
.syntax--meta.syntax--selector.syntax--css .syntax--entity.syntax--other.syntax--attribute-name.syntax--id {
  color: #8B98AB;
}
.syntax--meta.syntax--selector.syntax--css .syntax--entity.syntax--other.syntax--attribute-name.syntax--class {
  color: #62B1FE;
}
.syntax--meta.syntax--property-group .syntax--support.syntax--constant.syntax--property-value.syntax--css,
.syntax--meta.syntax--property-value .syntax--support.syntax--constant.syntax--property-value.syntax--css {
  color: #F9EE98;
}
.syntax--meta.syntax--preprocessor.syntax--at-rule .syntax--keyword.syntax--control.syntax--at-rule {
  color: #8693A5;
}
.syntax--meta.syntax--property-value .syntax--support.syntax--constant.syntax--named-color.syntax--css,
.syntax--meta.syntax--property-value .syntax--constant {
  color: #87C38A;
}
.syntax--meta.syntax--constructor.syntax--argument.syntax--css {
  color: #8F9D6A;
}
.syntax--meta.syntax--diff,
.syntax--meta.syntax--diff.syntax--header {
  color: #F8F8F8;
  background-color: #0E2231;
}
.syntax--meta.syntax--separator {
  color: #60A633;
  background-color: #242424;
}
.syntax--meta.syntax--line.syntax--entry.syntax--logfile,
.syntax--meta.syntax--line.syntax--exit.syntax--logfile {
  background-color: rgba(238, 238, 238, 0.16);
}
.syntax--meta.syntax--line.syntax--error.syntax--logfile {
  background-color: #751012;
}
.syntax--source.syntax--gfm {
  color: #999;
}
.syntax--gfm .syntax--markup.syntax--heading {
  color: #eee;
}
.syntax--gfm .syntax--link {
  color: #555;
}
.syntax--gfm .syntax--variable.syntax--list,
.syntax--gfm .syntax--support.syntax--quote {
  color: #555;
}
.syntax--gfm .syntax--link .syntax--entity {
  color: #ddd;
}
.syntax--gfm .syntax--raw {
  color: #aaa;
}
.syntax--markdown .syntax--paragraph {
  color: #999;
}
.syntax--markdown .syntax--heading {
  color: #eee;
}
.syntax--markdown .syntax--raw {
  color: #aaa;
}
.syntax--markdown .syntax--link {
  color: #555;
}
.syntax--markdown .syntax--link .syntax--string {
  color: #555;
}
.syntax--markdown .syntax--link .syntax--string.syntax--title {
  color: #ddd;
}
</style>

  </head>
  <body>
    <h3><strong>tmux notes</strong></h3>
<p>Send commands:</p>
<ul>
<li>from command line such as “tmux attach”</li>
<li>from shortcuts using the default prefix ctrl-b then the shortcut</li>
<li>from command mode by entering prefix : then typing the word command</li>
</ul>
<p>Change the default prefix from ctrl-b</p>
<p>add the following to .tmux.conf</p>
<p>The default tmux server name is default, which is stored in /tmp/tmu-1000 directory</p>
<p>Windows shortcuts</p>
<table>
  <tbody><tr>
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
   <td>Prefix + &amp;
   </td>
  </tr>
</tbody></table>
<p>Panes</p>
<table>
  <tbody><tr>
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
</tbody></table>
<p>Sessions</p>
<table>
  <tbody><tr>
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
</tbody></table>
<p>Commands</p>
<table>
  <tbody><tr>
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
</tbody></table>
<p>.tmux.conf</p>
<p>Pane switching with Alt+arrow</p>
<p>bind -n M-Left select-pane -L <br>
bind -n M-Right select-pane -R <br>
bind -n M-Up select-pane -U <br>
bind -n M-Down select-pane -D</p>
<p>Activity Monitoring</p>
<p>setw -g monitor-activity on <br>
set -g visual-activity on</p>
<p>Highlighting Current Window Using Specified Colour</p>
<p>set-window-option -g window-status-current-bg yellow</p>
<p>tmux tries to read .bash_profile instead of .bashrc.</p>
<p>source ~/.bashrc</p>
<!-- Docs to Markdown version 1.0β17 -->

  </body>
</html>
