# Flask Benchmarking with wrk

### Installing wrk
This repo assumes that you have python3 and [wrk](https://github.com/wg/wrk) installed and properly configured.

wrk installation:
* [Mac Users](https://github.com/wg/wrk/wiki/Installing-wrk-on-OS-X)
* [Linux](https://github.com/wg/wrk/wiki/Installing-wrk-on-Linux)
* [Windows](https://github.com/wg/wrk/wiki/Installing-wrk-on-Windows-10)

### Installing dependencies
Run:

    $ cd flask
    $ make
    
### Run all tests
Run: 

    $ ./test.sh  

### Test a specific server
To start the gunicorn server in the NoFramework folder simply run:
    
    $ cd NoFramework
    $ make gunicorn
    $ make test CONNECTIONS=500 RESULTS=SERVER.500.log
    
The results will be in `results/` folder. `connection` and `result` defaults to 500 and result.500.log, respectively.

*Other wsgi server options are: meinheld, uwsgi, and cherrypy*    

### Run parser
parse.py will parse the results, producing a CSV file. Simply pass in the directory with the results:
    
    $ python parse.py results > results.csv


