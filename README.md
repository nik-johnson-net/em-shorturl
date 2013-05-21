EventMachine ShortURL Gem
=========================

The `em-shorturl` gem is a module extending EventMachine to provide asynchronous URL shortening functionality to eventmachine-based applications. 

Usage
-----
### Quick start
  
    require 'em-shorturl'
    
    EM.run do
      request = EM::ShortURL.shorten('http://google.com')
      request.callback { |url, request| puts "Short URL: #{url}" }
      request.errback { |error, request| puts "Received error: #{error}" }
    end

### Supported services

* Google

Run tests
---------

The tests for most of the code is a live test of the driver, making a real request to the shortening service and checking the result. Tests are provided to verify login methods via environment variables, which fail if the credentials are not supplied.

To run the tests, simply run `rake test`.

Thanks
------

First off, everyone needs to thank the EventMachine crew for building such an awesome library. If you ever pass by one of the authors on the street, buy them a beer.

Second, the authors of em-http-request which this gem relies upon for HTTP fetching. It provides a great interface for creating requests and hasn't given me any issues.
