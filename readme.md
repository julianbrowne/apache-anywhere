
# Apache Anywhere

There are a [plenty](https://gist.github.com/willurd/5720255) [of](https://www.devdungeon.com/content/one-line-http-servers) one line "run a web site from here" commands that spawn an HTTP server from the command line.

The problem is the web servers they spawn don't always represent the _actual_ web server you might use
in production, so they don't support, for example, `.htaccess` files.

Cue Apache Anywhere, which starts a fully functional Apache server wherever you want, on whatever port you want, as many times as you want.

Got a directory full of html, javascript and css files with cgi scripts and htacces controls?
Just fire up apache-anywhere.

It's like Apache, but Anywhere.

## Dependencies

None. Comes with the binary and most of the common modules and it's easy to add your own.

## Installation

* Clone this repository to your local machine: `git clone https://github.com/julianbrowne/apache-anywhere.git`  
* Add any modules into `modules` or replace the `httpd` binary in `bin` if you need to  
* Edit the config file `httpd.conf` if required  
* Add the `apache-anywhere/bin` to your path  

## Usage

`apache`                            // starts apache httpd in the current directory at port 8686

`apache -p 8123`                    // at current directory on port 8123

`apache -d /tmp`                    // sets root docs directory to /tmp

`apache -d /home/user42 -p 8456`    // you get the idea

If you're running apache as a regular user then the port number needs to be above 8000 as below that ports
are reserved for system processes. Also, ensure that whichever user you are logged in as has appropriate permissions to the access the files in the root docs directory.

`apache stop 8123`                  // stops the apache http process running on port 8123

`apache clean 8123`                 // cleans up all temp files created by process on 8123

`apache stats`                      // provides stats about the permanent apache config in etc
                                        // useful to check what's already running on what port

Apache log and tmp files are created at `/tmp/{process_id}/`

