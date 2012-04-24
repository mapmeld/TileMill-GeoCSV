<h3>GeoCSV</h3>

Helps you create geo queries to style point features in TileMill.<br/>
Works with CSV files from <a href="http://geocommons.com">GeoCommons</a>, the EPA, and more.<br/>
Potentially works with any layer that includes latitude and longitude points as attributes, in addition to geometry

<h3>Install</h3>
Mac OS X Terminal one-liner:
<code>cp -r GeoCSV /Applications/TileMill.app/Contents/Resources/plugins/</code>

<h3>What to do</h3>
<ol>
<li>Open the new GeoCSV plugin.</li>
<li>Write code like this:<br/>
<code>
#busstops [ near 32.3, -112.1, 0.5 ] {<br/>
&nbsp;&nbsp;&nbsp;&nbsp;marker-fill: red;<br/>
}
</code></li>
<li>Click 'Process' and GeoCSV will print a list of IDs in Carto which fit those standards:
<code>
#busstops [ id = "101" ],<br/>
#busstops [ id = "103" ],<br/>
#busstops [ id = "204" ]{<br/>
&nbsp;&nbsp;&nbsp;&nbsp;marker-fill: red;<br/>
}
</code></li>
</ol>

<img src="http://i.imgur.com/ubQEU.png"/>

<img src="http://i.imgur.com/D0K03.png"/>

<h3>Possible Queries</h3>
<ul>
<li>[ near LAT, LNG, DEGREES ]</li>
<li>[ nearest LAT, LNG, COUNT ]</li>
<li>[ far LAT, LNG, DEGREES ]</li>
<li>[ farthest LAT, LNG, COUNT ]</li>
<li>[ neighbor_others_by DEGREES ] for clustering</li>
<li>[ inside lat1,lng1,lat2,lng2,lat3,lng3 ] for polygons</li>
<li>You don't need a plugin for INSIDE / OUTSIDE boxes: combine rules [ latitude > 10 ] [ latitude < 20 ] [ longitude > -120 ] [ longitude < -110 ] </li>
</ul>
TODO: combine rules such as [ far LAT, LNG, DEGREES ] [ far LAT, LNG, DEGREES ] to highlight points distant from all of the lat/lngs listed

<h3>Potential uses</h3>
<ul>
<li>Highlight the three closest bus stops to your building</li>
<li>Re-style densely-packed points to make them more distinct</li>
<li></li>
</ul>