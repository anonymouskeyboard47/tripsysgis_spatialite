<H3>tripsysgis_spatialite</H3>
Spatialite database similar to the tripsys database in PostgreSQL. tripsysgis.sqlite

<P>

The Ubuntu command below was used to derive the spatialite tables from the running PostgreSQL database

<PRE>
nohup ogr2ogr --config PG_LIST_ALL_TABLES YES --config PG_SKIP_VIEWS YES -f "SQLite" tripsysgis.sqlite -progress PG:"dbname='tripsysgis' schemas=public host='localhost' port='5432' user='postgres' password='postgres' " -lco LAUNDER=yes  -dsco SPATIALITE=yes -lco SPATIAL_INDEX=yes -gt 65536 > spatialLiteexport.out > spatialLiteExportError.txt < /dev/null &
</PRE>

</P>
