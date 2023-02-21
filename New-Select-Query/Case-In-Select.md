# Simple Case in Select query

```abap
SELECT vbeln, vbtyp,
CASE
  WHEN auart = 'ZQ' THEN 'Quotation'
  WHEN auart = 'INQ' THEN 'Inquiry'
ELSE 'Standard Order'
END AS order_type
FROM vbak
WHERE vbeln IN @s_vbeln
INTO @DATA(lw_vbak).
```
