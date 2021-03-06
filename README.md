# assignment-05-set-operations-in-sql

## Query #1

*The union of all the tracks with genreid 18 and 20*

```sql
(SELECT "TrackId", "Name", "GenreId" FROM public."Track" where "GenreId" = 18)
union
(SELECT "TrackId", "Name", "GenreId" FROM public."Track" where "GenreId" = 20)
```

#### Results:

| "TrackId" | "Name"                                   | "GenreId" | 
|-----------|------------------------------------------|-----------| 
| 3243      | "Murder On the Rising Star"              | 20        | 
| 3232      | "The Long Patrol"                        | 20        | 
| 3246      | "Baltar's Escape"                        | 20        | 
| 3248      | "Take the Celestra"                      | 20        | 
| 2837      | "Crossroads, Pt. 1"                      | 20        | 
| 3236      | "The Young Lords"                        | 20        | 
| 3230      | "Lost Planet of the Gods, Pt. 2"         | 20        | 
| 2825      | "A Measure of Salvation"                 | 18        | 
| 3228      | "Battlestar Galactica, Pt. 3"            | 20        | 
| 3238      | "The Living Legend, Pt. 2"               | 20        | 
| 3237      | "The Living Legend, Pt. 1"               | 20        | 
| 3231      | "The Lost Warrior"                       | 20        | 
| 3244      | "Greetings from Earth, Pt. 1"            | 20        | 
| 3242      | "The Man With Nine Lives"                | 20        | 
| 2828      | "The Passage"                            | 18        | 
| 3226      | "Battlestar Galactica, Pt. 1"            | 20        | 
| 2836      | "The Son Also Rises"                     | 18        | 
| 3245      | "Greetings from Earth, Pt. 2"            | 20        | 
| 2832      | "The Woman King"                         | 18        | 
| 2819      | "Battlestar Galactica: The Story So Far" | 18        | 
| 3249      | "The Hand of God"                        | 20        | 
| 2831      | "Taking a Break from All Your Worries"   | 18        | 
| 2838      | "Crossroads, Pt. 2"                      | 20        | 
| 2826      | "Hero"                                   | 18        | 
| 2830      | "Rapture"                                | 18        | 
| 3247      | "Experiment In Terra"                    | 20        | 
| 2829      | "The Eye of Jupiter"                     | 18        | 
| 2835      | "Maelstrom"                              | 18        | 
| 2834      | "Dirty Hands"                            | 18        | 
| 3240      | "War of the Gods, Pt. 1"                 | 20        | 
| 3233      | "The Gun On Ice Planet Zero, Pt. 1"      | 20        | 
| 2827      | "Unfinished Business"                    | 18        | 
| 3239      | "Fire In Space"                          | 20        | 
| 3229      | "Lost Planet of the Gods, Pt. 1"         | 20        | 
| 3234      | "The Gun On Ice Planet Zero, Pt. 2"      | 20        | 
| 3235      | "The Magnificent Warriors"               | 20        | 
| 3227      | "Battlestar Galactica, Pt. 2"            | 20        | 
| 2833      | "A Day In the Life"                      | 18        | 
| 3241      | "War of the Gods, Pt. 2"                 | 20        | 


## Query #2

*The intersection of all the invoices that are cheaper than 10 dollars and the invoices that are more expensive than 5 dollars*

```sql
(SELECT "InvoiceId", "CustomerId", "InvoiceDate", "Total" FROM public."Invoice" where "Total" < 10)
intersect
(SELECT "InvoiceId", "CustomerId", "InvoiceDate", "Total" FROM public."Invoice" where "Total" > 5)
```

#### Results:

