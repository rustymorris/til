<div id="page">

<div id="main" class="aui-page-panel">

<div id="main-header">

<div id="breadcrumb-section">

1.  [[Morris, Rusty](index.html)]{}

</div>

[ Morris, Rusty : Python Notes ]{#title-text} {#title-heading .pagetitle}
=============================================

</div>

<div id="content" class="view">

<div class="page-metadata">

Created by [ Morris, Rusty]{.author}, last modified on May 10, 2019

</div>

<div id="main-content" class="wiki-content group">

PEP8 - Python Enhancement Proposal

Python 2 vs Python 3 - Python 2 maintained but no new features, EOL in
2020 and still the default on many systems. Python 3 released Dec.
2008. 

\

**virtualenv**

Use virtualenvs for all projects to keep them isolated to avoid
conflicts. 

Use virtualenvwrapper to allow using workon command with will deactivate
the current project, activate and switches the  working directory. 

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: bash; gutter: false; theme: Confluence" data-theme="Confluence"}
sudo pip install virtualenv
sudo pip install virtualenvwrapper 
```

</div>

</div>

\

Configure virtualenvwrapper by edited .profile as below.

You could use \~/dev and \~/.virtualenvs to keep code separate for
version control from envs.

Bind virtualenvs to projects by

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: bash; gutter: false; theme: Confluence" data-theme="Confluence"}
# Virtualenvwrapper setup
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/netdev
source /usr/local/bin/virtualenvwrapper.sh

# Configure code directory with virtualenv when using workon to change projects. 
cd ~/dev/webapp
setvirtualenvproject # This will sync the ~/dev/webapp code directory with the ~/virualenvs/webapp as referenced in .profile. 
```

</div>

</div>

Use mkvirtualenv willcreate a new Python 2.x virtual environment and
activate it. The 

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: bash; gutter: false; theme: Confluence" data-theme="Confluence"}
mkvirtualenv amaze
mkvirtualenv --python=/usr/bin/python3 mist
```

</div>

</div>

Use mkproject to create a new virtual environment, create a new project
directory, bind them together and activate the project. 

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: bash; gutter: false; theme: Confluence" data-theme="Confluence"}
mkproject chucknorris
```

</div>

</div>

\

Use workon to move between virtual enviroments

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: bash; gutter: false; theme: Confluence" data-theme="Confluence"}
workon charm
```

</div>

</div>

\

List of all environments.

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: bash; gutter: false; theme: Confluence" data-theme="Confluence"}
lsvirtualenv
```

</div>

</div>

Change project to use Python3 in virtualenv

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: py; gutter: false; theme: Confluence" data-theme="Confluence"}
python3 -m venv <myenvname>
```

</div>

</div>

\

**Using Pip**

Pip comes pre-installed starting with Python 3.4. 

Use PyPi to install pyhton add-ons. The packages are downloaded from the
cheese shop <https://pypi.org/>

Install pip by following the instructions
at <http://www.pip-installer.org>

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: py; gutter: false; theme: Confluence" data-theme="Confluence"}
sudo apt-get install python-pip # if pip is not installed

pip list # List all packages used by the active project.

pip search 'query'  # Seach all pip packages

pip uninstall requests  # Remove pip package requests
```

</div>

</div>

\

**Django**

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: py; gutter: false; theme: Confluence" data-theme="Confluence"}
(djangoapp): pip install django # Start venv and install django

django-admin startproject djangoapp # Run from the directory to store site to create initial django config in djangoapp directory

: cd ./mysite
: setvirtualenv
: workon djangoapp

(djangoapp): python manage.py runserver # this will start a django server on the default port 8000, http://127.0.0.1:8000
(djangoapp): python manage.py runserver 8080 # start the server using port 8080
(djangoapp): python manage.py runserver ip_address:8080 # start the server using ip_address on port 8080
(djangoapp): python manage.py startapp main_app    # creates app main_app
```

</div>

</div>

The urls.py file is the mapping to the view files. 

\

**View sys.path?**

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: py; gutter: false; theme: Confluence" data-theme="Confluence"}
python
import sys
sys.path    # will display the system search path
```

</div>

</div>

\

\

**Projects**

chucknorris

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: py; gutter: false; theme: Confluence" data-theme="Confluence"}
python manage.py runserver
```

</div>

</div>

Tresuregram

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` {.syntaxhighlighter-pre data-syntaxhighlighter-params="brush: py; gutter: false; theme: Confluence" data-theme="Confluence"}
python manage.py runserver
```

</div>

</div>

\

\

\

</div>

</div>

</div>

<div id="footer" role="contentinfo">

<div class="section footer-body">

Document generated by Confluence on May 15, 2019 13:34

<div id="footer-logo">

[Atlassian](http://www.atlassian.com/)

</div>

</div>

</div>

</div>
