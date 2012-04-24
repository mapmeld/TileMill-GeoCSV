<h3>GeoCSV</h3>

Helps you create geo queries to style point features in TileMill.<br/>
Works with CSV files from <a href="http://geocommons.com">GeoCommons</a>, the EPA, and more.<br/>
Works with any layer that includes attributes for latitude and longitude ( they can have any name, but they must appear in the layer inspector view )

<h3>Install</h3>
Mac OS X Terminal one-liner:
<code>cp -r TileMill-GeoCSV /Applications/TileMill.app/Contents/Resources/plugins/</code>

<h3>What to do</h3>
<ol>
<li>Open the new GeoCSV plugin (it looks like a dot).</li>
<li>Select layer and properties.</li>
<li>Write code like this:<br/>
<code>
[ near 32.3 -112.1 0.5 ]
</code></li>
<li>Click 'Process' and GeoCSV will print a list of IDs in Carto which fit those standards:
<br/>
<code>#busstops [ id = "101" ],<br/>
#busstops [ id = "103" ],<br/>
#busstops [ id = "204" ]{<br/>
<br/>
}
</code></li>
</ol>

Filling out a query: three points closest to southern tip of Manhattan

<img src="http://i.imgur.com/ubQEU.png"/>

The result:

<img src="http://i.imgur.com/D0K03.png"/>

<h3>Possible Queries</h3>
<ul>
<li>[ near LAT, LNG, DEGREES ]</li>
<li>[ nearest LAT, LNG, COUNT ]</li>
<li>[ far LAT, LNG, DEGREES ]</li>
<li>[ farthest LAT, LNG, COUNT ]</li>
<li>[ neighbor_others_by DEGREES ] for clustering</li>
<li>[ inside lat1,lng1,lat2,lng2,lat3,lng3 ] for polygons</li>
<li>You don't need a plugin for INSIDE / OUTSIDE boxes: combine rules [ latitude > 10 ] [ latitude < 20 ]
<br/>[ longitude > -120 ] [ longitude < -110 ] </li>
</ul>
TODO: combine rules such as [ far LAT, LNG, DEGREES ] [ far LAT, LNG, DEGREES ] to highlight points distant from all of the lat/lngs listed

<h3>Potential uses</h3>
<ul>
<li>Highlight the three closest bus stops to your building</li>
<li>Re-style densely-packed points to make them more distinct</li>
<li>Map toxic sites within your city limits</li>
<li>Contrast points within and outside of a business/delivery service area</li>
</ul>