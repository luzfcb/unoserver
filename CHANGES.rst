2.1.0 (unreleased)
------------------

- Nothing changed yet.


2.0.2 (2024-03-21)
------------------

- Added --version flags to the commands to print the version number.
  Also unoserver prints the version on startup.

- File paths are now always sent as absolute paths.


2.1b1 (2024-01-12)
------------------

- Add a --input-filter argument to specify a different file type than the
  one LibreOffice will guess.

- For consistency renamed --filter to --output-filter, but the --filter
  will remain for backwards compatibility.

- If you specify a non-existent filter, the list of filters is now alphabetical.

- You can now use both the LibreOffice name, but also internal shorter names
  and sometimes even file suffices to specify the filter.


2.0.1 (2024-01-12)
------------------

- Specifying `--host-location=remote` didn't work for the outfile if you
  used port forwarding from localhost.

- Always default the uno interface to 127.0.0.1, no matter what the XMLRPC
  interface is.


2.0 (2023-10-19)
----------------

- Made the --daemon parameter work again

- Added a --filter-option alias for --filter-options


2.0b1 (2023-08-18)
------------------

- A large refactoring with an XML-RPC server and a new client using that XML-RPC
  server for communicating. This means the client can now be lightweight, and
  no longer needs the Uno library, or even LibreOffice installed. Instead the
  new `unoserver.client.UnoClient()` can be used as a library from Python.

- A cleanup and refactor of the commands, with new, more gooder parameter names.


1.6 (2023-08-18)
----------------

- Added some deprecation warnings for command arguments as they will change in 2.0.


1.5 (2023-08-11)
----------------

- Added support for passing in filter options with the --filter-options parameter.

- Add `--user-installation` flag to `unoserver` for custom user installations.

- Add a `--libreoffice-pid-file` argument for `unoserver` to save the LibreOffice PID.


1.4 (2023-04-28)
----------------

- Added new feature: comparing documents and export the result to any format.

- You can run the new module as scripts, and also with ``python3 -m unoserver.comparer`` just
  like the ``python3 -m unoserver.server`` and ``python3 -m unoserver.converter``.

- Porting feature from previous release: refresh of index in the Table of Contents


1.3 (2023-02-03)
----------------

- Now works on Windows (although it's not officially supported).

- Added --filter argument to unoconverter to allow explicit selection of which
  export filter to use for conversion.


1.2 (2022-03-17)
----------------

- Move logging configuration from import time to the main() functions.

- Improved the handling of KeyboardInterrupt

- Added the deprecated but still necessary com.sun.star.text.WebDocument
  for HTML docs.


1.1 (2021-10-14)
----------------

- Fixed a bug: If you specified an unknown file extension while piping the
  result to stdout, you would get a type error instead of the correct error.

- Added an extra check that libreoffice is quite dead when exiting,
  I experienced a few cases where soffice.bin was using 100% load in the
  background after unoserver exited. I hope this takes care of that.

- Added ``if __name__ == "main":`` blocks so you can run the modules
  as scripts, and also with ``python3 -m unoserver.server`` and
  ``python3 -m unoserver.converter``.


1.0.1 (2021-09-20)
------------------

- Fixed a bug that meant `unoserver` did not behave well with Supervisord's restart command.


1.0 (2021-08-10)
----------------

- A few small spelling and grammar changes.


1.0b3 (2021-07-01)
------------------

- Make sure `interface` and `port` options are honored.

- Added an --executable option to the server to pick a specific libreoffice installation.

- Changed the infile and outfile options to be positional.

- Added support for using stdin and stdout.

- Added a --convert-to argument to specify the resulting filetype.


1.0b2 (2021-06-24)
------------------

- A bug prevented converting to or from files in the local directory.


1.0b1 (2021-06-24)
------------------

- First beta release


0.0.1 (2021-06-16)
------------------

- First alpha release