| "InvoiceId" | "CustomerId" | "InvoiceDate"         | "Total" | 
|-------------|--------------|-----------------------|---------| 
| 297         | 11           | "2012-07-28 00:00:00" | "5.94"  | 
| 165         | 3            | "2010-12-20 00:00:00" | "8.91"  | 
| 256         | 25           | "2012-01-27 00:00:00" | "8.91"  | 
| 326         | 51           | "2012-12-02 00:00:00" | "8.91"  | 
| 24          | 4            | "2009-04-06 00:00:00" | "5.94"  | 
| 179         | 20           | "2011-02-20 00:00:00" | "8.91"  | 
| 46          | 6            | "2009-07-11 00:00:00" | "8.91"  | 
| 213         | 27           | "2011-07-22 00:00:00" | "5.94"  | 
| 241         | 2            | "2011-11-23 00:00:00" | "5.94"  | 
| 25          | 10           | "2009-04-09 00:00:00" | "8.91"  | 
| 4           | 14           | "2009-01-06 00:00:00" | "8.91"  | 
| 17          | 25           | "2009-03-06 00:00:00" | "5.94"  | 
| 136         | 22           | "2010-08-15 00:00:00" | "5.94"  | 
| 172         | 41           | "2011-01-20 00:00:00" | "8.91"  | 
| 347         | 47           | "2013-03-05 00:00:00" | "8.91"  | 
| 151         | 45           | "2010-10-19 00:00:00" | "8.91"  | 
| 276         | 15           | "2012-04-26 00:00:00" | "5.94"  | 
| 109         | 53           | "2010-04-16 00:00:00" | "8.91"  | 
| 122         | 5            | "2010-06-14 00:00:00" | "5.94"  | 
| 199         | 10           | "2011-05-21 00:00:00" | "5.94"  | 
| 368         | 43           | "2013-06-06 00:00:00" | "8.91"  | 
| 360         | 58           | "2013-05-03 00:00:00" | "5.94"  | 
| 235         | 29           | "2011-10-26 00:00:00" | "8.91"  | 
| 290         | 32           | "2012-06-27 00:00:00" | "5.94"  | 
| 158         | 24           | "2010-11-19 00:00:00" | "8.91"  | 
| 228         | 50           | "2011-09-25 00:00:00" | "8.91"  | 
| 346         | 41           | "2013-03-02 00:00:00" | "5.94"  | 
| 234         | 23           | "2011-10-23 00:00:00" | "5.94"  | 
| 137         | 28           | "2010-08-18 00:00:00" | "8.91"  | 
| 11          | 52           | "2009-02-06 00:00:00" | "8.91"  | 
| 39          | 27           | "2009-06-10 00:00:00" | "8.91"  | 
| 143         | 1            | "2010-09-15 00:00:00" | "5.94"  | 
| 242         | 8            | "2011-11-26 00:00:00" | "8.91"  | 
| 102         | 15           | "2010-03-16 00:00:00" | "9.91"  | 
| 333         | 30           | "2013-01-02 00:00:00" | "8.91"  | 
| 403         | 56           | "2013-11-08 00:00:00" | "8.91"  | 
| 18          | 31           | "2009-03-09 00:00:00" | "8.91"  | 
| 381         | 54           | "2013-08-04 00:00:00" | "5.94"  | 
| 339         | 3            | "2013-01-30 00:00:00" | "5.94"  | 
| 410         | 35           | "2013-12-09 00:00:00" | "8.91"  | 
| 200         | 16           | "2011-05-24 00:00:00" | "8.91"  | 
| 95          | 36           | "2010-02-13 00:00:00" | "8.91"  | 
| 304         | 49           | "2012-08-28 00:00:00" | "5.94"  | 
| 81          | 19           | "2009-12-13 00:00:00" | "8.91"  | 
| 74          | 40           | "2009-11-12 00:00:00" | "8.91"  | 
| 94          | 30           | "2010-02-10 00:00:00" | "5.94"  | 
| 409         | 29           | "2013-12-06 00:00:00" | "5.94"  | 
| 214         | 33           | "2011-07-25 00:00:00" | "8.91"  | 
| 178         | 14           | "2011-02-17 00:00:00" | "5.94"  | 
| 277         | 21           | "2012-04-29 00:00:00" | "8.91"  | 
| 123         | 11           | "2010-06-17 00:00:00" | "8.91"  | 
| 108         | 47           | "2010-04-13 00:00:00" | "5.94"  | 
| 353         | 20           | "2013-04-02 00:00:00" | "5.94"  | 
| 255         | 19           | "2012-01-24 00:00:00" | "5.94"  | 
| 45          | 59           | "2009-07-08 00:00:00" | "5.94"  | 
| 395         | 12           | "2013-10-05 00:00:00" | "5.94"  | 
| 150         | 39           | "2010-10-16 00:00:00" | "5.94"  | 
| 291         | 38           | "2012-06-30 00:00:00" | "8.91"  | 
| 354         | 26           | "2013-04-05 00:00:00" | "8.91"  | 
| 52          | 38           | "2009-08-08 00:00:00" | "5.94"  | 
| 130         | 49           | "2010-07-18 00:00:00" | "8.91"  | 
| 205         | 44           | "2011-06-20 00:00:00" | "7.96"  | 
| 249         | 46           | "2011-12-27 00:00:00" | "8.91"  | 
| 340         | 9            | "2013-02-02 00:00:00" | "8.91"  | 
| 115         | 26           | "2010-05-14 00:00:00" | "5.94"  | 
| 10          | 46           | "2009-02-03 00:00:00" | "5.94"  | 
| 382         | 1            | "2013-08-07 00:00:00" | "8.91"  | 
| 262         | 57           | "2012-02-24 00:00:00" | "5.94"  | 
| 32          | 48           | "2009-05-10 00:00:00" | "8.91"  | 
| 164         | 56           | "2010-12-17 00:00:00" | "5.94"  | 
| 361         | 5            | "2013-05-06 00:00:00" | "8.91"  | 
| 67          | 2            | "2009-10-12 00:00:00" | "8.91"  | 
| 116         | 32           | "2010-05-17 00:00:00" | "8.91"  | 
| 325         | 45           | "2012-11-29 00:00:00" | "5.94"  | 
| 53          | 44           | "2009-08-11 00:00:00" | "8.91"  | 
| 263         | 4            | "2012-02-27 00:00:00" | "8.91"  | 
| 60          | 23           | "2009-09-11 00:00:00" | "8.91"  | 
| 73          | 34           | "2009-11-09 00:00:00" | "5.94"  | 
| 389         | 39           | "2013-09-07 00:00:00" | "8.91"  | 
| 269         | 36           | "2012-03-26 00:00:00" | "5.94"  | 
| 31          | 42           | "2009-05-07 00:00:00" | "5.94"  | 
| 206         | 48           | "2011-06-21 00:00:00" | "8.94"  | 
| 396         | 18           | "2013-10-08 00:00:00" | "8.91"  | 
| 185         | 52           | "2011-03-20 00:00:00" | "5.94"  | 
| 144         | 7            | "2010-09-18 00:00:00" | "8.91"  | 
| 87          | 51           | "2010-01-10 00:00:00" | "6.94"  | 
| 402         | 50           | "2013-11-05 00:00:00" | "5.94"  | 
| 367         | 37           | "2013-06-03 00:00:00" | "5.94"  | 
| 248         | 40           | "2011-12-24 00:00:00" | "5.94"  | 
| 318         | 7            | "2012-10-29 00:00:00" | "5.94"  | 
| 59          | 17           | "2009-09-08 00:00:00" | "5.94"  | 
| 221         | 12           | "2011-08-25 00:00:00" | "8.91"  | 
| 157         | 18           | "2010-11-16 00:00:00" | "5.94"  | 
| 270         | 42           | "2012-03-29 00:00:00" | "8.91"  | 
| 192         | 31           | "2011-04-20 00:00:00" | "5.94"  | 
| 171         | 35           | "2011-01-17 00:00:00" | "5.94"  | 
| 310         | 24           | "2012-09-27 00:00:00" | "7.96"  | 
| 283         | 53           | "2012-05-27 00:00:00" | "5.94"  | 
| 305         | 55           | "2012-08-31 00:00:00" | "8.91"  | 
| 66          | 55           | "2009-10-09 00:00:00" | "5.94"  | 
| 374         | 16           | "2013-07-04 00:00:00" | "5.94"  | 
| 101         | 9            | "2010-03-13 00:00:00" | "5.94"  | 
| 186         | 58           | "2011-03-23 00:00:00" | "8.91"  | 
| 3           | 8            | "2009-01-03 00:00:00" | "5.94"  | 
| 129         | 43           | "2010-07-15 00:00:00" | "5.94"  | 
| 388         | 33           | "2013-09-04 00:00:00" | "5.94"  | 
| 284         | 59           | "2012-05-30 00:00:00" | "8.91"  | 
| 207         | 54           | "2011-06-24 00:00:00" | "8.91"  | 
| 38          | 21           | "2009-06-07 00:00:00" | "5.94"  | 
| 220         | 6            | "2011-08-22 00:00:00" | "5.94"  | 
| 80          | 13           | "2009-12-10 00:00:00" | "5.94"  | 
| 332         | 24           | "2012-12-30 00:00:00" | "5.94"  | 
| 227         | 44           | "2011-09-22 00:00:00" | "5.94"  | 
| 375         | 22           | "2013-07-07 00:00:00" | "8.91"  | 
| 319         | 13           | "2012-11-01 00:00:00" | "8.91"  | 

