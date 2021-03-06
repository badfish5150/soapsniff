SOAP Sniffer
============

Captures TCP packets and handles HTTP and SOAP requests
to track call/request statistics and trigger custom handlers.

Requirements
------------

* python 2.7+
* pcapy
* impacket

Using Debian/Ubuntu simply do:

    sudo apt-get install python-pcapy python-impacket


Running
-------

Start server (default port 8080) and packet sniffer on same host:

    ./server.py &
    sudo ./soapsniff.py -v -s localhost:8080

Example soap request handler which stores soap method and arguments in server:

    ./server.py &
    sudo ./soapsniff.py -v -c example_soap_handlers.soap_request_handler -s localhost:8080

Afterwards you can track the last 500 soap calls under http://localhost:8080/deque
