# Guía de NLP I

## Ejercicio 1

Dada la siguiente tabla de Count Vectorizer:

|    | Car | Dog | Police | Gun |
|----|-----|-----|--------|-----|
| D1 | 0   | 1   | 2      | 5   |
| D2 | 2   | 1   | 1      | 4   |
| D3 | 1   | 0   | 0      | 0   |


Devolver el documento que menos distancia coseno tenga con la query:
"Police officer accidentaly discharge their gun while eating a donut. Car survives."

## Ejercicio 2

Dados los siguientes documentos:

```
D1: news about organic food campaign
D2: news of presidential campaign
D3: news of presidential campaign, presidential candidate
D4: news of presidential campaign presidential candidate
D5: news of organic food campaign campaign campaign campaign
```

Si nuestra consulta es "news about presidential campaign" y usamos TF-IDF: Calcule los vectores de cada documento y de la consulta y encuentre el documento más cercano. ¿Cómo cambia usando CountVectorizer?
