##wos2vivo

Mapping publications from the Web of Science™ via [Web Services](http://ipscience-help.thomsonreuters.com/wosWebServicesLite/WebServicesLiteOverviewGroup/Introduction.html) to [VIVO](http://vivoweb.org)

This requires access to the Web of Science Web Services. If your organization subscribes to the Web of Science and would like a username and password to use the Web Services, please email `research.networking@thomsonreuters.com`.


###usage

This toolkit requires Python 2.7.

* Clone the git repository:

```
$ git clone https://github.com/lawlesst/wos2vivo.git
```

* Install the Python dependencies
```
$ cd wos2vivo
$ pip install -r requirements
```

* Set environment variables
```
$ cp .env.sample .env
# adjust values to match your VIVO data namespace and Web of Science username and password
$ source .env
```

* Modify `example.py`

This example shows how the web service can be called. A user query and time span is required.
A `record.py` object will be returned. To convert to VIVO rdf call the `to_rdf` method.

###development


#### running the tests
Install test dependencies first with `pip install -r tests/dev_requirements.txt`.

```
$ python -m unittest discover tests/
```

Tests will use [Betamax](http://betamax.readthedocs.org/en/latest/configuring.html) to record
HTTP interactions. This allows us to run the tests without actually hitting the web service and
to keep the sample data stable.

Feedback, bug reports and pull requests welcome.