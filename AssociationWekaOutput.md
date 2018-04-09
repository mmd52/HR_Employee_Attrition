### Association rule output from weka

```
            MonthlyIncome
=== Associator model (full training set) ===


Apriori
=======

Minimum support: 0.15 (221 instances)
Minimum metric <confidence>: 0.9
Number of cycles performed: 17

Generated sets of large itemsets:

Size of set of large itemsets L(1): 16

Size of set of large itemsets L(2): 35

Size of set of large itemsets L(3): 38

Size of set of large itemsets L(4): 15

Best rules found:

 1. JobRole=Sales Executive 326 ==> Department=Sales 326    <conf:(1)> lift:(3.3) lev:(0.15) [227] conv:(227.09)
 2. JobRole=Research Scientist 292 ==> Department=Research & Development 292    <conf:(1)> lift:(1.53) lev:(0.07) [101] conv:(101.11)
 3. JobRole=Research Scientist MonthlyIncome=Poor 291 ==> Department=Research & Development 291    <conf:(1)> lift:(1.53) lev:(0.07) [100] conv:(100.76)
 4. Attrition=No JobRole=Sales Executive 269 ==> Department=Sales 269    <conf:(1)> lift:(3.3) lev:(0.13) [187] conv:(187.39)
 5. JobRole=Laboratory Technician 259 ==> Department=Research & Development 259    <conf:(1)> lift:(1.53) lev:(0.06) [89] conv:(89.68)
 6. JobRole=Laboratory Technician MonthlyIncome=Poor 258 ==> Department=Research & Development 258    <conf:(1)> lift:(1.53) lev:(0.06) [89] conv:(89.33)
 7. Attrition=No JobRole=Research Scientist 245 ==> Department=Research & Development 245    <conf:(1)> lift:(1.53) lev:(0.06) [84] conv:(84.83)
 8. Attrition=No JobRole=Research Scientist MonthlyIncome=Poor 244 ==> Department=Research & Development 244    <conf:(1)> lift:(1.53) lev:(0.06) [84] conv:(84.49)
 9. BusinessTravel=Travel_Rarely JobRole=Sales Executive 228 ==> Department=Sales 228    <conf:(1)> lift:(3.3) lev:(0.11) [158] conv:(158.82)
10. JobRole=Research Scientist 292 ==> MonthlyIncome=Poor 291    <conf:(1)> lift:(1.4) lev:(0.06) [82] conv:(41.91)
```