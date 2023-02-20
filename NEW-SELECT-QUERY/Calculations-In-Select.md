## Simple Arithmetic Computation -

```abap
SELECT num1, num2,
      CAST( num1 AS FLTP ) / CAST( num2 AS FLTP ) AS ratio,
      DIV( num1, num2 ) AS div,
      DIVISION( num1, num2, 2 ) AS division,
      MOD( num1, num2 ) AS mod,
      @offset + ABS( num1 - num2 ) AS sum
      FROM demo_expressions
      ORDER BY sum DESCENDING
      INTO TABLE @DATA(results).
```

Real example using Subtraction
```abap
SELECT carrid,
       seatsmax,
       seatsocc,
* Maximum seats - Occupied seats = Available Seats
       ( setsmax - setsocc ) AS seatsfree
       FROM slight
       INTO TABLE @DATA(li_flight).
*Display Outupt
cl_demo_output=>display_data( li_flight ).
```
