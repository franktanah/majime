![](./resources/majime-logo1.png)

Dead simple API Unit Testing

## Install

`pip install majime`

[Package on Pypi](https://pypi.org/project/majime/)

## Usage

    Usage:

     -f Load and run tests from YAML file
        Example: majime -f test.yaml
     -g Generate test suite (YAML) from Swagger document
        Example: majime -g http://api.example.com/swagger.json

    Switches:

     -s No output, just response code
     -j JSON output
     -d Dry-Run, do not execute tests - good for testing your YAML file
     -n no colors in output
     -c do not stop on the first error

## Example

#### Generate Test Cases from Swagger

`majime -g http://backend.yoisho.dob.jp/fx/swagger`

    Title: Yoisho Currency Exchange
    Host: backend.yoisho.dob.jp
    Base Path: /fx
    Scheme: http
    Path: /currency
		Method: GET
		Description: Get the FX rate for desired currency
		Query Parameters: ['currency']
		Expected Response: 200

#### Run Test Cases

Modify the parameters so they make sense, in this case XXX-> USD.

`majime -f Yoisho_Currency_Exchange-*.yaml`

    GET http://backend.yoisho.dob.jp/fx/currency?currency=USD
	HTTP 200
