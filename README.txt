// About

Portmaster Assist is a collection of 3 shell scripts which can help
you to maintain the ports collection ("/usr/ports") with the help of
Git ("devel/git") and the Portmaster script ("ports-mgmt/portmaster").

These scripts can be used to:
* Keep the ports collection up to date using Git.
* Check which packages have an update available, while also parsing
  "/usr/ports/CHANGES" to search for mention of any specific upgrade
  instructions.
* Upgrade packages using Portmaster while also allowing you to
  ignore certain ports (think of screen, llvm or Rust).
* Detect moved ports, and automatically handle the move and/or
  rename.

This project was created in 2018, got updated when the FreeBSD
project moved away from Subversion in favor of Git and then got a
bit abandoned in a "mostly working" state (the scripts refresh and
update work without issue, but pmmove always had a few problems).

Time for a revival!

// The project revival

When I started this project I fully relied on vi, vim
(sporadically), as well as Git, to maintain things; I actually did
most of the work from a FreeBSD command line. While this worked
like a charm for me it also took up quite a bit of time, and in
addition this didn't allow me to take any advantage of all the
other features which GitHub provides, such as the Issue tracker.

Between then and now two things changed: I got quite familiar with
using Visual Studio Code, and in addition I also developed a
serious liking for the Python programming language.

// The revival 'todo' list

The whole revival effort resolves around the Project revision 2026
milestone as listed on the Issue tracker.

These steps basically consist of (in random order):

* Updating the GitHub repository to reflect on the current situation.
  * Updating documentation.
  * Adding or revising todo items for the Issue tracker.
  * Updating the Portmaster Assist wiki.
* Actually fixing the code.
* Building a Python backend (my plan is to either rebuild the whole
  project in Python, or to maintain two projects: this one and a
  Python based project, py-portmaster-assist).

For more information please refer to the Portmaster Assist wiki.

// References

* GitHub project:
  https://github.com/ShelLuser/portmaster-assist
* Issue tracker:
  https://github.com/ShelLuser/portmaster-assist/issues
* Project revision 2026 milestone:
  https://github.com/ShelLuser/portmaster-assist/milestone/3
* Portmaster Assist wiki:
  https://github.com/ShelLuser/portmaster-assist/wiki
* Visual Studio Code:
  https://code.visualstudio.com/
* Python:
  https://www.python.org/
