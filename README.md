NMEA 0183 parser and formatter
----
github.com/HomegrownMarine


Usage
-----

<code>
var nmea = require('homegrown-nmea');

var message = '$GPRMC,030000,A,4740.36415,N,12225.35953,W,000.02,059.5,160612,016.6,E*52';

//make sure checksum is correct.
nmea.validate(message);


var data = nmea.parse(message);

{ msg: 'GPRMC,030000,A,4740.36415,N,12225.35953,W,000.02,059.5,160612,016.6,E',
  type: 'rmc',
  lat: 47.67273583333334,
  latStr: '4740.36415,N',
  lon: -122.42265883333333,
  lonStr: '12225.35953,W',
  time: /* moment time */,
  variation: -16.6,
  sog: 0.02,
  cog: 59.5 }

</code>