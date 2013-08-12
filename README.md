git-started
===========

### git-started is a repo for those working with ORCAS

* Guidelines for front-end dev, design, backend dev and best practices.
* Tips and Tricks to add to your .bashprofile and others to get started and keep running smoothly.

Development Environment
================

The only dependencies to develop with ORCAS are [Python](http://www.python.org/download/)
(>= 2.6, <= 3.x), [Pip](http://www.pip-installer.org/en/latest/installing.html), (a python package
manager, install this globally) [Git](http://git-scm.com/downloads), and SSH (Putty will do). All
the other dependencies can be installed using Pip. You will also need an account on the ORCAS staging
server in order to access the DB.

Once you have Pip installed, you can use it to globally install `virtualenvwrapper`. Open a
terminal window and enter the following:

`sudo pip install virtualenvwrapper`

Finally, you need to add the following line to your `~/.bashrc` file in order to enable virtualenvwrapper
in each new terminal window:

`source /usr/local/bin/virtualenvwrapper.sh`

Now you can get setup to work on a project. Open a new terminal window and follow along.

1. Use git to clone the project: `git clone <repository_url>`
2. cd into the created directory and use `virtualenvwrapper` to make a new virtual environment for the project: `mkvirtualenv <env_name>`
3. Use Pip to install the requirements. NOTE: we don't use `sudo` here, because we only want to install these packages into the virtual environment, not globally: `pip install requirements/local.txt`
4. When step 3 is finally finished, you need to get the private keys for the project. We don't store them in the repository since they are sensitive information: `scp <username>@<server>:/www/<project_name>/web/settings/secret_keys.py web/settings/`
5. All the code is now ready, you just need to use SSH to forward the DB connection: `ssh -N -L 1234:localhost:5432 <username>@<server>`
6. Now you can run the django development server: `python manage.py runserver`
7. Done! By default the development server runs on port 8000 so you should be able to see it at http://127.0.0.1:8000


Style guides
============
In order to make our code more readable and maintainable by everyone, we do
our best to use consistent styles on all our projects. Please read through the following guides,
and make sure any contributed code uses the same style. That said, a quick quote from
Python's style guide is in order:
> A Foolish Consistency is the Hobgoblin of Little Minds

If any of these guidelines cause the code to be less readable, just use your best judgement to
make the necessary adjustments to fix the problem. The style guides can be found below.

###[Less/CSS](styles/Less.md)

###[JavaScript](styles/JavaScript.md)

###[HTML](styles/HTML.md)

###[Python](styles/Python.md)

There are also several recommendations we believe should apply universally to retain consistency
throughout our projects, regardless of the language used:
* There should be no extra space at the end of lines. Many editors have a setting to
automatically strip off extra white space when saving.
* There should be one blank line at the end of every file. Again, many editors have an option to
make this happen automatically.

Comments
--------
Use code comments to serve as documentation. To go from the top to the bottom hierarchically:
* Each project should have a `README` file at the root level to describe how to setup the project,
how the various pieces fit together, and how to use it.
* Each file should have a comment at the beginning to give a summary of what the code in the file
does and how it should be used.
* Each module/function in the file should also have comment block describing what the function
does and how to use it.
* Inline comments should be used to explain any complex logic, or summarize logical blocks.