## Query #3

*The set of all customers from USA, subtracted by the set of all customers with an email ending in 'yahoo.com'*

```sql
(SELECT "CustomerId", "FirstName", "LastName", "Country", "Email" FROM public."Customer" where "Country" = 'USA')
except
(SELECT "CustomerId", "FirstName", "LastName", "Country", "Email" FROM public."Customer" where "Email" like '%yahoo.com')
```

#### Results:

| "CustomerId" | "FirstName" | "LastName"   | "Country" | "Email"                    | 
|--------------|-------------|--------------|-----------|----------------------------| 
| 28           | "Julia"     | "Barnett"    | "USA"     | "jubarnett@gmail.com"      | 
| 27           | "Patrick"   | "Gray"       | "USA"     | "patrick.gray@aol.com"     | 
| 22           | "Heather"   | "Leacock"    | "USA"     | "hleacock@gmail.com"       | 
| 17           | "Jack"      | "Smith"      | "USA"     | "jacksmith@microsoft.com"  | 
| 21           | "Kathy"     | "Chase"      | "USA"     | "kachase@hotmail.com"      | 
| 19           | "Tim"       | "Goyer"      | "USA"     | "tgoyer@apple.com"         | 
| 16           | "Frank"     | "Harris"     | "USA"     | "fharris@google.com"       | 
| 18           | "Michelle"  | "Brooks"     | "USA"     | "michelleb@aol.com"        | 
| 26           | "Richard"   | "Cunningham" | "USA"     | "ricunningham@hotmail.com" | 
| 24           | "Frank"     | "Ralston"    | "USA"     | "fralston@gmail.com"       | 
| 20           | "Dan"       | "Miller"     | "USA"     | "dmiller@comcast.com"      | 

