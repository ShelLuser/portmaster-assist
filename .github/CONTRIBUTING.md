## Development tools and/or platforms

* The project is meant to be used on [FreeBSD](https://www.freebsd.org/).
  * Only [currently supported releases](https://www.freebsd.org/releases/), such as *production* and *legacy*.
* It's build to support Portmaster (`ports-mgmt/portmaster`).
* Our preferred editor is [Visual Studio Code](https://code.visualstudio.com/).
  * A pretty much required extension is ShellCheck.

### Regarding the use of AI

AI assisted contributions are no problem, *however...*

* **No** generated code.
* Please carefully review any generated documentation.
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
* Run ShellCheck.
* Add motivation as to why you think the change is needed.

## Bug reports

*Always* include the following information:

* The FreeBSD version you used (use `uname -Uv` when in doubt).
* The Portmaster version (see `pkg info -o portmaster`).
* Command output.
* Any relevant logfile(s) if relevant.
