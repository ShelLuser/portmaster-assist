# Portmaster Assist (project revival)

### About

Portmaster Assist is a collection of 3 shell scripts which can help you to maintain the ports collection (`/usr/ports`) with the help of Git (`devel/git`) and the Portmaster script (`ports-mgmt/portmaster`).

These scripts can be used to:
* Keep the ports collection up to date using Git.
* Checking which packages have an update available, while also parsing `/usr/ports/CHANGES` to search for mention of any specific upgrade instructions.
* Upgrade packages using Portmaster while also allowing you to ignore certain ports (think of screen, llvm or Rust).
* Detecing moved ports, and to automatically handle the move and/or rename.

This project was created in 2018, got updated when the FreeBSD project moved away from Subversion in favor of Git and then got a bit abandoned in a "mostly working" state (the scripts *refresh* and *update* work without issue, but *pmmove* always had a few problems).

***Time for a revival!***

## The project revival

When I started this project I fully relied on vi, vim (sporadicaly) as well as Git to maintain things; I actually did most of the work from a FreeBSD commmand line. While this worked like a charm for me it also took up quite a bit of time, and in addition this didn't allow me to take any advantage of all the other features which GitHub provides, such as the [Issue tracker](https://github.com/ShelLuser/portmaster-assist/issues).

Between then and now 2 things changed: I got quite familiar with using [Visual Studio Code](https://code.visualstudio.com/), and in addition I *also* developed a __serious__ liking for the [Python programming language](https://www.python.org/). And *that* resulted in *this*:

![The project in VS Code](https://i.imgur.com/QHIWmVQ.png "Project revival with VS Code")

### _The revival 'todo' list_

The whole revival effort resolves around the [Project revision 2026](https://github.com/ShelLuser/portmaster-assist/milestone/3) milestone as listed on the [Issue tracker](https://github.com/ShelLuser/portmaster-assist/issues).

These steps basically consists of (in random order):

* Updating the GitHub repository to reflect on the current situation.
  * => Updating documentation (like this new README.md).
  * => Adding / revising todo items for the [Issue tracker](https://github.com/ShelLuser/portmaster-assist/issues).
  * => Updating [the Portmaster Assist wiki](https://github.com/ShelLuser/portmaster-assist/wiki).
* ~~Setting up VS Code for easier access to the repository~~ (***done!***).
* Actually fixing the code (*duh!*).
* Building a Python backend (my plan is to either rebuild the whole project in Python, *or* to maintain 2 projects: this one and a Python based project (py-portmaster-assist? ;)).

For more information please refer to the [Portmaster Assist wiki](https://github.com/ShelLuser/portmaster-assist/wiki).
