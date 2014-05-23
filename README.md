## apache-anywhere

Command line util to start ad-hoc apache server in chosen directory on chosen port

### Installation

-  Apache must already be installed. Edit the bin/serve script if it's not at:

    ```/usr/sbin/httpd```

-  Clone this repository to your local machine:

    ```git clone https://github.com/julianbrowne/apache-anywhere.git```

-  Edit config file **config/httpd.conf** if required (contains a minimum set of functionality)

### Usage

	serve -d document_root -p port

	document_root: must be a directory containing your html files   
	port: port to access apache from

-  Make sure the serve script is on the PATH and run the serve command as needed. This will run apache in the current directory on port 8123, meaning you can browse at http://127.0.0.1:8123/

   ```serve -d . -p 8123```

-  Log files etc will appear in the log directory

-  When done, stop the server

	```serve stop```

