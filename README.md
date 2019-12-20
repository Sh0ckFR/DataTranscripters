# DataTranscripters

This repository will be used to describe a new method to decrease the volume of big data volumes.

I saw some people on Twitter talking about the Artificial Intelligence in 2019, sadly most of the time, people don't know what they're stocking and they stock the data directly (they are trusting the computing power and the stockage to create a pseudo Artificial Intelligence).

There's a new approach, stock a limited data if the data concern a link between the different entities.

Let me explain you, you're an human, you probably have pets, maybe 1 dog and 2 cats.

Actually in a common database, we stock you like this data structure:

- Your firstname is 'John', your name is 'Doe' and you have 1 dog 'called doggy' and 2 cats 'called Jessie and James', Jessie is White, and James is Black, so you will stock all the data about that like that :

**Table 'humans'**

| ID | NAME | FIRSTNAME |
|----|------|-----------|
| 1  | Doe  | John      |

**Table 'pets'**

| ID | NAME   | COLOR |
|----|--------|-------|
| 1  | Jessie | White |
| 2  | James  | Black |

**Table 'humans-pets-relations'**

| ID_HUMAN | ID_PET |
|----------|--------|
| 1        | 1      |
| 1        | 2      |
  
Let's try my approach, you could only stock something like:

```
1H[John-Doe]=1D[Doggy]/2C[Jessie#FFF,James#000]
```

In only one line, you could stock your data and your relations:

```
1 Human named [John-Doe] got 1 Dog named [Doggy]

AND

2 Cats [Jessie] who is White [#FFF is white in Hexa] and [James] who is Black [#000 is black in Hexa].
```

All data could be stored like that via **common DataTranscripters** (json compatible why not) and a DataTranscripter could represent the structure of a real entity (here the pets) but you could apply this structure to all entities in the world (cars, homes objects, computer hardwares etc...)

The principal objective is to be agree to a common langage to stock the data correctly with DataTranscripters only in English like this one for humans (pull requests could be interesting if a community could support the translations):

```
{
  'humans': {
    'ID': 'ID',
    'name': 'N',
    'firstname': 'F',
    'age': 'A',
    'relations': 'R'
  }
}
```

And the result could be:

```
ID[1]H[F=John,N=Doe,A=30,R=2]P[1D['Doggy'#FFF]3C['Tom'#000, 'Jerry'#FFF, 'Mickey'#00FF00]]

ID[2]H[F=Jane,N=Doe,A=42,R=1]

ID[3]H[F=Jack,N=Dupont,A=18,R=1,2]
```

The result in this case:

```
John is a relation of Jane and Jane is a relation of John, John have 4 Pets, 1 dog (named Doggy and Doggy is White), 3 cats (Tom -> Black, Jerry -> White and Mickey -> Red).
Jack got 2 relations, John and Jane and he's 18 years old and his name is Dupont.
```

The DataTranscripters could be only one letter or multiple letters if necessary (you want do translate a guinea pig, the letters could be 'GP' for Guinea Pig, it doesn't matter, the most important thing is to preserve a common and (international) langage to stock the data.

DataTranscripters could be used to translate the data between 2 databases or just to got an human version of the stored data.

I hope you liked this theory, if you are interested, just share this github and talk about that around you.
