---
type: snippet
title: AMPscript ClaimRow coupon assignment
date: 2026-05-27
source: chatgpt-project-mc-arquitecto
tags: [sfmc, amscript, claimrow, coupons]
status: canonical
language: ampscript
---

# Uso

```ampscript
%%[
SET @customerId = AttributeValue("CUSTOMER_ID")
SET @now = FormatDate(DateAdd(Now(), 2, "H"), "yyyy-MM-dd HH:mm:ss")

SET @row = ClaimRow(
 "TEST - DE - We Miss You FUS Coupons",
 "IS_CLAIMED",
 "CUSTOMER_ID", @customerId,
 "CLAIMED_DATE", @now
)

IF NOT Empty(@row) THEN
 SET @couponCode = Field(@row, "COUPON_CODE")
ELSE
 SET @couponCode = "SIN CUPÓN"
ENDIF
]%%
```

# Notas

- Validar el comportamiento de `Now()` en envíos reales
- No asumir que el retorno de `ClaimRow()` será siempre un `RowSet`
- Evitar `UpdateDE()` posterior sobre el mismo registro reclamado

## Debug temporal

```html
<p>Customer ID: %%=v(@customerId)=%%</p>
<p>Fecha: %%=v(@now)=%%</p>
<p>Cupón: %%=v(@couponCode)=%%</p>
```
