## apache-anywhere

Command line util to start ad-hoc apache server in chosen directory on chosen port

### Installation

-   Clone this repository to your local machine:

    ```git clone https://github.com/julianbrowne/apache-anywhere.git```

-   Apache must already be installed

-   Edit the **bin/serve** script if the apache binary is not at **/usr/sbin/httpd**

-   Edit config file **config/httpd.conf** if required (contains a minimum set of functionality)

### Usage

	serve -d document_root -p port

	document_root: must be a directory containing your html files   
	port: port to access apache from

-   Make sure the serve script is on the PATH and run the serve command as needed

-   For example, this will set the document root of apache to the current directory and expose it via port 8123, meaning you can point your browser at http://127.0.0.1:8123/

    ```serve -d . -p 8123```

-   Log files etc will appear in the log directory where you installed these scripts

-   When done, stop the httpd process:

    ```serve stop```