## Query #4

*The union of the set of all albums playing something by Mozart and the set of all albums playing something with Bach*

```sql
(SELECT "TrackId", "Name", "Composer", "GenreId" FROM public."Track" where "Composer" = 'Johann Sebastian Bach')
union
(SELECT "TrackId", "Name", "Composer", "GenreId" FROM public."Track" where "Composer" like 'Wolfgang Amadeus Mozart')
```

#### Results:

| "TrackId"                                                           | "Name"                                                                                     | "Composer"                | "GenreId" | 
|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------|---------------------------|-----------| 
| 3413                                                                | "Concerto for Clarinet in A Major, K. 622: II. Adagio"                                     | "Wolfgang Amadeus Mozart" | 24        | 
| 3482                                                                | "Suite No. 3 in D, BWV 1068: III. Gavotte I & II"                                          | "Johann Sebastian Bach"   | 24        | 
| 3409                                                                | "Suite for Solo Cello No. 1 in G Major, BWV 1007: I. Prélude"                              | "Johann Sebastian Bach"   | 24        | 
| 3408                                                                | "Aria Mit 30 Veränderungen, BWV 988 ""Goldberg Variations"": Aria"                         | "Johann Sebastian Bach"   | 24        | 
| 3502                                                                | "Quintet for Horn, Violin, 2 Violas, and Cello in E Flat Major, K. 407/386c: III. Allegro" | "Wolfgang Amadeus Mozart" | 24        | 
| 3433                                                                | "Concerto No.2 in F Major, BWV1047, I. Allegro"                                            | "Johann Sebastian Bach"   | 24        | 
| 3407                                                                | "Concerto for 2 Violins in D Minor, BWV 1043: I. Vivace"                                   | "Johann Sebastian Bach"   | 24        | 
| 3430                                                                | "Toccata and Fugue in D Minor, BWV 565: I. Toccata"                                        | "Johann Sebastian Bach"   | 24        | 
| 3412 | ""Eine Kleine Nachtmusik" Serenade In G, K. 525: I. Allegro" | "Wolfgang Amadeus Mozart"                                                                  | 24                        |           | 
| 3490                                                                | "Partita in E Major, BWV 1006A: I. Prelude"                                                | "Johann Sebastian Bach"   | 24        | 
| 3454                                                                | "Symphony No. 41 in C Major, K. 551, ""Jupiter"": IV. Molto allegro"                       | "Wolfgang Amadeus Mozart" | 24        | 
| 3451                                                                | "Die Zauberflöte, K.620: ""Der Hölle Rache Kocht in Meinem Herze"""                        | "Wolfgang Amadeus Mozart" | 25        | 
