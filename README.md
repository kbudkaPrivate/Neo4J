Neo4J
=====


Baza danych : Muzyka

Baza zawiera 2 zespoły muzyczne. Do każdego z nich przypisane są albumy, które nagrali, a z albumu możemy wyciągnąć listę utworów. 

Zespół (Band) posiada 2 atrybuty: nazwę i rok założenia.
Album (Album) posiada nazwę i rok wydania.
Każdy utwór opisany jest nazwą i pozycją na płycie.

W całości baza wygląda tak:

[MATCH n RETURN n LIMIT 25] :

![Cała baza] (src/cala_baza.png)

