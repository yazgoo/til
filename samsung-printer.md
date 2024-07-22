https://bbs.archlinux.org/viewtopic.php?pid=1502597#p1502597

1. remove foomatic-db-engine, it is the source of the original error
2. go to http://localhost:631/ in your browser to get to the CUPS interface
3. click "add printer"
4. select  "LPD/LPR Host or Printer" (this is where I ran into issues, selecting the Brother printer that CUPS found didn't use the IP of the printer, instead it used some sort of ID, and wouldn't work after getting the printer set up)
5. type in "lpd://IP/BINARY_P1" where IP is the IP address of the printer, BINARY_P1 is the queue, leave it as it is unless it doesn't work
6. set the name, description, and location to whatever you want, they aren't critical to getting the printer online
7. select "generic" as the printer's make
8. select "Generic PCL Laser Printer" as the driver (this will return the error that started this thread instead of a list of drivers if foomatic-db-engine is installed)
9. pick the defaults you want, if you turn on 2 sided printing, CUPS will prompt you to set the Duplexer as installed, click the duplexer link and set it as installed
10. push the "set printer defaults" button if you haven't already. Done.

Last edited by l0vot (2015-02-13 14:35:54)
