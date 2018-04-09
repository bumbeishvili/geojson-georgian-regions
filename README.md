# geojson-georgian-regions
GeoJson Data For Georgian Regions and Subregions

## See the preview  [at observablehq](https://beta.observablehq.com/@bumbeishvili/simple-map-of-georgia)

credits : [Eric Barrett](https://github.com/brrttwrks)



Linked resources  
[wikidata query](https://query.wikidata.org/)  
[query syntax](https://www.mediawiki.org/wiki/Wikidata_query_service/User_Manual)  
[query example](https://query.wikidata.org/#%23%20Human%20settlement%20in%20georgia%0ASELECT%20%3Fitem%20%3FitemLabel%20%3Frange%20%3Fcoor%0AWHERE%0A%7B%0A%09%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2A%20wd%3AQ486972%3B%0A%20%20%09%3Frange%20wd%3AQ230%3B%0A%20%20%09wdt%3AP625%20%3Fcoor.%0A%20%20%09SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22ka%22%20%7D%0A%7D)  

[wikidata query props](https://www.wikidata.org/wiki/Wikidata:List_of_properties)


 cities, coords and population
 ```sparql
 # Human settlement in georgia
  SELECT ?item ?itemLabel ?range ?coor ?popul
  WHERE
  {
     ?item wdt:P31/wdt:P279* wd:Q515;
      ?range wd:Q230;


      OPTIONAL {?item wdt:P1082 ?popul. }
      Optional {?item wdt:P625 ?coor.}
      Optional {?item wdt:P625 ?coor.}

      SERVICE wikibase:label { bd:serviceParam wikibase:language "ka" }
  }
 ```
 

 
 
 human settlements, coords and population
 ```sparql
 # Human settlement in georgia
 SELECT ?item ?itemLabel ?range ?coor ?popul
 WHERE
 {
  	?item wdt:P31/wdt:P279* wd:Q486972;
  	?range wd:Q230;
          
                    
    OPTIONAL {?item wdt:P1082 ?popul. }
  	Optional {?item wdt:P625 ?coor.}
    Optional {?item wdt:P625 ?coor.}

  	SERVICE wikibase:label { bd:serviceParam wikibase:language "ka" }
 }
 ```
 
 
 
 [overpass-turbo](http://overpass-turbo.eu/)  
 query  
 ```
area[name="საქართველო"];
(node["place"~"town|city"](area););
out;
 ```
