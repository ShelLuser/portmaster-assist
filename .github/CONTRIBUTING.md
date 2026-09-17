## Development tools and/or platforms

* The project is meant to be used on [FreeBSD](https://www.freebsd.org/).
  * Only on [currently supported releases](https://www.freebsd.org/releases/), such as *production* and *legacy*.
* It's designed to support Portmaster (`ports-mgmt/portmaster`).
* Our preferred editor is [Visual Studio Code](https://code.visualstudio.com/).
  * Some must-have extensions are: [GitHub Pull Requests](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github), [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) and [ShellCheck](https://marketplace.visualstudio.com/items?itemName=timonwong.shellcheck).

### Regarding the use of AI

AI assisted contributions are no problem, *however...*

* **No** generated code.
* Please review any generated files carefully.
  * Be sure to use the `copilot` branch for changes that involve(d) AI.
* You, the contributor, will *always* remain responsible.
  * "*AI made me do it*", is **not** a valid excuse.

## Coding style

* The scripts are build for `/bin/sh`, the standard interpreter on FreeBSD.
  * Ergo: Bash specific coding styles are a no-go.
* Security concerns are a thing, so the use of `doas` and/or `sudo` within these scripts is strictly prohibited.
* Error messages should *always* be sent to `/dev/stderr`.

## Pull requests

* Keep changes focussed.
* Always test on FreeBSD (using a supported release).
* Verify using ShellCheck.
* Add motivation as to why you think the change is needed.
  * Maybe also consider the use of the [Issue tracker](https://github.com/ShelLuser/portmaster-assist/issues).

## Bug reports

*Always* include the following information:

* The FreeBSD version you used (use `uname -Uv` when in doubt).
* The Portmaster version (see `pkg info -o portmaster`).
* Command output.
* Any relevant logfile(s) if relevant.
