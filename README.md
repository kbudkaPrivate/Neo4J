Neo4J
=====


Baza danych : Muzyka

Baza zawiera 2 zespoły muzyczne. Do każdego z nich przypisane są albumy, które nagrali, a z albumu możemy wyciągnąć listę utworów. 

The Beatles : Sgt. Peppers Lonely Hearts Club Band
Pink Floyd : The Dark Side Of The Moon, Animals

oraz listy utworów


Zespół (Band) posiada 2 atrybuty: nazwę i rok założenia.
Album (Album) posiada nazwę i rok wydania.
Każdy utwór opisany jest nazwą i pozycją na płycie.

W całości baza wygląda tak: [MATCH n RETURN n LIMIT 25] :

![Cała baza] (src/cala_baza.png)


Albumy, które powstały po 1973: [MATCH (a:Album) WHERE a.year > 1973 RETURN a;]


Skrypt:
CREATE (beatles:Band { name:'The Beatles', year:1960 })
CREATE (pinkFloyd:Band { name:'Pink Floyd', year:1965 })

CREATE (darkSide:Album { name:'The Dark Side Of The Moon', year:1973, qtySongs:9 })
CREATE (animals:Album { name:'Animals', year:1977, qtySongs:5 })
CREATE (stg:Album { name:'Sgt. Peppers Lonely Hearts Club Band', year:1967, qtySongs:13 })

CREATE (darkSide1:Song { name:'Speak to Me/Breathe', no:1 })
CREATE (darkSide2:Song { name:'On the Run', no:2 })
CREATE (darkSide3:Song { name:'Time', no:3 })
CREATE (darkSide4:Song { name:'The Great Gig in the Sky', no:4 })
CREATE (darkSide5:Song { name:'Money', no:5 })
CREATE (darkSide6:Song { name:'Us and Them', no:6 })
CREATE (darkSide7:Song { name:'Any Colour You Like', no:7 })
CREATE (darkSide8:Song { name:'Brain Damage', no:8 })
CREATE (darkSide9:Song { name:'Eclipse', no:9 })

CREATE (animals1:Song { name:'Pigs on the Wing, Part 1', no:1 })
CREATE (animals2:Song { name:'Dogs', no:2 })
CREATE (animals3:Song { name:'Pigs (Three Different Ones)', no:3 })
CREATE (animals4:Song { name:'Sheep', no:4 })
CREATE (animals5:Song { name:'Pigs on the Wing, Part 2', no:5 })

CREATE (stg1:Song { name:'Sgt. Pepper’s Lonely Hearts Club Band', no:1 })
CREATE (stg2:Song { name:'With a Little Help from My Friends', no:2 })
CREATE (stg3:Song { name:'Lucy in the Sky with Diamonds', no:3 })
CREATE (stg4:Song { name:'Getting Better', no:4 })
CREATE (stg5:Song { name:'Fixing a Hole', no:5 })
CREATE (stg6:Song { name:'She’s Leaving Home', no:6 })
CREATE (stg7:Song { name:'Being for the Benefit of Mr. Kite!', no:7 })
CREATE (stg8:Song { name:'Within You Without You', no:8 })
CREATE (stg9:Song { name:'When Im Sixty-Four', no:9 })
CREATE (stg10:Song { name:'Lovely Rita', no:10 })
CREATE (stg11:Song { name:'Good Morning Good Morning', no:11 })
CREATE (stg12:Song { name:'Sgt. Pepper’s Lonely Hearts Club Band (Reprise)', no:12 })
CREATE (stg13:Song { name:'A Day in the Life', no:13 })



CREATE (pinkFloyd)-[:GRA { WYDANAL_JAKO : 'ósma' }]->(darkSide)
CREATE (pinkFloyd)-[:GRA { WYDANAL_JAKO : 'dziesiąta' }]->(animals)
CREATE (beatles)-[:GRA { WYDANAL_JAKO : 'ósma' }]->(stg)

CREATE (animals1)-[:ZNAJDUJE_SIE_NA { pozycja : '1' }]->(animals)
CREATE (animals2)-[:ZNAJDUJE_SIE_NA { pozycja : '2' }]->(animals)
CREATE (animals3)-[:ZNAJDUJE_SIE_NA { pozycja : '3' }]->(animals)
CREATE (animals4)-[:ZNAJDUJE_SIE_NA { pozycja : '4' }]->(animals)
CREATE (animals5)-[:ZNAJDUJE_SIE_NA { pozycja : '5' }]->(animals)

CREATE (stg1)-[:ZNAJDUJE_SIE_NA { pozycja : '1' }]->(stg)
CREATE (stg2)-[:ZNAJDUJE_SIE_NA { pozycja : '2' }]->(stg)
CREATE (stg3)-[:ZNAJDUJE_SIE_NA { pozycja : '3' }]->(stg)
CREATE (stg4)-[:ZNAJDUJE_SIE_NA { pozycja : '4' }]->(stg)
CREATE (stg5)-[:ZNAJDUJE_SIE_NA { pozycja : '5' }]->(stg)
CREATE (stg6)-[:ZNAJDUJE_SIE_NA { pozycja : '6' }]->(stg)
CREATE (stg7)-[:ZNAJDUJE_SIE_NA { pozycja : '7' }]->(stg)
CREATE (stg8)-[:ZNAJDUJE_SIE_NA { pozycja : '8' }]->(stg)
CREATE (stg9)-[:ZNAJDUJE_SIE_NA { pozycja : '9' }]->(stg)
CREATE (stg10)-[:ZNAJDUJE_SIE_NA { pozycja : '10' }]->(stg)
CREATE (stg11)-[:ZNAJDUJE_SIE_NA { pozycja : '11' }]->(stg)
CREATE (stg12)-[:ZNAJDUJE_SIE_NA { pozycja : '12' }]->(stg)
CREATE (stg13)-[:ZNAJDUJE_SIE_NA { pozycja : '13' }]->(stg)

CREATE (darkSide1)-[:ZNAJDUJE_SIE_NA { pozycja : '1' }]->(darkSide)
CREATE (darkSide2)-[:ZNAJDUJE_SIE_NA { pozycja : '2' }]->(darkSide)
CREATE (darkSide3)-[:ZNAJDUJE_SIE_NA { pozycja : '3' }]->(darkSide)
CREATE (darkSide4)-[:ZNAJDUJE_SIE_NA { pozycja : '4' }]->(darkSide)
CREATE (darkSide5)-[:ZNAJDUJE_SIE_NA { pozycja : '5' }]->(darkSide)
CREATE (darkSide6)-[:ZNAJDUJE_SIE_NA { pozycja : '6' }]->(darkSide)
CREATE (darkSide7)-[:ZNAJDUJE_SIE_NA { pozycja : '7' }]->(darkSide)
CREATE (darkSide8)-[:ZNAJDUJE_SIE_NA { pozycja : '8' }]->(darkSide)
CREATE (darkSide9)-[:ZNAJDUJE_SIE_NA { pozycja : '9' }]->(darkSide)

