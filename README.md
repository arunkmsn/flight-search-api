# Setup
This solution requires python2 and some dependencies like tornado, requests. In
order to setup the environment, please execute the `setup.sh` script.

# Running the program
   Please execute `fab start_services` in the project root folder to start the web
services. You can run the tests instead by using `fab test`. Please note that
this is a very simple helper script which isn't very robust. You will find that
simple cases like starting services twice will show up errors. You will need to
execute `fab stop_services` after starting_services. The tests, invoked by
'fab test' automatically starts and cleans up the required services after
they're done.

   The flight search service's port and other config can be changed in
`providers.cfg` file.

# Explanation
   All the flight search related APIs are in flight_search module. The
flight_search.py file contains class which handles fetching search results and
merging them. flight_search_service.py, as the name suggests, contains code
related to creation of service and routing for the flight search API. I've used
the tornado built-in coroutines and async http client to parallelize the
requests.

   I have also taken the liberty of organizing scraper and it's test into
respective modules of their own.

--
Arun Kumar M S
E-mail: arunkmsn@gmail.com
