SHP to OSM 0.6.1
Copyright Ian Dees, All rights reserved
20 Sept 2009
Project source: http://svn.yellowbkpk.com/geo/trunk/shp-to-osm/
Project website: http://redmine.yellowbkpk.com/projects/show/geo

Dependencies

 Dependencies are handled by the Maven pom.xml file included. The JAR distributed at the above
 site includes all of the required classfiles to run out of the box.

Rules file

 The rules file is a simple comma-separated text file:
 
 Field:  Description:
      1  The shapefile type to match (outer, inner, line, point)
      2  The source attribute name to match
      3  The source attribute value to match. Can be empty to match all values.
      4  The name of the tag to apply when the source key/value pair match.
      5  The value of the tag to apply. Use a sinlgle dash ("-") to use the original value.

Running

 Use the following command line to run the app. Also, you can use the .bat or .sh run files
to issue the same command as long as you give it the same set of arguments. The [-t] at the 
end of the command here is an optional flag to tell the application to only include ways that
have had a tag applied to them. For now, it is required to be at the end of the arguments list.

 java -cp shp-to-osm-0.6.1-with-dependencies.jar Main
                                  --shapefile <path to input shapefile> \
                                  --rulesfile <path to rules file> \
                                  --osmfile <prefix of the output osm file name> \
                                  [--outdir <root directory for output>] \
                                  [--maxnodes <max nodes per osm file>] \
                                  [-t]