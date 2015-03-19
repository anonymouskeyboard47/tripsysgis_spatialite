<H3>tripsysgis_spatialite</H3>
Spatialite database similar to the <EM>tripsysgis</EM> database in the PostgreSQL database <A href="https://github.com/anonymouskeyboard47/postgresql_database">in this repository</A>. tripsysgis.sqlite

<P>
The Ubuntu command below was used to derive the Spatialite table-sets from the running PostgreSQL database on my server. The entire database is over 1GB in size, therefore I will try and extract each individual table to make the subsets useful for lighter work.
</P>

<P>
<PRE>
<CODE>
nohup ogr2ogr --config PG_LIST_ALL_TABLES YES --config PG_SKIP_VIEWS YES -f "SQLite" tripsysgis.sqlite -progress PG:"dbname='tripsysgis' schemas=public host='localhost' port='5432' user='postgres' password='postgres' " -lco LAUNDER=yes  -dsco SPATIALITE=yes -lco SPATIAL_INDEX=yes -gt 65536 > spatialLiteexport.out > spatialLiteExportError.txt < /dev/null &
</CODE>
</PRE>
</P>
