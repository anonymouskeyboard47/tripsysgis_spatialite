<H3>Introduction</H3>
<P>
This is a Spatialite database (tripsysgis.sqlite) that is completely similar to the <EM>tripsysgis</EM> database in the PostgreSQL database found within <A href="https://github.com/anonymouskeyboard47/postgresql_database">this repository</A>. 
</P>
<P>
The Ubuntu command below was used to derive the Spatialite table-sets from the running PostgreSQL database on my server. The entire spatialite database is over 1GB in size, therefore I will try and extract each individual table to make the subsets useful for lighter work.
</P>

<P>
<PRE>
<CODE>
nohup ogr2ogr --config PG_LIST_ALL_TABLES YES --config PG_SKIP_VIEWS YES -f "SQLite" tripsysgis.sqlite -progress PG:"dbname='tripsysgis' schemas=public host='localhost' port='5432' user='postgres' password='postgres' " -lco LAUNDER=yes  -dsco SPATIALITE=yes -lco SPATIAL_INDEX=yes -gt 65536 > spatialLiteexport.out > spatialLiteExportError.txt < /dev/null &
</CODE>
</PRE>
</P>


<H4>How to view the database</H4>
<P>
There are several ways of rendering the geographical/spatial content in a Spatialite database. A Spatialite database is inherently a SQLite database, and therefore
</P>
<P>
QGIS (tm), TileMill (tm), AutoCadMap (tm) 2013, FME (tm), ESRI ArcGIS(tm) are some of the desktop applications that you can use to render the maps in the Spatialite database. For a complete list of software applications available for working woth Spatialite please read through the <EM>Reference</EM> section below.
</P>

<H4>References</H4>
<UL>
<LI><A href="http://trac.osgeo.org/postgis/wiki/SpatiaLite">http://trac.osgeo.org/postgis/wiki/SpatiaLite</A>
<LI><A href="http://en.wikipedia.org/wiki/SpatiaLite">http://en.wikipedia.org/wiki/SpatiaLite</A>
</UL>

All the trademarks listed on this webpage are property of their respective owners.
