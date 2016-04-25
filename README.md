vhost-analyzer
==============

Useful tool to get an idea what's going on on your webserver hosting
many different vhosts all logging into one logfile.

To produce log files compatible with the tool, the log format needs to
be configured as follows:

        LogFormat "%V %h %l %u %t \"%r\" %s %b <more options>" vcombined

Only the first couple of fields are parsed, the rest is ignored.

Examples
--------

- Analyze all requests:

        vhost-analyzer access.log

- Analyze requests to one specific vhost:

        vhost-analyzer -s vhost=domain.com access.log

- Exclude static files:

        vhost-analyzer -s 'path!~\.(css|js|png|gif|jpg)$' access.log

- Consider only requests to static files:

        vhost-analyzer -s 'path=~\.(css|js|png|gif|jpg)$' access.log

License
-------

Copyright 2016 Oliver Hitz <oliver@net-track.ch>

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or (at
your option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
General Public License for more details.
