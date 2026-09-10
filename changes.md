# Changes

## 2026-09-10

* `bin/apache` no longer ships a bundled `httpd` binary (which tied usage to
  Intel Macs). It now looks for a locally installed Apache httpd in the usual
  mac locations - Homebrew (Apple Silicon and Intel), MacPorts, and macOS's
  built-in system Apache - and uses whichever it finds first. If none can be
  found, it exits with a message explaining how to install one (e.g.
  `brew install httpd`) instead of failing with an unhelpful error.
* `config/httpd.conf` now loads its modules from the detected installation's
  own modules directory (via the `APACHE_HTTPD_MODULES` variable exported by
  `bin/apache`) instead of a local `modules/` folder, since modules are no
  longer bundled with the project either.
