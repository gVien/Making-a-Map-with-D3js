# Making-a-Map-with-D3js

Learning how to make a map with D3.js!

I learned how to build the map at [http://bost.ocks.org/mike/map](http://bost.ocks.org/mike/map/).

The instruction at section `Converting Data` might not be so clear and you might end up with the following errors:

`FAILURE:
Unable to open datasource `ne_10m_admin_0_map_subunits.shp' with the following drivers.`

To fix this, download the data at [map subunits](http://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/cultural/ne_10m_admin_0_map_subunits.zip)

and then run

`ogr2ogr \`<br>
`-f GeoJSON \`<br>
`-where "ADM0_A3 IN ('GBR', 'IRL')" \`<br>
`subunits.json \`<br>
`ne_10m_admin_0_map_subunits.shp`<br>

Likewise, download the [populated places](http://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/cultural/ne_10m_populated_places.zip)

and run the remaining commands in the tutorial or:

`ogr2ogr \`<br>
`-f GeoJSON \`<br>
`-where "ISO_A2 = 'GB' AND SCALERANK < 8" \`<br>
`places.json \`<br>
`ne_10m_populated_places.shp`<br>

and

`topojson \`<br>
`-o uk.json \`<br>
`--id-property SU_A3 \`<br>
`--properties name=NAME \`<br>
`-- \`<br>
`subunits.json \`<br>
`places.json`<br>

You should now have all the files you need to go through the tutorials.
