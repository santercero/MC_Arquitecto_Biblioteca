---
type: snippet
title: SQL voucher order service cloud simulation
date: 2026-05-27
source: conversacion-interna-mc-arquitecto
tags: [sfmc, sql, voucher, order, service-cloud, aliases]
status: canonical
language: sql
---

# Uso

```sql
SELECT
o.Customer_First_Name__c AS [Order:Order_Contact__r:FirstName],
o.Customer_Last_Name__c AS [Order:Order_Contact__r:LastName],
o.Id AS [Order:Id],
o.CreatedDate AS [Order:CreatedDate],
o.LoyaltyQualified__c AS [Order:LoyaltyQualified__c],
o.Origin_Channel__c AS [Order:Origin__c],
o.Status AS [Order:Status],
o.Customer_Email__c AS [Order:Order_Contact__r:Email],
'False' AS [Order:Order_Contact__r:HasOptedOutOfEmail],
'IT' AS [Order:Order_Contact__r:CommunicationCountry__c],
'it' AS [Order:Order_Contact__r:Preferred_Language__c],
'True' AS [Order:Order_Contact__r:Contactable_Email__c],
v.ContactId AS [ContactID],
v.Status AS [Estado],
v.Id AS [VoucherId],
o.Store__c AS [StoreId]
FROM ent.[Voucher_Salesforce] v
INNER JOIN ent.[Order_Salesforce_4] o
ON o.Order_Contact__c = v.ContactId
WHERE
v.Status = 'Issued'
AND o.CreatedDate = (
SELECT MAX(o2.CreatedDate)
FROM ent.[Order_Salesforce_4] o2
WHERE o2.Order_Contact__c = o.Order_Contact__c
)
AND o.LoyaltyQualified__c = '1'
```

# Notas

- Encerrar siempre aliases con `:` entre corchetes `[]`
- `Order` es palabra reservada y no debe usarse sin escape adecuado
- Revisar rendimiento de la subquery correlacionada sobre tablas grandes
- Si varias orders comparten exactamente el mismo `CreatedDate`, pueden aparecer duplicados
