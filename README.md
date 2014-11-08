Neo4J
=====


Baza danych : Muzyka

Baza zawiera 2 zespoły muzyczne. Do każdego z nich przypisane są albumy, które nagrali, a z albumu możemy wyciągnąć listę utworów. 

The Beatles : "Sgt. Peppers Lonely Hearts Club Band"<br>
Pink Floyd : "The Dark Side Of The Moon, Animals"<br>

oraz listy utworów


Zespół (Band) posiada 2 atrybuty: nazwę i rok założenia.
Album (Album) posiada nazwę i rok wydania.
Każdy utwór opisany jest nazwą i pozycją na płycie.

W całości baza wygląda tak: [MATCH n RETURN n LIMIT 25] :

![Cała baza] (src/cala_baza.png)


Albumy, które powstały po 1973: [MATCH (a:Album) WHERE a.year > 1973 RETURN a;]


Skrypt:<br>
CREATE (beatles:Band { name:'The Beatles', year:1960 })<br>
CREATE (pinkFloyd:Band { name:'Pink Floyd', year:1965 })<br>
<br>
CREATE (darkSide:Album { name:'The Dark Side Of The Moon', year:1973, qtySongs:9 })<br>
CREATE (animals:Album { name:'Animals', year:1977, qtySongs:5 })<br>
CREATE (stg:Album { name:'Sgt. Peppers Lonely Hearts Club Band', year:1967, qtySongs:13 })<br>
<br>
CREATE (darkSide1:Song { name:'Speak to Me/Breathe', no:1 })<br>
CREATE (darkSide2:Song { name:'On the Run', no:2 })<br>
CREATE (darkSide3:Song { name:'Time', no:3 })<br>
CREATE (darkSide4:Song { name:'The Great Gig in the Sky', no:4 })<br>
CREATE (darkSide5:Song { name:'Money', no:5 })<br>
CREATE (darkSide6:Song { name:'Us and Them', no:6 })<br>
CREATE (darkSide7:Song { name:'Any Colour You Like', no:7 })<br>
CREATE (darkSide8:Song { name:'Brain Damage', no:8 })<br>
CREATE (darkSide9:Song { name:'Eclipse', no:9 })<br>
<br>
CREATE (animals1:Song { name:'Pigs on the Wing, Part 1', no:1 })<br>
CREATE (animals2:Song { name:'Dogs', no:2 })<br>
CREATE (animals3:Song { name:'Pigs (Three Different Ones)', no:3 })<br>
CREATE (animals4:Song { name:'Sheep', no:4 })<br>
CREATE (animals5:Song { name:'Pigs on the Wing, Part 2', no:5 })<br>
<br>
CREATE (stg1:Song { name:'Sgt. Pepper’s Lonely Hearts Club Band', no:1 })<br>
CREATE (stg2:Song { name:'With a Little Help from My Friends', no:2 })<br>
CREATE (stg3:Song { name:'Lucy in the Sky with Diamonds', no:3 })<br>
CREATE (stg4:Song { name:'Getting Better', no:4 })<br>
CREATE (stg5:Song { name:'Fixing a Hole', no:5 })<br>
CREATE (stg6:Song { name:'She’s Leaving Home', no:6 })<br>
CREATE (stg7:Song { name:'Being for the Benefit of Mr. Kite!', no:7 })<br>
CREATE (stg8:Song { name:'Within You Without You', no:8 })<br>
CREATE (stg9:Song { name:'When Im Sixty-Four', no:9 })<br>
CREATE (stg10:Song { name:'Lovely Rita', no:10 })<br>
CREATE (stg11:Song { name:'Good Morning Good Morning', no:11 })<br>
CREATE (stg12:Song { name:'Sgt. Pepper’s Lonely Hearts Club Band (Reprise)', no:12 })<br>
CREATE (stg13:Song { name:'A Day in the Life', no:13 })<br>
<br>
<br>
<br>
CREATE (pinkFloyd)-[:GRA { WYDANAL_JAKO : 'ósma' }]->(darkSide)<br>
CREATE (pinkFloyd)-[:GRA { WYDANAL_JAKO : 'dziesiąta' }]->(animals)<br>
CREATE (beatles)-[:GRA { WYDANAL_JAKO : 'ósma' }]->(stg)<br>
<br>
CREATE (animals1)-[:ZNAJDUJE_SIE_NA { pozycja : '1' }]->(animals)<br>
CREATE (animals2)-[:ZNAJDUJE_SIE_NA { pozycja : '2' }]->(animals)<br>
CREATE (animals3)-[:ZNAJDUJE_SIE_NA { pozycja : '3' }]->(animals)<br>
CREATE (animals4)-[:ZNAJDUJE_SIE_NA { pozycja : '4' }]->(animals)<br>
CREATE (animals5)-[:ZNAJDUJE_SIE_NA { pozycja : '5' }]->(animals)<br>
<br>
CREATE (stg1)-[:ZNAJDUJE_SIE_NA { pozycja : '1' }]->(stg)<br>
CREATE (stg2)-[:ZNAJDUJE_SIE_NA { pozycja : '2' }]->(stg)<br>
CREATE (stg3)-[:ZNAJDUJE_SIE_NA { pozycja : '3' }]->(stg)<br>
CREATE (stg4)-[:ZNAJDUJE_SIE_NA { pozycja : '4' }]->(stg)<br>
CREATE (stg5)-[:ZNAJDUJE_SIE_NA { pozycja : '5' }]->(stg)<br>
CREATE (stg6)-[:ZNAJDUJE_SIE_NA { pozycja : '6' }]->(stg)<br>
CREATE (stg7)-[:ZNAJDUJE_SIE_NA { pozycja : '7' }]->(stg)<br>
CREATE (stg8)-[:ZNAJDUJE_SIE_NA { pozycja : '8' }]->(stg)<br>
CREATE (stg9)-[:ZNAJDUJE_SIE_NA { pozycja : '9' }]->(stg)<br>
CREATE (stg10)-[:ZNAJDUJE_SIE_NA { pozycja : '10' }]->(stg)<br>
CREATE (stg11)-[:ZNAJDUJE_SIE_NA { pozycja : '11' }]->(stg)<br>
CREATE (stg12)-[:ZNAJDUJE_SIE_NA { pozycja : '12' }]->(stg)<br>
CREATE (stg13)-[:ZNAJDUJE_SIE_NA { pozycja : '13' }]->(stg)<br>

CREATE (darkSide1)-[:ZNAJDUJE_SIE_NA { pozycja : '1' }]->(darkSide)<br>
CREATE (darkSide2)-[:ZNAJDUJE_SIE_NA { pozycja : '2' }]->(darkSide)<br>
CREATE (darkSide3)-[:ZNAJDUJE_SIE_NA { pozycja : '3' }]->(darkSide)<br>
CREATE (darkSide4)-[:ZNAJDUJE_SIE_NA { pozycja : '4' }]->(darkSide)<br>
CREATE (darkSide5)-[:ZNAJDUJE_SIE_NA { pozycja : '5' }]->(darkSide)<br>
CREATE (darkSide6)-[:ZNAJDUJE_SIE_NA { pozycja : '6' }]->(darkSide)<br>
CREATE (darkSide7)-[:ZNAJDUJE_SIE_NA { pozycja : '7' }]->(darkSide)<br>
CREATE (darkSide8)-[:ZNAJDUJE_SIE_NA { pozycja : '8' }]->(darkSide)<br>
CREATE (darkSide9)-[:ZNAJDUJE_SIE_NA { pozycja : '9' }]->(darkSide)<br>

