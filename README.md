# apache-anywhere

There are a raft of "run a web site from here" commands that spawn an HTTP server from the command line.
The problem is the web servers they spawn don't always represent the actuall web server you might use
in production, so they don't support, for example, ``.htaccess`` files.

Cue apache-anywhere, which start a fully functional apache server wherever you want on whatever port you want, as many times as you want. Got a directory full of html, javascript and css files with cgi scripts and htacces controls? Just fire up apache-anywhere.

It's like Apache, but Anywhere.

## Dependencies

-   Apache
-   A bash shell to run commands in

## Installation

-   Clone this repository to your local machine:

    ```
	git clone https://github.com/julianbrowne/apache-anywhere.git
    ```

-   Apache must already be installed

-   Edit the ``bin/apache`` script (only if the apache binary is **not** at ``/usr/sbin/httpd``)

-   Edit config file **config/httpd.conf** if required (contains a minimum set of functionality)

## Usage

With ``apache-anywhere/bin`` on the path

	apache                              // starts apache httpd in the current directory at port 8686

    apache -p 8123                      // at current directory on port 8123

    apache -d /tmp                      // sets root docs directory to /tmp

    apache -d /home/user42 -p 8456      // you get the idea

If you're running apache as a regular user then the port number needs to be above 8000 as below that ports
are reserved for system processes. Whichever user you are logged in as should also have access to the files
in the documents directory.

    apache stop 8123                    // stops the apache http process running on port 8123

Apache log and tmp files are created at ``/tmp/{process_id}/``
