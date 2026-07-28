# T24 Complete SELECT Statement Analysis

**Generated**: 2026-03-31 14:22:40

---

## Executive Summary

- **Total SELECT statements**: 822
- **TAFJ Compatible**: 818 (99%)
- **Syntax errors**: 4  CRITICAL (invalid JQL syntax)
- **I-type field issues**: 0  CRITICAL (calculated I-descriptors, not LOCAL.REF)
- **J-type field issues**: 0  CRITICAL (complex J-descriptors)
- **Multivalue field warnings**: 104   WARNING (Performance risk - cannot create index on M fields)
- **J-type supported info**: 0   INFO (simple J-descriptors - TAFJ compatible via views)
- **LOCAL.REF field info**: 45   INFO (physical fields in database - TAFJ compatible)
- **Performance warnings**: 254   WARNING (SELECT without WITH clause - full table scan)
- **Dictionaries loaded**: 221

### SELECT Statements by Routine Type

- **BATCH (inferred)**: 398 (48%)
- **NOFILE (inferred)**: 186 (22%)
- **Unknown**: 139 (16%)
- **ENQUIRY (inferred)**: 52 (6%)
- **SUBROUTINE (inferred)**: 24 (2%)
- **VERSION (inferred)**: 23 (2%)

###  **CRITICAL ISSUES FOUND - Manual review required**

---

## Package Summary

| Package | SELECT Statements | TAFJ Compatible | I-Type Issues | J-Type Issues | Multivalue Fields | J-Supported Info | LOCAL.REF Info |
|---------|------------------:|----------------:|--------------:|--------------:|------------------:|-----------------:|---------------:|
| R21_SOURCE | 822 | 818 | 0 | 0 | 104 | 0 | 45 |

---

##  CRITICAL SYNTAX ERRORS

Found 4 SELECT statements with **invalid JQL syntax**.

**These must be fixed before TAFJ migration!**

### Syntax Error #1

**File**: `BAPA.M.MTN99.FILL.SWIFT.BOOK.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAPA.M.MTN99.FILL.SWIFT.BOOK.b`

**Routine**: `BAPA.M.MTN99.FILL.SWIFT.BOOK` (Unknown)

**Line**: 51

**Table**: DE.BIC

**SELECT Statement**:
```
SELECT F.DE.BIC NE TRCKCHZZXXX
```

**Errors**:
-  CRITICAL SYNTAX ERROR: Operator 'NE' without WITH clause - Missing field name. Should be: SELECT F.DE.BIC WITH <field_name> NE ...

---

### Syntax Error #2

**File**: `BAN.E.NOF.PREST.MOV.LOG.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAN.E.NOF.PREST.MOV.LOG.b`

**Routine**: `BAN.E.NOF.PREST.MOV.LOG` (NOFILE (inferred))

**Line**: 152

**Table**: WITH

**SELECT Statement**:
```
SELECT  WITH SAMPLE_VALUE BY FECHA.PROCESO WITH {CHANGE(SEL.CMD.FILTER, @FM, ' AND ')} BY FECHA.PROCESO WITH {CHANGE(SEL.CMD.FILTER, @FM, ' AND ')} BY FECHA.PROCESO
```

**Errors**:
- Invalid operator: BY

---

### Syntax Error #3

**File**: `BPA.S.GET.COD.OFFICE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.S.GET.COD.OFFICE.b`

**Routine**: `BPA.S.GET.COD.OFFICE` (SUBROUTINE (inferred))

**Line**: 70

**Table**: CHEQUE.ISSUE

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LK VALUE123
```

**Errors**:
- Invalid operator: LK

---

### Syntax Error #4

**File**: `BPA.S.GET.NO.CHQ.BOOK.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.S.GET.NO.CHQ.BOOK.b`

**Routine**: `BPA.S.GET.NO.CHQ.BOOK` (SUBROUTINE (inferred))

**Line**: 69

**Table**: CHEQUE.ISSUE

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LK VALUE123
```

**Errors**:
- Invalid operator: LK

---

##   PERFORMANCE WARNINGS (Full Table Scan)

Found 255 SELECT statements without WITH clause (no WHERE clause in SQL).

**Impact**: These SELECT statements will perform a **full table scan**, which can cause severe performance issues on large tables.

**Recommendation**: Add appropriate WITH clause to filter records, or ensure the table is small enough that full scan is acceptable.

### Performance Warning #1

**File**: `BAPA.B.CONS.ADD.INFO.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\STBP_35077_BAPA\SOURCE\STBP_35077-BAPA\Source\Private\BAPA.B.CONS.ADD.INFO.SELECT.b`

**Line**: 33

**Table**: EB.BAPA.L.TEMP.CONST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.TEMP.CONST
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_TEMP_CONST
```

---

### Performance Warning #2

**File**: `BAPA.B.CONS.SCHDUL.UP.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\STBP_35077_BAPA\SOURCE\STBP_35077-BAPA\Source\Private\BAPA.B.CONS.SCHDUL.UP.SELECT.b`

**Line**: 31

**Table**: EB.BAPA.L.TEMP.CONST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.TEMP.CONST
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_TEMP_CONST
```

---

### Performance Warning #3

**File**: `BSAP.COMPARE.AIA.ECB.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\PACS_CompareAIA\Source\Private\BSAP.COMPARE.AIA.ECB.POST.b`

**Line**: 43

**Table**: ACC.DIFF.BP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACC.DIFF.BP
```

**SQL Translation**:
```sql
SELECT *
FROM ACC_DIFF_BP
```

---

### Performance Warning #4

**File**: `BSAP.COMPARE.AIA.ECB.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\PACS_CompareAIA\Source\Private\BSAP.COMPARE.AIA.ECB.POST.b`

**Line**: 61

**Table**: ACC.DIFFDETAILS.BP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACC.DIFFDETAILS.BP
```

**SQL Translation**:
```sql
SELECT *
FROM ACC_DIFFDETAILS_BP
```

---

### Performance Warning #5

**File**: `PACS.AC.DATA.EXTRACT.EXEC.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\PACS_AcDataExtract\Source\Private\PACS.AC.DATA.EXTRACT.EXEC.b`

**Line**: 368

**Table**: ENTRY.HOLD

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.ENTRY.HOLD
```

**SQL Translation**:
```sql
SELECT *
FROM ENTRY_HOLD
```

---

### Performance Warning #6

**File**: `PACS.AC.DATA.EXTRACT.EXEC.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\PACS_AcDataExtract\Source\Private\PACS.AC.DATA.EXTRACT.EXEC.b`

**Line**: 798

**Table**: EB.SYSTEM.SUMMARY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SSELECT F.EB.SYSTEM.SUMMARY
```

**SQL Translation**:
```sql
SELECT *
FROM EB_SYSTEM_SUMMARY
ORDER BY RECID ASC
```

---

### Performance Warning #7

**File**: `PACS.AC.DATA.EXTRACT.SUB.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\PACS_AcDataExtract\Source\Private\PACS.AC.DATA.EXTRACT.SUB.b`

**Line**: 369

**Table**: ENTRY.HOLD

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.ENTRY.HOLD
```

**SQL Translation**:
```sql
SELECT *
FROM ENTRY_HOLD
```

---

### Performance Warning #8

**File**: `PACS.AC.DATA.EXTRACT.SUB.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\PACS_AcDataExtract\Source\Private\PACS.AC.DATA.EXTRACT.SUB.b`

**Line**: 798

**Table**: EB.SYSTEM.SUMMARY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SSELECT F.EB.SYSTEM.SUMMARY
```

**SQL Translation**:
```sql
SELECT *
FROM EB_SYSTEM_SUMMARY
ORDER BY RECID ASC
```

---

### Performance Warning #9

**File**: `BAN.E.NOF.LATAM.ACH.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\BAN.E.NOF.LATAM.ACH.b`

**Line**: 70

**Table**: LATAM.ACH.BATCH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.LATAM.ACH.BATCH
```

**SQL Translation**:
```sql
SELECT *
FROM LATAM_ACH_BATCH
```

---

### Performance Warning #10

**File**: `LATAM.ACH.AML.RESPONSE.UPDATE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.AML.RESPONSE.UPDATE.SELECT.b`

**Line**: 75

**Table**: AML.RESPONSE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AML.RESPONSE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM AML_RESPONSE_PATH
```

---

### Performance Warning #11

**File**: `LATAM.ACH.GENERATE.CAPTURE.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.GENERATE.CAPTURE.POST.b`

**Line**: 28

**Table**: ACH.CAPTURE.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACH.CAPTURE.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM ACH_CAPTURE_FILE_PATH
```

---

### Performance Warning #12

**File**: `LATAM.ACH.GENERATE.CAPTURE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.GENERATE.CAPTURE.SELECT.b`

**Line**: 70

**Table**: ACH.CAPTURE.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACH.CAPTURE.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM ACH_CAPTURE_FILE_PATH
```

---

### Performance Warning #13

**File**: `LATAM.ACH.UPDATE.WAREHOUSE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.UPDATE.WAREHOUSE.SELECT.b`

**Line**: 64

**Table**: LATAM.ACH.OUTWARD

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SSELECT LATAM.ACH.OUTWARD
```

**SQL Translation**:
```sql
SELECT *
FROM LATAM_ACH_OUTWARD
ORDER BY RECID ASC
```

---

### Performance Warning #14

**File**: `LATAM.ACH.UPLOAD.WAREHOUSE.ISO.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.UPLOAD.WAREHOUSE.ISO.SELECT.b`

**Line**: 54

**Table**: WRK.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT WRK.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM WRK_FILE_PATH
```

---

### Performance Warning #15

**File**: `LATAM.ACH.UPLOAD.WAREHOUSE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.UPLOAD.WAREHOUSE.SELECT.b`

**Line**: 54

**Table**: WRK.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT WRK.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM WRK_FILE_PATH
```

---

### Performance Warning #16

**File**: `LATAM.ACH.VALIDATE.FILE.ISO.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.VALIDATE.FILE.ISO.SELECT.b`

**Line**: 51

**Table**: INWARD.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT INWARD.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM INWARD_FILE_PATH
```

---

### Performance Warning #17

**File**: `LATAM.ACH.VALIDATE.FILE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\LATAMACH_UtilityLat\LATAMACH_UtilityLat\Source\Private\LATAM.ACH.VALIDATE.FILE.SELECT.b`

**Line**: 62

**Table**: INWARD.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT INWARD.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM INWARD_FILE_PATH
```

---

### Performance Warning #18

**File**: `BAN.B.DEPU.INTERM.TRANS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATT_MigCaja\BAPATT_MigCaja\Source\Private\BAN.B.DEPU.INTERM.TRANS.SELECT.b`

**Line**: 45

**Table**: BAN.INTERMEDI.TRANS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.INTERMEDI.TRANS
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_INTERMEDI_TRANS
```

---

### Performance Warning #19

**File**: `BAN.E.NOF.TXN.PAR.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATT_MigCaja\BAPATT_MigCaja\Source\Private\BAN.E.NOF.TXN.PAR.b`

**Line**: 50

**Table**: TELLER.TRANSACTION

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.TELLER.TRANSACTION
```

**SQL Translation**:
```sql
SELECT *
FROM TELLER_TRANSACTION
```

---

### Performance Warning #20

**File**: `BAN.E.NOF.TXN.PAR.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATT_MigCaja\BAPATT_MigCaja\Source\Private\BAN.E.NOF.TXN.PAR.b`

**Line**: 55

**Table**: FT.TXN.TYPE.CONDITION

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FT.TXN.TYPE.CONDITION
```

**SQL Translation**:
```sql
SELECT *
FROM FT_TXN_TYPE_CONDITION
```

---

### Performance Warning #21

**File**: `BAN.B.PURGE.OPERATION.REQUEST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.B.PURGE.OPERATION.REQUEST.SELECT.b`

**Line**: 46

**Table**: BAN.TCIB.OPERATION.REQUEST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.TCIB.OPERATION.REQUEST
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

### Performance Warning #22

**File**: `BAN.B.TCIB.RELEASE.AFFILIATION.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.B.TCIB.RELEASE.AFFILIATION.SELECT.b`

**Line**: 42

**Table**: BAN.TC.AFFILIATION.STATUS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.TC.AFFILIATION.STATUS
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TC_AFFILIATION_STATUS
```

---

### Performance Warning #23

**File**: `BAN.E.NOF.CASHPOOLING.ACCOUNTS.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.E.NOF.CASHPOOLING.ACCOUNTS.b`

**Line**: 98

**Table**: BAN.CASHPOOLING.INFO

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFO
```

---

### Performance Warning #24

**File**: `BAN.E.NOF.CASHPOOLING.INFO.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.E.NOF.CASHPOOLING.INFO.b`

**Line**: 101

**Table**: BAN.CASHPOOLING.INFO

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFO
```

---

### Performance Warning #25

**File**: `BAN.E.NOF.PAYROLL.PENDING.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.E.NOF.PAYROLL.PENDING.b`

**Line**: 140

**Table**: BAN.TCIB.OPERATION.REQUEST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

### Performance Warning #26

**File**: `BAN.E.NOF.TCIB.PENDING.FT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.E.NOF.TCIB.PENDING.FT.b`

**Line**: 99

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU DEBIT.ACCT.NO EQ VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

### Performance Warning #27

**File**: `BAN.E.NOF.TXN.PENDING.CORPORATE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.E.NOF.TXN.PENDING.CORPORATE.b`

**Line**: 172

**Table**: BAN.TCIB.OPERATION.REQUEST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

### Performance Warning #28

**File**: `BAN.E.NOF.TXN.PENDING.PERSONAL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.E.NOF.TXN.PENDING.PERSONAL.b`

**Line**: 158

**Table**: BAN.TCIB.OPERATION.REQUEST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

### Performance Warning #29

**File**: `BAN.ID.GENERATION.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAN.ID.GENERATION.b`

**Line**: 71

**Table**: BAN.CASHPOOLING.INFO

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFO
```

---

### Performance Warning #30

**File**: `BAPA.M.MTN99.FILL.SWIFT.BOOK.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BAPA.M.MTN99.FILL.SWIFT.BOOK.b`

**Line**: 51

**Table**: DE.BIC

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.DE.BIC NE TRCKCHZZXXX
```

**SQL Translation**:
```sql
SELECT *
FROM DE_BIC
```

---

### Performance Warning #31

**File**: `BPA.E.NOF.UPDATE.TCIB.CUSTOMER.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_MigTCIB\BAPATCIB_MigTCIB\Source\Private\BPA.E.NOF.UPDATE.TCIB.CUSTOMER.b`

**Line**: 76

**Table**: CUSTOMER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CUSTOMER$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM CUSTOMER$NAU
```

---

### Performance Warning #32

**File**: `BAPA.B.EX.ENRICH.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_Framework\Source\Private\BAPA.B.EX.ENRICH.SELECT.b`

**Line**: 28

**Table**: ACCT.ENT.LWORK.DAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCT.ENT.LWORK.DAY
```

**SQL Translation**:
```sql
SELECT *
FROM ACCT_ENT_LWORK_DAY
```

---

### Performance Warning #33

**File**: `BAPA.B.EX.ENRICH.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPATCIB_Framework\Source\Private\BAPA.B.EX.ENRICH.SELECT.b`

**Line**: 38

**Table**: ACCT.ENT.TODAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCT.ENT.TODAY
```

**SQL Translation**:
```sql
SELECT *
FROM ACCT_ENT_TODAY
```

---

### Performance Warning #34

**File**: `BAPA.PARAM.LIMIT.DAILY.RESET.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAPP_Framework\Source\Private\BAPA.PARAM.LIMIT.DAILY.RESET.b`

**Line**: 130

**Table**: EB.BAPA.PARAM.LIMIT.BICS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.PARAM.LIMIT.BICS
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_PARAM_LIMIT_BICS
```

---

### Performance Warning #35

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVariosV2\Source\Private\BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 217

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
```

---

### Performance Warning #36

**File**: `BACM3M.B.FINAL.FILE.GEN.RED.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BACM3M.B.FINAL.FILE.GEN.RED.SELECT.b`

**Line**: 20

**Table**: BACM3M.DATA.FINAL.GEN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BACM3M.DATA.FINAL.GEN
```

**SQL Translation**:
```sql
SELECT *
FROM BACM3M_DATA_FINAL_GEN
```

---

### Performance Warning #37

**File**: `BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Line**: 56

**Table**: ACCT.ENT.LWORK.DAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCT.ENT.LWORK.DAY
```

**SQL Translation**:
```sql
SELECT *
FROM ACCT_ENT_LWORK_DAY
```

---

### Performance Warning #38

**File**: `BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Line**: 63

**Table**: CATEG.ENT.LWORK.DAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT CATEG.ENT.LWORK.DAY
```

**SQL Translation**:
```sql
SELECT *
FROM CATEG_ENT_LWORK_DAY
```

---

### Performance Warning #39

**File**: `BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Line**: 70

**Table**: RE.SPEC.ENT.LWORK.DAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT RE.SPEC.ENT.LWORK.DAY
```

**SQL Translation**:
```sql
SELECT *
FROM RE_SPEC_ENT_LWORK_DAY
```

---

### Performance Warning #40

**File**: `BACM3M.B.TXNS.SELECT.COLLECT.RED.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BACM3M.B.TXNS.SELECT.COLLECT.RED.SELECT.b`

**Line**: 66

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #41

**File**: `BAN.B.AA.CHG.SETTLE.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.AA.CHG.SETTLE.LOAD.b`

**Line**: 73

**Table**: TAX

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.TAX
```

**SQL Translation**:
```sql
SELECT *
FROM TAX
```

---

### Performance Warning #42

**File**: `BAN.B.AA.CHG.SETTLE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.AA.CHG.SETTLE.SELECT.b`

**Line**: 211

**Table**: BAN.AA.T.CHG.PENDING

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.AA.T.CHG.PENDING
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

### Performance Warning #43

**File**: `BAN.B.DEL.RECORD.LOCK.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.DEL.RECORD.LOCK.SELECT.b`

**Line**: 24

**Table**: RECORD.LOCK

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT RECORD.LOCK
```

**SQL Translation**:
```sql
SELECT *
FROM RECORD_LOCK
```

---

### Performance Warning #44

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.DELETE.TXN.SELECT.b`

**Line**: 44

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FUNDS.TRANSFER$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

### Performance Warning #45

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.DELETE.TXN.SELECT.b`

**Line**: 49

**Table**: TELLER.FINANCIAL.SERVICES$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT TELLER.FINANCIAL.SERVICES$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM TELLER_FINANCIAL_SERVICES$NAU
```

---

### Performance Warning #46

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.DELETE.TXN.SELECT.b`

**Line**: 58

**Table**: VALUE123$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.VALUE123$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123$NAU
```

---

### Performance Warning #47

**File**: `BAN.B.MOV.LOCKED.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.MOV.LOCKED.SELECT.b`

**Line**: 51

**Table**: AC.LOCKED.EVENTS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AC.LOCKED.EVENTS
```

**SQL Translation**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
```

---

### Performance Warning #48

**File**: `BAN.B.RC.DETAIL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.RC.DETAIL.SELECT.b`

**Line**: 45

**Table**: BAN.RC.DETAIL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.RC.DETAIL
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_RC_DETAIL
```

---

### Performance Warning #49

**File**: `BAN.B.RC.TIMBRES.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.B.RC.TIMBRES.POST.b`

**Line**: 65

**Table**: Y.TEMP.FILE.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SQL Translation**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

### Performance Warning #50

**File**: `BAN.CLEAR.FILES.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.CLEAR.FILES.SELECT.b`

**Line**: 79

**Table**: BAN.AC.AUTO.PYMT.STOP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.AC.AUTO.PYMT.STOP
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_AC_AUTO_PYMT_STOP
```

---

### Performance Warning #51

**File**: `BAN.CUS.ACC.MOVE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.CUS.ACC.MOVE.b`

**Line**: 49

**Table**: BAN.CREATE.CUS.ACC

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CREATE.CUS.ACC
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
```

---

### Performance Warning #52

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.BLD.FT.PEND.TCIB.b`

**Line**: 154

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ {EB.Reports.getDRangeAndValue()<APPL.POS>}
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

### Performance Warning #53

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.BLD.FT.PEND.TCIB.b`

**Line**: 179

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

### Performance Warning #54

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.BLD.FT.PEND.TCIB.b`

**Line**: 202

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ VALUE123 AND CO.CODE EQ ID.COMPANY
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE CO_CODE = 'ID.COMPANY'
```

---

### Performance Warning #55

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.BLD.FT.PEND.TCIB.b`

**Line**: 228

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ VALUE123 AND CO.CODE EQ ID.COMPANY
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE CO_CODE = 'ID.COMPANY'
```

---

### Performance Warning #56

**File**: `BAN.E.NOF.CO.SEV.INST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.NOF.CO.SEV.INST.b`

**Line**: 91

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #57

**File**: `BAN.E.NOF.EXCEPTION.ALL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.NOF.EXCEPTION.ALL.b`

**Line**: 55

**Table**: BAN.PARAMETER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.PARAMETER
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_PARAMETER
```

---

### Performance Warning #58

**File**: `BAN.E.NOF.EXCEPTION.ALL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.NOF.EXCEPTION.ALL.b`

**Line**: 170

**Table**: VALUE123$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.VALUE123$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123$NAU
```

---

### Performance Warning #59

**File**: `BAN.E.NOF.EXCEPTION.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.NOF.EXCEPTION.b`

**Line**: 535

**Table**: VALUE123$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.VALUE123$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123$NAU
```

---

### Performance Warning #60

**File**: `BAN.E.TCMB.BEN.LIST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.E.TCMB.BEN.LIST.b`

**Line**: 56

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND LT.CCY EQ SAMPLE_VALUE AND LT.CCY EQ {Y.VALUES<POS3>} AND LT.CCY EQ {Y.VALUES<POS3>}
```

**SQL Translation**:
```sql
SELECT *
FROM AND
WHERE LT_CCY = 'SAMPLE_VALUE' AND LT_CCY = '{Y.VALUES<POS3>}' AND LT_CCY = '{Y.VALUES<POS3>}'
```

---

### Performance Warning #61

**File**: `BAN.EXP.PROTOCOL.PURGE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.EXP.PROTOCOL.PURGE.SELECT.b`

**Line**: 31

**Table**: BAN.PROTOCOL.EXP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.PROTOCOL.EXP
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_PROTOCOL_EXP
```

---

### Performance Warning #62

**File**: `BAN.NOFILE.ENQ.HIST.PLEDGE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAN.NOFILE.ENQ.HIST.PLEDGE.b`

**Line**: 54

**Table**: BAN.CONCAT.COLLATERAL.ALE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CONCAT.COLLATERAL.ALE
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CONCAT_COLLATERAL_ALE
```

---

### Performance Warning #63

**File**: `BAPA.ACCT.DETAILS.DELETE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.ACCT.DETAILS.DELETE.b`

**Line**: 64

**Table**: BPA.OD.ACCT.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.OD.ACCT.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_OD_ACCT_DETAILS
```

---

### Performance Warning #64

**File**: `BAPA.ADJ.COVID.CURCHARGE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.ADJ.COVID.CURCHARGE.SELECT.b`

**Line**: 23

**Table**: BAPA.GEN.COV.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAPA.GEN.COV.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA_GEN_COV_DETAILS
```

---

### Performance Warning #65

**File**: `BAPA.ADJ.COVID.UNCCHARGE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.ADJ.COVID.UNCCHARGE.SELECT.b`

**Line**: 22

**Table**: INTERFACE.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT INTERFACE.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

### Performance Warning #66

**File**: `BAPA.ADJ.COVID.UPD.UNCCHARGE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.ADJ.COVID.UPD.UNCCHARGE.b`

**Line**: 68

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamOutputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamOutputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamOutputDir>
```

---

### Performance Warning #67

**File**: `BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Line**: 77

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #68

**File**: `BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Line**: 207

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #69

**File**: `BAPA.B.ACR.NAU.DEL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.ACR.NAU.DEL.SELECT.b`

**Line**: 23

**Table**: AC.CHARGE.REQUEST$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AC.CHARGE.REQUEST$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST$NAU
```

---

### Performance Warning #70

**File**: `BAPA.B.ACR.PREPARE.FILES.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.ACR.PREPARE.FILES.b`

**Line**: 112

**Table**: IN.DIR

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.IN.DIR
```

**SQL Translation**:
```sql
SELECT *
FROM IN_DIR
```

---

### Performance Warning #71

**File**: `BAPA.B.ADJ.CASTIGO.BILL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.ADJ.CASTIGO.BILL.SELECT.b`

**Line**: 24

**Table**: BSAP.L.CASTIGADO.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BSAP.L.CASTIGADO.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BSAP_L_CASTIGADO_DETAILS
```

---

### Performance Warning #72

**File**: `BAPA.B.AUTO.MONITOR.SERVICE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.AUTO.MONITOR.SERVICE.SELECT.b`

**Line**: 21

**Table**: INTERFACE.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT INTERFACE.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

### Performance Warning #73

**File**: `BAPA.B.AUTO.UPD.DEPT.OFF.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.AUTO.UPD.DEPT.OFF.SELECT.b`

**Line**: 23

**Table**: BAPA.CUS.DAO.LIST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAPA.CUS.DAO.LIST
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA_CUS_DAO_LIST
```

---

### Performance Warning #74

**File**: `BAPA.B.BOL.TO.INT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.BOL.TO.INT.b`

**Line**: 110

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #75

**File**: `BAPA.B.BOL.TO.PAY.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.BOL.TO.PAY.b`

**Line**: 108

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #76

**File**: `BAPA.B.CHG.PENDING.DATE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.CHG.PENDING.DATE.b`

**Line**: 44

**Table**: BAN.AA.T.CHG.PENDING

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.AA.T.CHG.PENDING
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

### Performance Warning #77

**File**: `BAPA.B.EXT.DT.FINAL.FILE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.EXT.DT.FINAL.FILE.b`

**Line**: 67

**Table**: Y.TEMP.FILE.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SQL Translation**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

### Performance Warning #78

**File**: `BAPA.B.FT.NAU.DEL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.FT.NAU.DEL.SELECT.b`

**Line**: 22

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FUNDS.TRANSFER$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

### Performance Warning #79

**File**: `BAPA.B.TRG.OFS.STRING.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.TRG.OFS.STRING.b`

**Line**: 67

**Table**: BAPA.ADJ.CASTIGO.LIST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAPA.ADJ.CASTIGO.LIST
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA_ADJ_CASTIGO_LIST
```

---

### Performance Warning #80

**File**: `BAPA.B.TSA.START.SCHEDL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.TSA.START.SCHEDL.b`

**Line**: 60

**Table**: BAPA.H.TSA.AUTO.SCHEDULER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAPA.H.TSA.AUTO.SCHEDULER
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA_H_TSA_AUTO_SCHEDULER
```

---

### Performance Warning #81

**File**: `BAPA.B.TT.NAU.DEL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.B.TT.NAU.DEL.SELECT.b`

**Line**: 24

**Table**: TELLER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT TELLER$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM TELLER$NAU
```

---

### Performance Warning #82

**File**: `BAPA.CHG.ISSUE.BILL.NO.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.CHG.ISSUE.BILL.NO.SELECT.b`

**Line**: 46

**Table**: INTERFACE.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT INTERFACE.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

### Performance Warning #83

**File**: `BAPA.CONSOLIDATE.LOG.REM.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.CONSOLIDATE.LOG.REM.b`

**Line**: 83

**Table**: Y.TEMP.FILE.POINTER.TEM

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SQL Translation**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER_TEM
```

---

### Performance Warning #84

**File**: `BAPA.E.NOF.GET.JOB.LIST.DTL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.E.NOF.GET.JOB.LIST.DTL.b`

**Line**: 122

**Table**: yLockingSelRec

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT yLockingSelRec
```

**SQL Translation**:
```sql
SELECT *
FROM yLockingSelRec
```

---

### Performance Warning #85

**File**: `BAPA.FT.NAU.DEL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.FT.NAU.DEL.b`

**Line**: 92

**Table**: FUNDS.TRANSFER$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

### Performance Warning #86

**File**: `BAPA.PARTICIPANT.DELETE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.PARTICIPANT.DELETE.b`

**Line**: 58

**Table**: BPA.ARR.BY.PARTICIPANT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.ARR.BY.PARTICIPANT
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_ARR_BY_PARTICIPANT
```

---

### Performance Warning #87

**File**: `BAPA.S.GET.FILE.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BAPA.S.GET.FILE.POST.b`

**Line**: 81

**Table**: SIM.FILES

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT SIM.FILES
```

**SQL Translation**:
```sql
SELECT *
FROM SIM_FILES
```

---

### Performance Warning #88

**File**: `BPA.B.CUS.FILE.PRE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BPA.B.CUS.FILE.PRE.b`

**Line**: 69

**Table**: Y.TEMP.FILE.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT Y.TEMP.FILE.POINTER.AUX        ;* Seleccionar los archivos que contiene el directorio
```

**SQL Translation**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

### Performance Warning #89

**File**: `BSAP.B.UPD.SUSP.AMT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\BSAP.B.UPD.SUSP.AMT.SELECT.b`

**Line**: 22

**Table**: INTERFACE.FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT INTERFACE.FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

### Performance Warning #90

**File**: `CAL.UPDATE.BL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\CAL.UPDATE.BL.b`

**Line**: 48

**Table**: AC.BALANCE.TYPE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.AC.BALANCE.TYPE
```

**SQL Translation**:
```sql
SELECT *
FROM AC_BALANCE_TYPE
```

---

### Performance Warning #91

**File**: `CAL.UPDATE.BL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\CAL.UPDATE.BL.b`

**Line**: 65

**Table**: CONSOLIDATE.ASST.LIAB

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CONSOLIDATE.ASST.LIAB
```

**SQL Translation**:
```sql
SELECT *
FROM CONSOLIDATE_ASST_LIAB
```

---

### Performance Warning #92

**File**: `TECH.CHARGE.POB.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAOTH_MigVarios\BAPAOTH_MigVarios\Source\Private\TECH.CHARGE.POB.SELECT.b`

**Line**: 40

**Table**: TECH.BOL.CHG.PARAM

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT TECH.BOL.CHG.PARAM
```

**SQL Translation**:
```sql
SELECT *
FROM TECH_BOL_CHG_PARAM
```

---

### Performance Warning #93

**File**: `BAN.A.OUTCLG.CLEARED.APPLY.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.A.OUTCLG.CLEARED.APPLY.b`

**Line**: 53

**Table**: BAN.OUT.CLEARING.CHQRET.HEAD

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_HEAD
```

---

### Performance Warning #94

**File**: `BAN.B.CHQ.GET.CLGDATA.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.CHQ.GET.CLGDATA.b`

**Line**: 127

**Table**: BAN.CHEQUE.COLLECTION

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CHEQUE.COLLECTION
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CHEQUE_COLLECTION
```

---

### Performance Warning #95

**File**: `BAN.B.DELETE.IHLD.FT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.DELETE.IHLD.FT.SELECT.b`

**Line**: 43

**Table**: BPA.FT.910.LIST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.FT.910.LIST
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_FT_910_LIST
```

---

### Performance Warning #96

**File**: `BAN.B.FT.XML.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.FT.XML.b`

**Line**: 124

**Table**: FUNDS.TRANSFER$DEL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FUNDS.TRANSFER$DEL LIKE VALUE123... AND PROCESSING.DATE EQ TODAY
```

**SQL Translation**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
WHERE PROCESSING_DATE = 'TODAY'
```

---

### Performance Warning #97

**File**: `BAN.B.INCLG.CHQ.UPLOAD.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.INCLG.CHQ.UPLOAD.LOAD.b`

**Line**: 111

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #98

**File**: `BAN.B.INCLG.CHQ.UPLOAD.PRE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.INCLG.CHQ.UPLOAD.PRE.b`

**Line**: 106

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #99

**File**: `BAN.B.SAVE.CHQRET.HEAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.SAVE.CHQRET.HEAD.b`

**Line**: 198

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #100

**File**: `BAN.B.SAVE.INCLG.HEAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.SAVE.INCLG.HEAD.b`

**Line**: 190

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #101

**File**: `BAN.B.TXN.PENDING.BENEF.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.B.TXN.PENDING.BENEF.b`

**Line**: 49

**Table**: BAN.PENDING.TRX

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.PENDING.TRX
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_PENDING_TRX
```

---

### Performance Warning #102

**File**: `BAN.BUILD.OUTCLG.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.BUILD.OUTCLG.b`

**Line**: 47

**Table**: CHEQUE.COLLECTION$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
```

---

### Performance Warning #103

**File**: `BAN.CHANGE.EXPDATE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.CHANGE.EXPDATE.b`

**Line**: 54

**Table**: CHEQUE.COLLECTION$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
```

---

### Performance Warning #104

**File**: `BAN.E.CNV.TOD.CHQ.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.E.CNV.TOD.CHQ.b`

**Line**: 52

**Table**: CHEQUE.REGISTER.SUPPLEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
```

---

### Performance Warning #105

**File**: `BAN.E.NOF.INCLG.FILE.LOTE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAN.E.NOF.INCLG.FILE.LOTE.b`

**Line**: 86

**Table**: BAN.INWARD.CLEARING

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.INWARD.CLEARING @ID LIKE VALUE123... AND HEAD.ID EQ VALUE123 BY LOTE.NUMBER BY CHQ.TYPE
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE HEAD_ID = 'VALUE123'
ORDER BY LOTE_NUMBER ASC, CHQ_TYPE ASC
```

---

### Performance Warning #106

**File**: `BAPA.B.VAL.ACT.PAYMENT.CHG.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAPA.B.VAL.ACT.PAYMENT.CHG.LOAD.b`

**Line**: 97

**Table**: TAX

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.TAX
```

**SQL Translation**:
```sql
SELECT *
FROM TAX
```

---

### Performance Warning #107

**File**: `BAPA3M.B.INTF.CHQ.STATUS.EXT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAPA3M.B.INTF.CHQ.STATUS.EXT.b`

**Line**: 133

**Table**: BAPA3M.CONCAT.CHEQUE.PROC

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAPA3M.CONCAT.CHEQUE.PROC
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA3M_CONCAT_CHEQUE_PROC
```

---

### Performance Warning #108

**File**: `BAPA3M.B.INTF.STOPPED.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BAPA3M.B.INTF.STOPPED.SELECT.b`

**Line**: 45

**Table**: BAPA3M.CONCAT.CHEQUE.PROC

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAPA3M.CONCAT.CHEQUE.PROC
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA3M_CONCAT_CHEQUE_PROC
```

---

### Performance Warning #109

**File**: `BCM.B.RH.UP.PAYMENT.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BCM.B.RH.UP.PAYMENT.LOAD.b`

**Line**: 110

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

### Performance Warning #110

**File**: `BCM.POST.MV.UP.PAY.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BCM.POST.MV.UP.PAY.b`

**Line**: 121

**Table**: BCM.RH.PAYROLL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BCM.RH.PAYROLL BY CREDIT.ACCOUNT BY AMOUNT
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_RH_PAYROLL
ORDER BY CREDIT_ACCOUNT ASC, AMOUNT ASC
```

---

### Performance Warning #111

**File**: `BPA.B.ACH.FILE.REMOVE.HEADER.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.ACH.FILE.REMOVE.HEADER.b`

**Line**: 43

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #112

**File**: `BPA.B.ADQU.CHARGE.PRE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.ADQU.CHARGE.PRE.b`

**Line**: 40

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #113

**File**: `BPA.B.ADQU.PRE.ACCOUNT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.ADQU.PRE.ACCOUNT.SELECT.b`

**Line**: 19

**Table**: BAN.CONCAT.ADQU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.CONCAT.ADQU
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CONCAT_ADQU
```

---

### Performance Warning #114

**File**: `BPA.B.ADQU.PROCESS.TXN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.ADQU.PROCESS.TXN.SELECT.b`

**Line**: 54

**Table**: BAN.CONCAT.ADQU.AC

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.CONCAT.ADQU.AC
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CONCAT_ADQU_AC
```

---

### Performance Warning #115

**File**: `BPA.B.BUILD.DATA.CHQ.OUTCLG.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.BUILD.DATA.CHQ.OUTCLG.b`

**Line**: 87

**Table**: IN.FILE.DIR

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.IN.FILE.DIR
```

**SQL Translation**:
```sql
SELECT *
FROM IN_FILE_DIR
```

---

### Performance Warning #116

**File**: `BPA.B.FT.BULK.MULTIFILE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.FT.BULK.MULTIFILE.SELECT.b`

**Line**: 43

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #117

**File**: `BPA.B.OUTCLG.DATAMAE.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.OUTCLG.DATAMAE.POST.b`

**Line**: 67

**Table**: Y.TEMP.FILE.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SQL Translation**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

### Performance Warning #118

**File**: `BPA.B.OUTCLG.DATATRN.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.OUTCLG.DATATRN.b`

**Line**: 171

**Table**: BPA.CONCAT.TXN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.CONCAT.TXN BY CO.CODE.TXN BY CHQ.BANK
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_CONCAT_TXN
ORDER BY CO_CODE_TXN ASC, CHQ_BANK ASC
```

---

### Performance Warning #119

**File**: `BPA.B.PURGE.TOT.DATATXN.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.PURGE.TOT.DATATXN.b`

**Line**: 58

**Table**: BPA.TOT.DATATRN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.TOT.DATATRN
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_TOT_DATATRN
```

---

### Performance Warning #120

**File**: `BPA.B.TOT.DATATRN.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.TOT.DATATRN.b`

**Line**: 84

**Table**: BPA.TOT.DATATRN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.TOT.DATATRN
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_TOT_DATATRN
```

---

### Performance Warning #121

**File**: `BPA.B.UPLOAD.PLANILLA.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.UPLOAD.PLANILLA.POST.b`

**Line**: 84

**Table**: BAN.FT.BULK.MULTIFILE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.FT.BULK.MULTIFILE
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_FT_BULK_MULTIFILE
```

---

### Performance Warning #122

**File**: `BPA.B.UPLOAD.PLANILLA.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.B.UPLOAD.PLANILLA.SELECT.b`

**Line**: 41

**Table**: BAN.FT.BULK.MULTIFILE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.FT.BULK.MULTIFILE
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_FT_BULK_MULTIFILE
```

---

### Performance Warning #123

**File**: `BPA.DOMTDC.PAY.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.DOMTDC.PAY.POST.b`

**Line**: 61

**Table**: FILE.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FILE.POINTER
```

**SQL Translation**:
```sql
SELECT *
FROM FILE_POINTER
```

---

### Performance Warning #124

**File**: `BPA.E.NOF.RH.PAYROLL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.E.NOF.RH.PAYROLL.b`

**Line**: 74

**Table**: BCM.RH.PAYROLL$NAU

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BCM.RH.PAYROLL$NAU
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_RH_PAYROLL$NAU
```

---

### Performance Warning #125

**File**: `BPA.INWARD.PRE.PROCESS.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.INWARD.PRE.PROCESS.b`

**Line**: 229

**Table**: IN.FILE.DIR

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT IN.FILE.DIR
```

**SQL Translation**:
```sql
SELECT *
FROM IN_FILE_DIR
```

---

### Performance Warning #126

**File**: `BPA.INWARD.PRE.PROCESS.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_MigPago\BAPAFT_MigPago\Source\Private\BPA.INWARD.PRE.PROCESS.b`

**Line**: 272

**Table**: IN.FILE.DIR

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT IN.FILE.DIR
```

**SQL Translation**:
```sql
SELECT *
FROM IN_FILE_DIR
```

---

### Performance Warning #127

**File**: `BAPA.B.DEVO.FT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAFT_Framework\Source\Private\BAPA.B.DEVO.FT.b`

**Line**: 55

**Table**: FILE.PATH.1

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FILE.PATH.1
```

**SQL Translation**:
```sql
SELECT *
FROM FILE_PATH_1
```

---

### Performance Warning #128

**File**: `BAN.B.ACC.WB.TDC.DUE.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.B.ACC.WB.TDC.DUE.POST.b`

**Line**: 62

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #129

**File**: `BAN.B.ACC.WB.TDC.DUE.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.B.ACC.WB.TDC.DUE.POST.b`

**Line**: 107

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #130

**File**: `BAN.B.ACCT.WB.TDC.DUE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.B.ACCT.WB.TDC.DUE.SELECT.b`

**Line**: 60

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #131

**File**: `BAN.E.BLD.RSK.QAL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.E.BLD.RSK.QAL.b`

**Line**: 33

**Table**: BAN.RISK.QUALIFY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.RISK.QUALIFY BY @ID
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_RISK_QUALIFY
ORDER BY ID ASC
```

---

### Performance Warning #132

**File**: `BAN.E.CONV.OTHER.OFF.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.E.CONV.OTHER.OFF.b`

**Line**: 44

**Table**: CR.OTHER.PRODUCTS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CR.OTHER.PRODUCTS CUSTOMER LIKE {FIELD(O.DATA,'#',1)}...
```

**SQL Translation**:
```sql
SELECT *
FROM CR_OTHER_PRODUCTS
```

---

### Performance Warning #133

**File**: `BAN.E.NOF.AA.LENDING.PRINT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.E.NOF.AA.LENDING.PRINT.b`

**Line**: 156

**Table**: BAN.REPORTING.PRINT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.REPORTING.PRINT REPORT.NAME EQ VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_REPORTING_PRINT
```

---

### Performance Warning #134

**File**: `BAN.S.TDD.FINAL.FILE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BAN.S.TDD.FINAL.FILE.b`

**Line**: 87

**Table**: TEMP.FOLDER.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT TEMP.FOLDER.POINTER
```

**SQL Translation**:
```sql
SELECT *
FROM TEMP_FOLDER_POINTER
```

---

### Performance Warning #135

**File**: `BCM.B.AC.STMT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BCM.B.AC.STMT.SELECT.b`

**Line**: 83

**Table**: ACCOUNT.STATEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCOUNT.STATEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM ACCOUNT_STATEMENT
```

---

### Performance Warning #136

**File**: `BCM.B.PROCESS.AML.DATA.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BCM.B.PROCESS.AML.DATA.SELECT.b`

**Line**: 31

**Table**: BCM.AML.REPORT.RECORDS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BCM.AML.REPORT.RECORDS
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_AML_REPORT_RECORDS
```

---

### Performance Warning #137

**File**: `BCM.B.TDD.LIQ.DEB.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BCM.B.TDD.LIQ.DEB.POST.b`

**Line**: 85

**Table**: FILE.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FILE.POINTER
```

**SQL Translation**:
```sql
SELECT *
FROM FILE_POINTER
```

---

### Performance Warning #138

**File**: `BCM.B.TDD.LIQ.DEB.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BCM.B.TDD.LIQ.DEB.POST.b`

**Line**: 204

**Table**: EB.BAPA.ID.PENDING.CHG

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.EB.BAPA.ID.PENDING.CHG
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_ID_PENDING_CHG
```

---

### Performance Warning #139

**File**: `BCM.B.TDD.RPOS.LIQ.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BCM.B.TDD.RPOS.LIQ.SELECT.b`

**Line**: 44

**Table**: BCM.TMP.TDD.LIQ.DEB

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BCM.TMP.TDD.LIQ.DEB
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_TMP_TDD_LIQ_DEB
```

---

### Performance Warning #140

**File**: `BCM.S.PROTOCOL.DATA.UPD.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACUS_MigCliente\BAPACUS_MigCliente\Source\Private\BCM.S.PROTOCOL.DATA.UPD.SELECT.b`

**Line**: 32

**Table**: BCM.AML.REPORT.RECORDS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BCM.AML.REPORT.RECORDS
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_AML_REPORT_RECORDS
```

---

### Performance Warning #141

**File**: `BAPA.B.INCLG.CHQ.APPLY.POST2.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACQ_FRAMEWORK\Source\Private\BAPA.B.INCLG.CHQ.APPLY.POST2.b`

**Line**: 94

**Table**: BAPA.B.CHQ.WRK.LIST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAPA.B.CHQ.WRK.LIST
```

**SQL Translation**:
```sql
SELECT *
FROM BAPA_B_CHQ_WRK_LIST
```

---

### Performance Warning #142

**File**: `BAPA.V.EXISTS.ID.STMT.PRINTED.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACQ_FRAMEWORK\Source\Private\BAPA.V.EXISTS.ID.STMT.PRINTED.SELECT.b`

**Line**: 50

**Table**: BPA.INCLG.CHQ.OFS.LIST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.INCLG.CHQ.OFS.LIST
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_INCLG_CHQ_OFS_LIST
```

---

### Performance Warning #143

**File**: `BPA.B.CLEAR.SALDOS.CHQ.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACQ_FRAMEWORK\Source\Private\BPA.B.CLEAR.SALDOS.CHQ.SELECT.b`

**Line**: 49

**Table**: EB.BAPA.L.ACCT.VAL.TEM

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.ACCT.VAL.TEM
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_ACCT_VAL_TEM
```

---

### Performance Warning #144

**File**: `BPA.B.SALDOS.CHQ.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPACQ_FRAMEWORK\Source\Private\BPA.B.SALDOS.CHQ.SELECT.b`

**Line**: 49

**Table**: EB.BAPA.L.ACCT.VAL.TEM

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.ACCT.VAL.TEM
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_ACCT_VAL_TEM
```

---

### Performance Warning #145

**File**: `BAN.AUTH.UPDATE.CONCAT.ALE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BAN.AUTH.UPDATE.CONCAT.ALE.b`

**Line**: 37

**Table**: AC.LOCKED.EVENTS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.AC.LOCKED.EVENTS
```

**SQL Translation**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
```

---

### Performance Warning #146

**File**: `BCM.B.EXTRACT.APCLS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.APCLS.SELECT.b`

**Line**: 58

**Table**: RE.STAT.REP.LINE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT RE.STAT.REP.LINE
```

**SQL Translation**:
```sql
SELECT *
FROM RE_STAT_REP_LINE
```

---

### Performance Warning #147

**File**: `BCM.B.EXTRACT.CPRBL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CPRBL.SELECT.b`

**Line**: 81

**Table**: MD.DEAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT MD.DEAL
```

**SQL Translation**:
```sql
SELECT *
FROM MD_DEAL
```

---

### Performance Warning #148

**File**: `BCM.B.EXTRACT.CUFIN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUFIN.SELECT.b`

**Line**: 32

**Table**: CUSTOMER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT CUSTOMER
```

**SQL Translation**:
```sql
SELECT *
FROM CUSTOMER
```

---

### Performance Warning #149

**File**: `BCM.B.EXTRACT.CUMAD.AA.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.AA.SELECT.b`

**Line**: 31

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #150

**File**: `BCM.B.EXTRACT.CUMAD.BENEF.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.BENEF.SELECT.b`

**Line**: 23

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #151

**File**: `BCM.B.EXTRACT.CUMAD.COLL.TIT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.COLL.TIT.SELECT.b`

**Line**: 23

**Table**: COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM COLLATERAL
```

---

### Performance Warning #152

**File**: `BCM.B.EXTRACT.CUMAD.COLLATERAL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.COLLATERAL.SELECT.b`

**Line**: 30

**Table**: COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM COLLATERAL
```

---

### Performance Warning #153

**File**: `BCM.B.EXTRACT.CUMAD.COMPANY.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.COMPANY.SELECT.b`

**Line**: 29

**Table**: BCM.CUS.COMPANY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BCM.CUS.COMPANY
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_CUS_COMPANY
```

---

### Performance Warning #154

**File**: `BCM.B.EXTRACT.CUMAD.CUSTOMER.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.CUSTOMER.SELECT.b`

**Line**: 29

**Table**: CUSTOMER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT CUSTOMER
```

**SQL Translation**:
```sql
SELECT *
FROM CUSTOMER
```

---

### Performance Warning #155

**File**: `BCM.B.EXTRACT.CUMAD.PEP.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.PEP.SELECT.b`

**Line**: 46

**Table**: BCM.CUS.PEP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BCM.CUS.PEP
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_CUS_PEP
```

---

### Performance Warning #156

**File**: `BCM.B.EXTRACT.CUMAD.REFERENCE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.REFERENCE.SELECT.b`

**Line**: 29

**Table**: BCM.CUS.REFERENCE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BCM.CUS.REFERENCE
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_CUS_REFERENCE
```

---

### Performance Warning #157

**File**: `BCM.B.EXTRACT.CUMAD.SIGNERS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMAD.SIGNERS.SELECT.b`

**Line**: 28

**Table**: EB.SIGNATORY.GROUP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.SIGNATORY.GROUP
```

**SQL Translation**:
```sql
SELECT *
FROM EB_SIGNATORY_GROUP
```

---

### Performance Warning #158

**File**: `BCM.B.EXTRACT.CUMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.CUMST.SELECT.b`

**Line**: 36

**Table**: CUSTOMER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT CUSTOMER
```

**SQL Translation**:
```sql
SELECT *
FROM CUSTOMER
```

---

### Performance Warning #159

**File**: `BCM.B.EXTRACT.DEALS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.DEALS.SELECT.b`

**Line**: 50

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #160

**File**: `BCM.B.EXTRACT.DLITP.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.DLITP.SELECT.b`

**Line**: 35

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #161

**File**: `BCM.B.EXTRACT.DLPMT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.DLPMT.SELECT.b`

**Line**: 46

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #162

**File**: `BCM.B.EXTRACT.DLSDE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.DLSDE.SELECT.b`

**Line**: 48

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #163

**File**: `BCM.B.EXTRACT.EUSER.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.EUSER.SELECT.b`

**Line**: 36

**Table**: EB.EXTERNAL.USER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.EXTERNAL.USER
```

**SQL Translation**:
```sql
SELECT *
FROM EB_EXTERNAL_USER
```

---

### Performance Warning #164

**File**: `BCM.B.EXTRACT.LCMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.LCMST.SELECT.b`

**Line**: 42

**Table**: MD.DEAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT MD.DEAL
```

**SQL Translation**:
```sql
SELECT *
FROM MD_DEAL
```

---

### Performance Warning #165

**File**: `BCM.B.EXTRACT.LCMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.LCMST.SELECT.b`

**Line**: 52

**Table**: LETTER.OF.CREDIT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LETTER.OF.CREDIT
```

**SQL Translation**:
```sql
SELECT *
FROM LETTER_OF_CREDIT
```

---

### Performance Warning #166

**File**: `BCM.B.EXTRACT.LDMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.LDMST.SELECT.b`

**Line**: 36

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #167

**File**: `BCM.B.EXTRACT.LNECR.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.LNECR.SELECT.b`

**Line**: 46

**Table**: LIMIT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LIMIT
```

**SQL Translation**:
```sql
SELECT *
FROM LIMIT
```

---

### Performance Warning #168

**File**: `BCM.B.EXTRACT.RCOLL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.RCOLL.SELECT.b`

**Line**: 52

**Table**: BAN.BANESCO.COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
```

---

### Performance Warning #169

**File**: `BCM.B.EXTRACT.ROCIN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.ROCIN.SELECT.b`

**Line**: 47

**Table**: BAN.BANESCO.COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
```

---

### Performance Warning #170

**File**: `BCM.B.EXTRACT.ROCOL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.EXTRACT.ROCOL.SELECT.b`

**Line**: 36

**Table**: BAN.BANESCO.COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
```

---

### Performance Warning #171

**File**: `BCM.B.TDD.REPORLIQ.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.TDD.REPORLIQ.LOAD.b`

**Line**: 146

**Table**: CARD.TYPE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CARD.TYPE
```

**SQL Translation**:
```sql
SELECT *
FROM CARD_TYPE
```

---

### Performance Warning #172

**File**: `BCM.B.TDD.REPORLIQ.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.B.TDD.REPORLIQ.SELECT.b`

**Line**: 61

**Table**: BCM.TDD.LIQ.DEB.TMP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BCM.TDD.LIQ.DEB.TMP
```

**SQL Translation**:
```sql
SELECT *
FROM BCM_TDD_LIQ_DEB_TMP
```

---

### Performance Warning #173

**File**: `BCM.POST.MON.FILE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BCM.POST.MON.FILE.b`

**Line**: 75

**Table**: R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>}
```

**SQL Translation**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamArchiveDir>
```

---

### Performance Warning #174

**File**: `BPA.B.EXTRACT.CLIENTE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.CLIENTE.SELECT.b`

**Line**: 59

**Table**: GENERICO

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT GENERICO
```

**SQL Translation**:
```sql
SELECT *
FROM GENERICO
```

---

### Performance Warning #175

**File**: `BPA.B.EXTRACT.HSBAPCLS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBAPCLS.SELECT.b`

**Line**: 58

**Table**: RE.STAT.REP.LINE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT RE.STAT.REP.LINE
```

**SQL Translation**:
```sql
SELECT *
FROM RE_STAT_REP_LINE
```

---

### Performance Warning #176

**File**: `BPA.B.EXTRACT.HSBCPBRL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBCPBRL.SELECT.b`

**Line**: 62

**Table**: MD.DEAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT MD.DEAL
```

**SQL Translation**:
```sql
SELECT *
FROM MD_DEAL
```

---

### Performance Warning #177

**File**: `BPA.B.EXTRACT.HSBCUMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBCUMST.SELECT.b`

**Line**: 36

**Table**: CUSTOMER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT CUSTOMER
```

**SQL Translation**:
```sql
SELECT *
FROM CUSTOMER
```

---

### Performance Warning #178

**File**: `BPA.B.EXTRACT.HSBDEALC.PRE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBDEALC.PRE.b`

**Line**: 46

**Table**: AC.LOCKED.EVENTS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.AC.LOCKED.EVENTS
```

**SQL Translation**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
```

---

### Performance Warning #179

**File**: `BPA.B.EXTRACT.HSBDEALC.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBDEALC.SELECT.b`

**Line**: 40

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #180

**File**: `BPA.B.EXTRACT.HSBGARANT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBGARANT.SELECT.b`

**Line**: 48

**Table**: COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM COLLATERAL
```

---

### Performance Warning #181

**File**: `BPA.B.EXTRACT.HSBLCMST.PRE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBLCMST.PRE.b`

**Line**: 37

**Table**: CUSTOMER.RELATIONSHIP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CUSTOMER.RELATIONSHIP
```

**SQL Translation**:
```sql
SELECT *
FROM CUSTOMER_RELATIONSHIP
```

---

### Performance Warning #182

**File**: `BPA.B.EXTRACT.HSBLCMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBLCMST.SELECT.b`

**Line**: 44

**Table**: MD.DEAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT MD.DEAL
```

**SQL Translation**:
```sql
SELECT *
FROM MD_DEAL
```

---

### Performance Warning #183

**File**: `BPA.B.EXTRACT.HSBLCMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBLCMST.SELECT.b`

**Line**: 54

**Table**: LETTER.OF.CREDIT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LETTER.OF.CREDIT
```

**SQL Translation**:
```sql
SELECT *
FROM LETTER_OF_CREDIT
```

---

### Performance Warning #184

**File**: `BPA.B.EXTRACT.HSBLNECR.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBLNECR.SELECT.b`

**Line**: 62

**Table**: LIMIT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LIMIT
```

**SQL Translation**:
```sql
SELECT *
FROM LIMIT
```

---

### Performance Warning #185

**File**: `BPA.B.EXTRACT.HSBOFMST.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBOFMST.LOAD.b`

**Line**: 85

**Table**: CURRENCY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CURRENCY
```

**SQL Translation**:
```sql
SELECT *
FROM CURRENCY
```

---

### Performance Warning #186

**File**: `BPA.B.EXTRACT.HSBOINACTIVOS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBOINACTIVOS.SELECT.b`

**Line**: 46

**Table**: ACCT.ENT.TODAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCT.ENT.TODAY
```

**SQL Translation**:
```sql
SELECT *
FROM ACCT_ENT_TODAY
```

---

### Performance Warning #187

**File**: `BPA.B.EXTRACT.HSBPLANV.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBPLANV.SELECT.b`

**Line**: 49

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #188

**File**: `BPA.B.EXTRACT.HSBPLMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBPLMST.SELECT.b`

**Line**: 36

**Table**: MD.DEAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT MD.DEAL
```

**SQL Translation**:
```sql
SELECT *
FROM MD_DEAL
```

---

### Performance Warning #189

**File**: `BPA.B.EXTRACT.HSBRCOLL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBRCOLL.SELECT.b`

**Line**: 49

**Table**: COLLATERAL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT COLLATERAL
```

**SQL Translation**:
```sql
SELECT *
FROM COLLATERAL
```

---

### Performance Warning #190

**File**: `BPA.B.EXTRACT.HSBTITULARES.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPABATCH_MigMallaBatch\BAPABATCH_MigMallaBatch\Source\Private\BPA.B.EXTRACT.HSBTITULARES.SELECT.b`

**Line**: 46

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #191

**File**: `BAPA.B.REACT.INACTIVE.ACCT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAC_Framework\Source\Private\BAPA.B.REACT.INACTIVE.ACCT.SELECT.b`

**Line**: 42

**Table**: IN.DIR

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT IN.DIR
```

**SQL Translation**:
```sql
SELECT *
FROM IN_DIR
```

---

### Performance Warning #192

**File**: `BAPA.B.DEL.ACH.C.CERR.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAACH_Framework\Source\Private\BAPA.B.DEL.ACH.C.CERR.SELECT.b`

**Line**: 23

**Table**: LATAM.ACH.DD.MANDATE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LATAM.ACH.DD.MANDATE
```

**SQL Translation**:
```sql
SELECT *
FROM LATAM_ACH_DD_MANDATE
```

---

### Performance Warning #193

**File**: `BAN.B.DEL.LOG.OFFPRINCIPAL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAA_Framework\BAPAAA_Framework\Source\Private\BAN.B.DEL.LOG.OFFPRINCIPAL.b`

**Line**: 74

**Table**: EB.BPA.LOG.OFFPRINCIPALINT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BPA_LOG_OFFPRINCIPALINT
```

---

### Performance Warning #194

**File**: `BAN.B.RR.ADJUST.OFFPRINCIPAL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAA_Framework\BAPAAA_Framework\Source\Private\BAN.B.RR.ADJUST.OFFPRINCIPAL.SELECT.b`

**Line**: 44

**Table**: ST.BAPA.SUSPEND.ENTRIES

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ST.BAPA.SUSPEND.ENTRIES
```

**SQL Translation**:
```sql
SELECT *
FROM ST_BAPA_SUSPEND_ENTRIES
```

---

### Performance Warning #195

**File**: `BAN.CUADRO.DPF.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAN.CUADRO.DPF.POST.b`

**Line**: 70

**Table**: BAN.CUADRO.DPF.LIST

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.CUADRO.DPF.LIST BY @ID
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CUADRO_DPF_LIST
ORDER BY ID ASC
```

---

### Performance Warning #196

**File**: `BAPA.B.ADJ.LOAN.CURBALANCE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAPA.B.ADJ.LOAN.CURBALANCE.b`

**Line**: 88

**Table**: FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM FILE_PATH
```

---

### Performance Warning #197

**File**: `BAPA.B.ADJ.LOAN.CURBALANCE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAPA.B.ADJ.LOAN.CURBALANCE.SELECT.b`

**Line**: 52

**Table**: FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM FILE_PATH
```

---

### Performance Warning #198

**File**: `BAPA.B.CAP.UPDATE.AAA.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAPA.B.CAP.UPDATE.AAA.SELECT.b`

**Line**: 19

**Table**: EB.BAPA.L.CAP.TEMP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

### Performance Warning #199

**File**: `BAPA.B.FT.UPDATE.AAA.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAPA.B.FT.UPDATE.AAA.SELECT.b`

**Line**: 20

**Table**: EB.BAPA.L.CAP.TEMP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

### Performance Warning #200

**File**: `BAPA.B.INFO.UPDATE.AAA.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAPA.B.INFO.UPDATE.AAA.SELECT.b`

**Line**: 19

**Table**: EB.BAPA.L.CAP.TEMP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

### Performance Warning #201

**File**: `BAPA.B.REVERSE.CHARGE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BAPA.B.REVERSE.CHARGE.SELECT.b`

**Line**: 19

**Table**: EB.BAPA.L.CAP.TEMP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

### Performance Warning #202

**File**: `BPA.B.ARC.DETAILS.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.B.ARC.DETAILS.SELECT.b`

**Line**: 48

**Table**: BPA.PRT.PLAM.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.PRT.PLAM.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_PRT_PLAM_DETAILS
```

---

### Performance Warning #203

**File**: `BPA.B.ARC.SUMMARY.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.B.ARC.SUMMARY.SELECT.b`

**Line**: 40

**Table**: BPA.PRT.PLAM.SUMMARY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.PRT.PLAM.SUMMARY
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_PRT_PLAM_SUMMARY
```

---

### Performance Warning #204

**File**: `BPA.B.PREST.PLAM.PAYMENT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.B.PREST.PLAM.PAYMENT.SELECT.b`

**Line**: 63

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**SQL Translation**:
```sql
SELECT *
FROM AND
```

---

### Performance Warning #205

**File**: `BPA.BA.PRT.PLAM.UPL.LOTE.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.BA.PRT.PLAM.UPL.LOTE.b`

**Line**: 89

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**SQL Translation**:
```sql
SELECT *
FROM AND
```

---

### Performance Warning #206

**File**: `BPA.E.NOF.PAYMENT.DETAILS.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.E.NOF.PAYMENT.DETAILS.b`

**Line**: 98

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**SQL Translation**:
```sql
SELECT *
FROM AND
```

---

### Performance Warning #207

**File**: `BPA.E.NOF.PAYMENT.DETAILS.HIST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.E.NOF.PAYMENT.DETAILS.HIST.b`

**Line**: 89

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**SQL Translation**:
```sql
SELECT *
FROM AND
```

---

### Performance Warning #208

**File**: `BPA.V.GET.PAYMENT.INFO.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigPrestamos\BAPAAAL_MigPrestamos\Source\Private\BPA.V.GET.PAYMENT.INFO.b`

**Line**: 70

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**SQL Translation**:
```sql
SELECT *
FROM AND
```

---

### Performance Warning #209

**File**: `BAN.B.COMM.PEND.PAYMENT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigCredito\BAPAAAL_MigCredito\Source\Private\BAN.B.COMM.PEND.PAYMENT.SELECT.b`

**Line**: 39

**Table**: BAN.COMM.PENDING

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.COMM.PENDING BY @ID
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_COMM_PENDING
ORDER BY ID ASC
```

---

### Performance Warning #210

**File**: `BPA.B.COL.AGRSUBSIDY.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigCredito\BAPAAAL_MigCredito\Source\Private\BPA.B.COL.AGRSUBSIDY.SELECT.b`

**Line**: 26

**Table**: BPA.AGRSUBSIDY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.AGRSUBSIDY
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_AGRSUBSIDY
```

---

### Performance Warning #211

**File**: `BPA.B.LOAN.COMM.AMORT.REP.POST.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigCredito\BAPAAAL_MigCredito\Source\Private\BPA.B.LOAN.COMM.AMORT.REP.POST.b`

**Line**: 87

**Table**: BPA.AMPRT.TEMP.RPT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BPA.AMPRT.TEMP.RPT
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_AMPRT_TEMP_RPT
```

---

### Performance Warning #212

**File**: `BPA.B.MRTG.FISCAL.LOAN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigCredito\BAPAAAL_MigCredito\Source\Private\BPA.B.MRTG.FISCAL.LOAN.SELECT.b`

**Line**: 18

**Table**: BPA.MRTG.PREF

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.MRTG.PREF
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_MRTG_PREF
```

---

### Performance Warning #213

**File**: `BPA.B.PAY.FECI.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigCredito\BAPAAAL_MigCredito\Source\Private\BPA.B.PAY.FECI.SELECT.b`

**Line**: 25

**Table**: BPA.FECI.ARRANGEMENTS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.FECI.ARRANGEMENTS
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_FECI_ARRANGEMENTS
```

---

### Performance Warning #214

**File**: `BPA.B.UPD.AGRSUBSIDY.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAL_MigCredito\BAPAAAL_MigCredito\Source\Private\BPA.B.UPD.AGRSUBSIDY.SELECT.b`

**Line**: 21

**Table**: BPA.AGRSUBSIDY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.AGRSUBSIDY
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_AGRSUBSIDY
```

---

### Performance Warning #215

**File**: `BAN.B.OUTCLG.LCLINTL.BALANCES.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAD_MigDepositos\BAPAAAD_MigDepositos\Source\Private\BAN.B.OUTCLG.LCLINTL.BALANCES.SELECT.b`

**Line**: 59

**Table**: ACCOUNT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCOUNT @ID LIKE LCCYSAMPLE_VALUE0001...
```

**SQL Translation**:
```sql
SELECT *
FROM ACCOUNT
```

---

### Performance Warning #216

**File**: `BAN.B.TT.CHQ.CRACC.APL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAD_MigDepositos\BAPAAAD_MigDepositos\Source\Private\BAN.B.TT.CHQ.CRACC.APL.SELECT.b`

**Line**: 28

**Table**: BAN.TT.CHQ.STMT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.TT.CHQ.STMT
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TT_CHQ_STMT
```

---

### Performance Warning #217

**File**: `BAN.B.TT.CHQ.STMT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAD_MigDepositos\BAPAAAD_MigDepositos\Source\Private\BAN.B.TT.CHQ.STMT.SELECT.b`

**Line**: 28

**Table**: BAN.TT.CHQ.STMT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.TT.CHQ.STMT
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TT_CHQ_STMT
```

---

### Performance Warning #218

**File**: `BAN.I.TT.CHQ.CLOSE.TILL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAD_MigDepositos\BAPAAAD_MigDepositos\Source\Private\BAN.I.TT.CHQ.CLOSE.TILL.b`

**Line**: 60

**Table**: BAN.TT.CHQ.CONTROL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.TT.CHQ.CONTROL @ID LIKE ID.NEW-... AND CHQ.PEND.AMT GT 0
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_TT_CHQ_CONTROL
WHERE CHQ_PEND_AMT > '0'
```

---

### Performance Warning #219

**File**: `BAN.I.TT.CHQ.CLOSE.TILL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAD_MigDepositos\BAPAAAD_MigDepositos\Source\Private\BAN.I.TT.CHQ.CLOSE.TILL.b`

**Line**: 76

**Table**: CHEQUE.COLLECTION

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ ID.NEW AND CO.CODE EQ ID.COMPANY AND BANK.SORT.CODE EQ {SORT.BANESCO<2>}
```

**SQL Translation**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE LT_DEP_TT_ID = 'ID.NEW' AND CO_CODE = 'ID.COMPANY' AND BANK_SORT_CODE = '{SORT.BANESCO<2>}'
```

---

### Performance Warning #220

**File**: `BACM3M.B.FINAL.FILE.GEN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BACM3M.B.FINAL.FILE.GEN.SELECT.b`

**Line**: 20

**Table**: BACM3M.DATA.FINAL.GEN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BACM3M.DATA.FINAL.GEN
```

**SQL Translation**:
```sql
SELECT *
FROM BACM3M_DATA_FINAL_GEN
```

---

### Performance Warning #221

**File**: `BACM3M.B.TXNS.SELECTION.COLLECT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BACM3M.B.TXNS.SELECTION.COLLECT.SELECT.b`

**Line**: 68

**Table**: VALUE123

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM VALUE123
```

---

### Performance Warning #222

**File**: `BACM3M.B.VAL.INI.ACCOUNTING.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BACM3M.B.VAL.INI.ACCOUNTING.b`

**Line**: 88

**Table**: FILE.PATH

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT FILE.PATH
```

**SQL Translation**:
```sql
SELECT *
FROM FILE_PATH
```

---

### Performance Warning #223

**File**: `BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Line**: 88

**Table**: ACCOUNT.STATEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCOUNT.STATEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM ACCOUNT_STATEMENT
```

---

### Performance Warning #224

**File**: `BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Line**: 122

**Table**: ACCOUNT.STATEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT ACCOUNT.STATEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM ACCOUNT_STATEMENT
```

---

### Performance Warning #225

**File**: `BAN.B.BATCH.CLEAN.T.AC.OD.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.BATCH.CLEAN.T.AC.OD.SELECT.b`

**Line**: 42

**Table**: BAN.ACCT.OD.DAY

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.ACCT.OD.DAY
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_ACCT_OD_DAY
```

---

### Performance Warning #226

**File**: `BAN.B.CMX.EXPIRED.TXN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.CMX.EXPIRED.TXN.SELECT.b`

**Line**: 29

**Table**: BAN.CMX.EXPIRED.TXN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.CMX.EXPIRED.TXN @ID EQ TODAY
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_CMX_EXPIRED_TXN
```

---

### Performance Warning #227

**File**: `BAN.B.DELETE.ONLINE.CLEARED.BAL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.DELETE.ONLINE.CLEARED.BAL.SELECT.b`

**Line**: 27

**Table**: BAN.NO.MONTHS.AC

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.NO.MONTHS.AC
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_NO_MONTHS_AC
```

---

### Performance Warning #228

**File**: `BAN.B.OD.MONTHS.YEAR.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.OD.MONTHS.YEAR.SELECT.b`

**Line**: 31

**Table**: BPA.OD.ACCT.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.OD.ACCT.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_OD_ACCT_DETAILS
```

---

### Performance Warning #229

**File**: `BAN.B.UPD.AVL.AMT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.UPD.AVL.AMT.b`

**Line**: 65

**Table**: BAN.STR.TXN.AMT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.STR.TXN.AMT
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_STR_TXN_AMT
```

---

### Performance Warning #230

**File**: `BAN.B.UPD.BAL.EXCEDLINE.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.UPD.BAL.EXCEDLINE.SELECT.b`

**Line**: 52

**Table**: BAN.T.ACCT.LIM.OD

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.T.ACCT.LIM.OD
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_T_ACCT_LIM_OD
```

---

### Performance Warning #231

**File**: `BAN.B.UPDATE.ONLINE.CLEARED.BAL.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.B.UPDATE.ONLINE.CLEARED.BAL.SELECT.b`

**Line**: 33

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT PRODUCT.LINE EQ ACCOUNTS
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #232

**File**: `BAN.CONT.FILE.FINAL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.CONT.FILE.FINAL.b`

**Line**: 116

**Table**: TEMP.FOLDER.POINTER

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT TEMP.FOLDER.POINTER
```

**SQL Translation**:
```sql
SELECT *
FROM TEMP_FOLDER_POINTER
```

---

### Performance Warning #233

**File**: `BAN.E.NOF.AC.OVERDRAWN.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.AC.OVERDRAWN.b`

**Line**: 143

**Table**: ACCOUNT.OVERDRAWN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.ACCOUNT.OVERDRAWN
```

**SQL Translation**:
```sql
SELECT *
FROM ACCOUNT_OVERDRAWN
```

---

### Performance Warning #234

**File**: `BAN.E.NOF.AC.OVERDRAWN.LC.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.AC.OVERDRAWN.LC.b`

**Line**: 122

**Table**: BAN.ACCT.OVERDRAWN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.ACCT.OVERDRAWN
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_ACCT_OVERDRAWN
```

---

### Performance Warning #235

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Line**: 105

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND @ID EQ SAMPLE_VALUE AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>}
```

**SQL Translation**:
```sql
SELECT *
FROM AND
WHERE ID = 'SAMPLE_VALUE' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}'
```

---

### Performance Warning #236

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Line**: 110

**Table**: AND

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT  AND @ID EQ SAMPLE_VALUE AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>}
```

**SQL Translation**:
```sql
SELECT *
FROM AND
WHERE ID = 'SAMPLE_VALUE' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}'
```

---

### Performance Warning #237

**File**: `BAN.E.NOF.NFT.NO.GEN.PRT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.NFT.NO.GEN.PRT.b`

**Line**: 113

**Table**: BAN.NO.FIN.TXN.NO.PRT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.BAN.NO.FIN.TXN.NO.PRT
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_NO_FIN_TXN_NO_PRT
```

---

### Performance Warning #238

**File**: `BAN.E.NOF.PS.CHQ.SUSP.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.PS.CHQ.SUSP.b`

**Line**: 133

**Table**: PAYMENT.STOP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE VALUE123 AND STOP.DATE LE VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE >= 'VALUE123' AND STOP_DATE <= 'VALUE123'
```

---

### Performance Warning #239

**File**: `BAN.E.NOF.PS.CHQ.SUSP.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.PS.CHQ.SUSP.b`

**Line**: 133

**Table**: PAYMENT.STOP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE <= 'VALUE123'
```

---

### Performance Warning #240

**File**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Line**: 141

**Table**: PAYMENT.STOP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE VALUE123 AND STOP.DATE LE VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE >= 'VALUE123' AND STOP_DATE <= 'VALUE123'
```

---

### Performance Warning #241

**File**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Line**: 141

**Table**: PAYMENT.STOP

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE VALUE123
```

**SQL Translation**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE <= 'VALUE123'
```

---

### Performance Warning #242

**File**: `BAPA.B.AC.LOCK.REVE.LOAD.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAPA.B.AC.LOCK.REVE.LOAD.b`

**Line**: 85

**Table**: IN.DIR

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT IN.DIR
```

**SQL Translation**:
```sql
SELECT *
FROM IN_DIR
```

---

### Performance Warning #243

**File**: `BAPA.B.PROCES.RAING.ACCT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAPA.B.PROCES.RAING.ACCT.SELECT.b`

**Line**: 29

**Table**: SAMPLE_VALUE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT SAMPLE_VALUE
```

**SQL Translation**:
```sql
SELECT *
FROM SAMPLE_VALUE
```

---

### Performance Warning #244

**File**: `BAPA.B.UPD.CHG.PENDING.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAPA.B.UPD.CHG.PENDING.SELECT.b`

**Line**: 26

**Table**: BAN.AA.T.CHG.PENDING

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.AA.T.CHG.PENDING
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

### Performance Warning #245

**File**: `BAPA.RETURN.OVERDUE.CAPITAL.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BAPA.RETURN.OVERDUE.CAPITAL.b`

**Line**: 104

**Table**: AC.BALANCE.TYPE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.AC.BALANCE.TYPE
```

**SQL Translation**:
```sql
SELECT *
FROM AC_BALANCE_TYPE
```

---

### Performance Warning #246

**File**: `BCM.B.LAST.CR.ACMST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BCM.B.LAST.CR.ACMST.SELECT.b`

**Line**: 27

**Table**: AA.ARRANGEMENT

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT
```

**SQL Translation**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

### Performance Warning #247

**File**: `BPA.B.OD.DAYS.START.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BPA.B.OD.DAYS.START.SELECT.b`

**Line**: 50

**Table**: BAN.ACCT.OVERDRAWN

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BAN.ACCT.OVERDRAWN
```

**SQL Translation**:
```sql
SELECT *
FROM BAN_ACCT_OVERDRAWN
```

---

### Performance Warning #248

**File**: `BPA.B.OD.MONTHS.YEAR.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_MigCuentas\BAPAAAC_MigCuentas\Source\Private\BPA.B.OD.MONTHS.YEAR.SELECT.b`

**Line**: 31

**Table**: BPA.OD.ACCT.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT BPA.OD.ACCT.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM BPA_OD_ACCT_DETAILS
```

---

### Performance Warning #249

**File**: `BAN.CLEAR.SUS.ENTRIES.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_AccountingEntries\BAPAAAC_AccountingEntries\Source\Private\BAN.CLEAR.SUS.ENTRIES.SELECT.b`

**Line**: 22

**Table**: LOCAL.TABLE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LOCAL.TABLE
```

**SQL Translation**:
```sql
SELECT *
FROM LOCAL_TABLE
```

---

### Performance Warning #250

**File**: `BAN.RAISE.SUS.ENTRIES.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BAPAAAC_AccountingEntries\BAPAAAC_AccountingEntries\Source\Private\BAN.RAISE.SUS.ENTRIES.SELECT.b`

**Line**: 22

**Table**: LOCAL.TABLE

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT LOCAL.TABLE
```

**SQL Translation**:
```sql
SELECT *
FROM LOCAL_TABLE
```

---

### Performance Warning #251

**File**: `BANV.ACLK.ACCOUNT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BANVAL_Framework\Source\Private\BANV.ACLK.ACCOUNT.SELECT.b`

**Line**: 25

**Table**: EB.BANV.CUS.ACC.PARAM

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BANV.CUS.ACC.PARAM
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BANV_CUS_ACC_PARAM
```

---

### Performance Warning #252

**File**: `BANV.E.NOF.PAYMENT.DETAILS.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BANVAL_Framework\Source\Private\BANV.E.NOF.PAYMENT.DETAILS.b`

**Line**: 73

**Table**: EB.BANV.PAYMENT.LOAN.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT F.EB.BANV.PAYMENT.LOAN.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BANV_PAYMENT_LOAN_DETAILS
```

---

### Performance Warning #253

**File**: `BANV.FT.DEBIT.ACCOUNT.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BANVAL_Framework\Source\Private\BANV.FT.DEBIT.ACCOUNT.SELECT.b`

**Line**: 25

**Table**: EB.BANV.DEBIT.ACLK.DETAIL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BANV.DEBIT.ACLK.DETAIL
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BANV_DEBIT_ACLK_DETAIL
```

---

### Performance Warning #254

**File**: `BANV.FT.PAYMENT.LOAN.POST.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BANVAL_Framework\Source\Private\BANV.FT.PAYMENT.LOAN.POST.SELECT.b`

**Line**: 25

**Table**: EB.BANV.PAYMENT.LOAN.DETAILS

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BANV.PAYMENT.LOAN.DETAILS
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BANV_PAYMENT_LOAN_DETAILS
```

---

### Performance Warning #255

**File**: `BANV.FT.PAYMENT.LOAN.SELECT.b`

**Full Path**: `C:\Users\arulp\Desktop\Select_Analyser_Project_Final\Select_Analyser_Project\R21_Source 1\R21_Source\BANVAL_Framework\Source\Private\BANV.FT.PAYMENT.LOAN.SELECT.b`

**Line**: 25

**Table**: EB.BANV.DEBIT.ACLK.DETAIL

**  Issue**: SELECT without WITH clause - Will scan entire table

**SELECT Statement**:
```
SELECT EB.BANV.DEBIT.ACLK.DETAIL
```

**SQL Translation**:
```sql
SELECT *
FROM EB_BANV_DEBIT_ACLK_DETAIL
```

---

##   LOCAL.REF Field Information

Found 45 SELECT statements using LOCAL.REF fields.

**Note**: LOCAL.REF fields are **physical fields** stored in the database (in the LOCAL.REF multivalue field). They are **TAFJ compatible** and can be indexed for performance.

**Example**: A field like `L.CUSTOM.FIELD` with I-descriptor `LOCAL.REF<1,12>` means it's stored in position 12 of the first multivalue in the LOCAL.REF field.

### Info #1

**File**: `LATAM.ACH.E.NOF.BENEF.CAPTURE.b`

**Line**: 77

**Table**: BENEFICIARY

**  LOCAL.REF Fields**: LT.CCY

**LT.CCY**  `LOCAL.REF<1,7>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,7>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.BENEFICIARY WITH LT.CCY EQ VALUE123 AND OWNING.CUSTOMER EQ VALUE123 AND TRANSACTION.TYPE LIKE "BC..." 
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #2

**File**: `BAN.E.NOF.TCIB.CCY.MARKET.b`

**Line**: 79

**Table**: CURRENCY

**  LOCAL.REF Fields**: LT.IB.TRFINT

**LT.IB.TRFINT**  `LOCAL.REF<1,2>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,2>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CURRENCY WITH LT.IB.TRFINT NE '' BY LT.IB.TRFINT
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #3

**File**: `BAN.E.NOF.TCIB.STO.b`

**Line**: 291

**Table**: STANDING.ORDER

**  LOCAL.REF Fields**: ACCOUNT

**ACCOUNT**  `@ID['.',1,1]`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: @ID['.',1,1]
-- SQL (MySQL): SUBSTRING_INDEX(RECID, '.', 1)
-- SQL (PostgreSQL/Oracle): SPLIT_PART(RECID, '.', 1)
```
</details>

**SELECT Statement**:
```
SELECT F.STANDING.ORDER WITH ACCOUNT EQ VALUE123 AND ( CURRENT.END.DATE EQ '' OR CURRENT.END.DATE GT VALUE123 )
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #4

**File**: `BAN.E.NOF.TCIB.STO.b`

**Line**: 294

**Table**: STANDING.ORDER$HIS

**  LOCAL.REF Fields**: ACCOUNT

**ACCOUNT**  `@ID['.',1,1]`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: @ID['.',1,1]
-- SQL (MySQL): SUBSTRING_INDEX(RECID, '.', 1)
-- SQL (PostgreSQL/Oracle): SPLIT_PART(RECID, '.', 1)
```
</details>

**SELECT Statement**:
```
SELECT F.STANDING.ORDER$HIS WITH ACCOUNT EQ VALUE123 AND ( CURRENT.END.DATE EQ '' OR CURRENT.END.DATE GT VALUE123 )
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #5

**File**: `BAN.E.NOF.TCIB.STO.b`

**Line**: 522

**Table**: FUNDS.TRANSFER

**  LOCAL.REF Fields**: LT.BAN.TC.OPER

**LT.BAN.TC.OPER**  `LOCAL.REF<1,54>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,54>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER WITH DEBIT.ACCT.NO EQ VALUE123 AND PROCESSING.DATE GT VALUE123 AND LT.BAN.TC.OPER EQ PAGOS-MISCTASBANESCOFUTURA.EJECUTAR PAGOS-RECARGAMISTARJETASFUTURA.EJECUTAR PAGOS-RECARGATDCBANESCOFUTURA.EJECUTAR PAGOS-TDCBANESCOFUTURA.EJECUTAR PAGOS-TDCMISTARJETASFUTURA.EJECUTAR PAGOS-TERCEROSBANESCOFUTURA.EJECUTAR
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #6

**File**: `BAN.E.NOF.TCIB.STO.b`

**Line**: 527

**Table**: FUNDS.TRANSFER$HIS

**  LOCAL.REF Fields**: LT.BAN.TC.OPER

**LT.BAN.TC.OPER**  `LOCAL.REF<1,54>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,54>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH DEBIT.ACCT.NO EQ VALUE123 WITH PROCESSING.DATE GT VALUE123 AND LT.BAN.TC.OPER EQ PAGOS-MISCTASBANESCOFUTURA.EJECUTAR PAGOS-RECARGAMISTARJETASFUTURA.EJECUTAR PAGOS-RECARGATDCBANESCOFUTURA.EJECUTAR PAGOS-TDCBANESCOFUTURA.EJECUTAR PAGOS-TDCMISTARJETASFUTURA.EJECUTAR PAGOS-TERCEROSBANESCOFUTURA.EJECUTAR
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #7

**File**: `BAN.E.NOF.TCIB.STO.b`

**Line**: 634

**Table**: LATAM.ACH.CAPTURE

**  LOCAL.REF Fields**: LT.BAN.TC.OPER

**LT.BAN.TC.OPER**  `LOCAL.REF<1,2>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,2>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.LATAM.ACH.CAPTURE WITH OFFSET.ACCOUNT EQ VALUE123 AND ( MATURITY.DATE GT VALUE123 ) AND LT.BAN.TC.OPER EQ PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR PAGOS-TDCOTROBANCOFUTURA.EJECUTAR PAGOS-TERCEROSOTROBANCOFUTURA.EJECUTAR
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #8

**File**: `BAN.E.NOF.TCIB.STO.b`

**Line**: 639

**Table**: LATAM.ACH.CAPTURE$HIS

**  LOCAL.REF Fields**: LT.BAN.TC.OPER

**LT.BAN.TC.OPER**  `LOCAL.REF<1,2>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,2>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.LATAM.ACH.CAPTURE$HIS WITH OFFSET.ACCOUNT EQ VALUE123 AND ( MATURITY.DATE GT VALUE123 ) AND LT.BAN.TC.OPER EQ PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR PAGOS-TDCOTROBANCOFUTURA.EJECUTAR PAGOS-TERCEROSOTROBANCOFUTURA.EJECUTAR
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #9

**File**: `BAN.S.GET.BANESCO.b`

**Line**: 63

**Table**: BC.SORT.CODE

**  LOCAL.REF Fields**: LT.BANK.FROM

**LT.BANK.FROM**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.BC.SORT.CODE WITH LT.BANK.FROM EQ "PRP"
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #10

**File**: `B.BAPA.ACH.FILE.UPLOD.SELECT.b`

**Line**: 20

**Table**: EB.FILE.UPLOAD

**  LOCAL.REF Fields**: BAPA.ACH.MAST

**BAPA.ACH.MAST**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT EB.FILE.UPLOAD WITH UPLOAD.TYPE EQ 'BAPA.ORIGINADORES' AND BAPA.ACH.MAST EQ ''
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #11

**File**: `BAPA.E.NOF.INW.IHLD.FT.103.OOT.b`

**Line**: 107

**Table**: FUNDS.TRANSFER$NAU

**  LOCAL.REF Fields**: LT.EFM.REF

**LT.EFM.REF**  `LOCAL.REF<1,57>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,57>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ IT AND RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND INWARD.PAY.TYPE EQ MT103 AND LT.EFM.REF EQ "" AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TIME
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #12

**File**: `BAN.B.NOT.CHARGE.PLANILLA.SELECT.b`

**Line**: 50

**Table**: FT.BULK.MASTER

**  LOCAL.REF Fields**: LT.STATUS.PLN

**LT.STATUS.PLN**  `LOCAL.REF<1,3>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,3>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT FT.BULK.MASTER WITH (STATUS EQ 'PROCESSING' OR STATUS EQ 'PROCESSED') AND LT.STATUS.PLN EQ '' AND (BULK.TYPE EQ 'SINGLE.PLANILLA' OR BULK.TYPE EQ 'SINGLE.PROVEEDOR')
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #13

**File**: `BAN.B.OUTCLG.CLEARED.SELECT.b`

**Line**: 135

**Table**: CHEQUE.COLLECTION

**  LOCAL.REF Fields**: LT.ISSUE.DATE, LT.SRC.EXP.DT

**LT.ISSUE.DATE**  `LOCAL.REF<1,22>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,22>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.SRC.EXP.DT**  `LOCAL.REF<1,10>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,10>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT CHEQUE.COLLECTION WITH LT.SRC.EXP.DT EQ BAT.EXP.DATE AND CHQ.STATUS EQ 'CLEARING' AND LT.ISSUE.DATE LE TODAYVALUE123TODAY
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #14

**File**: `BAN.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Line**: 79

**Table**: CHEQUE.COLLECTION$NAU

**  LOCAL.REF Fields**: LT.RET.COD.CC

**LT.RET.COD.CC**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED  AND LT.RET.COD.CC NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO) AND CHEQUE.NO EQ SAMPLE_VALUE AND CHEQUE.NO NE SAMPLE_VALUE AND CHEQUE.NO LK ...SAMPLE_VALUE...
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #15

**File**: `BAN.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Line**: 82

**Table**: FUNDS.TRANSFER$NAU

**  LOCAL.REF Fields**: LT.RET.COD.CC, LT.CC.ID

**LT.RET.COD.CC**  `LOCAL.REF<1,25>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,25>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.CC.ID**  `LOCAL.REF<1,31>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,31>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.RET.COD.CC NE "" AND LT.CC.ID NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #16

**File**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET.b`

**Line**: 108

**Table**: CHEQUE.COLLECTION

**  LOCAL.REF Fields**: LT.DEP.TT.ID

**LT.DEP.TT.ID**  `LOCAL.REF<1,4>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,4>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ {R.TELLER.USR<1>} AND CO.CODE EQ ID.COMPANY AND CHEQUE.NO EQ SAMPLE_VALUE AND CHEQUE.NO NE SAMPLE_VALUE AND CHEQUE.NO LK ...SAMPLE_VALUE...
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #17

**File**: `BAN.E.NOF.OUTCLG.RET.TOT.b`

**Line**: 160

**Table**: CHEQUE.COLLECTION

**  LOCAL.REF Fields**: LT.CHEQUE.ACC, LT.CHQ.ACC.TYP, LT.RET.COD.CC, LT.RET.FUNDS

**LT.CHEQUE.ACC**  `LOCAL.REF<1,3>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,3>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.CHQ.ACC.TYP**  `LOCAL.REF<1,13>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,13>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.RET.COD.CC**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.RET.FUNDS**  `LOCAL.REF<1,11>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,11>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ RETURNED AND STATUS.DATE EQ VALUE123 AND BANK.SORT.CODE EQ VALUE123 AND CO.CODE EQ VALUE123 AND LT.CHEQUE.ACC EQ VALUE123 AND CREDIT.ACC.NO EQ VALUE123 AND LT.RET.COD.CC EQ VALUE123 AND LT.RET.FUNDS EQ VALUE123 AND BANK.SORT.CODE NE SAMPLE_VALUE BY BANK.SORT.CODE BY LT.CHEQUE.ACC BY LT.CHQ.ACC.TYP BY LT.RET.COD.CC
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #18

**File**: `BAN.ENQ.B.OUTCLG.AUT.b`

**Line**: 46

**Table**: CHEQUE.COLLECTION$NAU

**  LOCAL.REF Fields**: LT.RET.COD.CHQ

**LT.RET.COD.CHQ**  `LOCAL.REF<1,2>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,2>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ CLEARED OR (CHQ.STATUS EQ 'RETURNED' AND LT.RET.COD.CHQ NE '')
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #19

**File**: `BAN.OUTCLG.CLDCC.b`

**Line**: 61

**Table**: FUNDS.TRANSFER$NAU

**  LOCAL.REF Fields**: LT.CC.ID

**LT.CC.ID**  `LOCAL.REF<1,31>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,31>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.CC.ID NE ''
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #20

**File**: `BAN.S.CLG.BAN.SORT.CODE.b`

**Line**: 43

**Table**: BC.SORT.CODE

**  LOCAL.REF Fields**: LT.BANK.FROM

**LT.BANK.FROM**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.BC.SORT.CODE WITH LT.BANK.FROM EQ 'PRP'
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #21

**File**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Line**: 103

**Table**: CHEQUE.COLLECTION$NAU

**  LOCAL.REF Fields**: LT.RET.COD.CC

**LT.RET.COD.CC**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED AND LT.RET.COD.CC NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #22

**File**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Line**: 106

**Table**: FUNDS.TRANSFER$NAU

**  LOCAL.REF Fields**: LT.RET.COD.CC, LT.CC.ID

**LT.RET.COD.CC**  `LOCAL.REF<1,25>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,25>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.CC.ID**  `LOCAL.REF<1,31>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,31>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.RET.COD.CC NE "" AND LT.CC.ID NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #23

**File**: `BPA.E.NOF.CHQ.OUTCLG.NO.RET.b`

**Line**: 93

**Table**: CHEQUE.COLLECTION$NAU

**  LOCAL.REF Fields**: LT.CHEQUE.ACC, LT.RET.COD.CC

**LT.CHEQUE.ACC**  `LOCAL.REF<1,3>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,3>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.RET.COD.CC**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO) AND BANK.SORT.CODE NE SAMPLE_VALUE AND STATUS.DATE EQ SAMPLE_VALUE AND STATUS.DATE NE SAMPLE_VALUE AND STATUS.DATE LK ...SAMPLE_VALUE... AND BANK.SORT.CODE EQ SAMPLE_VALUE AND BANK.SORT.CODE NE SAMPLE_VALUE AND BANK.SORT.CODE LK ...SAMPLE_VALUE... AND CO.CODE EQ SAMPLE_VALUE AND CO.CODE NE SAMPLE_VALUE AND CO.CODE LK ...SAMPLE_VALUE... AND LT.CHEQUE.ACC EQ SAMPLE_VALUE AND LT.CHEQUE.AC
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #24

**File**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET.b`

**Line**: 119

**Table**: CHEQUE.COLLECTION

**  LOCAL.REF Fields**: LT.CHEQUE.ACC

**LT.CHEQUE.ACC**  `LOCAL.REF<1,3>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,3>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND LT.CHEQUE.ACC EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAmount>}
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #25

**File**: `BAN.E.BLD.COUNTRY.CODE.b`

**Line**: 45

**Table**: COUNTRY

**  LOCAL.REF Fields**: LT.PHONE.CODE

**LT.PHONE.CODE**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.COUNTRY WITH LT.PHONE.CODE EQ 12345
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #26

**File**: `BCM.CUFIN.SELECT.RTN.b`

**Line**: 68

**Table**: CUSTOMER

**  LOCAL.REF Fields**: LT.PERSON.TYPE, LT.TCIB.TYPE

**LT.PERSON.TYPE**  `LOCAL.REF<1,11>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,11>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.TCIB.TYPE**  `LOCAL.REF<1,33>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,33>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CUSTOMER WITH LT.TCIB.TYPE NE PROSPECT AND CUSTOMER.TYPE NE PROSPECT AND LT.PERSON.TYPE EQ 1
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #27

**File**: `BAPA.CANCEL.COLLATERAL.b`

**Line**: 252

**Table**: AC.LOCKED.EVENTS

**  LOCAL.REF Fields**: LT.TYPE.BLOCK

**LT.TYPE.BLOCK**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.AC.LOCKED.EVENTS WITH LT.TYPE.BLOCK EQ PIGN AND ACCOUNT.NUMBER EQ {DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #28

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.b`

**Line**: 266

**Table**: AC.LOCKED.EVENTS

**  LOCAL.REF Fields**: LT.TYPE.BLOCK

**LT.TYPE.BLOCK**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT AC.LOCKED.EVENTS WITH LT.TYPE.BLOCK EQ PIGN AND ACCOUNT.NUMBER EQ {DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #29

**File**: `BPA.S.GET.CHQ.TYPE.b`

**Line**: 65

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: ACCOUNT.NO

**ACCOUNT.NO**  `@ID[".",2,1]`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: @ID[".",2,1]
-- SQL (MySQL): SUBSTRING_INDEX(SUBSTRING_INDEX(RECID, '.', 2), '.', -1)
-- SQL (PostgreSQL/Oracle): SPLIT_PART(RECID, '.', 2)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH ACCOUNT.NO EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #30

**File**: `BAN.E.CNV.TT.CHQ.GET.DETID.b`

**Line**: 42

**Table**: TELLER.FINANCIAL.SERVICES$NAU

**  LOCAL.REF Fields**: LT.TT.CHQ.CRTL

**LT.TT.CHQ.CRTL**  `LOCAL.REF<1,33>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,33>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.TELLER.FINANCIAL.SERVICES$NAU WITH LT.TT.CHQ.CRTL EQ 12345
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #31

**File**: `BAN.I.TT.CHQ.CLOSE.TILL.b`

**Line**: 76

**Table**: CHEQUE.COLLECTION

**  LOCAL.REF Fields**: LT.DEP.TT.ID

**LT.DEP.TT.ID**  `LOCAL.REF<1,4>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,4>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ ID.NEW AND CO.CODE EQ ID.COMPANY AND BANK.SORT.CODE EQ {SORT.BANESCO<2>}
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #32

**File**: `BAN.E.NOF.ACCR.NO.FIN.TXN.b`

**Line**: 137

**Table**: AC.CHARGE.REQUEST

**  LOCAL.REF Fields**: LT.NFT.ID

**LT.NFT.ID**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID NE '' AND LT.NFT.ID NE 'EMCHQ' AND CHARGE.DATE GE VALUE123 AND CHARGE.DATE LE VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #33

**File**: `BAN.E.NOF.ACCR.NO.FIN.TXN.b`

**Line**: 137

**Table**: AC.CHARGE.REQUEST

**  LOCAL.REF Fields**: LT.NFT.ID

**LT.NFT.ID**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID NE '' AND LT.NFT.ID NE 'EMCHQ' AND CHARGE.DATE LE VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #34

**File**: `BAN.E.NOF.CHQBK.SUSP.ACT.b`

**Line**: 120

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: ACCOUNT.NO

**ACCOUNT.NO**  `@ID[".",2,1]`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: @ID[".",2,1]
-- SQL (MySQL): SUBSTRING_INDEX(SUBSTRING_INDEX(RECID, '.', 2), '.', -1)
-- SQL (PostgreSQL/Oracle): SPLIT_PART(RECID, '.', 2)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 90 AND ACCOUNT.NO EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #35

**File**: `BAN.E.NOF.CI.CHQBK.REQ.b`

**Line**: 157

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: LT.ISSUE.DATE

**LT.ISSUE.DATE**  `LOCAL.REF<1,7>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,7>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH LT.ISSUE.DATE GE 19000101 AND LT.ISSUE.DATE LE 29991231
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #36

**File**: `BAN.E.NOF.CI.CHQBK.SUSP.b`

**Line**: 159

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: LT.ISSUE.DATE

**LT.ISSUE.DATE**  `LOCAL.REF<1,7>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,7>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 89 AND LT.ISSUE.DATE GE VALUE123 AND LT.ISSUE.DATE LE VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #37

**File**: `BAN.E.NOF.CI.CHQBK.SUSP.b`

**Line**: 159

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: LT.ISSUE.DATE

**LT.ISSUE.DATE**  `LOCAL.REF<1,7>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,7>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 89 AND LT.ISSUE.DATE LE VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #38

**File**: `BAN.E.NOF.RECEIVED.DRAFT.b`

**Line**: 75

**Table**: STOCK.ENTRY

**  LOCAL.REF Fields**: LT.STATUS.DRAFT

**LT.STATUS.DRAFT**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.STOCK.ENTRY WITH CHEQUE.TYPE EQ VALUE123 AND LT.STATUS.DRAFT EQ REQ AND IN.OUT.DATE EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #39

**File**: `BAN.E.NOF.SUBLOTE.CHQ.RECEIVED.b`

**Line**: 125

**Table**: CHEQUE.TYPE

**  LOCAL.REF Fields**: LT.ID.TYPE.CHQ, LT.COUNTRY.COD

**LT.ID.TYPE.CHQ**  `LOCAL.REF<1,8>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,8>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**LT.COUNTRY.COD**  `LOCAL.REF<1,9>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,9>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH LT.ID.TYPE.CHQ EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #40

**File**: `BPA.E.NOF.ACCR.CHQBK.REQ.b`

**Line**: 130

**Table**: AC.CHARGE.REQUEST

**  LOCAL.REF Fields**: LT.NFT.ID

**LT.NFT.ID**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID EQ EMCHQ AND CHARGE.DATE GE VALUE123 AND CHARGE.DATE LE VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #41

**File**: `BPA.E.NOF.ACCR.CHQBK.REQ.b`

**Line**: 130

**Table**: AC.CHARGE.REQUEST

**  LOCAL.REF Fields**: LT.NFT.ID

**LT.NFT.ID**  `LOCAL.REF<1,1>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,1>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID EQ EMCHQ AND CHARGE.DATE LE VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #42

**File**: `BPA.E.NOF.DELIV.CHQBK.SUSP.b`

**Line**: 115

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: ACCOUNT.NO

**ACCOUNT.NO**  `@ID[".",2,1]`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: @ID[".",2,1]
-- SQL (MySQL): SUBSTRING_INDEX(SUBSTRING_INDEX(RECID, '.', 2), '.', -1)
-- SQL (PostgreSQL/Oracle): SPLIT_PART(RECID, '.', 2)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 50 AND ACCOUNT.NO EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #43

**File**: `BPA.E.NOF.REQUEST.CHECK.BOOK.b`

**Line**: 76

**Table**: CHEQUE.TYPE

**  LOCAL.REF Fields**: LT.COUNTRY.COD

**LT.COUNTRY.COD**  `LOCAL.REF<1,9>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,9>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #44

**File**: `BRD.E.NOF.DELIV.CHQBK.SUSP.b`

**Line**: 115

**Table**: CHEQUE.ISSUE

**  LOCAL.REF Fields**: ACCOUNT.NO

**ACCOUNT.NO**  `@ID[".",2,1]`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: @ID[".",2,1]
-- SQL (MySQL): SUBSTRING_INDEX(SUBSTRING_INDEX(RECID, '.', 2), '.', -1)
-- SQL (PostgreSQL/Oracle): SPLIT_PART(RECID, '.', 2)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 50 AND ACCOUNT.NO EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

### Info #45

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Line**: 89

**Table**: CHEQUE.TYPE

**  LOCAL.REF Fields**: LT.COUNTRY.COD

**LT.COUNTRY.COD**  `LOCAL.REF<1,9>`

<details>
<summary> SQL Translation Suggestion (Click to expand)</summary>

```sql
-- T24: LOCAL.REF<1,9>
-- SQL: LOCAL_REF  (Note: Multivalue field - may need SUBSTRING_INDEX or array access)
```
</details>

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

** TAFJ Compatibility**:
-  LOCAL.REF fields are stored in the database
-  Can be indexed for performance
-  No code changes required for TAFJ migration

---

##  MULTIVALUE FIELD WARNINGS (Cannot index M fields)

Found 104 SELECT statements using multivalue (M) fields in the condition.

**Issue**: TAFJ cannot create database indexes on multivalue fields. Using these fields in a SELECT condition will prevent index usage and may cause performance degradation (full table scan if no other indexed fields are used).

**Recommendation**: If performance is critical, consider denormalizing the multivalue data into a separate table or a single-value field that can be indexed.

### Multivalue Warning #1

**File**: `LATAM.ACH.CAP.POPULATE.CANC.REVE.b`

**Line**: 94

**Table**: LATAM.ACH.CAPTURE

**  Multivalue Fields**: ORIG.US.ACH.ENTRY
  - `ORIG.US.ACH.ENTRY`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.LATAM.ACH.CAPTURE WITH @ID LIKE ACH{JULIAN[3,6]}... AND ORIG.US.ACH.ENTRY EQ {OrigUsAchEntry}
```

---

### Multivalue Warning #2

**File**: `LATAM.ACH.E.NOF.ADHOC.CAPTURE.b`

**Line**: 91

**Table**: LATAM.ACH.CORPORATE.INFO

**  Multivalue Fields**: CORPORATE.ID
  - `CORPORATE.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {SEL.VALUES<CORPORATE.ID.POS>}
```

---

### Multivalue Warning #3

**File**: `LATAM.ACH.E.NOF.ADHOC.CAPTURE.b`

**Line**: 136

**Table**: LATAM.ACH.CORPORATE.INFO

**  Multivalue Fields**: CORPORATE.ID
  - `CORPORATE.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}
```

---

### Multivalue Warning #4

**File**: `LATAM.ACH.E.NOF.ADHOC.SEC.CODE.b`

**Line**: 107

**Table**: LATAM.ACH.CORPORATE.INFO

**  Multivalue Fields**: CORPORATE.ID
  - `CORPORATE.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}
```

---

### Multivalue Warning #5

**File**: `BAPA.B.AA.DEP.AVRG.BALANCES.SELECT.b`

**Line**: 50

**Table**: AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ DEPOSITS
```

---

### Multivalue Warning #6

**File**: `BAN.E.NOF.TFS.PRESTACARD.b`

**Line**: 51

**Table**: TELLER.FINANCIAL.SERVICES

**  Multivalue Fields**: TRANSACTION
  - `TRANSACTION`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.TELLER.FINANCIAL.SERVICES WITH BOOKING.DATE EQ TODAY AND ( TRANSACTION EQ PR.EFECTIVO OR TRANSACTION EQ PR.CHPROPIO OR TRANSACTION EQ PR.CHLOCAL) AND INPUTTER LK …SAMPLE_VALUE…
```

---

### Multivalue Warning #7

**File**: `BAN.E.NOF.TFS.RECORDS.b`

**Line**: 92

**Table**: TELLER.FINANCIAL.SERVICES

**  Multivalue Fields**: UNDERLYING, REVERSAL.MARK
  - `UNDERLYING`: Type D, Single/Multi: M
  - `REVERSAL.MARK`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.TELLER.FINANCIAL.SERVICES WITH REVERSAL.MARK NE R AND BOOKING.DATE EQ TODAY AND CO.CODE EQ VALUE123 AND UNDERLYING EQ 'VALUE123' BY CO.CODE 
```

---

### Multivalue Warning #8

**File**: `BAN.E.NOF.OPER.BY.TYPE.b`

**Line**: 130

**Table**: BAN.TC.OPERATIONS

**  Multivalue Fields**: ACLM.CHANNEL, TCIB.TYPE, TXN.DESCRIPTION, ACLM.SEQ
  - `ACLM.CHANNEL`: Type D, Single/Multi: M
  - `TCIB.TYPE`: Type D, Single/Multi: M
  - `TXN.DESCRIPTION`: Type D, Single/Multi: M
  - `ACLM.SEQ`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.TC.OPERATIONS WITH ACLM.CHANNEL EQ VALUE123 AND TCIB.TYPE EQ VALUE123 AND TXN.DESCRIPTION NE '' AND ACLM.SEQ NE ''
```

---

### Multivalue Warning #9

**File**: `BAN.E.NOF.OPER.DEF.EXEC.b`

**Line**: 226

**Table**: BAN.TC.OPERATIONS

**  Multivalue Fields**: ACLM.CHANNEL, TCIB.TYPE, TXN.DESCRIPTION, ACLM.SEQ
  - `ACLM.CHANNEL`: Type D, Single/Multi: M
  - `TCIB.TYPE`: Type D, Single/Multi: M
  - `TXN.DESCRIPTION`: Type D, Single/Multi: M
  - `ACLM.SEQ`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.TC.OPERATIONS WITH ACLM.CHANNEL EQ VALUE123 AND TCIB.TYPE EQ VALUE123 AND TXN.DESCRIPTION NE '' AND ACLM.SEQ NE ''
```

---

### Multivalue Warning #10

**File**: `BAN.E.NOF.TCIB.CUST.CRED.b`

**Line**: 126

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: PRODUCT
  - `PRODUCT`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH @ID EQ {R.AA.CUSTOMER.ARRANGEMENT<AA.Framework.CustomerArrangement.CusarrArrangement>} AND ARR.STATUS EQ CURRENT MATURED EXPIRED AND PRODUCT EQ VALUE123
```

---

### Multivalue Warning #11

**File**: `BAN.S.GET.SIGNATURE.SCHEME.b`

**Line**: 184

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

---

### Multivalue Warning #12

**File**: `BAPA.I.SWIFT.MT103.CAMPO52.b`

**Line**: 115

**Table**: DE.BIC

**  Multivalue Fields**: INSTITUTION
  - `INSTITUTION`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.DE.BIC WITH @ID LIKE ...XXX AND INSTITUTION EQ 'VALUE123'
```

---

### Multivalue Warning #13

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 69

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: TXN.REF
  - `TXN.REF`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123...
```

---

### Multivalue Warning #14

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 80

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: TXN.DATE
  - `TXN.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.DATE EQ VALUE123
```

---

### Multivalue Warning #15

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 107

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: UETR.REF
  - `UETR.REF`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH UETR.REF EQ VALUE123
```

---

### Multivalue Warning #16

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 156

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: TXN.DATE, TXN.REF
  - `TXN.DATE`: Type D, Single/Multi: M
  - `TXN.REF`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123... AND TXN.DATE EQ VALUE123
```

---

### Multivalue Warning #17

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 168

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: UETR.REF, TXN.REF
  - `UETR.REF`: Type D, Single/Multi: M
  - `TXN.REF`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123... AND UETR.REF EQ VALUE123
```

---

### Multivalue Warning #18

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 179

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: TXN.DATE, UETR.REF
  - `TXN.DATE`: Type D, Single/Multi: M
  - `UETR.REF`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.DATE EQ VALUE123 AND UETR.REF EQ VALUE123
```

---

### Multivalue Warning #19

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Line**: 206

**Table**: BPA.TC.FT.INTL.TRACK.DETAILS

**  Multivalue Fields**: TXN.DATE, UETR.REF, TXN.REF
  - `TXN.DATE`: Type D, Single/Multi: M
  - `UETR.REF`: Type D, Single/Multi: M
  - `TXN.REF`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123... AND TXN.DATE EQ VALUE123 AND UETR.REF EQ VALUE123
```

---

### Multivalue Warning #20

**File**: `BAN.B.AA.CHG.SETTLE.SELECT.b`

**Line**: 59

**Table**: POSTING.RESTRICT

**  Multivalue Fields**: TXN.CODE
  - `TXN.CODE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT POSTING.RESTRICT WITH RESTRICTION.TYPE EQ "ALL" OR RESTRICTION.TYPE EQ "DEBIT" AND TXN.CODE NE ""
```

---

### Multivalue Warning #21

**File**: `BAN.E.CONV.TCMB.SALDO.DIFERIDO.b`

**Line**: 64

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: CREDIT.ACC.NO
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED CLEARING AND CREDIT.ACC.NO EQ VALUE123
```

---

### Multivalue Warning #22

**File**: `BAN.E.NOF.AA.CC.BAL.b`

**Line**: 115

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: CREDIT.ACC.NO
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ 20231210 AND CHQ.STATUS NE CLEARED AND CHQ.STATUS NE RETURNED
```

---

### Multivalue Warning #23

**File**: `BAN.E.NOF.ACCT.BAL.b`

**Line**: 105

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: CREDIT.ACC.NO
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ VALUE123 AND CHQ.STATUS NE CLEARED
```

---

### Multivalue Warning #24

**File**: `BAN.E.NOF.VIEW.DEL.HISTORY.b`

**Line**: 206

**Table**: TELLER.FINANCIAL.SERVICES$DEL

**  Multivalue Fields**: DR.VALUE.DATE
  - `DR.VALUE.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.TELLER.FINANCIAL.SERVICES$DEL WITH DR.VALUE.DATE EQ TODAY
```

---

### Multivalue Warning #25

**File**: `BAN.TCMB.ENQ.DEPOSITOS.LIST.b`

**Line**: 84

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: CUSTOMER
  - `CUSTOMER`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND PRODUCT.LINE EQ DEPOSITS AND ARR.STATUS EQ CURRENT
```

---

### Multivalue Warning #26

**File**: `BAN.TCMB.ENQ.PRESTAMOS.LIST.b`

**Line**: 67

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: CUSTOMER
  - `CUSTOMER`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND PRODUCT.LINE EQ LENDING AND ARR.STATUS EQ CURRENT
```

---

### Multivalue Warning #27

**File**: `BAPA.B.BOL.TO.INT.b`

**Line**: 266

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{FIELD(LINE,",",3)}"
```

---

### Multivalue Warning #28

**File**: `BAPA.B.BOL.TO.PAY.b`

**Line**: 265

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{FIELD(LINE,",",3)}"
```

---

### Multivalue Warning #29

**File**: `BAPA.B.EB.EOD.ERROR.SELECT.b`

**Line**: 30

**Table**: EB.EOD.ERROR

**  Multivalue Fields**: FIX.REQUIRED, DATE.RESOLVED
  - `FIX.REQUIRED`: Type D, Single/Multi: M
  - `DATE.RESOLVED`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT EB.EOD.ERROR WITH FIX.REQUIRED EQ YES AND DATE.RESOLVED EQ ''
```

---

### Multivalue Warning #30

**File**: `BAPA.B.ENVIA.NOTIFICACION.SELECT.b`

**Line**: 27

**Table**: CHEQUE.REGISTER.SUPPLEMENT

**  Multivalue Fields**: LT.RET.COD.CHQ
  - `LT.RET.COD.CHQ`: Type I, Single/Multi: M

**SELECT Statement**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH ISSUE.DATE EQ TODAY AND STATUS EQ RETURNED AND LT.RET.COD.CHQ NE 1001 AND LT.RET.COD.CHQ NE 0001
```

---

### Multivalue Warning #31

**File**: `BAPA.E.GET.FT.REJECTED.b`

**Line**: 193

**Table**: FUNDS.TRANSFER

**  Multivalue Fields**: ORDERING.CUST
  - `ORDERING.CUST`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ VALUE123
```

---

### Multivalue Warning #32

**File**: `BAPA.E.GET.FT.REJECTED.b`

**Line**: 197

**Table**: FUNDS.TRANSFER$NAU

**  Multivalue Fields**: ORDERING.CUST
  - `ORDERING.CUST`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ VALUE123
```

---

### Multivalue Warning #33

**File**: `BAPA.E.GET.FT.REJECTED.b`

**Line**: 201

**Table**: FUNDS.TRANSFER$HIS

**  Multivalue Fields**: ORDERING.CUST
  - `ORDERING.CUST`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ VALUE123
```

---

### Multivalue Warning #34

**File**: `BAPA.E.NOF.AUDIT.COMP.b`

**Line**: 233

**Table**: HELPTEXT.MENU

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.HELPTEXT.MENU WITH DATE.TIME GE 20010100010001
```

---

### Multivalue Warning #35

**File**: `BAPA.E.NOF.AUDIT.COMP.b`

**Line**: 246

**Table**: HELPTEXT.MENU

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.HELPTEXT.MENU WITH CURR.NO EQ 1 AND DATE.TIME GE 20010100010001 OR DATE.TIME GE {utcDateTime}
```

---

### Multivalue Warning #36

**File**: `BAPA.E.NOF.INW.IHLD.FT.103.b`

**Line**: 121

**Table**: FUNDS.TRANSFER$NAU

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND TRANSACTION.TYPE EQ IT AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND INWARD.PAY.TYPE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TIME
```

---

### Multivalue Warning #37

**File**: `BAPA.E.NOF.INW.IHLD.FT.103.OOT.b`

**Line**: 107

**Table**: FUNDS.TRANSFER$NAU

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ IT AND RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND INWARD.PAY.TYPE EQ MT103 AND LT.EFM.REF EQ "" AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TIME
```

---

### Multivalue Warning #38

**File**: `BAPA.RC.ACCT.STATUS.b`

**Line**: 90

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "VALUE123"
```

---

### Multivalue Warning #39

**File**: `TECH.CHARGE.DAILY.b`

**Line**: 66

**Table**: BAN.TCIB.AFFILIATION

**  Multivalue Fields**: ALLOWED.CUST
  - `ALLOWED.CUST`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT BAN.TCIB.AFFILIATION WITH ALLOWED.CUST EQ VALUE123 AND (STATUS EQ 'AFILIADO' OR STATUS EQ 'REAFILIADO' OR STATUS EQ 'DIFERIDA')
```

---

### Multivalue Warning #40

**File**: `BAN.E.NOF.CHQ.ACCT.INFO.b`

**Line**: 81

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: CREDIT.ACC.NO
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH (CHQ.STATUS EQ DEPOSITED OR CHQ.STATUS EQ CLEARING) AND CREDIT.ACC.NO EQ VALUE123
```

---

### Multivalue Warning #41

**File**: `BAN.E.NOF.INCLG.RECH.OFFICER.b`

**Line**: 140

**Table**: BAN.INWARD.CLEARING

**  Multivalue Fields**: CHQ.ACCOUNT.OFI
  - `CHQ.ACCOUNT.OFI`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ SAMPLE_VALUE AND LOAD.STATUS EQ RECHAZADO AND CHQ.RET.CODE EQ VALUE123 AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT.OFI EQ VALUE123 BY CHQ.ACCOUNT
```

---

### Multivalue Warning #42

**File**: `BAN.E.NOF.INCLG.RECH.OFFICER.b`

**Line**: 152

**Table**: BAN.INWARD.CLEARING

**  Multivalue Fields**: CHQ.ACCOUNT.OFI
  - `CHQ.ACCOUNT.OFI`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ SAMPLE_VALUE AND LOAD.STATUS EQ RECHAZADO AND CHQ.RET.CODE EQ VALUE123 AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT.OFI EQ VALUE123 BY CHQ.ACCOUNTSAMPLE_VALUE AND CHQ.ACCOUNT.CO EQ VALUE123 BY CHQ.ACCOUNT
```

---

### Multivalue Warning #43

**File**: `BAN.E.NOF.INCLG.RECH.TOTAL.b`

**Line**: 113

**Table**: BAN.INWARD.CLEARING

**  Multivalue Fields**: CHQ.ACCOUNT.OFI
  - `CHQ.ACCOUNT.OFI`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ SAMPLE_VALUE AND LOAD.STATUS EQ RECHAZADO AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT EQ VALUE123 AND CHQ.ACCOUNT.CO EQ VALUE123 AND CHQ.RET.CODE EQ VALUE123 AND CHQ.ACCOUNT.OFI EQ VALUE123 AND CHQ.ACCOUNT.ORG EQ VALUE123 BY CHQ.ACCOUNT
```

---

### Multivalue Warning #44

**File**: `BAN.E.NOF.OUTCLG.RET.TOT.b`

**Line**: 160

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: CREDIT.ACC.NO
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ RETURNED AND STATUS.DATE EQ VALUE123 AND BANK.SORT.CODE EQ VALUE123 AND CO.CODE EQ VALUE123 AND LT.CHEQUE.ACC EQ VALUE123 AND CREDIT.ACC.NO EQ VALUE123 AND LT.RET.COD.CC EQ VALUE123 AND LT.RET.FUNDS EQ VALUE123 AND BANK.SORT.CODE NE SAMPLE_VALUE BY BANK.SORT.CODE BY LT.CHEQUE.ACC BY LT.CHQ.ACC.TYP BY LT.RET.COD.CC
```

---

### Multivalue Warning #45

**File**: `BAPA3M.I.VALIDATE.CHECK.BOOK.TYPE.b`

**Line**: 80

**Table**: BAN.PARAMETERS.CHEQUE.BOOK

**  Multivalue Fields**: VALID.REQUEST
  - `VALID.REQUEST`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.PARAMETERS.CHEQUE.BOOK WITH VALID.REQUEST EQ {FIELD(ID.NEW,'.',1)}
```

---

### Multivalue Warning #46

**File**: `BCM.B.CHQ.CERT.STATUS.SELECT.b`

**Line**: 40

**Table**: CHEQUE.REGISTER.SUPPLEMENT

**  Multivalue Fields**: LT.CH.C.VALIDAC
  - `LT.CH.C.VALIDAC`: Type I, Single/Multi: M

**SELECT Statement**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ ISSUED AND LT.CH.C.VALIDAC EQ CERT
```

---

### Multivalue Warning #47

**File**: `BPA.B.OUTCLG.DATAMAE.SELECT.b`

**Line**: 48

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS BY LINKED.APPL.ID
```

---

### Multivalue Warning #48

**File**: `BPA.I.VAL.PLANILLA.b`

**Line**: 189

**Table**: EB.EXTERNAL.USER

**  Multivalue Fields**: CHANNEL.PERMISSION
  - `CHANNEL.PERMISSION`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.EB.EXTERNAL.USER WITH CUSTOMER EQ VALUE123 AND CHANNEL.PERMISSION EQ VALUE123-MASTER
```

---

### Multivalue Warning #49

**File**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET.b`

**Line**: 107

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: AMOUNT, CREDIT.ACC.NO
  - `AMOUNT`: Type D, Single/Multi: M
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND CREDIT.ACC.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdBenAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAmount>}
```

---

### Multivalue Warning #50

**File**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET.b`

**Line**: 119

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: AMOUNT
  - `AMOUNT`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND LT.CHEQUE.ACC EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAmount>}
```

---

### Multivalue Warning #51

**File**: `E.BAN.AC.CASH.GROUPS.b`

**Line**: 169

**Table**: AC.SHARED.ACCOUNT

**  Multivalue Fields**: CP.ID
  - `CP.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AC.SHARED.ACCOUNT WITH CP.ID NE ""
```

---

### Multivalue Warning #52

**File**: `BAPA.A.LEGITIMACION.COFRE.SELECT.b`

**Line**: 27

**Table**: FUNDS.TRANSFER$NAU

**  Multivalue Fields**: INPUTTER
  - `INPUTTER`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT FUNDS.TRANSFER$NAU WITH INPUTTER LIKE ...BAPA.FT.COFRE...
```

---

### Multivalue Warning #53

**File**: `BAN.E.NOF.AA.DEPOSITS.PRINT.b`

**Line**: 248

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: CUSTOMER
  - `CUSTOMER`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ SAMPLE_VALUE
```

---

### Multivalue Warning #54

**File**: `BAN.E.NOF.CUSTOMER.CARDS.b`

**Line**: 78

**Table**: CARD.ISSUE

**  Multivalue Fields**: ACCOUNT
  - `ACCOUNT`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CARD.ISSUE WITH ACCOUNT EQ VALUE123
```

---

### Multivalue Warning #55

**File**: `BAN.E.NOF.TELLER.PRINT.b`

**Line**: 263

**Table**: BAN.REFER.REQUEST

**  Multivalue Fields**: RR.ACCOUNT
  - `RR.ACCOUNT`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.REFER.REQUEST WITH RR.ACCOUNT EQ VALUE123 AND @ID LIKE VALUE123....
```

---

### Multivalue Warning #56

**File**: `BAN.I.ACCHARGE.REQUEST.b`

**Line**: 116

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

---

### Multivalue Warning #57

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Line**: 105

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

---

### Multivalue Warning #58

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Line**: 114

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

---

### Multivalue Warning #59

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Line**: 118

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

---

### Multivalue Warning #60

**File**: `BCM.B.EXTRACT.ACMST.b`

**Line**: 204

**Table**: AA.CHARGE.DETAILS

**  Multivalue Fields**: PAYMENT.DATE
  - `PAYMENT.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT AA.CHARGE.DETAILS WITH @ID LIKE VALUE123... BY-DSND PAYMENT.DATE
```

---

### Multivalue Warning #61

**File**: `BCM.B.EXTRACT.DEALS.LOAD.b`

**Line**: 174

**Table**: AA.PRD.DES.INTEREST

**  Multivalue Fields**: NR.TYPE
  - `NR.TYPE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.PRD.DES.INTEREST WITH NR.TYPE EQ MINIMUM OR NR.TYPE EQ MAXIMUM BY-DSND @ID
```

---

### Multivalue Warning #62

**File**: `BCM.CONV.ROCOL.COL.PLACED.b`

**Line**: 90

**Table**: BAN.BANESCO.COLLATERAL

**  Multivalue Fields**: LOAN.ID
  - `LOAN.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ VALUE123
```

---

### Multivalue Warning #63

**File**: `BPA.ATOM.GL.ACCOUNT.PRE.b`

**Line**: 45

**Table**: RE.STAT.REP.LINE

**  Multivalue Fields**: ASSET1
  - `ASSET1`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.RE.STAT.REP.LINE WITH TYPE EQ DETAIL AND ASSET1 NE '' 
```

---

### Multivalue Warning #64

**File**: `BPA.B.ATOM.GL.ACCOUNT.SELECT.b`

**Line**: 39

**Table**: RE.STAT.REP.LINE

**  Multivalue Fields**: ASSET1, DESC
  - `ASSET1`: Type D, Single/Multi: M
  - `DESC`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT RE.STAT.REP.LINE WITH TYPE EQ DETAIL AND ASSET1 NE '' AND DESC LIKE 8... 
```

---

### Multivalue Warning #65

**File**: `BAPA.V.AC.SIMPLIFI.b`

**Line**: 99

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: CUSTOMER
  - `CUSTOMER`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ VALUE123
```

---

### Multivalue Warning #66

**File**: `BAPA.E.LATAM.ACH.DD.MAN.REVE.b`

**Line**: 33

**Table**: LATAM.ACH.DD.MANDATE$HIS

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.LATAM.ACH.DD.MANDATE$HIS WITH DATE.TIME GE VALUE123 AND RECORD.STATUS EQ REVE AND INPUTTER LK ...LATAM.ACH...
```

---

### Multivalue Warning #67

**File**: `BAPA.ENQ.FT.PAPR.ACH.PAPR.b`

**Line**: 35

**Table**: EB.BAPA.ACH.PRES.CAST

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE VALUE123 AND STATUS EQ PAPR OR STATUS EQ PAFA
```

---

### Multivalue Warning #68

**File**: `BAPA.ENQ.FT.PAPR.ACH.PEND.b`

**Line**: 35

**Table**: EB.BAPA.ACH.PRES.CAST

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE VALUE123 AND STATUS EQ DEPR OR STATUS EQ REOP
```

---

### Multivalue Warning #69

**File**: `BAPA.ENQ.FT.PAPR.ACH.PEVA.b`

**Line**: 35

**Table**: EB.BAPA.ACH.PRES.CAST

**  Multivalue Fields**: DATE.TIME
  - `DATE.TIME`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE VALUE123 AND STATUS EQ PEVA
```

---

### Multivalue Warning #70

**File**: `BAN.B.DEL.LOG.OFFPRINCIPAL.b`

**Line**: 103

**Table**: EB.BPA.LOG.OFFPRINCIPALINT

**  Multivalue Fields**: DATE
  - `DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH DATE LE VALUE123VALUE123VALUE123
```

---

### Multivalue Warning #71

**File**: `BAN.CUADRO.DPF.SELECT.b`

**Line**: 28

**Table**: AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'DEPOSITS'
```

---

### Multivalue Warning #72

**File**: `BAN.CUADRO.SELECT.b`

**Line**: 29

**Table**: AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'LENDING'
```

---

### Multivalue Warning #73

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.b`

**Line**: 120

**Table**: BAN.BANESCO.COLLATERAL

**  Multivalue Fields**: LOAN.ID
  - `LOAN.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ SAMPLE_VALUE
```

---

### Multivalue Warning #74

**File**: `BPA.S.GET.EFFECTIVE.DATE.b`

**Line**: 60

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

---

### Multivalue Warning #75

**File**: `BPA.S.GET.MOBILIZATION.b`

**Line**: 85

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

---

### Multivalue Warning #76

**File**: `BPA.S.GET.ST.ACCT.b`

**Line**: 85

**Table**: AA.ARRANGEMENT

**  Multivalue Fields**: LINKED.APPL.ID
  - `LINKED.APPL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

---

### Multivalue Warning #77

**File**: `BAN.A.AA.UPDATE.AC.SETTLE.b`

**Line**: 166

**Table**: BAN.PENDING.BILL.AC

**  Multivalue Fields**: ARR.ACCT.NO
  - `ARR.ACCT.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.PENDING.BILL.AC WITH ARR.ACCT.NO EQ VALUE123
```

---

### Multivalue Warning #78

**File**: `BPA.B.MRTG.PREF.DISB.b`

**Line**: 41

**Table**: BAN.BANESCO.COLLATERAL

**  Multivalue Fields**: LOAN.ID
  - `LOAN.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ VALUE123
```

---

### Multivalue Warning #79

**File**: `BPA.E.AL.ENDORSEMENT.POLICIES.b`

**Line**: 115

**Table**: BAN.BANESCO.COLLATERAL

**  Multivalue Fields**: POLICY.CCY, POLICY, MAT.DATE, INSURE.ID
  - `POLICY.CCY`: Type D, Single/Multi: M
  - `POLICY`: Type D, Single/Multi: M
  - `MAT.DATE`: Type D, Single/Multi: M
  - `INSURE.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH MAT.DATE LE VALUE123 AND MAT.DATE GE VALUE123 AND POLICY EQ VALUE123 AND INSURE.ID EQ VALUE123 AND POLICY.CCY EQ VALUE123
```

---

### Multivalue Warning #80

**File**: `BPA.V.PARTICIPANTS.b`

**Line**: 160

**Table**: CUSTOMER

**  Multivalue Fields**: LEGAL.ID
  - `LEGAL.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CUSTOMER WITH LEGAL.ID EQ VALUE123
```

---

### Multivalue Warning #81

**File**: `BAN.B.AVRG.BALANCES.b`

**Line**: 117

**Table**: AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ DEPOSITS
```

---

### Multivalue Warning #82

**File**: `BAN.E.NOF.ACCT.BALANCES.DETAILS.b`

**Line**: 177

**Table**: CHEQUE.COLLECTION

**  Multivalue Fields**: CREDIT.ACC.NO
  - `CREDIT.ACC.NO`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ VALUE123 AND CHQ.STATUS NE CLEARED AND CHQ.STATUS NE RETURNED
```

---

### Multivalue Warning #83

**File**: `BACM3M.B.ACCT.TXN.DET.EXTRACT.b`

**Line**: 135

**Table**: RE.STAT.LINE.CONT

**  Multivalue Fields**: ASST.CONSOL.KEY
  - `ASST.CONSOL.KEY`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.RE.STAT.LINE.CONT WITH ASST.CONSOL.KEY EQ VALUE123
```

---

### Multivalue Warning #84

**File**: `BAN.B.ACCOUNTS.AUTM.STATUS.SELECT.b`

**Line**: 46

**Table**: AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS
```

---

### Multivalue Warning #85

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Line**: 121

**Table**: CHEQUE.TYPE

**  Multivalue Fields**: CATEGORY
  - `CATEGORY`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123
```

---

### Multivalue Warning #86

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Line**: 190

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

---

### Multivalue Warning #87

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Line**: 126

**Table**: CHEQUE.TYPE

**  Multivalue Fields**: CATEGORY
  - `CATEGORY`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123
```

---

### Multivalue Warning #88

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Line**: 195

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

---

### Multivalue Warning #89

**File**: `BAN.E.NOF.PS.CHQ.SUSP.b`

**Line**: 133

**Table**: PAYMENT.STOP

**  Multivalue Fields**: STOP.DATE
  - `STOP.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE VALUE123 AND STOP.DATE LE VALUE123
```

---

### Multivalue Warning #90

**File**: `BAN.E.NOF.PS.CHQ.SUSP.b`

**Line**: 133

**Table**: PAYMENT.STOP

**  Multivalue Fields**: STOP.DATE
  - `STOP.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE VALUE123
```

---

### Multivalue Warning #91

**File**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Line**: 141

**Table**: PAYMENT.STOP

**  Multivalue Fields**: STOP.DATE
  - `STOP.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE VALUE123 AND STOP.DATE LE VALUE123
```

---

### Multivalue Warning #92

**File**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Line**: 141

**Table**: PAYMENT.STOP

**  Multivalue Fields**: STOP.DATE
  - `STOP.DATE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE VALUE123
```

---

### Multivalue Warning #93

**File**: `BAN.E.NOF.RECEIVED.DRAFT.b`

**Line**: 75

**Table**: STOCK.ENTRY

**  Multivalue Fields**: CHEQUE.TYPE
  - `CHEQUE.TYPE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.STOCK.ENTRY WITH CHEQUE.TYPE EQ VALUE123 AND LT.STATUS.DRAFT EQ REQ AND IN.OUT.DATE EQ VALUE123
```

---

### Multivalue Warning #94

**File**: `BAPA.B.PROCES.RAING.ACCT.b`

**Line**: 105

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT ACCOUNT WITH ALT.ACCT.ID EQ TF
```

---

### Multivalue Warning #95

**File**: `BPA.B.OD.DAYS.END.SELECT.b`

**Line**: 79

**Table**: ACCOUNT.OVERDRAWN

**  Multivalue Fields**: MOVED.NARR
  - `MOVED.NARR`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT ACCOUNT.OVERDRAWN WITH MOVED.NARR EQ CLEARED
```

---

### Multivalue Warning #96

**File**: `BPA.B.OD.DAYS.START.SELECT.b`

**Line**: 74

**Table**: ACCOUNT.OVERDRAWN

**  Multivalue Fields**: MOVED.NARR
  - `MOVED.NARR`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT ACCOUNT.OVERDRAWN WITH MOVED.NARR NE CLEARED
```

---

### Multivalue Warning #97

**File**: `BPA.CR.UPD.ACCT.OPE.b`

**Line**: 116

**Table**: BAN.PARAM.ACCOUNT

**  Multivalue Fields**: PG.ACTIVITY, PRODUCT.GROUP
  - `PG.ACTIVITY`: Type D, Single/Multi: M
  - `PRODUCT.GROUP`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.PARAM.ACCOUNT WITH PRODUCT.GROUP EQ VALUE123 AND PG.ACTIVITY EQ ACCOUNTS-ESTADO-CTAOPERATIVA
```

---

### Multivalue Warning #98

**File**: `BPA.E.NOF.REQUEST.CHECK.BOOK.b`

**Line**: 76

**Table**: CHEQUE.TYPE

**  Multivalue Fields**: CATEGORY
  - `CATEGORY`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

---

### Multivalue Warning #99

**File**: `BPA.E.NOF.REQUEST.CHECK.BOOK.b`

**Line**: 130

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

---

### Multivalue Warning #100

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Line**: 89

**Table**: CHEQUE.TYPE

**  Multivalue Fields**: CATEGORY
  - `CATEGORY`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

---

### Multivalue Warning #101

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Line**: 197

**Table**: ACCOUNT

**  Multivalue Fields**: ALT.ACCT.ID
  - `ALT.ACCT.ID`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

---

### Multivalue Warning #102

**File**: `BRD.I.VALIDATE.CHECK.BOOK.TYPE.b`

**Line**: 79

**Table**: BAN.PARAMETERS.CHEQUE.BOOK

**  Multivalue Fields**: VALID.REQUEST
  - `VALID.REQUEST`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT F.BAN.PARAMETERS.CHEQUE.BOOK WITH VALID.REQUEST EQ {FIELD(ID.NEW,'.',1)}
```

---

### Multivalue Warning #103

**File**: `BANV.B.CUADRO.DPF.SELECT.b`

**Line**: 28

**Table**: FBCW.AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT FBCW.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'DEPOSITS'
```

---

### Multivalue Warning #104

**File**: `BANV.B.CUADRO.SELECT.b`

**Line**: 25

**Table**: FBCW.AA.CUSTOMER.ARRANGEMENT

**  Multivalue Fields**: PRODUCT.LINE
  - `PRODUCT.LINE`: Type D, Single/Multi: M

**SELECT Statement**:
```
SELECT FBCW.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'LENDING'
```

---

## Detailed Analysis

Total: 822 SELECT statements

### R21_SOURCE

Found 822 SELECT statements

#### SELECT #1 - Line 33

**File**: `BAPA.B.CONS.ADD.INFO.SELECT.b`

**Routine**: `BAPA.B.CONS.ADD.INFO.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.L.TEMP.CONST
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.TEMP.CONST
```

**Table**: `EB.BAPA.L.TEMP.CONST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_TEMP_CONST
```

---

#### SELECT #2 - Line 35

**File**: `BAPA.B.CONS.FT.TXN.SELECT.b`

**Routine**: `BAPA.B.CONS.FT.TXN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.L.TEMP.CONST WITH STATUS.FLAG EQ STATUS1
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.TEMP.CONST WITH STATUS.FLAG EQ STATUS1
```

**Table**: `EB.BAPA.L.TEMP.CONST`

**Fields** (1):
-  `STATUS.FLAG`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_TEMP_CONST
WHERE STATUS_FLAG = 'STATUS1'
```

---

#### SELECT #3 - Line 31

**File**: `BAPA.B.CONS.SCHDUL.UP.SELECT.b`

**Routine**: `BAPA.B.CONS.SCHDUL.UP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.L.TEMP.CONST
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.TEMP.CONST
```

**Table**: `EB.BAPA.L.TEMP.CONST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_TEMP_CONST
```

---

#### SELECT #4 - Line 44

**File**: `BAN.AA.OFS.MAKER.SELECT.b`

**Routine**: `BAN.AA.OFS.MAKER.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FBNK.AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS LENDING AND ARR.STATUS NE PENDING.CLOSURE REVERSED CLOSE
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS LENDING AND ARR.STATUS NE PENDING.CLOSURE REVERSED CLOSE
```

**Table**: `FBNK.AA.ARRANGEMENT`

**Fields** (2):
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'AA.ARRANGEMENT'

**Translated SQL**:
```sql
SELECT *
FROM FBNK_AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ARR_STATUS != 'PENDING.CLOSURE'
```

---

#### SELECT #5 - Line 43

**File**: `BSAP.COMPARE.AIA.ECB.POST.b`

**Routine**: `BSAP.COMPARE.AIA.ECB.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACC.DIFF.BP
```

**SIMULATED AT RUNTIME**:
```
SELECT ACC.DIFF.BP
```

**Table**: `ACC.DIFF.BP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'ACC.DIFF.BP' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACC.DIFF.BP

**Translated SQL**:
```sql
SELECT *
FROM ACC_DIFF_BP
```

---

#### SELECT #6 - Line 61

**File**: `BSAP.COMPARE.AIA.ECB.POST.b`

**Routine**: `BSAP.COMPARE.AIA.ECB.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACC.DIFFDETAILS.BP
```

**SIMULATED AT RUNTIME**:
```
SELECT ACC.DIFFDETAILS.BP
```

**Table**: `ACC.DIFFDETAILS.BP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'ACC.DIFFDETAILS.BP' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACC.DIFFDETAILS.BP

**Translated SQL**:
```sql
SELECT *
FROM ACC_DIFFDETAILS_BP
```

---

#### SELECT #7 - Line 16

**File**: `BSAP.COMPARE.AIA.ECB.SELECT.b`

**Routine**: `BSAP.COMPARE.AIA.ECB.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ "LENDING" OR PRODUCT.LINE EQ "DEPOSITS" OR PRODUCT.LINE EQ "ACCOUNTS"
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ "LENDING" OR PRODUCT.LINE EQ "DEPOSITS" OR PRODUCT.LINE EQ "ACCOUNTS"
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING'
```

---

#### SELECT #8 - Line 368

**File**: `PACS.AC.DATA.EXTRACT.EXEC.b`

**Routine**: `PACS.AC.DATA.EXTRACT.EXEC` (Unknown)

**Variable**: `SEL.CMD1`

**AS PER CODE**:
```
SELECT F.ENTRY.HOLD
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ENTRY.HOLD
```

**Table**: `ENTRY.HOLD`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ENTRY_HOLD
```

---

#### SELECT #9 - Line 798

**File**: `PACS.AC.DATA.EXTRACT.EXEC.b`

**Routine**: `PACS.AC.DATA.EXTRACT.EXEC` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SSELECT F.EB.SYSTEM.SUMMARY
```

**SIMULATED AT RUNTIME**:
```
SSELECT F.EB.SYSTEM.SUMMARY
```

**Table**: `EB.SYSTEM.SUMMARY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_SYSTEM_SUMMARY
ORDER BY RECID ASC
```

---

#### SELECT #10 - Line 369

**File**: `PACS.AC.DATA.EXTRACT.SUB.b`

**Routine**: `PACS.AC.DATA.EXTRACT.SUB` (Unknown)

**Variable**: `SEL.CMD1`

**AS PER CODE**:
```
SELECT F.ENTRY.HOLD
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ENTRY.HOLD
```

**Table**: `ENTRY.HOLD`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ENTRY_HOLD
```

---

#### SELECT #11 - Line 798

**File**: `PACS.AC.DATA.EXTRACT.SUB.b`

**Routine**: `PACS.AC.DATA.EXTRACT.SUB` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SSELECT F.EB.SYSTEM.SUMMARY
```

**SIMULATED AT RUNTIME**:
```
SSELECT F.EB.SYSTEM.SUMMARY
```

**Table**: `EB.SYSTEM.SUMMARY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_SYSTEM_SUMMARY
ORDER BY RECID ASC
```

---

#### SELECT #12 - Line 148

**File**: `BAPA.I.UPT.BAL.STMT.PRINT.b`

**Routine**: `BAPA.I.UPT.BAL.STMT.PRINT` (Unknown)

**Variable**: `STMT.ENTRY`

**AS PER CODE**:
```
SELECT FBNK.STMT.ENTRY WITH ACCOUNT.NUMBER EQ {FIELD(Line,';',1)} AND (BOOKING.DATE GE 20230401 AND BOOKING.DATE LE 20230430)
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.STMT.ENTRY WITH ACCOUNT.NUMBER EQ {FIELD(Line,';',1)} AND (BOOKING.DATE GE 20230401 AND BOOKING.DATE LE 20230430)
```

**Table**: `FBNK.STMT.ENTRY`

**Fields** (2):
-  `BOOKING.DATE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'STMT.ENTRY'
-   Unresolved variables: FIELD(Line,';',1)

**Translated SQL**:
```sql
SELECT *
FROM FBNK_STMT_ENTRY
WHERE ACCOUNT_NUMBER = '{FIELD(Line,' AND BOOKING_DATE <= '20230430)'
```

---

#### SELECT #13 - Line 136

**File**: `BAPA.M.UPDATE.ACCT.BAL.ACT.b`

**Routine**: `BAPA.M.UPDATE.ACCT.BAL.ACT` (Unknown)

**Variable**: `STMT.ENTRY`

**AS PER CODE**:
```
SELECT FBNK.STMT.ENTRY WITH ACCOUNT.NUMBER EQ {Y.ACCT.ID} AND (PROCESSING.DATE GE {v.dateIni} AND PROCESSING.DATE LE {v.dateFin})
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.STMT.ENTRY WITH ACCOUNT.NUMBER EQ 1000389249 AND (PROCESSING.DATE GE {v.dateIni} AND PROCESSING.DATE LE {v.dateFin})
```

**Table**: `FBNK.STMT.ENTRY`

**Fields** (2):
-  `PROCESSING.DATE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'STMT.ENTRY'

**Translated SQL**:
```sql
SELECT *
FROM FBNK_STMT_ENTRY
WHERE ACCOUNT_NUMBER = '1000389249' AND PROCESSING_DATE <= '{v.dateFin})'
```

---

#### SELECT #14 - Line 63

**File**: `BAPA.V.GET.BAL.ACC.DIFF.b`

**Routine**: `BAPA.V.GET.BAL.ACC.DIFF` (VERSION (inferred))

**Variable**: `STMT.ARR`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH PRODUCT.LINE EQ 'ACCOUNTS'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH PRODUCT.LINE EQ 'ACCOUNTS'
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS'
```

---

#### SELECT #15 - Line 124

**File**: `BAPA.V.GET.STMT.ENTRY.PRINT.b`

**Routine**: `BAPA.V.GET.STMT.ENTRY.PRINT` (VERSION (inferred))

**Variable**: `STMT.ENTRY`

**AS PER CODE**:
```
SELECT FBNK.STMT.ENTRY WITH ACCOUNT.NUMBER EQ {FIELD(Line,';',1)} AND (BOOKING.DATE GE 20230401 AND BOOKING.DATE LE 20230430)
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.STMT.ENTRY WITH ACCOUNT.NUMBER EQ {FIELD(Line,';',1)} AND (BOOKING.DATE GE 20230401 AND BOOKING.DATE LE 20230430)
```

**Table**: `FBNK.STMT.ENTRY`

**Fields** (2):
-  `BOOKING.DATE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'STMT.ENTRY'
-   Unresolved variables: FIELD(Line,';',1)

**Translated SQL**:
```sql
SELECT *
FROM FBNK_STMT_ENTRY
WHERE ACCOUNT_NUMBER = '{FIELD(Line,' AND BOOKING_DATE <= '20230430)'
```

---

#### SELECT #16 - Line 40

**File**: `BAPA.V.GET.DIFF.BAL.STMT.ACC.SELECT.b`

**Routine**: `BAPA.V.GET.DIFF.BAL.STMT.ACC.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FBNK.AA.ARRANGEMENT WITH PRODUCT.LINE EQ '{V.PR.LINE}' AND ARR.STATUS EQ '{V.ARR.STATUS}'
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.AA.ARRANGEMENT WITH PRODUCT.LINE EQ 'ACCOUNTS' AND ARR.STATUS EQ 'AUTH'
```

**Table**: `FBNK.AA.ARRANGEMENT`

**Fields** (2):
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'AA.ARRANGEMENT'

**Translated SQL**:
```sql
SELECT *
FROM FBNK_AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ARR_STATUS = 'AUTH'
```

---

#### SELECT #17 - Line 70

**File**: `BAN.E.NOF.LATAM.ACH.b`

**Routine**: `BAN.E.NOF.LATAM.ACH` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.BATCH
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.BATCH
```

**Table**: `LATAM.ACH.BATCH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_BATCH
```

---

#### SELECT #18 - Line 42

**File**: `BPA.B.REPORT.ACH.SELECT.b`

**Routine**: `BPA.B.REPORT.ACH.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LATAM.ACH.ENTRIES WITH @ID LIKE ...{Y.ID.DATE}... AND MSG.TYPE EQ OUTWARD AND STATUS EQ CLEARED
```

**SIMULATED AT RUNTIME**:
```
SELECT LATAM.ACH.ENTRIES WITH @ID LIKE ...VALUE123... AND MSG.TYPE EQ OUTWARD AND STATUS EQ CLEARED
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (3):
-  `STATUS`  Type: D
-  `MSG.TYPE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID.DATE

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID LIKE '%VALUE123%' AND MSG_TYPE = 'OUTWARD' AND STATUS = 'CLEARED'
```

---

#### SELECT #19 - Line 75

**File**: `LATAM.ACH.AML.RESPONSE.UPDATE.SELECT.b`

**Routine**: `LATAM.ACH.AML.RESPONSE.UPDATE.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getAmlResponsePath()}
```

**SIMULATED AT RUNTIME**:
```
SELECT AML.RESPONSE.PATH
```

**Table**: `AML.RESPONSE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AML.RESPONSE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AML.RESPONSE.PATH

**Translated SQL**:
```sql
SELECT *
FROM AML_RESPONSE_PATH
```

---

#### SELECT #20 - Line 45

**File**: `LATAM.ACH.APPROVE.AA.ACTIVITY.SELECT.b`

**Routine**: `LATAM.ACH.APPROVE.AA.ACTIVITY.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getAchFnActivity()} WITH TXN.CONTRACT.ID LIKE ...ACH...
```

**SIMULATED AT RUNTIME**:
```
SELECT ACH.FN.ACTIVITY WITH TXN.CONTRACT.ID LIKE ...ACH...
```

**Table**: `ACH.FN.ACTIVITY`

**Fields** (1):
-  `TXN.CONTRACT.ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'ACH.FN.ACTIVITY' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACH.FN.ACTIVITY

**Translated SQL**:
```sql
SELECT *
FROM ACH_FN_ACTIVITY
WHERE TXN_CONTRACT_ID LIKE '%ACH%'
```

---

#### SELECT #21 - Line 60

**File**: `LATAM.ACH.ARCHIVE.EXCEPTION.SELECT.b`

**Routine**: `LATAM.ACH.ARCHIVE.EXCEPTION.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getAchFnException()} WITH STATUS NE '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT ACH.FN.EXCEPTION WITH STATUS NE '' 
```

**Table**: `ACH.FN.EXCEPTION`

**Fields** (1):
-  `STATUS`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'ACH.FN.EXCEPTION' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACH.FN.EXCEPTION

**Translated SQL**:
```sql
SELECT *
FROM ACH_FN_EXCEPTION
```

---

#### SELECT #22 - Line 83

**File**: `LATAM.ACH.BLD.SERVICE.STATUS.b`

**Routine**: `LATAM.ACH.BLD.SERVICE.STATUS` (Unknown)

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.TSA.SERVICE WITH @ID LIKE {R.COMP<ST.CompanyCreation.Company.EbComMnemonic>}/LATAM.ACH... AND @ID UNLIKE ....ISO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TSA.SERVICE WITH @ID LIKE {R.COMP<ST.CompanyCreation.Company.EbComMnemonic>}/LATAM.ACH... AND @ID UNLIKE ....ISO
```

**Table**: `TSA.SERVICE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM TSA_SERVICE
WHERE ID LIKE '{R.COMP<ST.CompanyCreation.Company.EbComMnemonic>}/LATAM.ACH%' AND ID NOT LIKE '%.ISO'
```

---

#### SELECT #23 - Line 94

**File**: `LATAM.ACH.CAP.POPULATE.CANC.REVE.b`

**Routine**: `LATAM.ACH.CAP.POPULATE.CANC.REVE` (Unknown)

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE WITH @ID LIKE ACH{JULIAN[3,6]}... AND ORIG.US.ACH.ENTRY EQ {OrigUsAchEntry}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE WITH @ID LIKE ACH{JULIAN[3,6]}... AND ORIG.US.ACH.ENTRY EQ {OrigUsAchEntry}
```

**Table**: `LATAM.ACH.CAPTURE`

**Fields** (2):
-  `@ID`  Type: D
-  `ORIG.US.ACH.ENTRY`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ORIG.US.ACH.ENTRY' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE
WHERE ID LIKE 'ACH{JULIAN[3,6]}%' AND ORIG_US_ACH_ENTRY = '{OrigUsAchEntry}'
```

---

#### SELECT #24 - Line 109

**File**: `LATAM.ACH.CAP.POPULATE.CANC.REVE.b`

**Routine**: `LATAM.ACH.CAP.POPULATE.CANC.REVE` (Unknown)

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID LIKE ...{TODAY[3,6]}... AND MSG.TYPE EQ INWARD AND STATUS EQ RETURNED AND ORIG.TRACE.NO EQ {FIELDS(Y.ORG.ACH.ID,".",3)}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID LIKE ...{TODAY[3,6]}... AND MSG.TYPE EQ INWARD AND STATUS EQ RETURNED AND ORIG.TRACE.NO EQ {FIELDS(Y.ORG.ACH.ID,".",3)}
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (4):
-  `ORIG.TRACE.NO`  Type: D
-  `STATUS`  Type: D
-  `MSG.TYPE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FIELDS(Y.ORG.ACH.ID,".",3)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID LIKE '%{TODAY[3,6]}%' AND MSG_TYPE = 'INWARD' AND STATUS = 'RETURNED' AND ORIG_TRACE_NO = '{FIELDS(Y.ORG.ACH.ID,'
```

---

#### SELECT #25 - Line 138

**File**: `LATAM.ACH.CAP.POPULATE.CANC.REVE.b`

**Routine**: `LATAM.ACH.CAP.POPULATE.CANC.REVE` (Unknown)

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ADDENDA WITH @ID LIKE {Y.ORG.ACH.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ADDENDA WITH @ID LIKE VALUE123...
```

**Table**: `LATAM.ACH.ADDENDA`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ORG.ACH.ID

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ADDENDA
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #26 - Line 50

**File**: `LATAM.ACH.CAPTURE.ARCHIVE.SELECT.b`

**Routine**: `LATAM.ACH.CAPTURE.ARCHIVE.SELECT` (BATCH (inferred))

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getFnAchCapture()} WITH STATUS EQ COMPLETE AND MATURITY.DATE LT {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACH.CAPTURE WITH STATUS EQ COMPLETE AND MATURITY.DATE LT TODAY
```

**Table**: `ACH.CAPTURE`

**Fields** (2):
-  `STATUS`  Type: Unknown
-  `MATURITY.DATE`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'ACH.CAPTURE' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACH.CAPTURE

**Translated SQL**:
```sql
SELECT *
FROM ACH_CAPTURE
WHERE STATUS = 'COMPLETE' AND MATURITY_DATE < 'TODAY'
```

---

#### SELECT #27 - Line 69

**File**: `LATAM.ACH.E.CONV.GET.SVC.DESC.b`

**Routine**: `LATAM.ACH.E.CONV.GET.SVC.DESC` (ENQUIRY (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH OTHER.INFO EQ {SvcCode}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH OTHER.INFO EQ {SvcCode}
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `OTHER.INFO`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE OTHER_INFO = '{SvcCode}'
```

---

#### SELECT #28 - Line 151

**File**: `LATAM.ACH.E.GET.REPORTS.DETAIL.b`

**Routine**: `LATAM.ACH.E.GET.REPORTS.DETAIL` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND LOAD.DATE EQ {TODAY.VAL} AND MSG.TYPE EQ OUTWARD AND TRANSACTION.CODE EQ 21 26 31 36 41 46 51 56 AND ENTRY.CLASS.CODE NE COR BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND LOAD.DATE EQ TODAY AND MSG.TYPE EQ OUTWARD AND TRANSACTION.CODE EQ 21 26 31 36 41 46 51 56 AND ENTRY.CLASS.CODE NE COR BY @ID
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (5):
-  `LOAD.DATE`  Type: D
-  `ENTRY.CLASS.CODE`  Type: D
-  `TRANSACTION.CODE`  Type: D
-  `MSG.TYPE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID NOT LIKE 'T%' AND ID NOT LIKE 'R%' AND LOAD_DATE = 'TODAY' AND MSG_TYPE = 'OUTWARD' AND TRANSACTION_CODE = '21' AND ENTRY_CLASS_CODE != 'COR'
ORDER BY ID ASC
```

---

#### SELECT #29 - Line 154

**File**: `LATAM.ACH.E.IAT.REPORTS.DETAIL.b`

**Routine**: `LATAM.ACH.E.IAT.REPORTS.DETAIL` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND LOAD.DATE EQ {TODAY.VAL} AND MSG.TYPE EQ OUTWARD AND ENTRY.CLASS.CODE EQ IAT BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND LOAD.DATE EQ TODAY AND MSG.TYPE EQ OUTWARD AND ENTRY.CLASS.CODE EQ IAT BY @ID
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (4):
-  `LOAD.DATE`  Type: D
-  `ENTRY.CLASS.CODE`  Type: D
-  `MSG.TYPE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID NOT LIKE 'T%' AND ID NOT LIKE 'R%' AND LOAD_DATE = 'TODAY' AND MSG_TYPE = 'OUTWARD' AND ENTRY_CLASS_CODE = 'IAT'
ORDER BY ID ASC
```

---

#### SELECT #30 - Line 91

**File**: `LATAM.ACH.E.NOF.ADHOC.CAPTURE.b`

**Routine**: `LATAM.ACH.E.NOF.ADHOC.CAPTURE` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {SEL.VALUES<CORPORATE.ID.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {SEL.VALUES<CORPORATE.ID.POS>}
```

**Table**: `LATAM.ACH.CORPORATE.INFO`

**Fields** (1):
-  `CORPORATE.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CORPORATE.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CORPORATE_INFO
WHERE CORPORATE_ID = '{SEL.VALUES<CORPORATE.ID.POS>}'
```

---

#### SELECT #31 - Line 136

**File**: `LATAM.ACH.E.NOF.ADHOC.CAPTURE.b`

**Routine**: `LATAM.ACH.E.NOF.ADHOC.CAPTURE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}
```

**Table**: `LATAM.ACH.CORPORATE.INFO`

**Fields** (1):
-  `CORPORATE.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CORPORATE.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CORPORATE_INFO
WHERE CORPORATE_ID = '{R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}'
```

---

#### SELECT #32 - Line 107

**File**: `LATAM.ACH.E.NOF.ADHOC.SEC.CODE.b`

**Routine**: `LATAM.ACH.E.NOF.ADHOC.SEC.CODE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CORPORATE.INFO WITH CORPORATE.ID EQ {R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}
```

**Table**: `LATAM.ACH.CORPORATE.INFO`

**Fields** (1):
-  `CORPORATE.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CORPORATE.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CORPORATE_INFO
WHERE CORPORATE_ID = '{R.LATACH.PARAM<LATAMACH.UtilityLat.LatamAchParameter.LatAchParOurRtnNumber>}'
```

---

#### SELECT #33 - Line 75

**File**: `LATAM.ACH.E.NOF.BANK.b`

**Routine**: `LATAM.ACH.E.NOF.BANK` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.BANK WITH RELAT.TYPE EQ "INSTF" AND OPENING.DATE LE {ValueDate} AND BANK.CODE EQ {AchFormat} AND (END.DATE EQ "" OR END.DATE GT {ValueDate}) BY DESCRIPTION
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.BANK WITH RELAT.TYPE EQ "INSTF" AND OPENING.DATE LE {ValueDate} AND BANK.CODE EQ {AchFormat} AND (END.DATE EQ "" OR END.DATE GT {ValueDate}) BY DESCRIPTION
```

**Table**: `LATAM.ACH.BANK`

**Fields** (5):
-  `RELAT.TYPE`  Type: D
-  `END.DATE`  Type: D
-  `OPENING.DATE`  Type: D
-  `BANK.CODE`  Type: D
-  `DESCRIPTION`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_BANK
WHERE RELAT_TYPE = 'INSTF' AND OPENING_DATE <= '{ValueDate}' AND BANK_CODE = '{AchFormat}'
ORDER BY DESCRIPTION ASC
```

---

#### SELECT #34 - Line 67

**File**: `LATAM.ACH.E.NOF.BANK.EMP.b`

**Routine**: `LATAM.ACH.E.NOF.BANK.EMP` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.BANK WITH RELAT.TYPE EQ "EMP" AND OPENING.DATE LE {ValueDate} AND (END.DATE EQ "" OR END.DATE GT {ValueDate}) BY DESCRIPTION
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.BANK WITH RELAT.TYPE EQ "EMP" AND OPENING.DATE LE {ValueDate} AND (END.DATE EQ "" OR END.DATE GT {ValueDate}) BY DESCRIPTION
```

**Table**: `LATAM.ACH.BANK`

**Fields** (4):
-  `DESCRIPTION`  Type: D
-  `RELAT.TYPE`  Type: D
-  `END.DATE`  Type: D
-  `OPENING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_BANK
WHERE RELAT_TYPE = 'EMP' AND OPENING_DATE <= '{ValueDate}'
ORDER BY DESCRIPTION ASC
```

---

#### SELECT #35 - Line 77

**File**: `LATAM.ACH.E.NOF.BENEF.CAPTURE.b`

**Routine**: `LATAM.ACH.E.NOF.BENEF.CAPTURE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BENEFICIARY WITH LT.CCY EQ {Y.MONEDA} AND OWNING.CUSTOMER EQ {Y.CLIENTE} AND TRANSACTION.TYPE LIKE "BC..." 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BENEFICIARY WITH LT.CCY EQ VALUE123 AND OWNING.CUSTOMER EQ VALUE123 AND TRANSACTION.TYPE LIKE "BC..." 
```

**Table**: `BENEFICIARY`

**Fields** (3):
-  `OWNING.CUSTOMER`  Type: D
-  `LT.CCY`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,7>`)
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.CCY - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.MONEDA, Y.CLIENTE

**Translated SQL**:
```sql
SELECT *
FROM BENEFICIARY
WHERE LT_CCY = 'VALUE123' AND OWNING_CUSTOMER = 'VALUE123' AND TRANSACTION_TYPE LIKE 'BC%'
```

---

#### SELECT #36 - Line 107

**File**: `LATAM.ACH.E.NOF.REJ.EXCEPTION.INAU.b`

**Routine**: `LATAM.ACH.E.NOF.REJ.EXCEPTION.INAU` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH STATUS EQ 'REJECTED' AND ACH.RET.CODE EQ '' AND MSG.TYPE EQ 'INWARD' AND ROUTING.CUSTOMER EQ 'OUR.BANK' AND ENTRY.CLASS.CODE NE 'COR' @ID UL T... AND INDIVIDUAL.ID.NO EQ {SEL.VALUES<IND.TYPE.POS>} AND DFI.ACCOUNT.NO EQ {SEL.VALUES<ACC.POS>} AND VALUE.DATE EQ {SEL.VALU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH STATUS EQ 'REJECTED' AND ACH.RET.CODE EQ '' AND MSG.TYPE EQ 'INWARD' AND ROUTING.CUSTOMER EQ 'OUR.BANK' AND ENTRY.CLASS.CODE NE 'COR' @ID UL T... AND INDIVIDUAL.ID.NO EQ {SEL.VALUES<IND.TYPE.POS>} AND DFI.ACCOUNT.NO EQ {SEL.VALUES<ACC.POS>} AND VALUE.DATE EQ {SEL.VALU
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (9):
-  `STATUS`  Type: D
-  `ENTRY.CLASS.CODE`  Type: D
-  `DFI.ACCOUNT.NO`  Type: D
-  `VALUE.DATE`  Type: D
-  `INDIVIDUAL.ID.NO`  Type: D
-  `ACH.RET.CODE`  Type: D
-  `MSG.TYPE`  Type: D
-  `BATCH.ORIGINATOR`  Type: D
-  `ROUTING.CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE STATUS = 'REJECTED' AND MSG_TYPE = 'INWARD' AND ROUTING_CUSTOMER = 'OUR.BANK' AND ENTRY_CLASS_CODE != 'COR' AND INDIVIDUAL_ID_NO = '{SEL.VALUES<IND.TYPE.POS>}' AND DFI_ACCOUNT_NO = '{SEL.VALUES<ACC.POS>}' AND VALUE_DATE = '{SEL.VALUES<SETT.POS>}' AND BATCH_ORIGINATOR = '{SEL.VALUES<BAT.POS>}'
```

---

#### SELECT #37 - Line 107

**File**: `LATAM.ACH.E.NOF.RETURN.AUTH.b`

**Routine**: `LATAM.ACH.E.NOF.RETURN.AUTH` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.BATCH WITH STATUS EQ 'EXCEPTION' AND FILE.TYPE EQ 'OUTWARD' AND VALUE.DATE EQ {SEL.VALUES<VAL.DATE.POS>} AND SVC.CLASS.CODE EQ {SEL.VALUES<SVC.POS>} AND COMPANY.ID EQ {SEL.VALUES<COMP.ID.POS>} AND COMPANY.NAME EQ {SEL.VALUES<COMP.NAME.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.BATCH WITH STATUS EQ 'EXCEPTION' AND FILE.TYPE EQ 'OUTWARD' AND VALUE.DATE EQ {SEL.VALUES<VAL.DATE.POS>} AND SVC.CLASS.CODE EQ {SEL.VALUES<SVC.POS>} AND COMPANY.ID EQ {SEL.VALUES<COMP.ID.POS>} AND COMPANY.NAME EQ {SEL.VALUES<COMP.NAME.POS>}
```

**Table**: `LATAM.ACH.BATCH`

**Fields** (6):
-  `STATUS`  Type: D
-  `COMPANY.NAME`  Type: D
-  `SVC.CLASS.CODE`  Type: D
-  `VALUE.DATE`  Type: D
-  `COMPANY.ID`  Type: D
-  `FILE.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_BATCH
WHERE STATUS = 'EXCEPTION' AND FILE_TYPE = 'OUTWARD' AND VALUE_DATE = '{SEL.VALUES<VAL.DATE.POS>}' AND SVC_CLASS_CODE = '{SEL.VALUES<SVC.POS>}' AND COMPANY_ID = '{SEL.VALUES<COMP.ID.POS>}' AND COMPANY_NAME = '{SEL.VALUES<COMP.NAME.POS>}'
```

---

#### SELECT #38 - Line 109

**File**: `LATAM.ACH.E.NOF.RETURN.DR.CR.AUTH.b`

**Routine**: `LATAM.ACH.E.NOF.RETURN.DR.CR.AUTH` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH STATUS EQ 'EXCEPTION' AND MSG.TYPE EQ 'INWARD' AND ROUTING.CUSTOMER EQ 'OUR.BANK' AND ENTRY.CLASS.CODE NE 'COR' AND @ID UL T... AND INDIVIDUAL.ID.NO EQ {SEL.VALUES<INDIVIDUAL.ID.NO.POS>} AND DFI.ACCOUNT.NO EQ {SEL.VALUES<DFI.ACCOUNT.NO.POS>} AND AMOUNT EQ {SEL.VALUES<
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH STATUS EQ 'EXCEPTION' AND MSG.TYPE EQ 'INWARD' AND ROUTING.CUSTOMER EQ 'OUR.BANK' AND ENTRY.CLASS.CODE NE 'COR' AND @ID UL T... AND INDIVIDUAL.ID.NO EQ {SEL.VALUES<INDIVIDUAL.ID.NO.POS>} AND DFI.ACCOUNT.NO EQ {SEL.VALUES<DFI.ACCOUNT.NO.POS>} AND AMOUNT EQ {SEL.VALUES<
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (9):
-  `STATUS`  Type: D
-  `ENTRY.CLASS.CODE`  Type: D
-  `DFI.ACCOUNT.NO`  Type: D
-  `VALUE.DATE`  Type: D
-  `INDIVIDUAL.ID.NO`  Type: D
-  `AMOUNT`  Type: D
-  `MSG.TYPE`  Type: D
-  `BATCH.ORIGINATOR`  Type: D
-  `ROUTING.CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE STATUS = 'EXCEPTION' AND MSG_TYPE = 'INWARD' AND ROUTING_CUSTOMER = 'OUR.BANK' AND ENTRY_CLASS_CODE != 'COR' AND INDIVIDUAL_ID_NO = '{SEL.VALUES<INDIVIDUAL.ID.NO.POS>}' AND DFI_ACCOUNT_NO = '{SEL.VALUES<DFI.ACCOUNT.NO.POS>}' AND AMOUNT = '{SEL.VALUES<AMOUNT.POS>}' AND VALUE_DATE = '{SEL.VALUES<VALUE.DATE.POS>}' AND BATCH_ORIGINATOR = '{SEL.VALUES<BATCH.ORIGINATOR.POS>}'
```

---

#### SELECT #39 - Line 145

**File**: `LATAM.ACH.E.WAREHOUSE.RECON.REP.b`

**Routine**: `LATAM.ACH.E.WAREHOUSE.RECON.REP` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND VALUE.DATE GE {TODAY.VAL} AND ENTRY.CLASS.CODE NE COR BY ENTRY.CLASS.CODE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND VALUE.DATE GE TODAY AND ENTRY.CLASS.CODE NE COR BY ENTRY.CLASS.CODE
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (2):
-  `ENTRY.CLASS.CODE`  Type: D
-  `VALUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID NOT LIKE 'T%' AND ID NOT LIKE 'R%' AND VALUE_DATE >= 'TODAY' AND ENTRY_CLASS_CODE != 'COR'
ORDER BY ENTRY_CLASS_CODE ASC
```

---

#### SELECT #40 - Line 140

**File**: `LATAM.ACH.E.WAREHOUSE.RELEASE.REP.b`

**Routine**: `LATAM.ACH.E.WAREHOUSE.RELEASE.REP` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND VALUE.DATE GE {TODAY.VAL} AND ENTRY.CLASS.CODE NE COR
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.ENTRIES WITH @ID UNLIKE T... AND @ID UNLIKE R... AND VALUE.DATE GE RDATES AND ENTRY.CLASS.CODE NE COR
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (2):
-  `ENTRY.CLASS.CODE`  Type: D
-  `VALUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID NOT LIKE 'T%' AND ID NOT LIKE 'R%' AND VALUE_DATE >= 'RDATES' AND ENTRY_CLASS_CODE != 'COR'
```

---

#### SELECT #41 - Line 28

**File**: `LATAM.ACH.GENERATE.CAPTURE.POST.b`

**Routine**: `LATAM.ACH.GENERATE.CAPTURE.POST` (BATCH (inferred))

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT {FnAchCapturesFilePath}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACH.CAPTURE.FILE.PATH
```

**Table**: `ACH.CAPTURE.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'ACH.CAPTURE.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACH.CAPTURE.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM ACH_CAPTURE_FILE_PATH
```

---

#### SELECT #42 - Line 70

**File**: `LATAM.ACH.GENERATE.CAPTURE.SELECT.b`

**Routine**: `LATAM.ACH.GENERATE.CAPTURE.SELECT` (BATCH (inferred))

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT {FnAchCapturesFilePath}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACH.CAPTURE.FILE.PATH
```

**Table**: `ACH.CAPTURE.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'ACH.CAPTURE.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACH.CAPTURE.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM ACH_CAPTURE_FILE_PATH
```

---

#### SELECT #43 - Line 696

**File**: `LATAM.ACH.GENERATE.ENTRIES.b`

**Routine**: `LATAM.ACH.GENERATE.ENTRIES` (Unknown)

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getFnEbLookup()} WITH VIRTUAL.TABLE EQ LATAM.ACH.PERSON.TYPE
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.LOOKUP WITH VIRTUAL.TABLE EQ LATAM.ACH.PERSON.TYPE
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `VIRTUAL.TABLE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE VIRTUAL_TABLE = 'LATAM.ACH.PERSON.TYPE'
```

---

#### SELECT #44 - Line 804

**File**: `LATAM.ACH.GENERATE.ENTRIES.b`

**Routine**: `LATAM.ACH.GENERATE.ENTRIES` (Unknown)

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getFnLatamAchEntries()} WITH @ID LIKE ...{EB.SystemTables.getToday()[3,6]}... AND MSG.TYPE EQ INWARD AND TRACE.NUMBER EQ {OrigTraceNo}
```

**SIMULATED AT RUNTIME**:
```
SELECT LATAM.ACH.ENTRIES WITH @ID LIKE ...{EB.SystemTables.getToday()[3,6]}... AND MSG.TYPE EQ INWARD AND TRACE.NUMBER EQ {OrigTraceNo}
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (3):
-  `TRACE.NUMBER`  Type: D
-  `MSG.TYPE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID LIKE '%{EB.SystemTables.getToday()[3,6]}%' AND MSG_TYPE = 'INWARD' AND TRACE_NUMBER = '{OrigTraceNo}'
```

---

#### SELECT #45 - Line 248

**File**: `LATAM.ACH.GENERATE.OUT.FILE.b`

**Routine**: `LATAM.ACH.GENERATE.OUT.FILE` (Unknown)

**Variable**: `SelectStatement`

**AS PER CODE**:
```
SSELECT {LATAMACH.UtilityLat.getFnLatamAchEntries()} WITH @ID LIKE {AchBatchId}...
```

**SIMULATED AT RUNTIME**:
```
SSELECT LATAM.ACH.ENTRIES WITH @ID LIKE {AchBatchId}...
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID LIKE '{AchBatchId}%'
ORDER BY RECID ASC
```

---

#### SELECT #46 - Line 342

**File**: `LATAM.ACH.GENERATE.OUT.FILE.ISO.b`

**Routine**: `LATAM.ACH.GENERATE.OUT.FILE.ISO` (Unknown)

**Variable**: `SelectStatement`

**AS PER CODE**:
```
SSELECT {LATAMACH.UtilityLat.getFnLatamAchEntries()} WITH @ID LIKE {AchBatchId}...
```

**SIMULATED AT RUNTIME**:
```
SSELECT LATAM.ACH.ENTRIES WITH @ID LIKE {AchBatchId}...
```

**Table**: `LATAM.ACH.ENTRIES`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_ENTRIES
WHERE ID LIKE '{AchBatchId}%'
ORDER BY RECID ASC
```

---

#### SELECT #47 - Line 53

**File**: `LATAM.ACH.GENERATE.OUT.HEAD.ISO.b`

**Routine**: `LATAM.ACH.GENERATE.OUT.HEAD.ISO` (Unknown)

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.FILE WITH FILE.TYPE EQ "OUTWARD" AND STATUS EQ "PROCESSING" 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.FILE WITH FILE.TYPE EQ "OUTWARD" AND STATUS EQ "PROCESSING" 
```

**Table**: `LATAM.ACH.FILE`

**Fields** (2):
-  `STATUS`  Type: D
-  `FILE.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_FILE
WHERE FILE_TYPE = 'OUTWARD' AND STATUS = 'PROCESSING'
```

---

#### SELECT #48 - Line 127

**File**: `LATAM.ACH.GENERATE.OUTWARD.FT.b`

**Routine**: `LATAM.ACH.GENERATE.OUTWARD.FT` (Unknown)

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.FILE WITH FILE.TYPE EQ "OUTWARD" AND STATUS EQ "PROCESSING" 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.FILE WITH FILE.TYPE EQ "OUTWARD" AND STATUS EQ "PROCESSING" 
```

**Table**: `LATAM.ACH.FILE`

**Fields** (2):
-  `STATUS`  Type: D
-  `FILE.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_FILE
WHERE FILE_TYPE = 'OUTWARD' AND STATUS = 'PROCESSING'
```

---

#### SELECT #49 - Line 97

**File**: `LATAM.ACH.I.DD.VALIDATE.b`

**Routine**: `LATAM.ACH.I.DD.VALIDATE` (VERSION (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.DD.MANDATE WITH @ID LIKE {EB.SystemTables.getRNew(FT.Contract.FundsTransfer.DebitAcctNo)}... AND COMPANY.ID EQ {MANDATE.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.DD.MANDATE WITH @ID LIKE RNEW... AND COMPANY.ID EQ {R.LATAM.ACH.BATCH<LATAMACH.UtilityLat.LatamAchBatch.LatAchBatMandateId>}
```

**Table**: `LATAM.ACH.DD.MANDATE`

**Fields** (2):
-  `COMPANY.ID`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_DD_MANDATE
WHERE ID LIKE 'RNEW%' AND COMPANY_ID = '{R.LATAM.ACH.BATCH<LATAMACH.UtilityLat.LatamAchBatch.LatAchBatMandateId>}'
```

---

#### SELECT #50 - Line 53

**File**: `LATAM.ACH.LOAN.PAYMENT.SELECT.b`

**Routine**: `LATAM.ACH.LOAN.PAYMENT.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getAchFnachloanpayments()} WITH @ID LIKE ...-{EB.SystemTables.getToday()}-...
```

**SIMULATED AT RUNTIME**:
```
SELECT ACH.FNACHLOANPAYMENTS WITH @ID LIKE ...-TODAY-...
```

**Table**: `ACH.FNACHLOANPAYMENTS`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'ACH.FNACHLOANPAYMENTS' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/ACH.FNACHLOANPAYMENTS

**Translated SQL**:
```sql
SELECT *
FROM ACH_FNACHLOANPAYMENTS
WHERE ID LIKE '%-TODAY-%'
```

---

#### SELECT #51 - Line 64

**File**: `LATAM.ACH.UPDATE.WAREHOUSE.SELECT.b`

**Routine**: `LATAM.ACH.UPDATE.WAREHOUSE.SELECT` (BATCH (inferred))

**Variable**: `SelectStatement`

**AS PER CODE**:
```
SSELECT {LATAMACH.UtilityLat.getFnLatamAchOutward()}
```

**SIMULATED AT RUNTIME**:
```
SSELECT LATAM.ACH.OUTWARD
```

**Table**: `LATAM.ACH.OUTWARD`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'LATAM.ACH.OUTWARD' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/LATAM.ACH.OUTWARD

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_OUTWARD
ORDER BY RECID ASC
```

---

#### SELECT #52 - Line 54

**File**: `LATAM.ACH.UPLOAD.WAREHOUSE.ISO.SELECT.b`

**Routine**: `LATAM.ACH.UPLOAD.WAREHOUSE.ISO.SELECT` (BATCH (inferred))

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getWrkFilePath()}
```

**SIMULATED AT RUNTIME**:
```
SELECT WRK.FILE.PATH
```

**Table**: `WRK.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'WRK.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/WRK.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM WRK_FILE_PATH
```

---

#### SELECT #53 - Line 54

**File**: `LATAM.ACH.UPLOAD.WAREHOUSE.SELECT.b`

**Routine**: `LATAM.ACH.UPLOAD.WAREHOUSE.SELECT` (BATCH (inferred))

**Variable**: `SelectCommand`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getWrkFilePath()}
```

**SIMULATED AT RUNTIME**:
```
SELECT WRK.FILE.PATH
```

**Table**: `WRK.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'WRK.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/WRK.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM WRK_FILE_PATH
```

---

#### SELECT #54 - Line 86

**File**: `LATAM.ACH.V.VAL.MANDATE.DD.AMT.b`

**Routine**: `LATAM.ACH.V.VAL.MANDATE.DD.AMT` (VERSION (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.DD.MANDATE WITH @ID LIKE {IdNew}... AND COMPANY.ID EQ {CompanyId}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.DD.MANDATE WITH @ID LIKE {IdNew}... AND COMPANY.ID EQ {CompanyId}
```

**Table**: `LATAM.ACH.DD.MANDATE`

**Fields** (2):
-  `COMPANY.ID`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_DD_MANDATE
WHERE ID LIKE '{IdNew}%' AND COMPANY_ID = '{CompanyId}'
```

---

#### SELECT #55 - Line 51

**File**: `LATAM.ACH.VALIDATE.FILE.ISO.SELECT.b`

**Routine**: `LATAM.ACH.VALIDATE.FILE.ISO.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getInwardFilePath()}
```

**SIMULATED AT RUNTIME**:
```
SELECT INWARD.FILE.PATH
```

**Table**: `INWARD.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'INWARD.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/INWARD.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM INWARD_FILE_PATH
```

---

#### SELECT #56 - Line 62

**File**: `LATAM.ACH.VALIDATE.FILE.SELECT.b`

**Routine**: `LATAM.ACH.VALIDATE.FILE.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {LATAMACH.UtilityLat.getInwardFilePath()}
```

**SIMULATED AT RUNTIME**:
```
SELECT INWARD.FILE.PATH
```

**Table**: `INWARD.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'INWARD.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/INWARD.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM INWARD_FILE_PATH
```

---

#### SELECT #57 - Line 86

**File**: `LATAM.S.ACH.BANK.b`

**Routine**: `LATAM.S.ACH.BANK` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.BANK WITH @ID LIKE {BANK.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.BANK WITH @ID LIKE SAMPLE_VALUE...
```

**Table**: `LATAM.ACH.BANK`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: BANK.ID

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_BANK
WHERE ID LIKE 'SAMPLE_VALUE%'
```

---

#### SELECT #58 - Line 60

**File**: `TemplateRutine.b`

**Routine**: `TemplateRutine` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FBNK.EB.BAPA.GLOBAL.PARAMETER WITH @ID EQ EDOCTA.ACCOUNT.PRINT
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.EB.BAPA.GLOBAL.PARAMETER WITH @ID EQ EDOCTA.ACCOUNT.PRINT
```

**Table**: `FBNK.EB.BAPA.GLOBAL.PARAMETER`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'FBNK.EB.BAPA.GLOBAL.PARAMETER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FBNK.EB.BAPA.GLOBAL.PARAMETER

**Translated SQL**:
```sql
SELECT *
FROM FBNK_EB_BAPA_GLOBAL_PARAMETER
WHERE ID = 'EDOCTA.ACCOUNT.PRINT'
```

---

#### SELECT #59 - Line 50

**File**: `BAPA.B.AA.DEP.AVRG.BALANCES.SELECT.b`

**Routine**: `BAPA.B.AA.DEP.AVRG.BALANCES.SELECT` (BATCH (inferred))

**Variable**: `SEL.CUST.ARR`

**AS PER CODE**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ DEPOSITS
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ DEPOSITS
```

**Table**: `AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'DEPOSITS'
```

---

#### SELECT #60 - Line 45

**File**: `BAPA.BA.TRSY.ENQ.b`

**Routine**: `BAPA.BA.TRSY.ENQ` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CHARGE.REQUEST WITH RELATED.REF EQ {EB.Reports.getOData()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CHARGE.REQUEST WITH RELATED.REF EQ ODATA
```

**Table**: `AC.CHARGE.REQUEST`

**Fields** (1):
-  `RELATED.REF`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST
WHERE RELATED_REF = 'ODATA'
```

---

#### SELECT #61 - Line 31

**File**: `BAPA.B.AC.PEND.CLR.SIMPL.SELECT.b`

**Routine**: `BAPA.B.AC.PEND.CLR.SIMPL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.L.PENDING.CHG WITH AC.PRD.FLAG EQ YES
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.PENDING.CHG WITH AC.PRD.FLAG EQ YES
```

**Table**: `EB.BAPA.L.PENDING.CHG`

**Fields** (1):
-  `AC.PRD.FLAG`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_PENDING_CHG
WHERE AC_PRD_FLAG = 'YES'
```

---

#### SELECT #62 - Line 153

**File**: `BAN.A.EB.LM.EVAL.ACUM.b`

**Routine**: `BAN.A.EB.LM.EVAL.ACUM` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ '{Y.CHANNEL}' AND (VERSION.ID EQ '{EB.SystemTables.getApplication()}{EB.SystemTables.getPgmVersion()}' OR (TXN.APP.ID EQ '{Y.APPL}' AND TXN.CODE EQ '{Y.TXN.CODE}'))
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ 'VALUE123' AND (VERSION.ID EQ 'APPLICATIONPGM.VERSION' OR (TXN.APP.ID EQ 'TELLER' AND TXN.CODE EQ 'VALUE123'))
```

**Table**: `BAN.EB.LM.AC.TXN.PAR`

**Fields** (2):
-  `TXN.CODE`  Type: D
-  `CHANNEL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHANNEL, Y.TXN.CODE

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_AC_TXN_PAR
WHERE CHANNEL_ID = 'VALUE123' AND TXN_CODE = 'VALUE123'
```

---

#### SELECT #63 - Line 45

**File**: `BAN.B.DEPU.INTERM.TRANS.SELECT.b`

**Routine**: `BAN.B.DEPU.INTERM.TRANS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPATT.MigCaja.getFnBanIntermediTrans()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INTERMEDI.TRANS
```

**Table**: `BAN.INTERMEDI.TRANS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_INTERMEDI_TRANS
```

---

#### SELECT #64 - Line 30

**File**: `BAN.DSF.TFS.GET.TELLER.ID.b`

**Routine**: `BAN.DSF.TFS.GET.TELLER.ID` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {FN.TELLER.ID} WITH STATUS EQ OPEN AND USER EQ {EB.SystemTables.getOperator()}
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER.ID WITH STATUS EQ OPEN AND USER EQ OPERATOR
```

**Table**: `TELLER.ID`

**Fields** (2):
-  `USER`  Type: D
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM TELLER_ID
WHERE STATUS = 'OPEN' AND USER = 'OPERATOR'
```

---

#### SELECT #65 - Line 51

**File**: `BAN.E.NOF.TFS.PRESTACARD.b`

**Routine**: `BAN.E.NOF.TFS.PRESTACARD` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER.FINANCIAL.SERVICES WITH BOOKING.DATE EQ {EB.SystemTables.getToday()} AND ( TRANSACTION EQ PR.EFECTIVO OR TRANSACTION EQ PR.CHPROPIO OR TRANSACTION EQ PR.CHLOCAL) AND INPUTTER LK …{USER.ID}…
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.FINANCIAL.SERVICES WITH BOOKING.DATE EQ TODAY AND ( TRANSACTION EQ PR.EFECTIVO OR TRANSACTION EQ PR.CHPROPIO OR TRANSACTION EQ PR.CHLOCAL) AND INPUTTER LK …SAMPLE_VALUE…
```

**Table**: `TELLER.FINANCIAL.SERVICES`

**Fields** (2):
-  `BOOKING.DATE`  Type: D
-  `TRANSACTION`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TRANSACTION' used in condition (cannot create index on M fields)
-   Unresolved variables: USER.ID

**Translated SQL**:
```sql
SELECT *
FROM TELLER_FINANCIAL_SERVICES
WHERE BOOKING_DATE = 'TODAY'
```

---

#### SELECT #66 - Line 136

**File**: `BAN.E.NOF.TFS.REC.b`

**Routine**: `BAN.E.NOF.TFS.REC` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER WITH @ID NE '' AND CO.CODE EQ {Y.CO.CODE} AND TRANSACTION.CODE EQ {Y.TXN} AND (TELLER.ID.1 EQ {Y.TT} OR TELLER.ID.2 EQ {Y.TT}) BY CO.CODE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER WITH @ID NE '' AND CO.CODE EQ VALUE123 AND TRANSACTION.CODE EQ VALUE123 AND (TELLER.ID.1 EQ VALUE123 OR TELLER.ID.2 EQ VALUE123) BY CO.CODE
```

**Table**: `TELLER`

**Fields** (4):
-  `TELLER.ID.2`  Type: D
-  `CO.CODE`  Type: D
-  `TRANSACTION.CODE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CO.CODE, Y.TXN, Y.TT

**Translated SQL**:
```sql
SELECT *
FROM TELLER
WHERE CO_CODE = 'VALUE123' AND TRANSACTION_CODE = 'VALUE123'
ORDER BY CO_CODE ASC
```

---

#### SELECT #67 - Line 92

**File**: `BAN.E.NOF.TFS.RECORDS.b`

**Routine**: `BAN.E.NOF.TFS.RECORDS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER.FINANCIAL.SERVICES WITH REVERSAL.MARK NE R AND BOOKING.DATE EQ {EB.SystemTables.getToday()} AND CO.CODE EQ {Y.CO.CODE} AND UNDERLYING EQ '{Y.TXN}' BY CO.CODE 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.FINANCIAL.SERVICES WITH REVERSAL.MARK NE R AND BOOKING.DATE EQ TODAY AND CO.CODE EQ VALUE123 AND UNDERLYING EQ 'VALUE123' BY CO.CODE 
```

**Table**: `TELLER.FINANCIAL.SERVICES`

**Fields** (4):
-  `CO.CODE`  Type: D
-  `BOOKING.DATE`  Type: D
-  `UNDERLYING`  Type: D
-  `REVERSAL.MARK`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'UNDERLYING' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'REVERSAL.MARK' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CO.CODE, Y.TXN

**Translated SQL**:
```sql
SELECT *
FROM TELLER_FINANCIAL_SERVICES
WHERE REVERSAL_MARK != 'R' AND BOOKING_DATE = 'TODAY' AND CO_CODE = 'VALUE123' AND UNDERLYING = 'VALUE123'
ORDER BY CO_CODE ASC
```

---

#### SELECT #68 - Line 50

**File**: `BAN.E.NOF.TXN.PAR.b`

**Routine**: `BAN.E.NOF.TXN.PAR` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.TELLER.TRANSACTION
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.TRANSACTION
```

**Table**: `TELLER.TRANSACTION`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM TELLER_TRANSACTION
```

---

#### SELECT #69 - Line 55

**File**: `BAN.E.NOF.TXN.PAR.b`

**Routine**: `BAN.E.NOF.TXN.PAR` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.FT.TXN.TYPE.CONDITION
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.TXN.TYPE.CONDITION
```

**Table**: `FT.TXN.TYPE.CONDITION`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM FT_TXN_TYPE_CONDITION
```

---

#### SELECT #70 - Line 99

**File**: `BAN.EB.LM.AC.TXN.PAR.VALIDATE.b`

**Routine**: `BAN.EB.LM.AC.TXN.PAR.VALIDATE` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ {Y.CHANNEL.ID} AND TXN.APP.ID EQ {Y.TXN.APP.ID} AND TXN.CODE EQ {Y.TXN.CODE} AND TXN.APP.ID EQ {Y.TXN.APP.ID} AND TXN.CODE EQ {Y.TXN.CODE} AND VERSION.ID EQ {Y.VERSION.ID} AND VERSION.ID EQ {Y.VERSION.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ VALUE123 AND TXN.APP.ID EQ VALUE123 AND TXN.CODE EQ VALUE123 AND TXN.APP.ID EQ VALUE123 AND TXN.CODE EQ VALUE123 AND VERSION.ID EQ VALUE123 AND VERSION.ID EQ VALUE123
```

**Table**: `BAN.EB.LM.AC.TXN.PAR`

**Fields** (4):
-  `TXN.APP.ID`  Type: D
-  `TXN.CODE`  Type: D
-  `CHANNEL.ID`  Type: D
-  `VERSION.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHANNEL.ID, Y.TXN.APP.ID, Y.TXN.CODE, Y.VERSION.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_AC_TXN_PAR
WHERE CHANNEL_ID = 'VALUE123' AND TXN_APP_ID = 'VALUE123' AND TXN_CODE = 'VALUE123' AND TXN_APP_ID = 'VALUE123' AND TXN_CODE = 'VALUE123' AND VERSION_ID = 'VALUE123' AND VERSION_ID = 'VALUE123'
```

---

#### SELECT #71 - Line 181

**File**: `BAN.I.EB.EVAL.LIM.b`

**Routine**: `BAN.I.EB.EVAL.LIM` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ '{Y.CHANNEL}' AND (VERSION.ID EQ '{Y.VERSION}' OR (TXN.APP.ID EQ '{Y.APPL}' AND TXN.CODE EQ '{Y.TXN.CODE}'))
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ 'VALUE123' AND (VERSION.ID EQ 'VALUE123' OR (TXN.APP.ID EQ 'TELLER' AND TXN.CODE EQ 'VALUE123'))
```

**Table**: `BAN.EB.LM.AC.TXN.PAR`

**Fields** (2):
-  `TXN.CODE`  Type: D
-  `CHANNEL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHANNEL, Y.VERSION, Y.TXN.CODE

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_AC_TXN_PAR
WHERE CHANNEL_ID = 'VALUE123' AND TXN_CODE = 'VALUE123'
```

---

#### SELECT #72 - Line 82

**File**: `BAN.S.SEARCH.INTERMEDIARY.b`

**Routine**: `BAN.S.SEARCH.INTERMEDIARY` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INTERMEDIARY WITH LEGAL.ID EQ {Y.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INTERMEDIARY WITH LEGAL.ID EQ 12345
```

**Table**: `BAN.INTERMEDIARY`

**Fields** (1):
-  `LEGAL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_INTERMEDIARY
WHERE LEGAL_ID = '12345'
```

---

#### SELECT #73 - Line 96

**File**: `BCM.I.CHQ.CERT.PAY.b`

**Routine**: `BCM.I.CHQ.CERT.PAY` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE ...{EB.SystemTables.getRNew(FT.Contract.FundsTransfer.OrdCustAcct)}.{EB.SystemTables.getRNew(FT.Contract.FundsTransfer.StockNumber)}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE ...RNEW.RNEW...
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE ID LIKE '%RNEW.RNEW%'
```

---

#### SELECT #74 - Line 116

**File**: `BPA.ENQ.NOF.LD.CTA.TRN.b`

**Routine**: `BPA.ENQ.NOF.LD.CTA.TRN` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.ACUM WITH FROM.DATE NE '' AND @ID LIKE ...{Y.APPL.ID}... AND @ID LIKE ...{Y.APPL.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.ACUM WITH FROM.DATE NE '' AND @ID LIKE ...VALUE123... AND @ID LIKE ...VALUE123...
```

**Table**: `BAN.EB.LM.ACUM`

**Fields** (2):
-  `@ID`  Type: D
-  `FROM.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.APPL.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_ACUM
WHERE ID LIKE '%VALUE123%' AND ID LIKE '%VALUE123%'
```

---

#### SELECT #75 - Line 93

**File**: `BAPA.E.NOF.LT.NUM.REF.b`

**Routine**: `BAPA.E.NOF.LT.NUM.REF` (NOFILE (inferred))

**Variable**: `STMT.TT`

**AS PER CODE**:
```
SELECT F.TELLER WITH (TRANSACTION.CODE EQ 54) OR 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER WITH (TRANSACTION.CODE EQ 54) OR 
```

**Table**: `TELLER`

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM TELLER
```

---

#### SELECT #76 - Line 70

**File**: `BAN.A.TCIB.INVITE.NON.EXT.USER.b`

**Routine**: `BAN.A.TCIB.INVITE.NON.EXT.USER` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.EXTERNAL.USER WITH CUSTOMER EQ {Y.CUSTOMER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.EXTERNAL.USER WITH CUSTOMER EQ VALUE123
```

**Table**: `EB.EXTERNAL.USER`

**Fields** (1):
-  `CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUSTOMER

**Translated SQL**:
```sql
SELECT *
FROM EB_EXTERNAL_USER
WHERE CUSTOMER = 'VALUE123'
```

---

#### SELECT #77 - Line 109

**File**: `BAN.A.TCIB.UPD.OTP.DETAILS.b`

**Routine**: `BAN.A.TCIB.UPD.OTP.DETAILS` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH @ID LIKE {Y.CUS.ID}-...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH @ID LIKE VALUE123-...
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUS.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE ID LIKE 'VALUE123-%'
```

---

#### SELECT #78 - Line 46

**File**: `BAN.B.PURGE.OPERATION.REQUEST.SELECT.b`

**Routine**: `BAN.B.PURGE.OPERATION.REQUEST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.TCIB.OPERATION.REQUEST
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TCIB.OPERATION.REQUEST
```

**Table**: `BAN.TCIB.OPERATION.REQUEST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

#### SELECT #79 - Line 83

**File**: `BAN.B.TCIB.CANCELA.USER.SEC.b`

**Routine**: `BAN.B.TCIB.CANCELA.USER.SEC` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.TCIB.AFFILIATION WITH @ID LIKE ...-{USER.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TCIB.AFFILIATION WITH @ID LIKE ...-SAMPLE_VALUE
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: USER.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE ID LIKE '%-SAMPLE_VALUE'
```

---

#### SELECT #80 - Line 42

**File**: `BAN.B.TCIB.RELEASE.AFFILIATION.SELECT.b`

**Routine**: `BAN.B.TCIB.RELEASE.AFFILIATION.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.TC.AFFILIATION.STATUS
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TC.AFFILIATION.STATUS
```

**Table**: `BAN.TC.AFFILIATION.STATUS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TC_AFFILIATION_STATUS
```

---

#### SELECT #81 - Line 162

**File**: `BAN.BA.LM.AC.DEFINE.LINK.b`

**Routine**: `BAN.BA.LM.AC.DEFINE.LINK` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ {Y.ACLM.CHANNEL} AND VERSION.ID EQ '{Y.TXN.VERSION}' AND TXN.APP.ID EQ {Y.TXN.APP} AND TXN.CODE EQ {Y.TXN.CODE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ VALUE123 AND VERSION.ID EQ 'VALUE123' AND TXN.APP.ID EQ VALUE123 AND TXN.CODE EQ VALUE123
```

**Table**: `BAN.EB.LM.AC.TXN.PAR`

**Fields** (4):
-  `TXN.APP.ID`  Type: D
-  `VERSION.ID`  Type: D
-  `CHANNEL.ID`  Type: D
-  `TXN.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACLM.CHANNEL, Y.TXN.VERSION, Y.TXN.APP, Y.TXN.CODE

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_AC_TXN_PAR
WHERE CHANNEL_ID = 'VALUE123' AND VERSION_ID = 'VALUE123' AND TXN_APP_ID = 'VALUE123' AND TXN_CODE = 'VALUE123'
```

---

#### SELECT #82 - Line 236

**File**: `BAN.BA.TCIB.CALL.ENTRUST.b`

**Routine**: `BAN.BA.TCIB.CALL.ENTRUST` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH ISA.AA.ID EQ {Y.USER.EXT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH ISA.AA.ID EQ VALUE123
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `ISA.AA.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USER.EXT

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE ISA_AA_ID = 'VALUE123'
```

---

#### SELECT #83 - Line 269

**File**: `BAN.BA.UPDATE.RELATED.CUSTOMERS.b`

**Routine**: `BAN.BA.UPDATE.RELATED.CUSTOMERS` (Unknown)

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.AA.PRODUCT.GROUP WITH (PRODUCT.LINE EQ ACCOUNTS) OR (PRODUCT.LINE EQ LENDING) OR (PRODUCT.LINE EQ DEPOSITS)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.PRODUCT.GROUP WITH (PRODUCT.LINE EQ ACCOUNTS) OR (PRODUCT.LINE EQ LENDING) OR (PRODUCT.LINE EQ DEPOSITS)
```

**Table**: `AA.PRODUCT.GROUP`

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_PRODUCT_GROUP
```

---

#### SELECT #84 - Line 280

**File**: `BAN.BA.UPDATE.RELATED.CUSTOMERS.b`

**Routine**: `BAN.BA.UPDATE.RELATED.CUSTOMERS` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHANNEL.PERMISSION WITH @ID LIKE ...-{EB.SystemTables.getIdNew()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHANNEL.PERMISSION WITH @ID LIKE ...-ID.NEW
```

**Table**: `CHANNEL.PERMISSION`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHANNEL_PERMISSION
WHERE ID LIKE '%-ID.NEW'
```

---

#### SELECT #85 - Line 228

**File**: `BAN.BA.VALIDATE.ACCOUNTS.b`

**Routine**: `BAN.BA.VALIDATE.ACCOUNTS` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CASHPOOLING.INFO{Y.MENSAJE} OR WITH CUENTAS.SEC EQ {Y.ID.ACC} AND WITH @ID NE {EB.SystemTables.getIdNew()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CASHPOOLING.INFOVALUE123 OR WITH CUENTAS.SEC EQ VALUE123 OR WITH CUENTAS.SEC EQ VALUE123 AND WITH @ID NE ID.NEW
```

**Table**: `BAN.CASHPOOLING.INFOVALUE123`

**Fields** (2):
-  `@ID`  Type: Unknown
-  `CUENTAS.SEC`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BAN.CASHPOOLING.INFOVALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.CASHPOOLING.INFOVALUE123
-   Unresolved variables: Y.MENSAJE, Y.ID.ACC

**Translated SQL**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFOVALUE123
WHERE CUENTAS_SEC = 'VALUE123' AND CUENTAS_SEC = 'VALUE123' AND ID != 'ID.NEW'
```

---

#### SELECT #86 - Line 434

**File**: `BAN.BA.VALIDATE.ACCOUNTS.b`

**Routine**: `BAN.BA.VALIDATE.ACCOUNTS` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CP.GROUP.PARAM WITH @ID LIKE {Y.CUSTOMER.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CP.GROUP.PARAM WITH @ID LIKE VALUE123...
```

**Table**: `AC.CP.GROUP.PARAM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUSTOMER.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_CP_GROUP_PARAM
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #87 - Line 558

**File**: `BAN.BA.VALIDATE.ACCOUNTS.b`

**Routine**: `BAN.BA.VALIDATE.ACCOUNTS` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CP.GROUP.PARAM WITH @ID LIKE {Y.CUSTOMER.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CP.GROUP.PARAM WITH @ID LIKE VALUE123...
```

**Table**: `AC.CP.GROUP.PARAM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUSTOMER.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_CP_GROUP_PARAM
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #88 - Line 598

**File**: `BAN.BA.VALIDATE.ACCOUNTS.b`

**Routine**: `BAN.BA.VALIDATE.ACCOUNTS` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE {Y.AA.ID}-MINBALFEE...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE VALUE123-MINBALFEE...
```

**Table**: `AA.ARR.CHARGE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AA.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_CHARGE
WHERE ID LIKE 'VALUE123-MINBALFEE%'
```

---

#### SELECT #89 - Line 175

**File**: `BAN.CR.ASSIGN.LIM.PAR.b`

**Routine**: `BAN.CR.ASSIGN.LIM.PAR` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ {Y.ACLM.CHANNEL} AND VERSION.ID EQ '{Y.TXN.VERSION}' AND TXN.APP.ID EQ {Y.TXN.APP} AND TXN.CODE EQ {Y.TXN.CODE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ VALUE123 AND VERSION.ID EQ 'VALUE123' AND TXN.APP.ID EQ VALUE123 AND TXN.CODE EQ VALUE123
```

**Table**: `BAN.EB.LM.AC.TXN.PAR`

**Fields** (4):
-  `TXN.APP.ID`  Type: D
-  `VERSION.ID`  Type: D
-  `CHANNEL.ID`  Type: D
-  `TXN.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACLM.CHANNEL, Y.TXN.VERSION, Y.TXN.APP, Y.TXN.CODE

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_AC_TXN_PAR
WHERE CHANNEL_ID = 'VALUE123' AND VERSION_ID = 'VALUE123' AND TXN_APP_ID = 'VALUE123' AND TXN_CODE = 'VALUE123'
```

---

#### SELECT #90 - Line 90

**File**: `BAN.E.CNV.TCIB.NO.CHQ.NOT.AVAIL.b`

**Routine**: `BAN.E.CNV.TCIB.NO.CHQ.NOT.AVAIL` (ENQUIRY (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {Y.CHQ.TYPE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE VALUE123...
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHQ.TYPE

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #91 - Line 98

**File**: `BAN.E.NOF.CASHPOOLING.ACCOUNTS.b`

**Routine**: `BAN.E.NOF.CASHPOOLING.ACCOUNTS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**Table**: `BAN.CASHPOOLING.INFO`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFO
```

---

#### SELECT #92 - Line 207

**File**: `BAN.E.NOF.CASHPOOLING.ACCOUNTS.b`

**Routine**: `BAN.E.NOF.CASHPOOLING.ACCOUNTS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE {Y.AA.ID}-MINBALFEE...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE VALUE123-MINBALFEE...
```

**Table**: `AA.ARR.CHARGE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AA.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_CHARGE
WHERE ID LIKE 'VALUE123-MINBALFEE%'
```

---

#### SELECT #93 - Line 101

**File**: `BAN.E.NOF.CASHPOOLING.INFO.b`

**Routine**: `BAN.E.NOF.CASHPOOLING.INFO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**Table**: `BAN.CASHPOOLING.INFO`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFO
```

---

#### SELECT #94 - Line 584

**File**: `BAN.E.NOF.CASHPOOLING.INFO.b`

**Routine**: `BAN.E.NOF.CASHPOOLING.INFO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE {Y.AA.ID}-MINBALFEE...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE VALUE123-MINBALFEE...
```

**Table**: `AA.ARR.CHARGE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AA.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_CHARGE
WHERE ID LIKE 'VALUE123-MINBALFEE%'
```

---

#### SELECT #95 - Line 118

**File**: `BAN.E.NOF.CAT.STATUS.b`

**Routine**: `BAN.E.NOF.CAT.STATUS` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AUTH.ATTEMPS{" WITH CAT.ATTEMPS GE " Y.MAX.TAF.ATTEMPS}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AUTH.ATTEMPS{" WITH CAT.ATTEMPS GE " Y.MAX.TAF.ATTEMPS}
```

**Table**: `BAN.TCIB.AUTH.ATTEMPS`

**Fields** (1):
-  `CAT.ATTEMPS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AUTH_ATTEMPS
```

---

#### SELECT #96 - Line 114

**File**: `BAN.E.NOF.COS.STATUS.b`

**Routine**: `BAN.E.NOF.COS.STATUS` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH STATUS EQ BLOQUEADA
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH STATUS EQ BLOQUEADA
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE STATUS = 'BLOQUEADA'
```

---

#### SELECT #97 - Line 130

**File**: `BAN.E.NOF.OPER.BY.TYPE.b`

**Routine**: `BAN.E.NOF.OPER.BY.TYPE` (NOFILE (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.BAN.TC.OPERATIONS WITH ACLM.CHANNEL EQ {Y.CHANNEL.ID} AND TCIB.TYPE EQ {Y.TCIB.TYPE} AND TXN.DESCRIPTION NE '' AND ACLM.SEQ NE ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TC.OPERATIONS WITH ACLM.CHANNEL EQ VALUE123 AND TCIB.TYPE EQ VALUE123 AND TXN.DESCRIPTION NE '' AND ACLM.SEQ NE ''
```

**Table**: `BAN.TC.OPERATIONS`

**Fields** (4):
-  `ACLM.CHANNEL`  Type: D
-  `TCIB.TYPE`  Type: D
-  `TXN.DESCRIPTION`  Type: D
-  `ACLM.SEQ`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ACLM.CHANNEL' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TCIB.TYPE' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TXN.DESCRIPTION' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'ACLM.SEQ' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CHANNEL.ID, Y.TCIB.TYPE

**Translated SQL**:
```sql
SELECT *
FROM BAN_TC_OPERATIONS
WHERE ACLM_CHANNEL = 'VALUE123' AND TCIB_TYPE = 'VALUE123'
```

---

#### SELECT #98 - Line 226

**File**: `BAN.E.NOF.OPER.BY.TYPE.b`

**Routine**: `BAN.E.NOF.OPER.BY.TYPE` (NOFILE (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ {Y.ACLM.CHANNEL} AND VERSION.ID EQ '{Y.TXN.VERSION}' AND TXN.APP.ID EQ {Y.TXN.APP} AND TXN.CODE EQ {Y.TXN.CODE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.EB.LM.AC.TXN.PAR WITH CHANNEL.ID EQ VALUE123 AND VERSION.ID EQ 'VALUE123' AND TXN.APP.ID EQ VALUE123 AND TXN.CODE EQ VALUE123
```

**Table**: `BAN.EB.LM.AC.TXN.PAR`

**Fields** (4):
-  `TXN.APP.ID`  Type: D
-  `VERSION.ID`  Type: D
-  `CHANNEL.ID`  Type: D
-  `TXN.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACLM.CHANNEL, Y.TXN.VERSION, Y.TXN.APP, Y.TXN.CODE

**Translated SQL**:
```sql
SELECT *
FROM BAN_EB_LM_AC_TXN_PAR
WHERE CHANNEL_ID = 'VALUE123' AND VERSION_ID = 'VALUE123' AND TXN_APP_ID = 'VALUE123' AND TXN_CODE = 'VALUE123'
```

---

#### SELECT #99 - Line 226

**File**: `BAN.E.NOF.OPER.DEF.EXEC.b`

**Routine**: `BAN.E.NOF.OPER.DEF.EXEC` (NOFILE (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.BAN.TC.OPERATIONS WITH ACLM.CHANNEL EQ {Y.CHANNEL.ID} AND TCIB.TYPE EQ {Y.TCIB.TYPE} AND TXN.DESCRIPTION NE '' AND ACLM.SEQ NE ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TC.OPERATIONS WITH ACLM.CHANNEL EQ VALUE123 AND TCIB.TYPE EQ VALUE123 AND TXN.DESCRIPTION NE '' AND ACLM.SEQ NE ''
```

**Table**: `BAN.TC.OPERATIONS`

**Fields** (4):
-  `ACLM.CHANNEL`  Type: D
-  `TCIB.TYPE`  Type: D
-  `TXN.DESCRIPTION`  Type: D
-  `ACLM.SEQ`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ACLM.CHANNEL' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TCIB.TYPE' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TXN.DESCRIPTION' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'ACLM.SEQ' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CHANNEL.ID, Y.TCIB.TYPE

**Translated SQL**:
```sql
SELECT *
FROM BAN_TC_OPERATIONS
WHERE ACLM_CHANNEL = 'VALUE123' AND TCIB_TYPE = 'VALUE123'
```

---

#### SELECT #100 - Line 151

**File**: `BAN.E.NOF.OPERATION.MOVS.b`

**Routine**: `BAN.E.NOF.OPERATION.MOVS` (NOFILE (inferred))

**Variable**: `SEL.CMD.NAU`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH {SEL.CMD.FILTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH SAMPLE_VALUE
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: SEL.CMD.FILTER

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #101 - Line 152

**File**: `BAN.E.NOF.OPERATION.MOVS.b`

**Routine**: `BAN.E.NOF.OPERATION.MOVS` (NOFILE (inferred))

**Variable**: `SEL.CMD.LIV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER WITH {SEL.CMD.FILTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER WITH SAMPLE_VALUE
```

**Table**: `FUNDS.TRANSFER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: SEL.CMD.FILTER

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER
```

---

#### SELECT #102 - Line 153

**File**: `BAN.E.NOF.OPERATION.MOVS.b`

**Routine**: `BAN.E.NOF.OPERATION.MOVS` (NOFILE (inferred))

**Variable**: `SEL.CMD.HIS`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH {SEL.CMD.FILTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH SAMPLE_VALUE
```

**Table**: `FUNDS.TRANSFER$HIS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: SEL.CMD.FILTER

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$HIS
```

---

#### SELECT #103 - Line 140

**File**: `BAN.E.NOF.PAYROLL.PENDING.b`

**Routine**: `BAN.E.NOF.PAYROLL.PENDING` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**Table**: `BAN.TCIB.OPERATION.REQUEST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

#### SELECT #104 - Line 65

**File**: `BAN.E.NOF.TC.PROVINCE.b`

**Routine**: `BAN.E.NOF.TC.PROVINCE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BCM.PROVINCE WITH COUNTRY EQ PA
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.PROVINCE WITH COUNTRY EQ PA
```

**Table**: `BCM.PROVINCE`

**Fields** (1):
-  `COUNTRY`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BCM_PROVINCE
WHERE COUNTRY = 'PA'
```

---

#### SELECT #105 - Line 144

**File**: `BAN.E.NOF.TCIB.AUTH.SEC.USERS.b`

**Routine**: `BAN.E.NOF.TCIB.AUTH.SEC.USERS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH @ID LIKE ...-{Y.USER.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH @ID LIKE ...-VALUE123
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USER.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE ID LIKE '%-VALUE123'
```

---

#### SELECT #106 - Line 146

**File**: `BAN.E.NOF.TCIB.BULK.ITEM.INAU.b`

**Routine**: `BAN.E.NOF.TCIB.BULK.ITEM.INAU` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.FT.BULK.ITEM WITH @ID LIKE {Y.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.ITEM WITH @ID LIKE 12345...
```

**Table**: `FT.BULK.ITEM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_ITEM
WHERE ID LIKE '12345%'
```

---

#### SELECT #107 - Line 157

**File**: `BAN.E.NOF.TCIB.BULK.ITEM.INAU.b`

**Routine**: `BAN.E.NOF.TCIB.BULK.ITEM.INAU` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.FT.BULK.ITEM$NAU WITH @ID LIKE {Y.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.ITEM$NAU WITH @ID LIKE 12345...
```

**Table**: `FT.BULK.ITEM$NAU`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FT.BULK.ITEM'
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_ITEM$NAU
WHERE ID LIKE '12345%'
```

---

#### SELECT #108 - Line 100

**File**: `BAN.E.NOF.TCIB.CAT.PROCESS.b`

**Routine**: `BAN.E.NOF.TCIB.CAT.PROCESS` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH STATUS EQ {Y.AFF.STATUS}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH STATUS EQ VALUE123
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AFF.STATUS

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE STATUS = 'VALUE123'
```

---

#### SELECT #109 - Line 79

**File**: `BAN.E.NOF.TCIB.CCY.MARKET.b`

**Routine**: `BAN.E.NOF.TCIB.CCY.MARKET` (NOFILE (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.CURRENCY WITH LT.IB.TRFINT NE '' BY LT.IB.TRFINT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CURRENCY WITH LT.IB.TRFINT NE '' BY LT.IB.TRFINT
```

**Table**: `CURRENCY`

**Fields** (1):
-  `LT.IB.TRFINT`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,2>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.IB.TRFINT - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM CURRENCY
ORDER BY LT_IB_TRFINT ASC
```

---

#### SELECT #110 - Line 104

**File**: `BAN.E.NOF.TCIB.CHQ.DET.b`

**Routine**: `BAN.E.NOF.TCIB.CHQ.DET` (NOFILE (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {FIELD(Y.CHQ.BOOK.ID,'.',1)}.{FIELD(Y.CHQ.BOOK.ID,'.',2)}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {FIELD(Y.CHQ.BOOK.ID,'.',1)}.{FIELD(Y.CHQ.BOOK.ID,'.',2)}...
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FIELD(Y.CHQ.BOOK.ID,'.',1), FIELD(Y.CHQ.BOOK.ID,'.',2)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE ID LIKE '%{FIELD(Y.CHQ.BOOK.ID,%'
```

---

#### SELECT #111 - Line 126

**File**: `BAN.E.NOF.TCIB.CUST.CRED.b`

**Routine**: `BAN.E.NOF.TCIB.CUST.CRED` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH @ID EQ {R.AA.CUSTOMER.ARRANGEMENT<AA.Framework.CustomerArrangement.CusarrArrangement>} AND ARR.STATUS EQ CURRENT MATURED EXPIRED AND PRODUCT EQ {Y.TIPO.CRED}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH @ID EQ {R.AA.CUSTOMER.ARRANGEMENT<AA.Framework.CustomerArrangement.CusarrArrangement>} AND ARR.STATUS EQ CURRENT MATURED EXPIRED AND PRODUCT EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (3):
-  `PRODUCT`  Type: D
-  `ARR.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TIPO.CRED

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE ID = '{R.AA.CUSTOMER.ARRANGEMENT<AA.Framework.CustomerArrangement.CusarrArrangement>}' AND ARR_STATUS = 'CURRENT' AND PRODUCT = 'VALUE123'
```

---

#### SELECT #112 - Line 121

**File**: `BAN.E.NOF.TCIB.DIFE.STATUS.b`

**Routine**: `BAN.E.NOF.TCIB.DIFE.STATUS` (NOFILE (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH STATUS EQ DIFERIDA
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH STATUS EQ DIFERIDA
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE STATUS = 'DIFERIDA'
```

---

#### SELECT #113 - Line 99

**File**: `BAN.E.NOF.TCIB.PENDING.FT.b`

**Routine**: `BAN.E.NOF.TCIB.PENDING.FT` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU DEBIT.ACCT.NO EQ {Y.ACCOUNT.NO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU DEBIT.ACCT.NO EQ VALUE123
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.ACCOUNT.NO

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #114 - Line 192

**File**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS.b`

**Routine**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FT.BULK.ITEM WITH @ID LIKE {Y.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.ITEM WITH @ID LIKE 12345...
```

**Table**: `FT.BULK.ITEM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_ITEM
WHERE ID LIKE '12345%'
```

---

#### SELECT #115 - Line 193

**File**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS.b`

**Routine**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS` (NOFILE (inferred))

**Variable**: `SEL.CMD.NAU`

**AS PER CODE**:
```
SELECT F.FT.BULK.ITEM$NAU WITH @ID LIKE {Y.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.ITEM$NAU WITH @ID LIKE 12345...
```

**Table**: `FT.BULK.ITEM$NAU`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FT.BULK.ITEM'
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_ITEM$NAU
WHERE ID LIKE '12345%'
```

---

#### SELECT #116 - Line 154

**File**: `BAN.E.NOF.TCIB.PLANILLA.MASTER.b`

**Routine**: `BAN.E.NOF.TCIB.PLANILLA.MASTER` (NOFILE (inferred))

**Variable**: `SEL.CMD.NAU`

**AS PER CODE**:
```
SELECT F.FT.BULK.MASTER$NAU{Y.CONDITION} AND UPLOAD.REFERENCE EQ TCIB AND RECORD.STATUS EQ INAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.MASTER$NAU WITH CUSTOMER EQ VALUE123 AND (BULK.TYPE EQ SINGLE.PLANILLA OR BULK.TYPE EQ SINGLE.PROVEEDOR) AND UPLOAD.REFERENCE EQ TCIB AND RECORD.STATUS EQ INAU
```

**Table**: `FT.BULK.MASTER$NAU`

**Fields** (4):
-  `CUSTOMER`  Type: D
-  `RECORD.STATUS`  Type: D
-  `UPLOAD.REFERENCE`  Type: D
-  `BULK.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FT.BULK.MASTER'
-   Unresolved variables: Y.CUS.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_MASTER$NAU
WHERE CUSTOMER = 'VALUE123' AND UPLOAD_REFERENCE = 'TCIB' AND RECORD_STATUS = 'INAU'
```

---

#### SELECT #117 - Line 155

**File**: `BAN.E.NOF.TCIB.PLANILLA.MASTER.b`

**Routine**: `BAN.E.NOF.TCIB.PLANILLA.MASTER` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FT.BULK.MASTER WITH CUSTOMER EQ {Y.CUS.ID} AND (BULK.TYPE EQ SINGLE.PLANILLA OR BULK.TYPE EQ SINGLE.PROVEEDOR)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.MASTER WITH CUSTOMER EQ VALUE123 AND (BULK.TYPE EQ SINGLE.PLANILLA OR BULK.TYPE EQ SINGLE.PROVEEDOR)
```

**Table**: `FT.BULK.MASTER`

**Fields** (2):
-  `CUSTOMER`  Type: D
-  `BULK.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUS.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_MASTER
WHERE CUSTOMER = 'VALUE123'
```

---

#### SELECT #118 - Line 291

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.STANDING.ORDER WITH ACCOUNT EQ {Y.ACCOUNT.LIST} AND ( CURRENT.END.DATE EQ '' OR CURRENT.END.DATE GT {Y.ONE.YEAR} )
```

**SIMULATED AT RUNTIME**:
```
SELECT F.STANDING.ORDER WITH ACCOUNT EQ VALUE123 AND ( CURRENT.END.DATE EQ '' OR CURRENT.END.DATE GT VALUE123 )
```

**Table**: `STANDING.ORDER`

**Fields** (2):
-  `ACCOUNT`  Type: I-PHYSICAL.REF
-  `CURRENT.END.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: ACCOUNT - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM STANDING_ORDER
WHERE ACCOUNT = 'VALUE123'
```

---

#### SELECT #119 - Line 294

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.STANDING.ORDER$HIS WITH ACCOUNT EQ {Y.ACCOUNT.LIST} AND ( CURRENT.END.DATE EQ '' OR CURRENT.END.DATE GT {Y.ONE.YEAR} )
```

**SIMULATED AT RUNTIME**:
```
SELECT F.STANDING.ORDER$HIS WITH ACCOUNT EQ VALUE123 AND ( CURRENT.END.DATE EQ '' OR CURRENT.END.DATE GT VALUE123 )
```

**Table**: `STANDING.ORDER$HIS`

**Fields** (2):
-  `ACCOUNT`  Type: I-PHYSICAL.REF
-  `CURRENT.END.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'STANDING.ORDER'
-   INFO: LOCAL.REF fields found: ACCOUNT - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM STANDING_ORDER$HIS
WHERE ACCOUNT = 'VALUE123'
```

---

#### SELECT #120 - Line 396

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE WITH OFFSET.ACCOUNT EQ {Y.ACCOUNT.LIST} AND ( MATURITY.DATE GT {Y.ONE.YEAR} ) AND ( PAY.OPTION EQ 'RECURRING.PAYMENTS' ) AND ( SAVE.TEMPLATE NE 'YES' ) AND ( STATUS EQ '' )
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE WITH OFFSET.ACCOUNT EQ VALUE123 AND ( MATURITY.DATE GT VALUE123 ) AND ( PAY.OPTION EQ 'RECURRING.PAYMENTS' ) AND ( SAVE.TEMPLATE NE 'YES' ) AND ( STATUS EQ '' )
```

**Table**: `LATAM.ACH.CAPTURE`

**Fields** (1):
-  `OFFSET.ACCOUNT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE
WHERE OFFSET_ACCOUNT = 'VALUE123'
```

---

#### SELECT #121 - Line 400

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE$HIS WITH OFFSET.ACCOUNT EQ {Y.ACCOUNT.LIST} AND ( MATURITY.DATE GT {Y.ONE.YEAR} ) AND ( PAY.OPTION EQ 'RECURRING.PAYMENTS' ) AND ( SAVE.TEMPLATE NE 'YES' )
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE$HIS WITH OFFSET.ACCOUNT EQ VALUE123 AND ( MATURITY.DATE GT VALUE123 ) AND ( PAY.OPTION EQ 'RECURRING.PAYMENTS' ) AND ( SAVE.TEMPLATE NE 'YES' )
```

**Table**: `LATAM.ACH.CAPTURE$HIS`

**Fields** (1):
-  `OFFSET.ACCOUNT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'LATAM.ACH.CAPTURE'
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE$HIS
WHERE OFFSET_ACCOUNT = 'VALUE123'
```

---

#### SELECT #122 - Line 522

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER WITH DEBIT.ACCT.NO EQ {Y.ACCOUNT.LIST} AND PROCESSING.DATE GT {Y.ONE.YEAR} AND LT.BAN.TC.OPER EQ PAGOS-MISCTASBANESCOFUTURA.EJECUTAR PAGOS-RECARGAMISTARJETASFUTURA.EJECUTAR PAGOS-RECARGATDCBANESCOFUTURA.EJECUTAR PAGOS-TDCBANESCOFUTURA.EJECUTAR PAGOS-TDCMISTARJETASFUTURA.EJECU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER WITH DEBIT.ACCT.NO EQ VALUE123 AND PROCESSING.DATE GT VALUE123 AND LT.BAN.TC.OPER EQ PAGOS-MISCTASBANESCOFUTURA.EJECUTAR PAGOS-RECARGAMISTARJETASFUTURA.EJECUTAR PAGOS-RECARGATDCBANESCOFUTURA.EJECUTAR PAGOS-TDCBANESCOFUTURA.EJECUTAR PAGOS-TDCMISTARJETASFUTURA.EJECUTAR PAGOS-TE
```

**Table**: `FUNDS.TRANSFER`

**Fields** (3):
-  `LT.BAN.TC.OPER`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,54>`)
-  `DEBIT.ACCT.NO`  Type: D
-  `PROCESSING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.BAN.TC.OPER - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER
WHERE DEBIT_ACCT_NO = 'VALUE123' AND PROCESSING_DATE > 'VALUE123' AND LT_BAN_TC_OPER = 'PAGOS-MISCTASBANESCOFUTURA.EJECUTAR'
```

---

#### SELECT #123 - Line 527

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH DEBIT.ACCT.NO EQ {Y.ACCOUNT.LIST} WITH PROCESSING.DATE GT {Y.ONE.YEAR} AND LT.BAN.TC.OPER EQ PAGOS-MISCTASBANESCOFUTURA.EJECUTAR PAGOS-RECARGAMISTARJETASFUTURA.EJECUTAR PAGOS-RECARGATDCBANESCOFUTURA.EJECUTAR PAGOS-TDCBANESCOFUTURA.EJECUTAR PAGOS-TDCMISTARJETASFUTURA.
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH DEBIT.ACCT.NO EQ VALUE123 WITH PROCESSING.DATE GT VALUE123 AND LT.BAN.TC.OPER EQ PAGOS-MISCTASBANESCOFUTURA.EJECUTAR PAGOS-RECARGAMISTARJETASFUTURA.EJECUTAR PAGOS-RECARGATDCBANESCOFUTURA.EJECUTAR PAGOS-TDCBANESCOFUTURA.EJECUTAR PAGOS-TDCMISTARJETASFUTURA.EJECUTAR PAG
```

**Table**: `FUNDS.TRANSFER$HIS`

**Fields** (3):
-  `LT.BAN.TC.OPER`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,54>`)
-  `DEBIT.ACCT.NO`  Type: D
-  `PROCESSING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   INFO: LOCAL.REF fields found: LT.BAN.TC.OPER - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$HIS
WHERE DEBIT_ACCT_NO = 'VALUE123' AND PROCESSING_DATE > 'VALUE123' AND LT_BAN_TC_OPER = 'PAGOS-MISCTASBANESCOFUTURA.EJECUTAR'
```

---

#### SELECT #124 - Line 634

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE WITH OFFSET.ACCOUNT EQ {Y.ACCOUNT.LIST} AND ( MATURITY.DATE GT {Y.ONE.YEAR} ) AND LT.BAN.TC.OPER EQ PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR PAGOS-TDCOTROBANCOFUTURA.EJECUTAR PAGOS-TERCEROSOTROBANCOFUTURA.EJECUTAR
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE WITH OFFSET.ACCOUNT EQ VALUE123 AND ( MATURITY.DATE GT VALUE123 ) AND LT.BAN.TC.OPER EQ PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR PAGOS-TDCOTROBANCOFUTURA.EJECUTAR PAGOS-TERCEROSOTROBANCOFUTURA.EJECUTAR
```

**Table**: `LATAM.ACH.CAPTURE`

**Fields** (2):
-  `OFFSET.ACCOUNT`  Type: D
-  `LT.BAN.TC.OPER`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,2>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.BAN.TC.OPER - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE
WHERE OFFSET_ACCOUNT = 'VALUE123' AND LT_BAN_TC_OPER = 'PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR'
```

---

#### SELECT #125 - Line 639

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE$HIS WITH OFFSET.ACCOUNT EQ {Y.ACCOUNT.LIST} AND ( MATURITY.DATE GT {Y.ONE.YEAR} ) AND LT.BAN.TC.OPER EQ PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR PAGOS-TDCOTROBANCOFUTURA.EJECUTAR PAGOS-TERCEROSOTROBANCOFUTURA.EJECUTAR
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE$HIS WITH OFFSET.ACCOUNT EQ VALUE123 AND ( MATURITY.DATE GT VALUE123 ) AND LT.BAN.TC.OPER EQ PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR PAGOS-TDCOTROBANCOFUTURA.EJECUTAR PAGOS-TERCEROSOTROBANCOFUTURA.EJECUTAR
```

**Table**: `LATAM.ACH.CAPTURE$HIS`

**Fields** (2):
-  `OFFSET.ACCOUNT`  Type: D
-  `LT.BAN.TC.OPER`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,2>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'LATAM.ACH.CAPTURE'
-   INFO: LOCAL.REF fields found: LT.BAN.TC.OPER - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT.LIST, Y.ONE.YEAR

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE$HIS
WHERE OFFSET_ACCOUNT = 'VALUE123' AND LT_BAN_TC_OPER = 'PAGOS-MISCTASOTROBANCOFUTURA.EJECUTAR'
```

---

#### SELECT #126 - Line 1040

**File**: `BAN.E.NOF.TCIB.STO.b`

**Routine**: `BAN.E.NOF.TCIB.STO` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BAN.TCIB.TRAN.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BAN.TCIB.TRAN.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BAN.TCIB.TRAN.TYPE*%'
```

---

#### SELECT #127 - Line 107

**File**: `BAN.E.NOF.TCIB.TERM.b`

**Routine**: `BAN.E.NOF.TCIB.TERM` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE TCIBPLAZO...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE TCIBPLAZO...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'TCIBPLAZO%'
```

---

#### SELECT #128 - Line 172

**File**: `BAN.E.NOF.TXN.PENDING.CORPORATE.b`

**Routine**: `BAN.E.NOF.TXN.PENDING.CORPORATE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**Table**: `BAN.TCIB.OPERATION.REQUEST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

#### SELECT #129 - Line 158

**File**: `BAN.E.NOF.TXN.PENDING.PERSONAL.b`

**Routine**: `BAN.E.NOF.TXN.PENDING.PERSONAL` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.OPERATION.REQUEST
```

**Table**: `BAN.TCIB.OPERATION.REQUEST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_OPERATION_REQUEST
```

---

#### SELECT #130 - Line 165

**File**: `BAN.E.TCIB.BEN.LIST.b`

**Routine**: `BAN.E.TCIB.BEN.LIST` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BENEFICIARY WITH OWNING.CUSTOMER EQ {Y.OWNING.CUSTOMER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BENEFICIARY WITH OWNING.CUSTOMER EQ VALUE123
```

**Table**: `BENEFICIARY`

**Fields** (1):
-  `OWNING.CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.OWNING.CUSTOMER

**Translated SQL**:
```sql
SELECT *
FROM BENEFICIARY
WHERE OWNING_CUSTOMER = 'VALUE123'
```

---

#### SELECT #131 - Line 173

**File**: `BAN.I.ACT.API.TCIB.PERSONAL.b`

**Routine**: `BAN.I.ACT.API.TCIB.PERSONAL` (Unknown)

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.AA.PRODUCT.GROUP WITH (PRODUCT.LINE EQ ACCOUNTS) OR (PRODUCT.LINE EQ LENDING) OR (PRODUCT.LINE EQ DEPOSITS)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.PRODUCT.GROUP WITH (PRODUCT.LINE EQ ACCOUNTS) OR (PRODUCT.LINE EQ LENDING) OR (PRODUCT.LINE EQ DEPOSITS)
```

**Table**: `AA.PRODUCT.GROUP`

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_PRODUCT_GROUP
```

---

#### SELECT #132 - Line 161

**File**: `BAN.I.IBA.STO.DATA.b`

**Routine**: `BAN.I.IBA.STO.DATA` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE FREQUENCY*... AND OTHER.INFO EQ "{Y.FREQ}"
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE FREQUENCY*... AND OTHER.INFO EQ "VALUE123"
```

**Table**: `EB.LOOKUP`

**Fields** (2):
-  `OTHER.INFO`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FREQ

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'FREQUENCY*%' AND OTHER_INFO = 'VALUE123'
```

---

#### SELECT #133 - Line 123

**File**: `BAN.I.VAL.DUP.BENEF.b`

**Routine**: `BAN.I.VAL.DUP.BENEF` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BENEFICIARY WITH OWNING.CUSTOMER EQ {Y.OWN.CUSTOMER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BENEFICIARY WITH OWNING.CUSTOMER EQ VALUE123
```

**Table**: `BENEFICIARY`

**Fields** (1):
-  `OWNING.CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.OWN.CUSTOMER

**Translated SQL**:
```sql
SELECT *
FROM BENEFICIARY
WHERE OWNING_CUSTOMER = 'VALUE123'
```

---

#### SELECT #134 - Line 71

**File**: `BAN.ID.GENERATION.b`

**Routine**: `BAN.ID.GENERATION` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CASHPOOLING.INFO
```

**Table**: `BAN.CASHPOOLING.INFO`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_CASHPOOLING_INFO
```

---

#### SELECT #135 - Line 63

**File**: `BAN.S.GET.BANESCO.b`

**Routine**: `BAN.S.GET.BANESCO` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BC.SORT.CODE WITH LT.BANK.FROM EQ "PRP"
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BC.SORT.CODE WITH LT.BANK.FROM EQ "PRP"
```

**Table**: `BC.SORT.CODE`

**Fields** (1):
-  `LT.BANK.FROM`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.BANK.FROM - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM BC_SORT_CODE
WHERE LT_BANK_FROM = 'PRP'
```

---

#### SELECT #136 - Line 184

**File**: `BAN.S.GET.SIGNATURE.SCHEME.b`

**Routine**: `BAN.S.GET.SIGNATURE.SCHEME` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ {Y.PAYIN.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.PAYIN.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #137 - Line 95

**File**: `BAN.S.TCIB.SEND.NOTIFICATION.ID.b`

**Routine**: `BAN.S.TCIB.SEND.NOTIFICATION.ID` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.SEND.NOTIFICATION WITH @ID LIKE {Y.CUS.ID}-...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.SEND.NOTIFICATION WITH @ID LIKE VALUE123-...
```

**Table**: `BAN.TCIB.SEND.NOTIFICATION`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BAN.TCIB.SEND.NOTIFICATION' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.TCIB.SEND.NOTIFICATION
-   Unresolved variables: Y.CUS.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_SEND_NOTIFICATION
WHERE ID LIKE 'VALUE123-%'
```

---

#### SELECT #138 - Line 121

**File**: `BAN.TCIB.B.RELEASE.AFFILIATION.b`

**Routine**: `BAN.TCIB.B.RELEASE.AFFILIATION` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AUTH.CODE WITH AUTH.STATUS LIKE Blo... Dif... BLO... DIF...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AUTH.CODE WITH AUTH.STATUS LIKE Blo... Dif... BLO... DIF...
```

**Table**: `BAN.TCIB.AUTH.CODE`

**Fields** (1):
-  `AUTH.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AUTH_CODE
WHERE AUTH_STATUS LIKE 'Blo%'
```

---

#### SELECT #139 - Line 193

**File**: `BAN.TCIB.B.RELEASE.AFFILIATION.b`

**Routine**: `BAN.TCIB.B.RELEASE.AFFILIATION` (BATCH (inferred))

**Variable**: `Y.SEL.CMD1`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AUTH.CODE WITH AUTH.STATUS LIKE Blo... Dif... BLO... DIF... AND USER.EXT EQ {Y.AFFILI.EXTERN.USER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AUTH.CODE WITH AUTH.STATUS LIKE Blo... Dif... BLO... DIF... AND USER.EXT EQ VALUE123
```

**Table**: `BAN.TCIB.AUTH.CODE`

**Fields** (2):
-  `AUTH.STATUS`  Type: D
-  `USER.EXT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AFFILI.EXTERN.USER

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AUTH_CODE
WHERE AUTH_STATUS LIKE 'Blo%' AND USER_EXT = 'VALUE123'
```

---

#### SELECT #140 - Line 221

**File**: `BAN.V.GET.EXTRAFIN.ACCT.FT.b`

**Routine**: `BAN.V.GET.EXTRAFIN.ACCT.FT` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE EB.CARD.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE EB.CARD.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'EB.CARD.TYPE*%'
```

---

#### SELECT #141 - Line 51

**File**: `BAPA.M.MTN99.FILL.SWIFT.BOOK.b`

**Routine**: `BAPA.M.MTN99.FILL.SWIFT.BOOK` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.DE.BIC NE TRCKCHZZXXX
```

**SIMULATED AT RUNTIME**:
```
SELECT F.DE.BIC NE TRCKCHZZXXX
```

**Table**: `DE.BIC`

**TAFJ Compatible**:  No

**Warnings**:
-  CRITICAL SYNTAX ERROR: Operator 'NE' without WITH clause - Missing field name. Should be: SELECT F.DE.BIC WITH <field_name> NE ...

**Translated SQL**:
```sql
SELECT *
FROM DE_BIC
```

---

#### SELECT #142 - Line 126

**File**: `BPA.E.NOF.TC.LIMIT.DETAILS.b`

**Routine**: `BPA.E.NOF.TC.LIMIT.DETAILS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LIMIT WITH LIABILITY.NUMBER EQ {Y.LIABILITY.NUMBER} WITH RECORD.PARENT EQ {Y.LIM.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LIMIT WITH LIABILITY.NUMBER EQ VALUE123 WITH RECORD.PARENT EQ VALUE123
```

**Table**: `LIMIT`

**Fields** (2):
-  `RECORD.PARENT`  Type: D
-  `LIABILITY.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LIABILITY.NUMBER, Y.LIM.ID

**Translated SQL**:
```sql
SELECT *
FROM LIMIT
WHERE LIABILITY_NUMBER = 'VALUE123' AND RECORD_PARENT = 'VALUE123'
```

---

#### SELECT #143 - Line 76

**File**: `BPA.E.NOF.UPDATE.TCIB.CUSTOMER.b`

**Routine**: `BPA.E.NOF.UPDATE.TCIB.CUSTOMER` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CUSTOMER$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER$NAU
```

**Table**: `CUSTOMER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CUSTOMER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER$NAU
```

---

#### SELECT #144 - Line 124

**File**: `BAN.E.NOF.TCIB.CHQ.DET.EXT.b`

**Routine**: `BAN.E.NOF.TCIB.CHQ.DET.EXT` (NOFILE (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {FIELD(Y.CHQ.BOOK.ID,'.',1)}.{FIELD(Y.CHQ.BOOK.ID,'.',2)}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {FIELD(Y.CHQ.BOOK.ID,'.',1)}.{FIELD(Y.CHQ.BOOK.ID,'.',2)}...
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FIELD(Y.CHQ.BOOK.ID,'.',1), FIELD(Y.CHQ.BOOK.ID,'.',2)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE ID LIKE '%{FIELD(Y.CHQ.BOOK.ID,%'
```

---

#### SELECT #145 - Line 27

**File**: `BAPA.B.ENRICHMENT.DEP.SELECT.b`

**Routine**: `BAPA.B.ENRICHMENT.DEP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAPA.TRANS.ENRICHMENT WITH ESTATUS NE D AND FECHA LT {Y.DATE.CUTOFF}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.TRANS.ENRICHMENT WITH ESTATUS NE D AND FECHA LT VALUE123
```

**Table**: `BAPA.TRANS.ENRICHMENT`

**Fields** (2):
-  `ESTATUS`  Type: D
-  `FECHA`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATE.CUTOFF

**Translated SQL**:
```sql
SELECT *
FROM BAPA_TRANS_ENRICHMENT
WHERE ESTATUS != 'D' AND FECHA < 'VALUE123'
```

---

#### SELECT #146 - Line 34

**File**: `BAPA.B.EX.ENRI.UPD.SELECT.b`

**Routine**: `BAPA.B.EX.ENRI.UPD.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAPA.EX.ACCOUNT.PARAM WITH @ID NE SYSTEM
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.EX.ACCOUNT.PARAM WITH @ID NE SYSTEM
```

**Table**: `BAPA.EX.ACCOUNT.PARAM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAPA_EX_ACCOUNT_PARAM
WHERE ID != 'SYSTEM'
```

---

#### SELECT #147 - Line 28

**File**: `BAPA.B.EX.ENRICH.SELECT.b`

**Routine**: `BAPA.B.EX.ENRICH.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACCT.ENT.LWORK.DAY
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCT.ENT.LWORK.DAY
```

**Table**: `ACCT.ENT.LWORK.DAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCT_ENT_LWORK_DAY
```

---

#### SELECT #148 - Line 38

**File**: `BAPA.B.EX.ENRICH.SELECT.b`

**Routine**: `BAPA.B.EX.ENRICH.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACCT.ENT.TODAY
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCT.ENT.TODAY
```

**Table**: `ACCT.ENT.TODAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCT_ENT_TODAY
```

---

#### SELECT #149 - Line 54

**File**: `BAN.M.BEN.CUSTOMER.NAME.b`

**Routine**: `BAN.M.BEN.CUSTOMER.NAME` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BENEFICIARY WITH BEN.CUSTOMER
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BENEFICIARY WITH BEN.CUSTOMER
```

**Table**: `BENEFICIARY`

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BENEFICIARY
```

---

#### SELECT #150 - Line 115

**File**: `BAPA.I.SWIFT.MT103.CAMPO52.b`

**Routine**: `BAPA.I.SWIFT.MT103.CAMPO52` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.DE.BIC WITH @ID LIKE ...XXX AND INSTITUTION EQ '{Y.SWIFT.CODE}'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.DE.BIC WITH @ID LIKE ...XXX AND INSTITUTION EQ 'VALUE123'
```

**Table**: `DE.BIC`

**Fields** (2):
-  `INSTITUTION`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'INSTITUTION' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ORDERING.BANK

**Translated SQL**:
```sql
SELECT *
FROM DE_BIC
WHERE ID LIKE '%XXX' AND INSTITUTION = 'VALUE123'
```

---

#### SELECT #151 - Line 130

**File**: `BAPA.PARAM.LIMIT.DAILY.RESET.b`

**Routine**: `BAPA.PARAM.LIMIT.DAILY.RESET` (Unknown)

**Variable**: `SelectStatement`

**AS PER CODE**:
```
SELECT {fnBapa}
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.PARAM.LIMIT.BICS
```

**Table**: `EB.BAPA.PARAM.LIMIT.BICS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_PARAM_LIMIT_BICS
```

---

#### SELECT #152 - Line 70

**File**: `BAPA.V.PP.DEV.DETAILS.b`

**Routine**: `BAPA.V.PP.DEV.DETAILS` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.POR.TRANSACTION WITH CustomerSpecifiedReference EQ {Y.ID.PO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.POR.TRANSACTION WITH CustomerSpecifiedReference EQ VALUE123
```

**Table**: `POR.TRANSACTION`

**Fields** (1):
-  `CustomerSpecifiedReference`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID.PO

**Translated SQL**:
```sql
SELECT *
FROM POR_TRANSACTION
WHERE CustomerSpecifiedReference = 'VALUE123'
```

---

#### SELECT #153 - Line 551

**File**: `BAPA.V.PP.LIMIT.CORRES.b`

**Routine**: `BAPA.V.PP.LIMIT.CORRES` (VERSION (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.PP.LORO.NOSTRO.ACCOUNT WITH @ID LIKE '{Y.BIC.ID}.N.{Y.CCY}...' BY @ID DESC
```

**SIMULATED AT RUNTIME**:
```
SELECT F.PP.LORO.NOSTRO.ACCOUNT WITH @ID LIKE 'BKTRUS33XXX.N.USD...' BY @ID DESC
```

**Table**: `PP.LORO.NOSTRO.ACCOUNT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM PP_LORO_NOSTRO_ACCOUNT
WHERE ID LIKE 'BKTRUS33XXX.N.USD%'
ORDER BY ID ASC
```

---

#### SELECT #154 - Line 69

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE {Y.TXN.REF}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123...
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (1):
-  `TXN.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TXN.REF' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TXN.REF

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE TXN_REF LIKE 'VALUE123%'
```

---

#### SELECT #155 - Line 80

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.DATE EQ {Y.TXN.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.DATE EQ VALUE123
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (1):
-  `TXN.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TXN.DATE' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TXN.DATE

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE TXN_DATE = 'VALUE123'
```

---

#### SELECT #156 - Line 107

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH UETR.REF EQ {Y.UETR.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH UETR.REF EQ VALUE123
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (1):
-  `UETR.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'UETR.REF' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.UETR.REF

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE UETR_REF = 'VALUE123'
```

---

#### SELECT #157 - Line 156

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE {Y.TXN.REF}... AND TXN.DATE EQ {Y.TXN.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123... AND TXN.DATE EQ VALUE123
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (2):
-  `TXN.DATE`  Type: D
-  `TXN.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TXN.DATE' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TXN.REF' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TXN.REF, Y.TXN.DATE

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE TXN_REF LIKE 'VALUE123%' AND TXN_DATE = 'VALUE123'
```

---

#### SELECT #158 - Line 168

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE {Y.TXN.REF}... AND UETR.REF EQ {Y.UETR.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123... AND UETR.REF EQ VALUE123
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (2):
-  `UETR.REF`  Type: D
-  `TXN.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'UETR.REF' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TXN.REF' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TXN.REF, Y.UETR.REF

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE TXN_REF LIKE 'VALUE123%' AND UETR_REF = 'VALUE123'
```

---

#### SELECT #159 - Line 179

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.DATE EQ {Y.TXN.DATE} AND UETR.REF EQ {Y.UETR.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.DATE EQ VALUE123 AND UETR.REF EQ VALUE123
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (2):
-  `TXN.DATE`  Type: D
-  `UETR.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TXN.DATE' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'UETR.REF' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TXN.DATE, Y.UETR.REF

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE TXN_DATE = 'VALUE123' AND UETR_REF = 'VALUE123'
```

---

#### SELECT #160 - Line 206

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE {Y.TXN.REF}... AND TXN.DATE EQ {Y.TXN.DATE} AND UETR.REF EQ {Y.UETR.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS WITH TXN.REF LIKE VALUE123... AND TXN.DATE EQ VALUE123 AND UETR.REF EQ VALUE123
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**Fields** (3):
-  `TXN.DATE`  Type: D
-  `UETR.REF`  Type: D
-  `TXN.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TXN.DATE' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'UETR.REF' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'TXN.REF' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TXN.REF, Y.TXN.DATE, Y.UETR.REF

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
WHERE TXN_REF LIKE 'VALUE123%' AND TXN_DATE = 'VALUE123' AND UETR_REF = 'VALUE123'
```

---

#### SELECT #161 - Line 217

**File**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS.b`

**Routine**: `BAPA.E.TC.FT.INTL.TRACK.DETAILS` (ENQUIRY (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TC.FT.INTL.TRACK.DETAILS
```

**Table**: `BPA.TC.FT.INTL.TRACK.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_TC_FT_INTL_TRACK_DETAILS
```

---

#### SELECT #162 - Line 20

**File**: `B.BAPA.ACH.FILE.UPLOD.SELECT.b`

**Routine**: `B.BAPA.ACH.FILE.UPLOD.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnEbFileUpload()} WITH UPLOAD.TYPE EQ 'BAPA.ORIGINADORES' AND BAPA.ACH.MAST EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.FILE.UPLOAD WITH UPLOAD.TYPE EQ 'BAPA.ORIGINADORES' AND BAPA.ACH.MAST EQ ''
```

**Table**: `EB.FILE.UPLOAD`

**Fields** (2):
-  `BAPA.ACH.MAST`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)
-  `UPLOAD.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: BAPA.ACH.MAST - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM EB_FILE_UPLOAD
WHERE UPLOAD_TYPE = 'BAPA.ORIGINADORES'
```

---

#### SELECT #163 - Line 20

**File**: `BACM3M.B.FINAL.FILE.GEN.RED.SELECT.b`

**Routine**: `BACM3M.B.FINAL.FILE.GEN.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.DATA.FINAL.GEN
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.DATA.FINAL.GEN
```

**Table**: `BACM3M.DATA.FINAL.GEN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_DATA_FINAL_GEN
```

---

#### SELECT #164 - Line 64

**File**: `BACM3M.B.RE.LINE.WORKFILE.RED.SELECT.b`

**Routine**: `BACM3M.B.RE.LINE.WORKFILE.RED.SELECT` (BATCH (inferred))

**Variable**: `STAT.SEL.CMD`

**AS PER CODE**:
```
SELECT RE.STAT.LINE.CONT WITH RECID LIKE {yCompanyIDCountry}... AND TYPE EQ DETAIL
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.STAT.LINE.CONT WITH RECID LIKE {yCompanyIDCountry}... AND TYPE EQ DETAIL
```

**Table**: `RE.STAT.LINE.CONT`

**Fields** (2):
-  `RECID`  Type: Unknown
-  `TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_LINE_CONT
WHERE RECID LIKE '{yCompanyIDCountry}%' AND TYPE = 'DETAIL'
```

---

#### SELECT #165 - Line 21

**File**: `BACM3M.B.SUM.ACCOUNTING.RED.SELECT.b`

**Routine**: `BACM3M.B.SUM.ACCOUNTING.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...{Y.DATE.FINAL}
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...VALUE123
```

**Table**: `BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATE.FINAL

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE ID LIKE '%VALUE123'
```

---

#### SELECT #166 - Line 66

**File**: `BACM3M.B.TXNS.ACCT.ID.b`

**Routine**: `BACM3M.B.TXNS.ACCT.ID` (BATCH (inferred))

**Variable**: `SEL.CMD.XRF`

**AS PER CODE**:
```
SELECT STMT.ENTRY.DETAIL.XREF WITH @ID LIKE '{Y.LWORK.ID}...'
```

**SIMULATED AT RUNTIME**:
```
SELECT STMT.ENTRY.DETAIL.XREF WITH @ID LIKE '{y.Lwork.ID}...'
```

**Table**: `STMT.ENTRY.DETAIL.XREF`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM STMT_ENTRY_DETAIL_XREF
WHERE ID LIKE '{y.Lwork.ID}%'
```

---

#### SELECT #167 - Line 132

**File**: `BACM3M.B.TXNS.ACCT.ID.b`

**Routine**: `BACM3M.B.TXNS.ACCT.ID` (BATCH (inferred))

**Variable**: `SEL.CMD.XRF`

**AS PER CODE**:
```
SELECT CATEG.ENTRY.DETAIL.XREF WITH @ID LIKE '{Y.LWORK.ID}...'
```

**SIMULATED AT RUNTIME**:
```
SELECT CATEG.ENTRY.DETAIL.XREF WITH @ID LIKE '{y.Lwork.ID}...'
```

**Table**: `CATEG.ENTRY.DETAIL.XREF`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CATEG_ENTRY_DETAIL_XREF
WHERE ID LIKE '{y.Lwork.ID}%'
```

---

#### SELECT #168 - Line 199

**File**: `BACM3M.B.TXNS.ACCT.ID.b`

**Routine**: `BACM3M.B.TXNS.ACCT.ID` (BATCH (inferred))

**Variable**: `SEL.CMD.XRF`

**AS PER CODE**:
```
SELECT RE.SPEC.ENTRY.XREF WITH @ID LIKE '{Y.LWORK.ID}...'
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.SPEC.ENTRY.XREF WITH @ID LIKE '{y.Lwork.ID}...'
```

**Table**: `RE.SPEC.ENTRY.XREF`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM RE_SPEC_ENTRY_XREF
WHERE ID LIKE '{y.Lwork.ID}%'
```

---

#### SELECT #169 - Line 56

**File**: `BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Routine**: `BACM3M.B.TXNS.ACCT.ID.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACCT.ENT.LWORK.DAY
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCT.ENT.LWORK.DAY
```

**Table**: `ACCT.ENT.LWORK.DAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCT_ENT_LWORK_DAY
```

---

#### SELECT #170 - Line 63

**File**: `BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Routine**: `BACM3M.B.TXNS.ACCT.ID.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CATEG.ENT.LWORK.DAY
```

**SIMULATED AT RUNTIME**:
```
SELECT CATEG.ENT.LWORK.DAY
```

**Table**: `CATEG.ENT.LWORK.DAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CATEG_ENT_LWORK_DAY
```

---

#### SELECT #171 - Line 70

**File**: `BACM3M.B.TXNS.ACCT.ID.SELECT.b`

**Routine**: `BACM3M.B.TXNS.ACCT.ID.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT RE.SPEC.ENT.LWORK.DAY
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.SPEC.ENT.LWORK.DAY
```

**Table**: `RE.SPEC.ENT.LWORK.DAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM RE_SPEC_ENT_LWORK_DAY
```

---

#### SELECT #172 - Line 57

**File**: `BACM3M.B.TXNS.SELECT.CATEG.RED.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECT.CATEG.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.ID WITH @ID LIKE {Y.FILE.NA}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.ID WITH @ID LIKE CATEG...
```

**Table**: `BACM3M.ACCOUNTING.TXNS.ID`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BACM3M.ACCOUNTING.TXNS.ID' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BACM3M.ACCOUNTING.TXNS.ID

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_ID
WHERE ID LIKE 'CATEG%'
```

---

#### SELECT #173 - Line 66

**File**: `BACM3M.B.TXNS.SELECT.COLLECT.RED.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECT.COLLECT.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.OUT.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.OUT.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #174 - Line 60

**File**: `BACM3M.B.TXNS.SELECT.CONSOL.RED.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECT.CONSOL.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.ID WITH @ID LIKE {Y.FILE.NA}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.ID WITH @ID LIKE CONSOL...
```

**Table**: `BACM3M.ACCOUNTING.TXNS.ID`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BACM3M.ACCOUNTING.TXNS.ID' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BACM3M.ACCOUNTING.TXNS.ID

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_ID
WHERE ID LIKE 'CONSOL%'
```

---

#### SELECT #175 - Line 64

**File**: `BACM3M.B.TXNS.SELECT.FINAL.RED.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECT.FINAL.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...{Y.LWD} BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...VALUE123 BY @ID
```

**Table**: `BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LWD

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE ID LIKE '%VALUE123'
ORDER BY ID ASC
```

---

#### SELECT #176 - Line 62

**File**: `BACM3M.B.TXNS.SELECT.STMT.RED.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECT.STMT.RED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.ID WITH @ID LIKE {Y.FILE.NA}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.ID WITH @ID LIKE STMT...
```

**Table**: `BACM3M.ACCOUNTING.TXNS.ID`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BACM3M.ACCOUNTING.TXNS.ID' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BACM3M.ACCOUNTING.TXNS.ID

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_ID
WHERE ID LIKE 'STMT%'
```

---

#### SELECT #177 - Line 63

**File**: `BACM3M.B.VAL.INI.ACCOUNTING.RED.b`

**Routine**: `BACM3M.B.VAL.INI.ACCOUNTING.RED` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BATCH WITH @ID LIKE {Y.CMP.MNE}/... AND BATCH.STAGE NE "" AND PROCESS.STATUS NE 0
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BATCH WITH @ID LIKE VALUE123/... AND BATCH.STAGE NE "" AND PROCESS.STATUS NE 0
```

**Table**: `BATCH`

**Fields** (3):
-  `BATCH.STAGE`  Type: D
-  `PROCESS.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CMP.MNE

**Translated SQL**:
```sql
SELECT *
FROM BATCH
WHERE ID LIKE 'VALUE123/%' AND PROCESS_STATUS != '0'
```

---

#### SELECT #178 - Line 31

**File**: `BACM3M.CONSOL.RE.ENTRIES.b`

**Routine**: `BACM3M.CONSOL.RE.ENTRIES` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.RE.STAT.LINE.CONT WITH TYPE EQ DETAIL
```

**SIMULATED AT RUNTIME**:
```
SELECT F.RE.STAT.LINE.CONT WITH TYPE EQ DETAIL
```

**Table**: `RE.STAT.LINE.CONT`

**Fields** (1):
-  `TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_LINE_CONT
WHERE TYPE = 'DETAIL'
```

---

#### SELECT #179 - Line 35

**File**: `BAN.AA.ACCT.CLOSE.SELECT.b`

**Routine**: `BAN.AA.ACCT.CLOSE.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CLOSE.ACCT.DET WITH STATUS EQ "PENDING"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CLOSE.ACCT.DET WITH STATUS EQ "PENDING"
```

**Table**: `BAN.CLOSE.ACCT.DET`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CLOSE_ACCT_DET
WHERE STATUS = 'PENDING'
```

---

#### SELECT #180 - Line 35

**File**: `BAN.AA.ACCT.CREATE.SELECT.b`

**Routine**: `BAN.AA.ACCT.CREATE.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS EQ "PROCESSED" AND ACCOUNT.UPLOAD EQ "NEW"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS EQ "PROCESSED" AND ACCOUNT.UPLOAD EQ "NEW"
```

**Table**: `BAN.CREATE.CUS.ACC`

**Fields** (2):
-  `ACCOUNT.UPLOAD`  Type: D
-  `PROCESS.CUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
WHERE PROCESS_CUS = 'PROCESSED' AND ACCOUNT_UPLOAD = 'NEW'
```

---

#### SELECT #181 - Line 118

**File**: `BAN.AA.UPD.FREQ.ACCT.b`

**Routine**: `BAN.AA.UPD.FREQ.ACCT` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.AA.CHG.PENDING WITH ARRANGEMENT EQ {Y.ID.ARRANGEMENT} AND SETTLE.STATUS EQ 'PENDING'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.AA.CHG.PENDING WITH ARRANGEMENT EQ VALUE123 AND SETTLE.STATUS EQ 'PENDING'
```

**Table**: `BAN.AA.CHG.PENDING`

**Fields** (2):
-  `SETTLE.STATUS`  Type: D
-  `ARRANGEMENT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID.ARRANGEMENT

**Translated SQL**:
```sql
SELECT *
FROM BAN_AA_CHG_PENDING
WHERE ARRANGEMENT = 'VALUE123' AND SETTLE_STATUS = 'PENDING'
```

---

#### SELECT #182 - Line 34

**File**: `BAN.ACC.CHECK.SELECT.b`

**Routine**: `BAN.ACC.CHECK.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CREATE.CUS.ACC WITH (CUSTOMER.LOAD EQ "NEW" OR CUSTOMER.LOAD EQ "NOT NEW" OR CUSTOMER.LOAD EQ "UPDATE") AND PROCESS.CUS EQ "PROCESSED"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CREATE.CUS.ACC WITH (CUSTOMER.LOAD EQ "NEW" OR CUSTOMER.LOAD EQ "NOT NEW" OR CUSTOMER.LOAD EQ "UPDATE") AND PROCESS.CUS EQ "PROCESSED"
```

**Table**: `BAN.CREATE.CUS.ACC`

**Fields** (2):
-  `PROCESS.CUS`  Type: D
-  `CUSTOMER.LOAD`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
WHERE PROCESS_CUS = 'PROCESSED'
```

---

#### SELECT #183 - Line 73

**File**: `BAN.B.AA.CHG.SETTLE.LOAD.b`

**Routine**: `BAN.B.AA.CHG.SETTLE.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TAX
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TAX
```

**Table**: `TAX`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM TAX
```

---

#### SELECT #184 - Line 59

**File**: `BAN.B.AA.CHG.SETTLE.SELECT.b`

**Routine**: `BAN.B.AA.CHG.SETTLE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT POSTING.RESTRICT WITH RESTRICTION.TYPE EQ "ALL" OR RESTRICTION.TYPE EQ "DEBIT" AND TXN.CODE NE ""
```

**SIMULATED AT RUNTIME**:
```
SELECT POSTING.RESTRICT WITH RESTRICTION.TYPE EQ "ALL" OR RESTRICTION.TYPE EQ "DEBIT" AND TXN.CODE NE ""
```

**Table**: `POSTING.RESTRICT`

**Fields** (2):
-  `TXN.CODE`  Type: D
-  `RESTRICTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'TXN.CODE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM POSTING_RESTRICT
WHERE RESTRICTION_TYPE = 'ALL'
```

---

#### SELECT #185 - Line 211

**File**: `BAN.B.AA.CHG.SETTLE.SELECT.b`

**Routine**: `BAN.B.AA.CHG.SETTLE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.AA.T.CHG.PENDING
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.AA.T.CHG.PENDING
```

**Table**: `BAN.AA.T.CHG.PENDING`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

#### SELECT #186 - Line 24

**File**: `BAN.B.DEL.RECORD.LOCK.SELECT.b`

**Routine**: `BAN.B.DEL.RECORD.LOCK.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnRecordLock()}
```

**SIMULATED AT RUNTIME**:
```
SELECT RECORD.LOCK
```

**Table**: `RECORD.LOCK`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM RECORD_LOCK
```

---

#### SELECT #187 - Line 39

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Routine**: `BAN.B.DELETE.TXN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TELLER$NAU WITH TFS.REFERENCE EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER$NAU WITH TFS.REFERENCE EQ ''
```

**Table**: `TELLER$NAU`

**Fields** (1):
-  `TFS.REFERENCE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'TELLER'

**Translated SQL**:
```sql
SELECT *
FROM TELLER$NAU
```

---

#### SELECT #188 - Line 44

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Routine**: `BAN.B.DELETE.TXN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FUNDS.TRANSFER$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER$NAU
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #189 - Line 49

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Routine**: `BAN.B.DELETE.TXN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TELLER.FINANCIAL.SERVICES$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER.FINANCIAL.SERVICES$NAU
```

**Table**: `TELLER.FINANCIAL.SERVICES$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'TELLER.FINANCIAL.SERVICES'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM TELLER_FINANCIAL_SERVICES$NAU
```

---

#### SELECT #190 - Line 58

**File**: `BAN.B.DELETE.TXN.SELECT.b`

**Routine**: `BAN.B.DELETE.TXN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.{Y.APP.ID}$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.VALUE123$NAU
```

**Table**: `VALUE123$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'VALUE123'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123

**Translated SQL**:
```sql
SELECT *
FROM VALUE123$NAU
```

---

#### SELECT #191 - Line 54

**File**: `BAN.B.MOV.LOCKED.REV.SELECT.b`

**Routine**: `BAN.B.MOV.LOCKED.REV.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.MOV.LOCKED WITH @ID LIKE {Y.LAST.WORKING.DAY}-...
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.MOV.LOCKED WITH @ID LIKE VALUE123-...
```

**Table**: `BAN.MOV.LOCKED`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LAST.WORKING.DAY

**Translated SQL**:
```sql
SELECT *
FROM BAN_MOV_LOCKED
WHERE ID LIKE 'VALUE123-%'
```

---

#### SELECT #192 - Line 51

**File**: `BAN.B.MOV.LOCKED.SELECT.b`

**Routine**: `BAN.B.MOV.LOCKED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AC.LOCKED.EVENTS
```

**SIMULATED AT RUNTIME**:
```
SELECT AC.LOCKED.EVENTS
```

**Table**: `AC.LOCKED.EVENTS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
```

---

#### SELECT #193 - Line 60

**File**: `BAN.B.MOV.LOCKED.SELECT.b`

**Routine**: `BAN.B.MOV.LOCKED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.MOV.LOCKED WITH @ID LIKE '{EB.SystemTables.getToday()}-...'
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.MOV.LOCKED WITH @ID LIKE 'TODAY-...'
```

**Table**: `BAN.MOV.LOCKED`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_MOV_LOCKED
WHERE ID LIKE 'TODAY-%'
```

---

#### SELECT #194 - Line 45

**File**: `BAN.B.RC.DETAIL.SELECT.b`

**Routine**: `BAN.B.RC.DETAIL.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnBanRcDetail()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.RC.DETAIL
```

**Table**: `BAN.RC.DETAIL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAN.RC.DETAIL' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.RC.DETAIL

**Translated SQL**:
```sql
SELECT *
FROM BAN_RC_DETAIL
```

---

#### SELECT #195 - Line 54

**File**: `BAN.B.RC.DETAIL.SELECT.b`

**Routine**: `BAN.B.RC.DETAIL.SELECT` (BATCH (inferred))

**Variable**: `SELECT.EB.LOOKUP`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnEbLookup()} WITH @ID LIKE BAN.RC.DETAIL.PAY...
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.LOOKUP WITH @ID LIKE BAN.RC.DETAIL.PAY...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BAN.RC.DETAIL.PAY%'
```

---

#### SELECT #196 - Line 80

**File**: `BAN.B.RC.DETAIL.SELECT.b`

**Routine**: `BAN.B.RC.DETAIL.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnRcDetail()}{Y.TRAMA0}{Y.TRAMA1}
```

**SIMULATED AT RUNTIME**:
```
SELECT RC.DETAIL WITH TXN.TYPE EQ SAMPLE_VALUEVALUE123
```

**Table**: `RC.DETAIL`

**Fields** (1):
-  `TXN.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: TXN.TYPE, Y.TRAMA1

**Translated SQL**:
```sql
SELECT *
FROM RC_DETAIL
WHERE TXN_TYPE = 'SAMPLE_VALUEVALUE123'
```

---

#### SELECT #197 - Line 65

**File**: `BAN.B.RC.TIMBRES.POST.b`

**Routine**: `BAN.B.RC.TIMBRES.POST` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_65`

**AS PER CODE**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SIMULATED AT RUNTIME**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**Table**: `Y.TEMP.FILE.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'Y.TEMP.FILE.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/Y.TEMP.FILE.POINTER

**Translated SQL**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

#### SELECT #198 - Line 43

**File**: `BAN.B.RC.TIMBRES.SELECT.b`

**Routine**: `BAN.B.RC.TIMBRES.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS EQ AUTH
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS EQ AUTH
```

**Table**: `AA.ARRANGEMENT`

**Fields** (2):
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ARR_STATUS = 'AUTH'
```

---

#### SELECT #199 - Line 48

**File**: `BAN.B.UPD.FQU.CHG.b`

**Routine**: `BAN.B.UPD.FQU.CHG` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.AA.CHG.PENDING WITH ARRANGEMENT EQ {R.ACC<AC.AccountOpening.Account.ArrangementId>} AND SETTLE.STATUS EQ 'PENDING'
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.AA.CHG.PENDING WITH ARRANGEMENT EQ {R.ACC<AC.AccountOpening.Account.ArrangementId>} AND SETTLE.STATUS EQ 'PENDING'
```

**Table**: `BAN.AA.CHG.PENDING`

**Fields** (2):
-  `SETTLE.STATUS`  Type: D
-  `ARRANGEMENT`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_AA_CHG_PENDING
WHERE ARRANGEMENT = '{R.ACC<AC.AccountOpening.Account.ArrangementId>}' AND SETTLE_STATUS = 'PENDING'
```

---

#### SELECT #200 - Line 79

**File**: `BAN.CLEAR.FILES.SELECT.b`

**Routine**: `BAN.CLEAR.FILES.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.AC.AUTO.PYMT.STOP
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.AC.AUTO.PYMT.STOP
```

**Table**: `BAN.AC.AUTO.PYMT.STOP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_AC_AUTO_PYMT_STOP
```

---

#### SELECT #201 - Line 21

**File**: `BAN.CLEAR.T.CHG.PENDING.SELECT.b`

**Routine**: `BAN.CLEAR.T.CHG.PENDING.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.AA.T.CHG.PENDING WITH PENDING.BILL EQ '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.AA.T.CHG.PENDING WITH PENDING.BILL EQ '' 
```

**Table**: `BAN.AA.T.CHG.PENDING`

**Fields** (1):
-  `PENDING.BILL`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

#### SELECT #202 - Line 49

**File**: `BAN.CUS.ACC.MOVE.b`

**Routine**: `BAN.CUS.ACC.MOVE` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CREATE.CUS.ACC
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CREATE.CUS.ACC
```

**Table**: `BAN.CREATE.CUS.ACC`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
```

---

#### SELECT #203 - Line 31

**File**: `BAN.CUS.CHECK.SELECT.b`

**Routine**: `BAN.CUS.CHECK.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS NE "PROCESSED"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS NE "PROCESSED"
```

**Table**: `BAN.CREATE.CUS.ACC`

**Fields** (1):
-  `PROCESS.CUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
WHERE PROCESS_CUS != 'PROCESSED'
```

---

#### SELECT #204 - Line 31

**File**: `BAN.CUS.CREATE.SELECT.b`

**Routine**: `BAN.CUS.CREATE.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CREATE.CUS.ACC WITH (CUSTOMER.LOAD EQ "NEW" OR CUSTOMER.LOAD EQ "NOT NEW" OR CUSTOMER.LOAD EQ "UPDATE") AND PROCESS.CUS NE "PROCESSED"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CREATE.CUS.ACC WITH (CUSTOMER.LOAD EQ "NEW" OR CUSTOMER.LOAD EQ "NOT NEW" OR CUSTOMER.LOAD EQ "UPDATE") AND PROCESS.CUS NE "PROCESSED"
```

**Table**: `BAN.CREATE.CUS.ACC`

**Fields** (2):
-  `PROCESS.CUS`  Type: D
-  `CUSTOMER.LOAD`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
WHERE PROCESS_CUS != 'PROCESSED'
```

---

#### SELECT #205 - Line 154

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Routine**: `BAN.E.BLD.FT.PEND.TCIB` (ENQUIRY (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ {EB.Reports.getDRangeAndValue()<APPL.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ {EB.Reports.getDRangeAndValue()<APPL.POS>}
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #206 - Line 179

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Routine**: `BAN.E.BLD.FT.PEND.TCIB` (ENQUIRY (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ {Y.SEL.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ VALUE123
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.SEL.ID

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #207 - Line 202

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Routine**: `BAN.E.BLD.FT.PEND.TCIB` (ENQUIRY (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ {Y.SEL.ID} AND CO.CODE EQ {EB.SystemTables.getIdCompany()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ VALUE123 AND CO.CODE EQ ID.COMPANY
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (1):
-  `CO.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.SEL.ID

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE CO_CODE = 'ID.COMPANY'
```

---

#### SELECT #208 - Line 228

**File**: `BAN.E.BLD.FT.PEND.TCIB.b`

**Routine**: `BAN.E.BLD.FT.PEND.TCIB` (ENQUIRY (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ {Y.SEL.ID} AND CO.CODE EQ {EB.SystemTables.getIdCompany()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU TRANSACTION.TYPE EQ VALUE123 AND CO.CODE EQ ID.COMPANY
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (1):
-  `CO.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.SEL.ID

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE CO_CODE = 'ID.COMPANY'
```

---

#### SELECT #209 - Line 64

**File**: `BAN.E.CONV.TCMB.SALDO.DIFERIDO.b`

**Routine**: `BAN.E.CONV.TCMB.SALDO.DIFERIDO` (ENQUIRY (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED CLEARING AND CREDIT.ACC.NO EQ {Y.ACCOUNT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED CLEARING AND CREDIT.ACC.NO EQ VALUE123
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `CREDIT.ACC.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCOUNT.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHQ_STATUS = 'DEPOSITED' AND CREDIT_ACC_NO = 'VALUE123'
```

---

#### SELECT #210 - Line 115

**File**: `BAN.E.NOF.AA.CC.BAL.b`

**Routine**: `BAN.E.NOF.AA.CC.BAL` (NOFILE (inferred))

**Variable**: `Y.SEL.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ {Y.DATA} AND CHQ.STATUS NE CLEARED AND CHQ.STATUS NE RETURNED
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ 20231210 AND CHQ.STATUS NE CLEARED AND CHQ.STATUS NE RETURNED
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `CREDIT.ACC.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.DATA

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CREDIT_ACC_NO = '20231210' AND CHQ_STATUS != 'CLEARED' AND CHQ_STATUS != 'RETURNED'
```

---

#### SELECT #211 - Line 105

**File**: `BAN.E.NOF.ACCT.BAL.b`

**Routine**: `BAN.E.NOF.ACCT.BAL` (NOFILE (inferred))

**Variable**: `Y.SEL.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ {Y.ACCT.ID} AND CHQ.STATUS NE CLEARED
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ VALUE123 AND CHQ.STATUS NE CLEARED
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `CREDIT.ACC.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CREDIT_ACC_NO = 'VALUE123' AND CHQ_STATUS != 'CLEARED'
```

---

#### SELECT #212 - Line 80

**File**: `BAN.E.NOF.CO.SEV.INST.b`

**Routine**: `BAN.E.NOF.CO.SEV.INST` (NOFILE (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ACCOUNT.ID EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ACCOUNT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ACCOUNT.ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ACCOUNT_ID = 'VALUE123'
```

---

#### SELECT #213 - Line 85

**File**: `BAN.E.NOF.CO.SEV.INST.b`

**Routine**: `BAN.E.NOF.CO.SEV.INST` (NOFILE (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH ARRANGEMENT.ID EQ {Y.ARRANGEMENT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH ARRANGEMENT.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `ARRANGEMENT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE ARRANGEMENT_ID = 'VALUE123'
```

---

#### SELECT #214 - Line 91

**File**: `BAN.E.NOF.CO.SEV.INST.b`

**Routine**: `BAN.E.NOF.CO.SEV.INST` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #215 - Line 55

**File**: `BAN.E.NOF.EXCEPTION.ALL.b`

**Routine**: `BAN.E.NOF.EXCEPTION.ALL` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.BAN.PARAMETER
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PARAMETER
```

**Table**: `BAN.PARAMETER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAMETER
```

---

#### SELECT #216 - Line 170

**File**: `BAN.E.NOF.EXCEPTION.ALL.b`

**Routine**: `BAN.E.NOF.EXCEPTION.ALL` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.{Y.APPL.NAME}$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.VALUE123$NAU
```

**Table**: `VALUE123$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'VALUE123'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.APPLICACION

**Translated SQL**:
```sql
SELECT *
FROM VALUE123$NAU
```

---

#### SELECT #217 - Line 527

**File**: `BAN.E.NOF.EXCEPTION.b`

**Routine**: `BAN.E.NOF.EXCEPTION` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.{Y.APPL.NAME}$NAU WITH INITIATION.TYPE EQ {Y.VAL}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.VALUE123$NAU WITH INITIATION.TYPE EQ USER
```

**Table**: `VALUE123$NAU`

**Fields** (1):
-  `INITIATION.TYPE`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'VALUE123'
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.APPLICACION

**Translated SQL**:
```sql
SELECT *
FROM VALUE123$NAU
WHERE INITIATION_TYPE = 'USER'
```

---

#### SELECT #218 - Line 535

**File**: `BAN.E.NOF.EXCEPTION.b`

**Routine**: `BAN.E.NOF.EXCEPTION` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.{Y.APPL.NAME}$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.VALUE123$NAU
```

**Table**: `VALUE123$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'VALUE123'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.APPLICACION

**Translated SQL**:
```sql
SELECT *
FROM VALUE123$NAU
```

---

#### SELECT #219 - Line 173

**File**: `BAN.E.NOF.IHLD.FT.INW.b`

**Routine**: `BAN.E.NOF.IHLD.FT.INW` (NOFILE (inferred))

**Variable**: `FIN.SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH {SEL.CMD}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH SAMPLE_VALUE
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: SEL.CMD

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #220 - Line 85

**File**: `BAN.E.NOF.VIEW.DEL.HISTORY.b`

**Routine**: `BAN.E.NOF.VIEW.DEL.HISTORY` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.TELLER$DEL WITH VALUE.DATE.1 EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER$DEL WITH VALUE.DATE.1 EQ TODAY
```

**Table**: `TELLER$DEL`

**Fields** (1):
-  `VALUE.DATE.1`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'TELLER'

**Translated SQL**:
```sql
SELECT *
FROM TELLER$DEL
WHERE VALUE_DATE_1 = 'TODAY'
```

---

#### SELECT #221 - Line 160

**File**: `BAN.E.NOF.VIEW.DEL.HISTORY.b`

**Routine**: `BAN.E.NOF.VIEW.DEL.HISTORY` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH DEBIT.VALUE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH DEBIT.VALUE.DATE EQ TODAY
```

**Table**: `FUNDS.TRANSFER$DEL`

**Fields** (1):
-  `DEBIT.VALUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
WHERE DEBIT_VALUE_DATE = 'TODAY'
```

---

#### SELECT #222 - Line 206

**File**: `BAN.E.NOF.VIEW.DEL.HISTORY.b`

**Routine**: `BAN.E.NOF.VIEW.DEL.HISTORY` (NOFILE (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.TELLER.FINANCIAL.SERVICES$DEL WITH DR.VALUE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.FINANCIAL.SERVICES$DEL WITH DR.VALUE.DATE EQ TODAY
```

**Table**: `TELLER.FINANCIAL.SERVICES$DEL`

**Fields** (1):
-  `DR.VALUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DR.VALUE.DATE' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'TELLER.FINANCIAL.SERVICES'

**Translated SQL**:
```sql
SELECT *
FROM TELLER_FINANCIAL_SERVICES$DEL
WHERE DR_VALUE_DATE = 'TODAY'
```

---

#### SELECT #223 - Line 56

**File**: `BAN.E.TCMB.BEN.LIST.b`

**Routine**: `BAN.E.TCMB.BEN.LIST` (ENQUIRY (inferred))

**Variable**: `SEL.CMD.BEN`

**AS PER CODE**:
```
{SEL.CMD.BEN} AND LT.CCY EQ {Y.VALUES<POS3>} AND LT.CCY EQ {Y.VALUES<POS3>}
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND LT.CCY EQ SAMPLE_VALUE AND LT.CCY EQ {Y.VALUES<POS3>} AND LT.CCY EQ {Y.VALUES<POS3>}
```

**Table**: `AND`

**Fields** (1):
-  `LT.CCY`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND
-   Unresolved variables: CCY

**Translated SQL**:
```sql
SELECT *
FROM AND
WHERE LT_CCY = 'SAMPLE_VALUE' AND LT_CCY = '{Y.VALUES<POS3>}' AND LT_CCY = '{Y.VALUES<POS3>}'
```

---

#### SELECT #224 - Line 61

**File**: `BAN.EXP.PROTOCOL.GEN.FILE.b`

**Routine**: `BAN.EXP.PROTOCOL.GEN.FILE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.PROTOCOL.EXP WITH @ID LIKE {Y.EXP.DATE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PROTOCOL.EXP WITH @ID LIKE VALUE123...
```

**Table**: `BAN.PROTOCOL.EXP`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BAN.PROTOCOL.EXP' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.PROTOCOL.EXP
-   Unresolved variables: Y.EXP.DATE

**Translated SQL**:
```sql
SELECT *
FROM BAN_PROTOCOL_EXP
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #225 - Line 31

**File**: `BAN.EXP.PROTOCOL.PURGE.SELECT.b`

**Routine**: `BAN.EXP.PROTOCOL.PURGE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.PROTOCOL.EXP
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.PROTOCOL.EXP
```

**Table**: `BAN.PROTOCOL.EXP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAN.PROTOCOL.EXP' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.PROTOCOL.EXP

**Translated SQL**:
```sql
SELECT *
FROM BAN_PROTOCOL_EXP
```

---

#### SELECT #226 - Line 24

**File**: `BAN.GET.LOOKUP.ID.b`

**Routine**: `BAN.GET.LOOKUP.ID` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ {Y.LOOKUP.NAME}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ VALUE123
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `VIRTUAL.TABLE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LOOKUP.NAME

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE VIRTUAL_TABLE = 'VALUE123'
```

---

#### SELECT #227 - Line 94

**File**: `BAN.I.TELLER.ID.CLOSE.b`

**Routine**: `BAN.I.TELLER.ID.CLOSE` (Unknown)

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT F.{TABLAS}{NAU} WITH INPUTTER LIKE ...{EB.SystemTables.getOperator()}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.{APPLICACIONES<1,POS>}$NAU WITH INPUTTER LIKE ...OPERATOR...
```

**Table**: ``

**Fields** (1):
-  `INPUTTER`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   Table name not found

**Translated SQL**:
```sql
-- Cannot translate: table not found
```

---

#### SELECT #228 - Line 34

**File**: `BAN.LOCAL.CUS.CREATE.SELECT.b`

**Routine**: `BAN.LOCAL.CUS.CREATE.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS EQ "PROCESSED"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS EQ "PROCESSED"
```

**Table**: `BAN.CREATE.CUS.ACC`

**Fields** (1):
-  `PROCESS.CUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
WHERE PROCESS_CUS = 'PROCESSED'
```

---

#### SELECT #229 - Line 69

**File**: `BAN.NOF.CO.SEV.INST.b`

**Routine**: `BAN.NOF.CO.SEV.INST` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.COLLATERAL WITH APPLICATION.ID EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.COLLATERAL WITH APPLICATION.ID EQ VALUE123
```

**Table**: `COLLATERAL`

**Fields** (1):
-  `APPLICATION.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
WHERE APPLICATION_ID = 'VALUE123'
```

---

#### SELECT #230 - Line 49

**File**: `BAN.NOFILE.ENQ.HIST.PLEDGE.b`

**Routine**: `BAN.NOFILE.ENQ.HIST.PLEDGE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CONCAT.COLLATERAL.ALE WITH @ID EQ {EB.Reports.getDRangeAndValue()<FLD.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CONCAT.COLLATERAL.ALE WITH @ID EQ {EB.Reports.getDRangeAndValue()<FLD.POS>}
```

**Table**: `BAN.CONCAT.COLLATERAL.ALE`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'BAN.CONCAT.COLLATERAL.ALE' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.CONCAT.COLLATERAL.ALE

**Translated SQL**:
```sql
SELECT *
FROM BAN_CONCAT_COLLATERAL_ALE
WHERE ID = '{EB.Reports.getDRangeAndValue()<FLD.POS>}'
```

---

#### SELECT #231 - Line 54

**File**: `BAN.NOFILE.ENQ.HIST.PLEDGE.b`

**Routine**: `BAN.NOFILE.ENQ.HIST.PLEDGE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CONCAT.COLLATERAL.ALE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CONCAT.COLLATERAL.ALE
```

**Table**: `BAN.CONCAT.COLLATERAL.ALE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAN.CONCAT.COLLATERAL.ALE' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.CONCAT.COLLATERAL.ALE

**Translated SQL**:
```sql
SELECT *
FROM BAN_CONCAT_COLLATERAL_ALE
```

---

#### SELECT #232 - Line 97

**File**: `BAN.S.ACCT.SUM.BAL.b`

**Routine**: `BAN.S.ACCT.SUM.BAL` (SUBROUTINE (inferred))

**Variable**: `SEL.BAN`

**AS PER CODE**:
```
SELECT F.AC.CASH.POOL WITH GROUP.ID EQ {Y.CASH.POOL}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CASH.POOL WITH GROUP.ID EQ VALUE123
```

**Table**: `AC.CASH.POOL`

**Fields** (1):
-  `GROUP.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CASH.POOL

**Translated SQL**:
```sql
SELECT *
FROM AC_CASH_POOL
WHERE GROUP_ID = 'VALUE123'
```

---

#### SELECT #233 - Line 84

**File**: `BAN.TCMB.ENQ.DEPOSITOS.LIST.b`

**Routine**: `BAN.TCMB.ENQ.DEPOSITOS.LIST` (Unknown)

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND PRODUCT.LINE EQ DEPOSITS AND ARR.STATUS EQ CURRENT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND PRODUCT.LINE EQ DEPOSITS AND ARR.STATUS EQ CURRENT
```

**Table**: `AA.ARRANGEMENT`

**Fields** (3):
-  `ARR.STATUS`  Type: D
-  `CUSTOMER`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CUSTOMER' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE CUSTOMER = '{EB.Reports.getDRangeAndValue()<Y.POS>}' AND PRODUCT_LINE = 'DEPOSITS' AND ARR_STATUS = 'CURRENT'
```

---

#### SELECT #234 - Line 67

**File**: `BAN.TCMB.ENQ.PRESTAMOS.LIST.b`

**Routine**: `BAN.TCMB.ENQ.PRESTAMOS.LIST` (Unknown)

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND PRODUCT.LINE EQ LENDING AND ARR.STATUS EQ CURRENT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND PRODUCT.LINE EQ LENDING AND ARR.STATUS EQ CURRENT
```

**Table**: `AA.ARRANGEMENT`

**Fields** (3):
-  `ARR.STATUS`  Type: D
-  `CUSTOMER`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CUSTOMER' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE CUSTOMER = '{EB.Reports.getDRangeAndValue()<Y.POS>}' AND PRODUCT_LINE = 'LENDING' AND ARR_STATUS = 'CURRENT'
```

---

#### SELECT #235 - Line 252

**File**: `BANE.EXEC.SERVICE.b`

**Routine**: `BANE.EXEC.SERVICE` (Unknown)

**Variable**: `SELECT.CMD.CURR`

**AS PER CODE**:
```
SELECT F.TSA.STATUS WITH CURRENT.SERVICE EQ {SERVICE.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TSA.STATUS WITH CURRENT.SERVICE EQ SAMPLE_VALUE
```

**Table**: `TSA.STATUS`

**Fields** (1):
-  `CURRENT.SERVICE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: SERVICE.ID

**Translated SQL**:
```sql
SELECT *
FROM TSA_STATUS
WHERE CURRENT_SERVICE = 'SAMPLE_VALUE'
```

---

#### SELECT #236 - Line 413

**File**: `BANE.EXEC.SERVICE.b`

**Routine**: `BANE.EXEC.SERVICE` (Unknown)

**Variable**: `SELECT.CMD.CURR`

**AS PER CODE**:
```
SELECT F.TSA.STATUS WITH CURRENT.SERVICE EQ {SERVICE.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TSA.STATUS WITH CURRENT.SERVICE EQ SAMPLE_VALUE
```

**Table**: `TSA.STATUS`

**Fields** (1):
-  `CURRENT.SERVICE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: SERVICE.ID

**Translated SQL**:
```sql
SELECT *
FROM TSA_STATUS
WHERE CURRENT_SERVICE = 'SAMPLE_VALUE'
```

---

#### SELECT #237 - Line 19

**File**: `BAPA.ACCT.CHK.CHG.SELECT.b`

**Routine**: `BAPA.ACCT.CHK.CHG.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAPA.MT.CHG.PARAM WITH CHG.FLAG EQ 'NO' AND ACK.FLAG EQ 'ACTIVE'
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.MT.CHG.PARAM WITH CHG.FLAG EQ 'NO' AND ACK.FLAG EQ 'ACTIVE'
```

**Table**: `BAPA.MT.CHG.PARAM`

**Fields** (2):
-  `ACK.FLAG`  Type: D
-  `CHG.FLAG`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAPA_MT_CHG_PARAM
WHERE CHG_FLAG = 'NO' AND ACK_FLAG = 'ACTIVE'
```

---

#### SELECT #238 - Line 64

**File**: `BAPA.ACCT.DETAILS.DELETE.b`

**Routine**: `BAPA.ACCT.DETAILS.DELETE` (Unknown)

**Variable**: `SELECT.DETILS`

**AS PER CODE**:
```
SELECT F.BPA.OD.ACCT.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.OD.ACCT.DETAILS
```

**Table**: `BPA.OD.ACCT.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_OD_ACCT_DETAILS
```

---

#### SELECT #239 - Line 23

**File**: `BAPA.ADJ.COVID.CURCHARGE.SELECT.b`

**Routine**: `BAPA.ADJ.COVID.CURCHARGE.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BAPA.GEN.COV.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.GEN.COV.DETAILS
```

**Table**: `BAPA.GEN.COV.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAPA_GEN_COV_DETAILS
```

---

#### SELECT #240 - Line 22

**File**: `BAPA.ADJ.COVID.UNCCHARGE.SELECT.b`

**Routine**: `BAPA.ADJ.COVID.UNCCHARGE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.INTERFACE.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT INTERFACE.FILE.PATH
```

**Table**: `INTERFACE.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'INTERFACE.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/INTERFACE.FILE.PATH
-   Unresolved variables: FN.INTERFACE.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

#### SELECT #241 - Line 68

**File**: `BAPA.ADJ.COVID.UPD.UNCCHARGE.b`

**Routine**: `BAPA.ADJ.COVID.UPD.UNCCHARGE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {P.DEPOSITS}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamOutputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamOutputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamOutputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamOutputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamOutputDir>
```

---

#### SELECT #242 - Line 77

**File**: `BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Routine**: `BAPA.B.ACCOUNT.OFFICER.UPDATE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #243 - Line 200

**File**: `BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Routine**: `BAPA.B.ACCOUNT.OFFICER.UPDATE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BAPA.ACCT.OFFI.UPDATE.LOG WITH DATE.PROCESING EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.ACCT.OFFI.UPDATE.LOG WITH DATE.PROCESING EQ TODAY
```

**Table**: `EB.BAPA.ACCT.OFFI.UPDATE.LOG`

**Fields** (1):
-  `DATE.PROCESING`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_ACCT_OFFI_UPDATE_LOG
WHERE DATE_PROCESING = 'TODAY'
```

---

#### SELECT #244 - Line 207

**File**: `BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Routine**: `BAPA.B.ACCOUNT.OFFICER.UPDATE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #245 - Line 225

**File**: `BAPA.B.ACCOUNT.OFFICER.UPDATE.b`

**Routine**: `BAPA.B.ACCOUNT.OFFICER.UPDATE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.FILE.UPLOAD WITH SYSTEM.FILE.NAME EQ {Y.FILE.NAME}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.FILE.UPLOAD WITH SYSTEM.FILE.NAME EQ VALUE123
```

**Table**: `EB.FILE.UPLOAD`

**Fields** (1):
-  `SYSTEM.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.NAME

**Translated SQL**:
```sql
SELECT *
FROM EB_FILE_UPLOAD
WHERE SYSTEM_FILE_NAME = 'VALUE123'
```

---

#### SELECT #246 - Line 23

**File**: `BAPA.B.ACR.NAU.DEL.SELECT.b`

**Routine**: `BAPA.B.ACR.NAU.DEL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AC.CHARGE.REQUEST$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT AC.CHARGE.REQUEST$NAU
```

**Table**: `AC.CHARGE.REQUEST$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'AC.CHARGE.REQUEST'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST$NAU
```

---

#### SELECT #247 - Line 112

**File**: `BAPA.B.ACR.PREPARE.FILES.b`

**Routine**: `BAPA.B.ACR.PREPARE.FILES` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_112`

**AS PER CODE**:
```
SELECT F.IN.DIR
```

**SIMULATED AT RUNTIME**:
```
SELECT F.IN.DIR
```

**Table**: `IN.DIR`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'IN.DIR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/IN.DIR

**Translated SQL**:
```sql
SELECT *
FROM IN_DIR
```

---

#### SELECT #248 - Line 24

**File**: `BAPA.B.ADJ.CASTIGO.BILL.SELECT.b`

**Routine**: `BAPA.B.ADJ.CASTIGO.BILL.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BSAP.L.CASTIGADO.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT BSAP.L.CASTIGADO.DETAILS
```

**Table**: `BSAP.L.CASTIGADO.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BSAP_L_CASTIGADO_DETAILS
```

---

#### SELECT #249 - Line 23

**File**: `BAPA.B.ADJ.CASTIGO.INT.SELECT.b`

**Routine**: `BAPA.B.ADJ.CASTIGO.INT.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BSAP.L.CASTIGADO.DETAILS WITH PRINC.CURSTATUS EQ "PROCESSED"
```

**SIMULATED AT RUNTIME**:
```
SELECT BSAP.L.CASTIGADO.DETAILS WITH PRINC.CURSTATUS EQ "PROCESSED"
```

**Table**: `BSAP.L.CASTIGADO.DETAILS`

**Fields** (1):
-  `PRINC.CURSTATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BSAP_L_CASTIGADO_DETAILS
WHERE PRINC_CURSTATUS = 'PROCESSED'
```

---

#### SELECT #250 - Line 21

**File**: `BAPA.B.AUTO.MONITOR.SERVICE.SELECT.b`

**Routine**: `BAPA.B.AUTO.MONITOR.SERVICE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.INTERFACE.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT INTERFACE.FILE.PATH
```

**Table**: `INTERFACE.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'INTERFACE.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/INTERFACE.FILE.PATH
-   Unresolved variables: FN.INTERFACE.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

#### SELECT #251 - Line 23

**File**: `BAPA.B.AUTO.UPD.DEPT.OFF.SELECT.b`

**Routine**: `BAPA.B.AUTO.UPD.DEPT.OFF.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BAPA.CUS.DAO.LIST
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.CUS.DAO.LIST
```

**Table**: `BAPA.CUS.DAO.LIST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAPA.CUS.DAO.LIST' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAPA.CUS.DAO.LIST

**Translated SQL**:
```sql
SELECT *
FROM BAPA_CUS_DAO_LIST
```

---

#### SELECT #252 - Line 110

**File**: `BAPA.B.BOL.TO.INT.b`

**Routine**: `BAPA.B.BOL.TO.INT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {P.LENDING}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #253 - Line 266

**File**: `BAPA.B.BOL.TO.INT.b`

**Routine**: `BAPA.B.BOL.TO.INT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{FIELD(LINE,",",3)}"
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{FIELD(LINE,",",3)}"
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: FIELD(LINE,",",3)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = '{FIELD(LINE,'
```

---

#### SELECT #254 - Line 108

**File**: `BAPA.B.BOL.TO.PAY.b`

**Routine**: `BAPA.B.BOL.TO.PAY` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {P.LENDING}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #255 - Line 265

**File**: `BAPA.B.BOL.TO.PAY.b`

**Routine**: `BAPA.B.BOL.TO.PAY` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{FIELD(LINE,",",3)}"
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{FIELD(LINE,",",3)}"
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: FIELD(LINE,",",3)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = '{FIELD(LINE,'
```

---

#### SELECT #256 - Line 44

**File**: `BAPA.B.CHG.PENDING.DATE.b`

**Routine**: `BAPA.B.CHG.PENDING.DATE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.AA.T.CHG.PENDING
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.AA.T.CHG.PENDING
```

**Table**: `BAN.AA.T.CHG.PENDING`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

#### SELECT #257 - Line 100

**File**: `BAPA.B.CLOSED.BANK.CASH.b`

**Routine**: `BAPA.B.CLOSED.BANK.CASH` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER.ID$NAU WITH STATUS EQ CLOSE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.ID$NAU WITH STATUS EQ CLOSE
```

**Table**: `TELLER.ID$NAU`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'TELLER.ID'

**Translated SQL**:
```sql
SELECT *
FROM TELLER_ID$NAU
WHERE STATUS = 'CLOSE'
```

---

#### SELECT #258 - Line 30

**File**: `BAPA.B.EB.EOD.ERROR.SELECT.b`

**Routine**: `BAPA.B.EB.EOD.ERROR.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnEbEodError()} WITH FIX.REQUIRED EQ YES AND DATE.RESOLVED EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.EOD.ERROR WITH FIX.REQUIRED EQ YES AND DATE.RESOLVED EQ ''
```

**Table**: `EB.EOD.ERROR`

**Fields** (2):
-  `FIX.REQUIRED`  Type: D
-  `DATE.RESOLVED`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'FIX.REQUIRED' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'DATE.RESOLVED' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM EB_EOD_ERROR
WHERE FIX_REQUIRED = 'YES'
```

---

#### SELECT #259 - Line 27

**File**: `BAPA.B.ENVIA.NOTIFICACION.SELECT.b`

**Routine**: `BAPA.B.ENVIA.NOTIFICACION.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH ISSUE.DATE EQ {EB.SystemTables.getToday()} AND STATUS EQ RETURNED AND LT.RET.COD.CHQ NE 1001 AND LT.RET.COD.CHQ NE 0001
```

**SIMULATED AT RUNTIME**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH ISSUE.DATE EQ TODAY AND STATUS EQ RETURNED AND LT.RET.COD.CHQ NE 1001 AND LT.RET.COD.CHQ NE 0001
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (3):
-  `LT.RET.COD.CHQ`  Type: I (Formula: `LOCAL.REF<1,8>`)
-  `STATUS`  Type: D
-  `ISSUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LT.RET.COD.CHQ' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE ISSUE_DATE = 'TODAY' AND STATUS = 'RETURNED' AND LT_RET_COD_CHQ != '1001' AND LT_RET_COD_CHQ != '0001'
```

---

#### SELECT #260 - Line 67

**File**: `BAPA.B.EXT.DT.FINAL.FILE.b`

**Routine**: `BAPA.B.EXT.DT.FINAL.FILE` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_67`

**AS PER CODE**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SIMULATED AT RUNTIME**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**Table**: `Y.TEMP.FILE.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'Y.TEMP.FILE.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/Y.TEMP.FILE.POINTER

**Translated SQL**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

#### SELECT #261 - Line 22

**File**: `BAPA.B.FT.NAU.DEL.SELECT.b`

**Routine**: `BAPA.B.FT.NAU.DEL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FUNDS.TRANSFER$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER$NAU
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #262 - Line 36

**File**: `BAPA.B.ORP.PROCESS.SELECT.b`

**Routine**: `BAPA.B.ORP.PROCESS.SELECT` (BATCH (inferred))

**Variable**: `SEL.MASTER`

**AS PER CODE**:
```
SELECT BAPA.H.ORGINATOR.MASTER WITH STATUS EQ READY
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.H.ORGINATOR.MASTER WITH STATUS EQ READY
```

**Table**: `BAPA.H.ORGINATOR.MASTER`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAPA_H_ORGINATOR_MASTER
WHERE STATUS = 'READY'
```

---

#### SELECT #263 - Line 90

**File**: `BAPA.B.ORP.PROCESS.SELECT.b`

**Routine**: `BAPA.B.ORP.PROCESS.SELECT` (BATCH (inferred))

**Variable**: `SEL.DETAILS`

**AS PER CODE**:
```
SELECT BAPA.H.ORIGINATOR.DETAILS WITH MASTER.REF EQ {Y.LIST.ORIG.MASTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.H.ORIGINATOR.DETAILS WITH MASTER.REF EQ VALUE123
```

**Table**: `BAPA.H.ORIGINATOR.DETAILS`

**Fields** (1):
-  `MASTER.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LIST.ORIG.MASTER

**Translated SQL**:
```sql
SELECT *
FROM BAPA_H_ORIGINATOR_DETAILS
WHERE MASTER_REF = 'VALUE123'
```

---

#### SELECT #264 - Line 48

**File**: `BAPA.B.ORP.UPD.STATUS.b`

**Routine**: `BAPA.B.ORP.UPD.STATUS` (BATCH (inferred))

**Variable**: `SEL.MAS`

**AS PER CODE**:
```
SELECT F.BAPA.H.ORGINATOR.MASTER WITH STATUS EQ BK.MASTER.READY
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAPA.H.ORGINATOR.MASTER WITH STATUS EQ BK.MASTER.READY
```

**Table**: `BAPA.H.ORGINATOR.MASTER`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAPA_H_ORGINATOR_MASTER
WHERE STATUS = 'BK.MASTER.READY'
```

---

#### SELECT #265 - Line 19

**File**: `BAPA.B.PROCCESS.CHG.SELECT.b`

**Routine**: `BAPA.B.PROCCESS.CHG.SELECT` (BATCH (inferred))

**Variable**: `SEL.CHG`

**AS PER CODE**:
```
SELECT BAPA.H.AUTO.CHG.DETAILS WITH STATUS EQ TO.BE.PROCESS OR STATUS EQ TO.BE.REPROCESS
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.H.AUTO.CHG.DETAILS WITH STATUS EQ TO.BE.PROCESS OR STATUS EQ TO.BE.REPROCESS
```

**Table**: `BAPA.H.AUTO.CHG.DETAILS`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAPA_H_AUTO_CHG_DETAILS
```

---

#### SELECT #266 - Line 67

**File**: `BAPA.B.TRG.OFS.STRING.b`

**Routine**: `BAPA.B.TRG.OFS.STRING` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BAPA.ADJ.CASTIGO.LIST
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAPA.ADJ.CASTIGO.LIST
```

**Table**: `BAPA.ADJ.CASTIGO.LIST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAPA.ADJ.CASTIGO.LIST' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAPA.ADJ.CASTIGO.LIST

**Translated SQL**:
```sql
SELECT *
FROM BAPA_ADJ_CASTIGO_LIST
```

---

#### SELECT #267 - Line 60

**File**: `BAPA.B.TSA.START.SCHEDL.b`

**Routine**: `BAPA.B.TSA.START.SCHEDL` (BATCH (inferred))

**Variable**: `SEL.SCHED`

**AS PER CODE**:
```
SELECT F.BAPA.H.TSA.AUTO.SCHEDULER
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAPA.H.TSA.AUTO.SCHEDULER
```

**Table**: `BAPA.H.TSA.AUTO.SCHEDULER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAPA_H_TSA_AUTO_SCHEDULER
```

---

#### SELECT #268 - Line 24

**File**: `BAPA.B.TT.NAU.DEL.SELECT.b`

**Routine**: `BAPA.B.TT.NAU.DEL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TELLER$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER$NAU
```

**Table**: `TELLER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'TELLER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM TELLER$NAU
```

---

#### SELECT #269 - Line 46

**File**: `BAPA.CHG.ISSUE.BILL.NO.SELECT.b`

**Routine**: `BAPA.CHG.ISSUE.BILL.NO.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.INTERFACE.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT INTERFACE.FILE.PATH
```

**Table**: `INTERFACE.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'INTERFACE.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/INTERFACE.FILE.PATH
-   Unresolved variables: FN.INTERFACE.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

#### SELECT #270 - Line 55

**File**: `BAPA.COMMISSION.AMORT.DELETE.b`

**Routine**: `BAPA.COMMISSION.AMORT.DELETE` (Unknown)

**Variable**: `SELECT.DETILS`

**AS PER CODE**:
```
SELECT F.BPA.LOAN.COMMISSION.AMORT WITH START.DATE EQ "" AND EXPIRY.DATE GE {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.LOAN.COMMISSION.AMORT WITH START.DATE EQ "" AND EXPIRY.DATE GE TODAY
```

**Table**: `BPA.LOAN.COMMISSION.AMORT`

**Fields** (2):
-  `START.DATE`  Type: D
-  `EXPIRY.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_LOAN_COMMISSION_AMORT
WHERE EXPIRY_DATE >= 'TODAY'
```

---

#### SELECT #271 - Line 83

**File**: `BAPA.CONSOLIDATE.LOG.REM.b`

**Routine**: `BAPA.CONSOLIDATE.LOG.REM` (Unknown)

**Variable**: `INTERNAL_SELECT_LINE_83`

**AS PER CODE**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SIMULATED AT RUNTIME**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**Table**: `Y.TEMP.FILE.POINTER.TEM`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'Y.TEMP.FILE.POINTER.TEM' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/Y.TEMP.FILE.POINTER.TEM

**Translated SQL**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER_TEM
```

---

#### SELECT #272 - Line 48

**File**: `BAPA.DE.O.b`

**Routine**: `BAPA.DE.O` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAOTH.MigVarios.getFnDeOHistory()} WITH @ID LIKE {Y.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT DE.OHISTORY WITH @ID LIKE 12345...
```

**Table**: `DE.OHISTORY`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'DE.OHISTORY' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/DE.OHISTORY
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM DE_OHISTORY
WHERE ID LIKE '12345%'
```

---

#### SELECT #273 - Line 43

**File**: `BAPA.DEL.AAA.EXCEP.SELECT.b`

**Routine**: `BAPA.DEL.AAA.EXCEP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT.ACTIVITY$NAU WITH RECORD.STATUS NE '' AND @ID LIKE 'AAA...'
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT.ACTIVITY$NAU WITH RECORD.STATUS NE '' AND @ID LIKE 'AAA...'
```

**Table**: `AA.ARRANGEMENT.ACTIVITY$NAU`

**Fields** (2):
-  `RECORD.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'AA.ARRANGEMENT.ACTIVITY'

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT_ACTIVITY$NAU
WHERE ID LIKE 'AAA%'
```

---

#### SELECT #274 - Line 60

**File**: `BAPA.E.BLD.CUSTODY.PENDING.b`

**Routine**: `BAPA.E.BLD.CUSTODY.PENDING` (ENQUIRY (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.BAN.L.CUSTODY.FUND WITH NEXT.CHARGE.DATE LIKE {Y.LAST.RUN.DATE}... AND CURRENT.BALANCE GT 0
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.L.CUSTODY.FUND WITH NEXT.CHARGE.DATE LIKE VALUE123... AND CURRENT.BALANCE GT 0
```

**Table**: `BAN.L.CUSTODY.FUND`

**Fields** (2):
-  `CURRENT.BALANCE`  Type: D
-  `NEXT.CHARGE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LAST.RUN.DATE

**Translated SQL**:
```sql
SELECT *
FROM BAN_L_CUSTODY_FUND
WHERE NEXT_CHARGE_DATE LIKE 'VALUE123%' AND CURRENT_BALANCE > '0'
```

---

#### SELECT #275 - Line 32

**File**: `BAPA.E.BLD.REC.LOCK.b`

**Routine**: `BAPA.E.BLD.REC.LOCK` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000037
```

**SIMULATED AT RUNTIME**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000037
```

**Table**: `USER`

**Fields** (1):
-  `DEPARTMENT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM USER
WHERE DEPARTMENT_CODE = '8000000037'
```

---

#### SELECT #276 - Line 65

**File**: `BAPA.E.BLD.REC.LOCK.NEW.b`

**Routine**: `BAPA.E.BLD.REC.LOCK.NEW` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ {Y.DEPT.CODE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ VALUE123
```

**Table**: `USER`

**Fields** (1):
-  `DEPARTMENT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DEPT.CODE

**Translated SQL**:
```sql
SELECT *
FROM USER
WHERE DEPARTMENT_CODE = 'VALUE123'
```

---

#### SELECT #277 - Line 140

**File**: `BAPA.E.GET.ACCUM.b`

**Routine**: `BAPA.E.GET.ACCUM` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.AC.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AC.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #278 - Line 97

**File**: `BAPA.E.GET.DEL.HIS.ACCT.b`

**Routine**: `BAPA.E.GET.DEL.HIS.ACCT` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH DEBIT.ACCT.NO EQ {ctaDebito} AND @ID LIKE ...{dateEnq[6]}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH DEBIT.ACCT.NO EQ {ctaDebito} AND @ID LIKE ...{dateEnq[6]}...
```

**Table**: `FUNDS.TRANSFER$DEL`

**Fields** (2):
-  `DEBIT.ACCT.NO`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
WHERE DEBIT_ACCT_NO = '{ctaDebito}' AND ID LIKE '%{dateEnq[6]}%'
```

---

#### SELECT #279 - Line 193

**File**: `BAPA.E.GET.FT.REJECTED.b`

**Routine**: `BAPA.E.GET.FT.REJECTED` (ENQUIRY (inferred))

**Variable**: `SEL.CMD.DEV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ {Y.FT.ORIG}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ VALUE123
```

**Table**: `FUNDS.TRANSFER`

**Fields** (2):
-  `ORDERING.CUST`  Type: D
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ORDERING.CUST' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.FT.ORIG

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER
WHERE TRANSACTION_TYPE = 'ITRV' AND ORDERING_CUST = 'VALUE123'
```

---

#### SELECT #280 - Line 197

**File**: `BAPA.E.GET.FT.REJECTED.b`

**Routine**: `BAPA.E.GET.FT.REJECTED` (ENQUIRY (inferred))

**Variable**: `SEL.CMD.DEV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ {Y.FT.ORIG}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ VALUE123
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (2):
-  `ORDERING.CUST`  Type: D
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ORDERING.CUST' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: Y.FT.ORIG

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE TRANSACTION_TYPE = 'ITRV' AND ORDERING_CUST = 'VALUE123'
```

---

#### SELECT #281 - Line 201

**File**: `BAPA.E.GET.FT.REJECTED.b`

**Routine**: `BAPA.E.GET.FT.REJECTED` (ENQUIRY (inferred))

**Variable**: `SEL.CMD.DEV`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ {Y.FT.ORIG}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH TRANSACTION.TYPE EQ ITRV AND ORDERING.CUST EQ VALUE123
```

**Table**: `FUNDS.TRANSFER$HIS`

**Fields** (2):
-  `ORDERING.CUST`  Type: D
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ORDERING.CUST' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: Y.FT.ORIG

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$HIS
WHERE TRANSACTION_TYPE = 'ITRV' AND ORDERING_CUST = 'VALUE123'
```

---

#### SELECT #282 - Line 233

**File**: `BAPA.E.NOF.AUDIT.COMP.b`

**Routine**: `BAPA.E.NOF.AUDIT.COMP` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.HELPTEXT.MENU} WITH DATE.TIME GE {Y.DATE.ENQ}0001
```

**SIMULATED AT RUNTIME**:
```
SELECT F.HELPTEXT.MENU WITH DATE.TIME GE 20010100010001
```

**Table**: `HELPTEXT.MENU`

**Fields** (1):
-  `DATE.TIME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM HELPTEXT_MENU
WHERE DATE_TIME >= '20010100010001'
```

---

#### SELECT #283 - Line 246

**File**: `BAPA.E.NOF.AUDIT.COMP.b`

**Routine**: `BAPA.E.NOF.AUDIT.COMP` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.HELPTEXT.MENU} WITH CURR.NO EQ 1 AND DATE.TIME GE {Y.DATE.ENQ}0001 OR DATE.TIME GE {utcDateTime}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.HELPTEXT.MENU WITH CURR.NO EQ 1 AND DATE.TIME GE 20010100010001 OR DATE.TIME GE {utcDateTime}
```

**Table**: `HELPTEXT.MENU`

**Fields** (2):
-  `CURR.NO`  Type: D
-  `DATE.TIME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM HELPTEXT_MENU
WHERE CURR_NO = '1' AND DATE_TIME >= '20010100010001'
```

---

#### SELECT #284 - Line 75

**File**: `BAPA.E.NOF.GET.JOB.LIST.DTL.b`

**Routine**: `BAPA.E.NOF.GET.JOB.LIST.DTL` (NOFILE (inferred))

**Variable**: `yLockingSelCmd`

**AS PER CODE**:
```
SELECT {fnLocking} WITH @ID LIKE F.JOB.LIST...
```

**SIMULATED AT RUNTIME**:
```
SELECT LOCKING WITH @ID LIKE F.JOB.LIST...
```

**Table**: `LOCKING`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LOCKING
WHERE ID LIKE 'F.JOB.LIST%'
```

---

#### SELECT #285 - Line 78

**File**: `BAPA.E.NOF.GET.JOB.LIST.DTL.b`

**Routine**: `BAPA.E.NOF.GET.JOB.LIST.DTL` (NOFILE (inferred))

**Variable**: `yLockingSelCmd`

**AS PER CODE**:
```
SELECT {fnLocking} WITH @ID EQ {yJobListId}
```

**SIMULATED AT RUNTIME**:
```
SELECT LOCKING WITH @ID EQ {yJobListId}
```

**Table**: `LOCKING`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LOCKING
WHERE ID = '{yJobListId}'
```

---

#### SELECT #286 - Line 122

**File**: `BAPA.E.NOF.GET.JOB.LIST.DTL.b`

**Routine**: `BAPA.E.NOF.GET.JOB.LIST.DTL` (NOFILE (inferred))

**Variable**: `yJobListCmd`

**AS PER CODE**:
```
SELECT {fnJobListX}
```

**SIMULATED AT RUNTIME**:
```
SELECT yLockingSelRec
```

**Table**: `yLockingSelRec`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'yLockingSelRec' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/yLockingSelRec

**Translated SQL**:
```sql
SELECT *
FROM yLockingSelRec
```

---

#### SELECT #287 - Line 121

**File**: `BAPA.E.NOF.INW.IHLD.FT.103.b`

**Routine**: `BAPA.E.NOF.INW.IHLD.FT.103` (NOFILE (inferred))

**Variable**: `SEL.COMMAND`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND TRANSACTION.TYPE EQ IT AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND INWARD.PAY.TYPE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TI
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND TRANSACTION.TYPE EQ IT AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND INWARD.PAY.TYPE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TI
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (7):
-  `RECORD.STATUS`  Type: D
-  `DATE.TIME`  Type: D
-  `DELIVERY.INREF`  Type: D
-  `INWARD.PAY.TYPE`  Type: D
-  `TRANSACTION.TYPE`  Type: D
-  `@ID`  Type: D
-  `PROCESSING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE RECORD_STATUS = 'IHLD' AND TRANSACTION_TYPE = 'IT' AND ID = '{EB.Reports.getEnqSelection()<4,VAL.POS>}' AND INWARD_PAY_TYPE = '{EB.Reports.getEnqSelection()<4,VAL.POS>}' AND PROCESSING_DATE = '{EB.Reports.getEnqSelection()<4,VAL.POS>}'
ORDER BY DATE_TIME ASC
```

---

#### SELECT #288 - Line 107

**File**: `BAPA.E.NOF.INW.IHLD.FT.103.OOT.b`

**Routine**: `BAPA.E.NOF.INW.IHLD.FT.103.OOT` (NOFILE (inferred))

**Variable**: `SEL.COMMAND`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ IT AND RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND INWARD.PAY.TYPE EQ MT103 AND LT.EFM.REF EQ "" AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TIME
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ IT AND RECORD.STATUS EQ IHLD AND DELIVERY.INREF NE "" AND INWARD.PAY.TYPE EQ MT103 AND LT.EFM.REF EQ "" AND @ID EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} AND PROCESSING.DATE EQ {EB.Reports.getEnqSelection()<4,VAL.POS>} BY DATE.TIME
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (8):
-  `LT.EFM.REF`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,57>`)
-  `RECORD.STATUS`  Type: D
-  `DATE.TIME`  Type: D
-  `INWARD.PAY.TYPE`  Type: D
-  `DELIVERY.INREF`  Type: D
-  `@ID`  Type: D
-  `TRANSACTION.TYPE`  Type: D
-  `PROCESSING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   INFO: LOCAL.REF fields found: LT.EFM.REF - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE TRANSACTION_TYPE = 'IT' AND RECORD_STATUS = 'IHLD' AND INWARD_PAY_TYPE = 'MT103' AND ID = '{EB.Reports.getEnqSelection()<4,VAL.POS>}' AND PROCESSING_DATE = '{EB.Reports.getEnqSelection()<4,VAL.POS>}'
ORDER BY DATE_TIME ASC
```

---

#### SELECT #289 - Line 31

**File**: `BAPA.E.REC.LOCK.38.b`

**Routine**: `BAPA.E.REC.LOCK.38` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000038
```

**SIMULATED AT RUNTIME**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000038
```

**Table**: `USER`

**Fields** (1):
-  `DEPARTMENT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM USER
WHERE DEPARTMENT_CODE = '8000000038'
```

---

#### SELECT #290 - Line 43

**File**: `BAPA.E.REC.LOCK.CC.0044.b`

**Routine**: `BAPA.E.REC.LOCK.CC.0044` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000044
```

**SIMULATED AT RUNTIME**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000044
```

**Table**: `USER`

**Fields** (1):
-  `DEPARTMENT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM USER
WHERE DEPARTMENT_CODE = '8000000044'
```

---

#### SELECT #291 - Line 43

**File**: `BAPA.E.REC.LOCK.CC.0120.b`

**Routine**: `BAPA.E.REC.LOCK.CC.0120` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000120
```

**SIMULATED AT RUNTIME**:
```
SELECT F.USER WITH DEPARTMENT.CODE EQ 8000000120
```

**Table**: `USER`

**Fields** (1):
-  `DEPARTMENT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM USER
WHERE DEPARTMENT_CODE = '8000000120'
```

---

#### SELECT #292 - Line 92

**File**: `BAPA.FT.NAU.DEL.b`

**Routine**: `BAPA.FT.NAU.DEL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU
```

**Table**: `FUNDS.TRANSFER$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #293 - Line 19

**File**: `BAPA.MT.CHG.ACCT.SELECT.b`

**Routine**: `BAPA.MT.CHG.ACCT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAPA.MT.CHG.PARAM WITH (CHG.FLAG EQ '' OR CHG.FLAG EQ 'YES') AND ACK.FLAG EQ 'ACTIVE'
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.MT.CHG.PARAM WITH (CHG.FLAG EQ '' OR CHG.FLAG EQ 'YES') AND ACK.FLAG EQ 'ACTIVE'
```

**Table**: `BAPA.MT.CHG.PARAM`

**Fields** (2):
-  `ACK.FLAG`  Type: D
-  `CHG.FLAG`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAPA_MT_CHG_PARAM
WHERE ACK_FLAG = 'ACTIVE'
```

---

#### SELECT #294 - Line 58

**File**: `BAPA.PARTICIPANT.DELETE.b`

**Routine**: `BAPA.PARTICIPANT.DELETE` (Unknown)

**Variable**: `SEL.PRT`

**AS PER CODE**:
```
SELECT F.BPA.ARR.BY.PARTICIPANT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.ARR.BY.PARTICIPANT
```

**Table**: `BPA.ARR.BY.PARTICIPANT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_ARR_BY_PARTICIPANT
```

---

#### SELECT #295 - Line 90

**File**: `BAPA.RC.ACCT.STATUS.b`

**Routine**: `BAPA.RC.ACCT.STATUS` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "{Y.NO.ACCT.IN}"
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ "VALUE123"
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.NO.ACCT.IN

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #296 - Line 81

**File**: `BAPA.S.GET.FILE.POST.b`

**Routine**: `BAPA.S.GET.FILE.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.SIM.FILES}
```

**SIMULATED AT RUNTIME**:
```
SELECT SIM.FILES
```

**Table**: `SIM.FILES`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'SIM.FILES' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/SIM.FILES
-   Unresolved variables: F.SIM.FILES

**Translated SQL**:
```sql
SELECT *
FROM SIM_FILES
```

---

#### SELECT #297 - Line 40

**File**: `BAPA.S.ORP.CLEAR.ITEM.DETAIL.b`

**Routine**: `BAPA.S.ORP.CLEAR.ITEM.DETAIL` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAPA.H.ORIGINATOR.DETAILS @ID WITH MASTER.REF EQ {Y.FILE.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAPA.H.ORIGINATOR.DETAILS @ID WITH MASTER.REF EQ VALUE123
```

**Table**: `BAPA.H.ORIGINATOR.DETAILS`

**Fields** (1):
-  `MASTER.REF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.REF

**Translated SQL**:
```sql
SELECT *
FROM BAPA_H_ORIGINATOR_DETAILS
WHERE MASTER_REF = 'VALUE123'
```

---

#### SELECT #298 - Line 69

**File**: `BPA.B.CUS.FILE.PRE.b`

**Routine**: `BPA.B.CUS.FILE.PRE` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_69`

**AS PER CODE**:
```
SELECT Y.TEMP.FILE.POINTER.AUX        ;* Seleccionar los archivos que contiene el directorio
```

**SIMULATED AT RUNTIME**:
```
SELECT Y.TEMP.FILE.POINTER.AUX        ;* Seleccionar los archivos que contiene el directorio
```

**Table**: `Y.TEMP.FILE.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'Y.TEMP.FILE.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/Y.TEMP.FILE.POINTER

**Translated SQL**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

#### SELECT #299 - Line 27

**File**: `BPA.B.ECB.CECO.ALL.SELECT.b`

**Routine**: `BPA.B.ECB.CECO.ALL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH (@ID LIKE ...{Y.JUL.TODAY}...) OR (@ID LIKE ...{Y.JUL.LSTWD}...)
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH (@ID LIKE ...VALUE123...) OR (@ID LIKE ...VALUE123...)
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.JUL.TODAY, Y.JUL.LSTWD

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #300 - Line 120

**File**: `BPA.E.NOF.BPA.ENQ.CHQ.RETURNED.b`

**Routine**: `BPA.E.NOF.BPA.ENQ.CHQ.RETURNED` (NOFILE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ RETURNED AND ISSUE.DATE EQ {EB.Reports.getDRangeAndValue()<FIELD.POS>} AND ISSUE.DATE GE {ISSUE.DATE.VAL<1,1,1>} AND ISSUE.DATE LE {ISSUE.DATE.VAL<1,1,2>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ RETURNED AND ISSUE.DATE EQ {EB.Reports.getDRangeAndValue()<FIELD.POS>} AND ISSUE.DATE GE {ISSUE.DATE.VAL<1,1,1>} AND ISSUE.DATE LE {ISSUE.DATE.VAL<1,1,2>}
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (2):
-  `STATUS`  Type: D
-  `ISSUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE STATUS = 'RETURNED' AND ISSUE_DATE = '{EB.Reports.getDRangeAndValue()<FIELD.POS>}' AND ISSUE_DATE >= '{ISSUE.DATE.VAL<1,1,1>}' AND ISSUE_DATE <= '{ISSUE.DATE.VAL<1,1,2>}'
```

---

#### SELECT #301 - Line 43

**File**: `BPA.E.NOF.ECB.CECO.AA.b`

**Routine**: `BPA.E.NOF.ECB.CECO.AA` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS OR PRODUCT.LINE EQ LENDING OR PRODUCT.LINE EQ DEPOSITS AND @ID LIKE ...{Y.JUL.DATE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS OR PRODUCT.LINE EQ LENDING OR PRODUCT.LINE EQ DEPOSITS AND @ID LIKE ...VALUE123...
```

**Table**: `AA.ARRANGEMENT`

**Fields** (2):
-  `PRODUCT.LINE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.JUL.DATE

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ID LIKE '%VALUE123%'
```

---

#### SELECT #302 - Line 43

**File**: `BPA.E.NOF.ECB.CECO.MD.b`

**Routine**: `BPA.E.NOF.ECB.CECO.MD` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.MD.DEAL WITH @ID LIKE ...{Y.JUL.DATE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.MD.DEAL WITH @ID LIKE ...VALUE123...
```

**Table**: `MD.DEAL`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.JUL.DATE

**Translated SQL**:
```sql
SELECT *
FROM MD_DEAL
WHERE ID LIKE '%VALUE123%'
```

---

#### SELECT #303 - Line 92

**File**: `BPA.M.MAP.ISO.DATA.b`

**Routine**: `BPA.M.MAP.ISO.DATA` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE WITH STATUS EQ '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE WITH STATUS EQ '' 
```

**Table**: `LATAM.ACH.CAPTURE`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE
```

---

#### SELECT #304 - Line 136

**File**: `BPA.M.MAP.ISO.DATA.b`

**Routine**: `BPA.M.MAP.ISO.DATA` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.CAPTURE$NAU WITH STATUS EQ '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.CAPTURE$NAU WITH STATUS EQ '' 
```

**Table**: `LATAM.ACH.CAPTURE$NAU`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'LATAM.ACH.CAPTURE'

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_CAPTURE$NAU
```

---

#### SELECT #305 - Line 218

**File**: `BPA.M.MAP.ISO.DATA.b`

**Routine**: `BPA.M.MAP.ISO.DATA` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.DD.MANDATE WITH BANK.ID NE '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.DD.MANDATE WITH BANK.ID NE '' 
```

**Table**: `LATAM.ACH.DD.MANDATE`

**Fields** (1):
-  `BANK.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_DD_MANDATE
```

---

#### SELECT #306 - Line 19

**File**: `BPA.REM.CHQ.DATA.SELECT.b`

**Routine**: `BPA.REM.CHQ.DATA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ RETURNED
```

**SIMULATED AT RUNTIME**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ RETURNED
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE STATUS = 'RETURNED'
```

---

#### SELECT #307 - Line 119

**File**: `BRD.S.DRINT.BASE.AMT.b`

**Routine**: `BRD.S.DRINT.BASE.AMT` (SUBROUTINE (inferred))

**Variable**: `Y.SEL.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH (CREDIT.ACC.NO EQ {Y.ACCT.ID}) AND (CHQ.STATUS NE CLEARED) AND (CHQ.STATUS NE REJECTED)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH (CREDIT.ACC.NO EQ VALUE123) AND (CHQ.STATUS NE CLEARED) AND (CHQ.STATUS NE REJECTED)
```

**Table**: `CHEQUE.COLLECTION`

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
```

---

#### SELECT #308 - Line 22

**File**: `BSAP.B.UPD.SUSP.AMT.SELECT.b`

**Routine**: `BSAP.B.UPD.SUSP.AMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.INTERFACE.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT INTERFACE.FILE.PATH
```

**Table**: `INTERFACE.FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'INTERFACE.FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/INTERFACE.FILE.PATH
-   Unresolved variables: FN.INTERFACE.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM INTERFACE_FILE_PATH
```

---

#### SELECT #309 - Line 39

**File**: `BSAP.CORR.TCIB.COB.AAA.b`

**Routine**: `BSAP.CORR.TCIB.COB.AAA` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT.ACTIVITY$NAU WITH RECORD.STATUS EQ IHLD
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT.ACTIVITY$NAU WITH RECORD.STATUS EQ IHLD
```

**Table**: `AA.ARRANGEMENT.ACTIVITY$NAU`

**Fields** (1):
-  `RECORD.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'AA.ARRANGEMENT.ACTIVITY'

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT_ACTIVITY$NAU
WHERE RECORD_STATUS = 'IHLD'
```

---

#### SELECT #310 - Line 48

**File**: `CAL.UPDATE.BL.b`

**Routine**: `CAL.UPDATE.BL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.BALANCE.TYPE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.BALANCE.TYPE
```

**Table**: `AC.BALANCE.TYPE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AC_BALANCE_TYPE
```

---

#### SELECT #311 - Line 65

**File**: `CAL.UPDATE.BL.b`

**Routine**: `CAL.UPDATE.BL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CONSOLIDATE.ASST.LIAB
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CONSOLIDATE.ASST.LIAB
```

**Table**: `CONSOLIDATE.ASST.LIAB`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CONSOLIDATE_ASST_LIAB
```

---

#### SELECT #312 - Line 66

**File**: `TECH.CHARGE.DAILY.b`

**Routine**: `TECH.CHARGE.DAILY` (Unknown)

**Variable**: `SEL.CMD.CUST`

**AS PER CODE**:
```
SELECT BAN.TCIB.AFFILIATION WITH ALLOWED.CUST EQ {Y.ID.CUSTOMER} AND (STATUS EQ 'AFILIADO' OR STATUS EQ 'REAFILIADO' OR STATUS EQ 'DIFERIDA')
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TCIB.AFFILIATION WITH ALLOWED.CUST EQ VALUE123 AND (STATUS EQ 'AFILIADO' OR STATUS EQ 'REAFILIADO' OR STATUS EQ 'DIFERIDA')
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (2):
-  `ALLOWED.CUST`  Type: D
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALLOWED.CUST' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ID.CUSTOMER

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE ALLOWED_CUST = 'VALUE123'
```

---

#### SELECT #313 - Line 342

**File**: `TECH.CHARGE.DAILY.b`

**Routine**: `TECH.CHARGE.DAILY` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FBNK.TAX WITH @ID LIKE {Y.TAX.CODE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.TAX WITH @ID LIKE VALUE123...
```

**Table**: `FBNK.TAX`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'TAX'
-   Unresolved variables: Y.TAX.CODE

**Translated SQL**:
```sql
SELECT *
FROM FBNK_TAX
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #314 - Line 29

**File**: `TECH.CHARGE.DAILY.SELECT.b`

**Routine**: `TECH.CHARGE.DAILY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TECH.BOL.CHG.PARAM WITH NEXT.DATE LE {EB.SystemTables.getToday()} AND EXCEPTION NE Yes
```

**SIMULATED AT RUNTIME**:
```
SELECT TECH.BOL.CHG.PARAM WITH NEXT.DATE LE TODAY AND EXCEPTION NE Yes
```

**Table**: `TECH.BOL.CHG.PARAM`

**Fields** (2):
-  `EXCEPTION`  Type: D
-  `NEXT.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM TECH_BOL_CHG_PARAM
WHERE NEXT_DATE <= 'TODAY' AND EXCEPTION != 'Yes'
```

---

#### SELECT #315 - Line 39

**File**: `TECH.CHARGE.POB.SELECT.b`

**Routine**: `TECH.CHARGE.POB.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.TCIB`

**AS PER CODE**:
```
SELECT BAN.TCIB.AFFILIATION WITH (@ID LIKE '...PERSONAL' OR @ID LIKE '...MASTER') AND (STATUS EQ AFILIADO OR STATUS EQ REAFILIADO OR STATUS EQ DIFERIDA)
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TCIB.AFFILIATION WITH (@ID LIKE '...PERSONAL' OR @ID LIKE '...MASTER') AND (STATUS EQ AFILIADO OR STATUS EQ REAFILIADO OR STATUS EQ DIFERIDA)
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (2):
-  `STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
```

---

#### SELECT #316 - Line 40

**File**: `TECH.CHARGE.POB.SELECT.b`

**Routine**: `TECH.CHARGE.POB.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.AC`

**AS PER CODE**:
```
SELECT TECH.BOL.CHG.PARAM
```

**SIMULATED AT RUNTIME**:
```
SELECT TECH.BOL.CHG.PARAM
```

**Table**: `TECH.BOL.CHG.PARAM`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM TECH_BOL_CHG_PARAM
```

---

#### SELECT #317 - Line 85

**File**: `BAPA.B.MASIVE.AUTH.IHLD.SELECT.b`

**Routine**: `BAPA.B.MASIVE.AUTH.IHLD.SELECT` (BATCH (inferred))

**Variable**: `ySelCmd`

**AS PER CODE**:
```
SELECT {FN.SSTable} WITH RECORD.STATUS EQ 'IHLD'
```

**SIMULATED AT RUNTIME**:
```
SELECT {FN.SSTable} WITH RECORD.STATUS EQ 'IHLD'
```

**Table**: `SSTable`

**Fields** (1):
-  `RECORD.STATUS`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'SSTable' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/SSTable

**Translated SQL**:
```sql
SELECT *
FROM SSTable
WHERE RECORD_STATUS = 'IHLD'
```

---

#### SELECT #318 - Line 99

**File**: `BPA.B.EXTRACT.REFERE.A.SELECT.b`

**Routine**: `BPA.B.EXTRACT.REFERE.A.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING AND (ARR.STATUS NE AUTH AND ARR.STATUS NE UNAUTH) AND START.DATE LE {Y.LAST.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING AND (ARR.STATUS NE AUTH AND ARR.STATUS NE UNAUTH) AND START.DATE LE VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (3):
-  `START.DATE`  Type: D
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LAST.DAY

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING' AND ARR_STATUS != 'UNAUTH)' AND START_DATE <= 'VALUE123'
```

---

#### SELECT #319 - Line 55

**File**: `BAN.TT.CHQ.CONTROL.DETAIL.ID.b`

**Routine**: `BAN.TT.CHQ.CONTROL.DETAIL.ID` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TT.CHQ.CONTROL.DETAIL WITH @ID LIKE {Y.ID.TT}... BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TT.CHQ.CONTROL.DETAIL WITH @ID LIKE VALUE123... BY @ID
```

**Table**: `BAN.TT.CHQ.CONTROL.DETAIL`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID.TT

**Translated SQL**:
```sql
SELECT *
FROM BAN_TT_CHQ_CONTROL_DETAIL
WHERE ID LIKE 'VALUE123%'
ORDER BY ID ASC
```

---

#### SELECT #320 - Line 29

**File**: `BAPA.B.CONSOLIDA.ACCOUNTING.b`

**Routine**: `BAPA.B.CONSOLIDA.ACCOUNTING` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.DATA.FINAL.GEN.TEMP WITH RECID LIKE '{GROUP.ID}-...'
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.DATA.FINAL.GEN.TEMP WITH RECID LIKE 'SAMPLE_VALUE-...'
```

**Table**: `BACM3M.DATA.FINAL.GEN.TEMP`

**Fields** (1):
-  `RECID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: GROUP.ID

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_DATA_FINAL_GEN_TEMP
WHERE RECID LIKE 'SAMPLE_VALUE-%'
```

---

#### SELECT #321 - Line 46

**File**: `BAN.A.CLEARING.CHQRET.DEL.b`

**Routine**: `BAN.A.CLEARING.CHQRET.DEL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH FILE.NAME EQ {EB.SystemTables.getRNew(BAPALOCALTABLE.MigTablas3.BanOutClearingChqretHead.BanOcchFileName)}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH FILE.NAME EQ RNEW
```

**Table**: `BAN.OUT.CLEARING.CHQRET.DET`

**Fields** (1):
-  `FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_DET
WHERE FILE_NAME = 'RNEW'
```

---

#### SELECT #322 - Line 32

**File**: `BAN.A.FT.CAUSE.RETURN.b`

**Routine**: `BAN.A.FT.CAUSE.RETURN` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH LIKE {Y.FT.DEL}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH LIKE VALUE123...
```

**Table**: `FUNDS.TRANSFER$DEL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: Y.FT.DEL

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
```

---

#### SELECT #323 - Line 32

**File**: `BAN.A.FT.COMM.RETURN.b`

**Routine**: `BAN.A.FT.COMM.RETURN` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH LIKE {Y.FT.HIS}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$HIS WITH LIKE VALUE123...
```

**Table**: `FUNDS.TRANSFER$HIS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: Y.FT.HIS

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$HIS
```

---

#### SELECT #324 - Line 48

**File**: `BAN.A.INWARD.CLEARING.DEL.b`

**Routine**: `BAN.A.INWARD.CLEARING.DEL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH FILE.NAME EQ {EB.SystemTables.getRNew(BAPALOCALTABLE.MigTablas2.BanInwardClearingHead.BanIchFileName)}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH FILE.NAME EQ RNEW
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (1):
-  `FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE FILE_NAME = 'RNEW'
```

---

#### SELECT #325 - Line 53

**File**: `BAN.A.OUTCLG.CLEARED.APPLY.b`

**Routine**: `BAN.A.OUTCLG.CLEARED.APPLY` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD
```

**Table**: `BAN.OUT.CLEARING.CHQRET.HEAD`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_HEAD
```

---

#### SELECT #326 - Line 75

**File**: `BAN.B.BATCH.XML.b`

**Routine**: `BAN.B.BATCH.XML` (BATCH (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.BAN.DELIVERY.MAIL WITH STATUS EQ BATCH
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.DELIVERY.MAIL WITH STATUS EQ BATCH
```

**Table**: `BAN.DELIVERY.MAIL`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_DELIVERY_MAIL
WHERE STATUS = 'BATCH'
```

---

#### SELECT #327 - Line 127

**File**: `BAN.B.CHQ.GET.CLGDATA.b`

**Routine**: `BAN.B.CHQ.GET.CLGDATA` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CHEQUE.COLLECTION
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CHEQUE.COLLECTION
```

**Table**: `BAN.CHEQUE.COLLECTION`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_CHEQUE_COLLECTION
```

---

#### SELECT #328 - Line 152

**File**: `BAN.B.CHQ.GET.CLGDATA.b`

**Routine**: `BAN.B.CHQ.GET.CLGDATA` (BATCH (inferred))

**Variable**: `SEL.CMD.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH TXN.ID EQ {Y.ID.TT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH TXN.ID EQ VALUE123
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (1):
-  `TXN.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE TXN_ID = 'VALUE123'
```

---

#### SELECT #329 - Line 214

**File**: `BAN.B.CHQ.GET.CLGDATA.b`

**Routine**: `BAN.B.CHQ.GET.CLGDATA` (BATCH (inferred))

**Variable**: `SEL.CMD.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH TXN.ID EQ {Y.ID.TT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH TXN.ID EQ VALUE123
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (1):
-  `TXN.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE TXN_ID = 'VALUE123'
```

---

#### SELECT #330 - Line 73

**File**: `BAN.B.CHQ.OUTCLG.FILE.TOT.RET.b`

**Routine**: `BAN.B.CHQ.OUTCLG.FILE.TOT.RET` (BATCH (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH CHQ.STATUS EQ DEVUELTO AND FILE.DATE EQ {EB.SystemTables.getToday()} AND RETURN.CHEQUE EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH CHQ.STATUS EQ DEVUELTO AND FILE.DATE EQ TODAY AND RETURN.CHEQUE EQ ''
```

**Table**: `BAN.OUT.CLEARING.CHQRET.DET`

**Fields** (3):
-  `CHQ.STATUS`  Type: D
-  `RETURN.CHEQUE`  Type: D
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_DET
WHERE CHQ_STATUS = 'DEVUELTO' AND FILE_DATE = 'TODAY'
```

---

#### SELECT #331 - Line 38

**File**: `BAN.B.CHQ.VENCIDOS.SELECT.b`

**Routine**: `BAN.B.CHQ.VENCIDOS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ EXPIRED
```

**SIMULATED AT RUNTIME**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ EXPIRED
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE STATUS = 'EXPIRED'
```

---

#### SELECT #332 - Line 43

**File**: `BAN.B.DELETE.IHLD.FT.SELECT.b`

**Routine**: `BAN.B.DELETE.IHLD.FT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.FT.910.LIST
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.FT.910.LIST
```

**Table**: `BPA.FT.910.LIST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BPA.FT.910.LIST' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BPA.FT.910.LIST

**Translated SQL**:
```sql
SELECT *
FROM BPA_FT_910_LIST
```

---

#### SELECT #333 - Line 124

**File**: `BAN.B.FT.XML.b`

**Routine**: `BAN.B.FT.XML` (BATCH (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT FUNDS.TRANSFER$DEL LIKE {Y.FT.ID}... AND PROCESSING.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER$DEL LIKE VALUE123... AND PROCESSING.DATE EQ TODAY
```

**Table**: `FUNDS.TRANSFER$DEL`

**Fields** (1):
-  `PROCESSING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.FT.ID

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
WHERE PROCESSING_DATE = 'TODAY'
```

---

#### SELECT #334 - Line 33

**File**: `BAN.B.INCLG.CHQ.APPLY.SELECT.b`

**Routine**: `BAN.B.INCLG.CHQ.APPLY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING WITH HEAD.ID EQ {Y.HEAD.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING WITH HEAD.ID EQ VALUE123
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (1):
-  `HEAD.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.HEAD.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE HEAD_ID = 'VALUE123'
```

---

#### SELECT #335 - Line 154

**File**: `BAN.B.INCLG.CHQ.UPLOAD.b`

**Routine**: `BAN.B.INCLG.CHQ.UPLOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.INWARD.CLEARING.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #336 - Line 111

**File**: `BAN.B.INCLG.CHQ.UPLOAD.LOAD.b`

**Routine**: `BAN.B.INCLG.CHQ.UPLOAD.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #337 - Line 106

**File**: `BAN.B.INCLG.CHQ.UPLOAD.PRE.b`

**Routine**: `BAN.B.INCLG.CHQ.UPLOAD.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #338 - Line 213

**File**: `BAN.B.INCLG.CHQ.UPLOAD.PRE.b`

**Routine**: `BAN.B.INCLG.CHQ.UPLOAD.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.INWARD.CLEARING.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #339 - Line 37

**File**: `BAN.B.INCLG.PROC.RETURNED.REJ.SELECT.b`

**Routine**: `BAN.B.INCLG.PROC.RETURNED.REJ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING WITH FILE.DATE EQ {EB.SystemTables.getToday()} AND LOAD.STATUS EQ 'RECHAZADO' AND CHQ.STATUS EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING WITH FILE.DATE EQ TODAY AND LOAD.STATUS EQ 'RECHAZADO' AND CHQ.STATUS EQ ''
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (3):
-  `LOAD.STATUS`  Type: D
-  `CHQ.STATUS`  Type: D
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE FILE_DATE = 'TODAY' AND LOAD_STATUS = 'RECHAZADO'
```

---

#### SELECT #340 - Line 52

**File**: `BAN.B.INCLG.PROC.TOTAL.RET.SELECT.b`

**Routine**: `BAN.B.INCLG.PROC.TOTAL.RET.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING WITH FILE.DATE EQ {Y.TODAY} AND CHQ.STATUS EQ 'DEVUELTO'
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING WITH FILE.DATE EQ VALUE123 AND CHQ.STATUS EQ 'DEVUELTO'
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE FILE_DATE = 'VALUE123' AND CHQ_STATUS = 'DEVUELTO'
```

---

#### SELECT #341 - Line 168

**File**: `BAN.B.NOT.CHARGE.PLANILLA.b`

**Routine**: `BAN.B.NOT.CHARGE.PLANILLA` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FT.BULK.ITEM WITH @ID LIKE {Y.BLK.MAS.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT FT.BULK.ITEM WITH @ID LIKE VALUE123...
```

**Table**: `FT.BULK.ITEM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.BLK.MAS.ID

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_ITEM
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #342 - Line 50

**File**: `BAN.B.NOT.CHARGE.PLANILLA.SELECT.b`

**Routine**: `BAN.B.NOT.CHARGE.PLANILLA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FT.BULK.MASTER WITH (STATUS EQ 'PROCESSING' OR STATUS EQ 'PROCESSED') AND LT.STATUS.PLN EQ '' AND (BULK.TYPE EQ 'SINGLE.PLANILLA' OR BULK.TYPE EQ 'SINGLE.PROVEEDOR')
```

**SIMULATED AT RUNTIME**:
```
SELECT FT.BULK.MASTER WITH (STATUS EQ 'PROCESSING' OR STATUS EQ 'PROCESSED') AND LT.STATUS.PLN EQ '' AND (BULK.TYPE EQ 'SINGLE.PLANILLA' OR BULK.TYPE EQ 'SINGLE.PROVEEDOR')
```

**Table**: `FT.BULK.MASTER`

**Fields** (3):
-  `LT.STATUS.PLN`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,3>`)
-  `STATUS`  Type: D
-  `BULK.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.STATUS.PLN - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_MASTER
```

---

#### SELECT #343 - Line 80

**File**: `BAN.B.OUTCLG.CHQ.APPLY.b`

**Routine**: `BAN.B.OUTCLG.CHQ.APPLY` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH FILE.NAME EQ {Y.FILE.NAME} AND LOAD.STATUS EQ OK AND CHQ.STATUS EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH FILE.NAME EQ VALUE123 AND LOAD.STATUS EQ OK AND CHQ.STATUS EQ ''
```

**Table**: `BAN.OUT.CLEARING.CHQRET.DET`

**Fields** (3):
-  `FILE.NAME`  Type: D
-  `CHQ.STATUS`  Type: D
-  `LOAD.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.NAME

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_DET
WHERE FILE_NAME = 'VALUE123' AND LOAD_STATUS = 'OK'
```

---

#### SELECT #344 - Line 93

**File**: `BAN.B.OUTCLG.CLEARED.SELECT.b`

**Routine**: `BAN.B.OUTCLG.CLEARED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAFT.MigPago.getFnBanOutClearingChqretHead()} WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.OUT.CLEARING.CHQRET.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #345 - Line 135

**File**: `BAN.B.OUTCLG.CLEARED.SELECT.b`

**Routine**: `BAN.B.OUTCLG.CLEARED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.CC`

**AS PER CODE**:
```
SELECT {BAPAFT.MigPago.getFnChequeCollection()} WITH LT.SRC.EXP.DT EQ {BAPAFT.MigPago.getBatExpDate()} AND CHQ.STATUS EQ 'CLEARING' AND LT.ISSUE.DATE LE {EB.SystemTables.getToday()}{Y.ACCT}{EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT CHEQUE.COLLECTION WITH LT.SRC.EXP.DT EQ BAT.EXP.DATE AND CHQ.STATUS EQ 'CLEARING' AND LT.ISSUE.DATE LE TODAYVALUE123TODAY
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (3):
-  `LT.ISSUE.DATE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,22>`)
-  `LT.SRC.EXP.DT`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,10>`)
-  `CHQ.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.ISSUE.DATE, LT.SRC.EXP.DT - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCT

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE LT_SRC_EXP_DT = 'BAT.EXP.DATE' AND CHQ_STATUS = 'CLEARING' AND LT_ISSUE_DATE <= 'TODAYVALUE123TODAY'
```

---

#### SELECT #346 - Line 87

**File**: `BAN.B.SAVE.CHQRET.HEAD.b`

**Routine**: `BAN.B.SAVE.CHQRET.HEAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.OUT.CLEARING.CHQRET.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #347 - Line 96

**File**: `BAN.B.SAVE.CHQRET.HEAD.b`

**Routine**: `BAN.B.SAVE.CHQRET.HEAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH FILE.NAME EQ {Y.FILE.NAME} AND HEAD.ID EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH FILE.NAME EQ VALUE123 AND HEAD.ID EQ ''
```

**Table**: `BAN.OUT.CLEARING.CHQRET.DET`

**Fields** (2):
-  `FILE.NAME`  Type: D
-  `HEAD.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.NAME

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_DET
WHERE FILE_NAME = 'VALUE123'
```

---

#### SELECT #348 - Line 198

**File**: `BAN.B.SAVE.CHQRET.HEAD.b`

**Routine**: `BAN.B.SAVE.CHQRET.HEAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #349 - Line 87

**File**: `BAN.B.SAVE.INCLG.HEAD.b`

**Routine**: `BAN.B.SAVE.INCLG.HEAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.INWARD.CLEARING.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #350 - Line 98

**File**: `BAN.B.SAVE.INCLG.HEAD.b`

**Routine**: `BAN.B.SAVE.INCLG.HEAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH FILE.NAME EQ {Y.FILE.NAME} AND HEAD.ID EQ ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH FILE.NAME EQ VALUE123 AND HEAD.ID EQ ''
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (2):
-  `FILE.NAME`  Type: D
-  `HEAD.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.NAME

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE FILE_NAME = 'VALUE123'
```

---

#### SELECT #351 - Line 190

**File**: `BAN.B.SAVE.INCLG.HEAD.b`

**Routine**: `BAN.B.SAVE.INCLG.HEAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #352 - Line 49

**File**: `BAN.B.TXN.PENDING.BENEF.b`

**Routine**: `BAN.B.TXN.PENDING.BENEF` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.PENDING.TRX
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PENDING.TRX
```

**Table**: `BAN.PENDING.TRX`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_PENDING_TRX
```

---

#### SELECT #353 - Line 52

**File**: `BAN.B.TXN.PENDING.BENEF.b`

**Routine**: `BAN.B.TXN.PENDING.BENEF` (BATCH (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.BAN.PENDING.TRX WITH @ID LE {Y.TODAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PENDING.TRX WITH @ID LE VALUE123
```

**Table**: `BAN.PENDING.TRX`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM BAN_PENDING_TRX
WHERE ID <= 'VALUE123'
```

---

#### SELECT #354 - Line 47

**File**: `BAN.BUILD.OUTCLG.b`

**Routine**: `BAN.BUILD.OUTCLG` (Unknown)

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION$NAU
```

**Table**: `CHEQUE.COLLECTION$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CHEQUE.COLLECTION'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
```

---

#### SELECT #355 - Line 54

**File**: `BAN.CHANGE.EXPDATE.b`

**Routine**: `BAN.CHANGE.EXPDATE` (Unknown)

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION$NAU
```

**Table**: `CHEQUE.COLLECTION$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CHEQUE.COLLECTION'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
```

---

#### SELECT #356 - Line 52

**File**: `BAN.E.CNV.TOD.CHQ.b`

**Routine**: `BAN.E.CNV.TOD.CHQ` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
```

---

#### SELECT #357 - Line 48

**File**: `BAN.E.CNV.TOT.REG.b`

**Routine**: `BAN.E.CNV.TOT.REG` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH @ID EQ {Y.ID} AND (FILE.STATUS EQ CARGADOOR FILE.STATUS EQ PROCESADO)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH @ID EQ 12345 AND (FILE.STATUS EQ CARGADOOR FILE.STATUS EQ PROCESADO)
```

**Table**: `BAN.INWARD.CLEARING.HEAD`

**Fields** (2):
-  `FILE.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING_HEAD
WHERE ID = '12345'
```

---

#### SELECT #358 - Line 46

**File**: `BAN.E.CNV.TOT.VAL.b`

**Routine**: `BAN.E.CNV.TOT.VAL` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH @ID EQ {Y.ID} AND (FILE.STATUS EQ CARGADO OR FILE.STATUS EQ PROCESADO)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING.HEAD WITH @ID EQ 12345 AND (FILE.STATUS EQ CARGADO OR FILE.STATUS EQ PROCESADO)
```

**Table**: `BAN.INWARD.CLEARING.HEAD`

**Fields** (2):
-  `FILE.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING_HEAD
WHERE ID = '12345'
```

---

#### SELECT #359 - Line 96

**File**: `BAN.E.NOF.BLD.CHQ.SUPP.b`

**Routine**: `BAN.E.NOF.BLD.CHQ.SUPP` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID LIKE {Y.TODAY}... AND CHQ.ACCOUNT LIKE {Y.CHQ.ACCOUNT}... AND CHQ.ACCOUNT LIKE {Y.CHQ.ACCOUNT}... AND CHQ.ACCOUNT EQ {Y.CHQ.ACCOUNT} AND CHQ.ACCOUNT EQ {Y.CHQ.ACCOUNT} AND CHQ.NUMBER EQ {Y.CHQ.NUMBER} AND CHQ.NUMBER EQ {Y.CHQ.NUMBER} AND CHQ.AMOUNT EQ {Y.CHQ.AMO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID LIKE VALUE123... AND CHQ.ACCOUNT LIKE VALUE123... AND CHQ.ACCOUNT LIKE VALUE123... AND CHQ.ACCOUNT EQ VALUE123 AND CHQ.ACCOUNT EQ VALUE123 AND CHQ.NUMBER EQ VALUE123 AND CHQ.NUMBER EQ VALUE123 AND CHQ.AMOUNT EQ VALUE123 AND CHQ.AMOUNT EQ VALUE123 AND BEN.BANK EQ
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (7):
-  `CHQ.NUMBER`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `PROCESS.STATUS`  Type: D
-  `BEN.BANK`  Type: D
-  `@ID`  Type: D
-  `CHQ.RET.CODE`  Type: D
-  `CHQ.AMOUNT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TODAY, Y.CHQ.ACCOUNT, Y.CHQ.NUMBER, Y.CHQ.AMOUNT, Y.BEN.BANK

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID LIKE 'VALUE123%' AND CHQ_ACCOUNT LIKE 'VALUE123%' AND CHQ_ACCOUNT LIKE 'VALUE123%' AND CHQ_ACCOUNT = 'VALUE123' AND CHQ_ACCOUNT = 'VALUE123' AND CHQ_NUMBER = 'VALUE123' AND CHQ_NUMBER = 'VALUE123' AND CHQ_AMOUNT = 'VALUE123' AND CHQ_AMOUNT = 'VALUE123' AND BEN_BANK = 'VALUE123' AND BEN_BANK = 'VALUE123' AND CHQ_RET_CODE = 'VALUE123' AND CHQ_RET_CODE = 'VALUE123' AND PROCESS_STATUS = 'PROCESADO' AND PROCESS_STATUS = 'PROCESADO'
ORDER BY CHQ_ACCOUNT ASC, CHQ_ACCOUNT ASC
```

---

#### SELECT #360 - Line 81

**File**: `BAN.E.NOF.CHQ.ACCT.INFO.b`

**Routine**: `BAN.E.NOF.CHQ.ACCT.INFO` (NOFILE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH (CHQ.STATUS EQ DEPOSITED OR CHQ.STATUS EQ CLEARING) AND CREDIT.ACC.NO EQ {Y.CHQ.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH (CHQ.STATUS EQ DEPOSITED OR CHQ.STATUS EQ CLEARING) AND CREDIT.ACC.NO EQ VALUE123
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `CREDIT.ACC.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CHQ.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CREDIT_ACC_NO = 'VALUE123'
```

---

#### SELECT #361 - Line 79

**File**: `BAN.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Routine**: `BAN.E.NOF.CHQ.OUTCLG.AUT.RET` (NOFILE (inferred))

**Variable**: `SEL.CHQ.COL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED  AND LT.RET.COD.CC NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO) AND CHEQUE.NO EQ {CHEQUE.NO.VAL} AND CHEQUE.NO NE {CHEQUE.NO.VAL} AND CHEQUE.NO LK ...{CHEQUE.NO.VAL}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED  AND LT.RET.COD.CC NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO) AND CHEQUE.NO EQ SAMPLE_VALUE AND CHEQUE.NO NE SAMPLE_VALUE AND CHEQUE.NO LK ...SAMPLE_VALUE...
```

**Table**: `CHEQUE.COLLECTION$NAU`

**Fields** (4):
-  `CHQ.STATUS`  Type: D
-  `CHEQUE.NO`  Type: D
-  `RECORD.STATUS`  Type: D
-  `LT.RET.COD.CC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CHEQUE.COLLECTION'
-   INFO: LOCAL.REF fields found: LT.RET.COD.CC - Physical fields in database (TAFJ compatible)
-   Unresolved variables: CHEQUE.NO.VAL

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
WHERE CHQ_STATUS = 'RETURNED' AND CHEQUE_NO = 'SAMPLE_VALUE' AND CHEQUE_NO != 'SAMPLE_VALUE'
```

---

#### SELECT #362 - Line 82

**File**: `BAN.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Routine**: `BAN.E.NOF.CHQ.OUTCLG.AUT.RET` (NOFILE (inferred))

**Variable**: `SEL.FT.STMT`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.RET.COD.CC NE "" AND LT.CC.ID NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.RET.COD.CC NE "" AND LT.CC.ID NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (3):
-  `LT.RET.COD.CC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,25>`)
-  `LT.CC.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,31>`)
-  `RECORD.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   INFO: LOCAL.REF fields found: LT.RET.COD.CC, LT.CC.ID - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #363 - Line 91

**File**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET.ADM.b`

**Routine**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET.ADM` (NOFILE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND CO.CODE EQ {EB.SystemTables.getIdCompany()} AND CHEQUE.NO EQ {CHEQUE.NO.VAL} AND CHEQUE.NO NE {CHEQUE.NO.VAL} AND CHEQUE.NO LK ...{CHEQUE.NO.VAL}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND CO.CODE EQ ID.COMPANY AND CHEQUE.NO EQ SAMPLE_VALUE AND CHEQUE.NO NE SAMPLE_VALUE AND CHEQUE.NO LK ...SAMPLE_VALUE...
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (3):
-  `CO.CODE`  Type: D
-  `CHQ.STATUS`  Type: D
-  `CHEQUE.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: CHEQUE.NO.VAL

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHQ_STATUS = 'DEPOSITED' AND CO_CODE = 'ID.COMPANY' AND CHEQUE_NO = 'SAMPLE_VALUE' AND CHEQUE_NO != 'SAMPLE_VALUE'
```

---

#### SELECT #364 - Line 89

**File**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET.ATM.b`

**Routine**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET.ATM` (NOFILE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND CO.CODE EQ {EB.SystemTables.getIdCompany()} AND TXN.ID LIKE FT... AND CHEQUE.NO EQ {CHEQUE.NO.VAL} AND CHEQUE.NO NE {CHEQUE.NO.VAL} AND CHEQUE.NO LK ...{CHEQUE.NO.VAL}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND CO.CODE EQ ID.COMPANY AND TXN.ID LIKE FT... AND CHEQUE.NO EQ SAMPLE_VALUE AND CHEQUE.NO NE SAMPLE_VALUE AND CHEQUE.NO LK ...SAMPLE_VALUE...
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (4):
-  `CO.CODE`  Type: D
-  `CHQ.STATUS`  Type: D
-  `TXN.ID`  Type: D
-  `CHEQUE.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: CHEQUE.NO.VAL

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHQ_STATUS = 'DEPOSITED' AND CO_CODE = 'ID.COMPANY' AND TXN_ID LIKE 'FT%' AND CHEQUE_NO = 'SAMPLE_VALUE' AND CHEQUE_NO != 'SAMPLE_VALUE'
```

---

#### SELECT #365 - Line 108

**File**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET.b`

**Routine**: `BAN.E.NOF.CHQ.OUTCLG.CLDRET` (NOFILE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ {R.TELLER.USR<1>} AND CO.CODE EQ {EB.SystemTables.getIdCompany()} AND CHEQUE.NO EQ {CHEQUE.NO.VAL} AND CHEQUE.NO NE {CHEQUE.NO.VAL} AND CHEQUE.NO LK ...{CHEQUE.NO.VAL}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ {R.TELLER.USR<1>} AND CO.CODE EQ ID.COMPANY AND CHEQUE.NO EQ SAMPLE_VALUE AND CHEQUE.NO NE SAMPLE_VALUE AND CHEQUE.NO LK ...SAMPLE_VALUE...
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (4):
-  `CO.CODE`  Type: D
-  `CHQ.STATUS`  Type: D
-  `CHEQUE.NO`  Type: D
-  `LT.DEP.TT.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,4>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.DEP.TT.ID - Physical fields in database (TAFJ compatible)
-   Unresolved variables: CHEQUE.NO.VAL

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHQ_STATUS = 'DEPOSITED' AND LT_DEP_TT_ID = '{R.TELLER.USR<1>}' AND CO_CODE = 'ID.COMPANY' AND CHEQUE_NO = 'SAMPLE_VALUE' AND CHEQUE_NO != 'SAMPLE_VALUE'
```

---

#### SELECT #366 - Line 46

**File**: `BAN.E.NOF.FT.ENQ.AML.HIT.b`

**Routine**: `BAN.E.NOF.FT.ENQ.AML.HIT` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.FUNDS.TRANSFER$DEL} WITH CREDIT.THEIR.REF EQ '' AND DELIVERY.INREF NE ''
```

**SIMULATED AT RUNTIME**:
```
SELECT {F.FUNDS.TRANSFER$DEL} WITH CREDIT.THEIR.REF EQ '' AND DELIVERY.INREF NE ''
```

**Table**: `FUNDS.TRANSFER$DEL`

**Fields** (2):
-  `CREDIT.THEIR.REF`  Type: D
-  `DELIVERY.INREF`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: F.FUNDS.TRANSFER$DEL

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
```

---

#### SELECT #367 - Line 86

**File**: `BAN.E.NOF.INCLG.FILE.LOTE.b`

**Routine**: `BAN.E.NOF.INCLG.FILE.LOTE` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING @ID LIKE {Y.DATE.ID}... AND HEAD.ID EQ {Y.HEAD.ID} BY LOTE.NUMBER BY CHQ.TYPE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING @ID LIKE VALUE123... AND HEAD.ID EQ VALUE123 BY LOTE.NUMBER BY CHQ.TYPE
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (3):
-  `CHQ.TYPE`  Type: D
-  `LOTE.NUMBER`  Type: D
-  `HEAD.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.DATE.ID, Y.HEAD.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE HEAD_ID = 'VALUE123'
ORDER BY LOTE_NUMBER ASC, CHQ_TYPE ASC
```

---

#### SELECT #368 - Line 140

**File**: `BAN.E.NOF.INCLG.RECH.OFFICER.b`

**Routine**: `BAN.E.NOF.INCLG.RECH.OFFICER` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ {R.BAN.INCLG.CHQ.REJECTED} AND LOAD.STATUS EQ RECHAZADO AND CHQ.RET.CODE EQ {Y.CIN.RET.COD.OFF} AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT.OFI EQ {Y.USR.OFFICER} BY CHQ.ACCOUNT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ SAMPLE_VALUE AND LOAD.STATUS EQ RECHAZADO AND CHQ.RET.CODE EQ VALUE123 AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT.OFI EQ VALUE123 BY CHQ.ACCOUNT
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (7):
-  `CHQ.ACCOUNT.OFI`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `PROCESS.STATUS`  Type: D
-  `LOAD.STATUS`  Type: D
-  `@ID`  Type: D
-  `CHQ.RET.CODE`  Type: D
-  `CHQ.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CHQ.ACCOUNT.OFI' used in condition (cannot create index on M fields)
-   Unresolved variables: R.BAN.INCLG.CHQ.REJECTED, Y.CIN.RET.COD.OFF, Y.USR.OFFICER

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID = 'SAMPLE_VALUE' AND LOAD_STATUS = 'RECHAZADO' AND CHQ_RET_CODE = 'VALUE123' AND CHQ_TYPE = 'CTACTE' AND PROCESS_STATUS = 'PROCESADO' AND CHQ_ACCOUNT_OFI = 'VALUE123'
ORDER BY CHQ_ACCOUNT ASC
```

---

#### SELECT #369 - Line 152

**File**: `BAN.E.NOF.INCLG.RECH.OFFICER.b`

**Routine**: `BAN.E.NOF.INCLG.RECH.OFFICER` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ {R.BAN.INCLG.CHQ.REJECTED} AND LOAD.STATUS EQ RECHAZADO AND CHQ.RET.CODE EQ {Y.CIN.RET.COD.OFF} AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT.OFI EQ {Y.USR.OFFICER} BY CHQ.ACCOUNT{SEL.CMD.SUPERVISOR} AND CHQ.ACCOUNT.CO EQ {Y.COMPANY} 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ SAMPLE_VALUE AND LOAD.STATUS EQ RECHAZADO AND CHQ.RET.CODE EQ VALUE123 AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT.OFI EQ VALUE123 BY CHQ.ACCOUNTSAMPLE_VALUE AND CHQ.ACCOUNT.CO EQ VALUE123 BY CHQ.ACCOUNT
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (9):
-  `CHQ.ACCOUNT.OFI`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `PROCESS.STATUS`  Type: D
-  `CHQ.ACCOUNTSAMPLE_VALUE`  Type: Unknown
-  `LOAD.STATUS`  Type: D
-  `@ID`  Type: D
-  `CHQ.RET.CODE`  Type: D
-  `CHQ.ACCOUNT.CO`  Type: D
-  `CHQ.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CHQ.ACCOUNT.OFI' used in condition (cannot create index on M fields)
-   Unresolved variables: R.BAN.INCLG.CHQ.REJECTED, Y.CIN.RET.COD.OFF, Y.USR.OFFICER, SEL.CMD.SUPERVISOR, Y.COMPANY

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID = 'SAMPLE_VALUE' AND LOAD_STATUS = 'RECHAZADO' AND CHQ_RET_CODE = 'VALUE123' AND CHQ_TYPE = 'CTACTE' AND PROCESS_STATUS = 'PROCESADO' AND CHQ_ACCOUNT_OFI = 'VALUE123' AND CHQ_ACCOUNT_CO = 'VALUE123'
ORDER BY CHQ_ACCOUNTSAMPLE_VALUE ASC, CHQ_ACCOUNT ASC
```

---

#### SELECT #370 - Line 113

**File**: `BAN.E.NOF.INCLG.RECH.TOTAL.b`

**Routine**: `BAN.E.NOF.INCLG.RECH.TOTAL` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ {R.BAN.INCLG.CHQ.REJECTED} AND LOAD.STATUS EQ RECHAZADO AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT EQ {Y.FLD.ACCOUNT} AND CHQ.ACCOUNT.CO EQ {Y.FLD.AGE} AND CHQ.RET.CODE EQ {Y.FLD.RET.COD} AND CHQ.ACCOUNT.OFI EQ {Y.FLD.ACC.OFI} AND 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID EQ SAMPLE_VALUE AND LOAD.STATUS EQ RECHAZADO AND CHQ.TYPE EQ CTACTE AND PROCESS.STATUS EQ PROCESADO AND CHQ.ACCOUNT EQ VALUE123 AND CHQ.ACCOUNT.CO EQ VALUE123 AND CHQ.RET.CODE EQ VALUE123 AND CHQ.ACCOUNT.OFI EQ VALUE123 AND CHQ.ACCOUNT.ORG EQ VALUE123 BY CHQ.ACC
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (9):
-  `CHQ.ACCOUNT.OFI`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `PROCESS.STATUS`  Type: D
-  `LOAD.STATUS`  Type: D
-  `@ID`  Type: D
-  `CHQ.RET.CODE`  Type: D
-  `CHQ.ACCOUNT.CO`  Type: D
-  `CHQ.TYPE`  Type: D
-  `CHQ.ACCOUNT.ORG`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CHQ.ACCOUNT.OFI' used in condition (cannot create index on M fields)
-   Unresolved variables: R.BAN.INCLG.CHQ.REJECTED, Y.FLD.ACCOUNT, Y.FLD.AGE, Y.FLD.RET.COD, Y.FLD.ACC.OFI

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID = 'SAMPLE_VALUE' AND LOAD_STATUS = 'RECHAZADO' AND CHQ_TYPE = 'CTACTE' AND PROCESS_STATUS = 'PROCESADO' AND CHQ_ACCOUNT = 'VALUE123' AND CHQ_ACCOUNT_CO = 'VALUE123' AND CHQ_RET_CODE = 'VALUE123' AND CHQ_ACCOUNT_OFI = 'VALUE123' AND CHQ_ACCOUNT_ORG = 'VALUE123'
ORDER BY CHQ_ACCOUNT ASC
```

---

#### SELECT #371 - Line 160

**File**: `BAN.E.NOF.OUTCLG.RET.TOT.b`

**Routine**: `BAN.E.NOF.OUTCLG.RET.TOT` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ RETURNED AND STATUS.DATE EQ {Y.STATUS.DATE} AND BANK.SORT.CODE EQ {Y.BANK.SORT.CODE} AND CO.CODE EQ {Y.CO.CODE} AND LT.CHEQUE.ACC EQ {Y.CHEQUE.ACC} AND CREDIT.ACC.NO EQ {Y.CREDIT.ACC.NO} AND LT.RET.COD.CC EQ {Y.RET.COD.CC} AND LT.RET.FUNDS EQ {Y.RET.FUND
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ RETURNED AND STATUS.DATE EQ VALUE123 AND BANK.SORT.CODE EQ VALUE123 AND CO.CODE EQ VALUE123 AND LT.CHEQUE.ACC EQ VALUE123 AND CREDIT.ACC.NO EQ VALUE123 AND LT.RET.COD.CC EQ VALUE123 AND LT.RET.FUNDS EQ VALUE123 AND BANK.SORT.CODE NE SAMPLE_VALUE BY BANK.
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (9):
-  `CHQ.STATUS`  Type: D
-  `LT.CHEQUE.ACC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,3>`)
-  `STATUS.DATE`  Type: D
-  `CREDIT.ACC.NO`  Type: D
-  `LT.CHQ.ACC.TYP`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,13>`)
-  `LT.RET.COD.CC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)
-  `LT.RET.FUNDS`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,11>`)
-  `CO.CODE`  Type: D
-  `BANK.SORT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)
-   INFO: LOCAL.REF fields found: LT.CHEQUE.ACC, LT.CHQ.ACC.TYP, LT.RET.COD.CC, LT.RET.FUNDS - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.STATUS.DATE, Y.BANK.SORT.CODE, Y.CO.CODE, Y.CHEQUE.ACC, Y.CREDIT.ACC.NO

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHQ_STATUS = 'RETURNED' AND STATUS_DATE = 'VALUE123' AND BANK_SORT_CODE = 'VALUE123' AND CO_CODE = 'VALUE123' AND LT_CHEQUE_ACC = 'VALUE123' AND CREDIT_ACC_NO = 'VALUE123' AND LT_RET_COD_CC = 'VALUE123' AND LT_RET_FUNDS = 'VALUE123' AND BANK_SORT_CODE != 'SAMPLE_VALUE'
ORDER BY BANK_SORT_CODE ASC, LT_CHEQUE_ACC ASC, LT_CHQ_ACC_TYP ASC, LT_RET_COD_CC ASC
```

---

#### SELECT #372 - Line 121

**File**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS.ERROR.b`

**Routine**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS.ERROR` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FT.BULK.MASTER WITH CUSTOMER EQ {Y.ID} AND PROCESSING.DATE GE {Y.START.DATE} AND PROCESSING.DATE LE {Y.END.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.MASTER WITH CUSTOMER EQ 12345 AND PROCESSING.DATE GE VALUE123 AND PROCESSING.DATE LE VALUE123
```

**Table**: `FT.BULK.MASTER`

**Fields** (2):
-  `CUSTOMER`  Type: D
-  `PROCESSING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID, Y.START.DATE, Y.END.DATE

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_MASTER
WHERE CUSTOMER = '12345' AND PROCESSING_DATE >= 'VALUE123' AND PROCESSING_DATE <= 'VALUE123'
```

---

#### SELECT #373 - Line 189

**File**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS.ERROR.b`

**Routine**: `BAN.E.NOF.TCIB.PLANILLA.ITEMS.ERROR` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FT.BULK.ITEM WITH @ID LIKE {Y.FT.BULK.MASTER.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FT.BULK.ITEM WITH @ID LIKE VALUE123...
```

**Table**: `FT.BULK.ITEM`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM FT_BULK_ITEM
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #374 - Line 46

**File**: `BAN.ENQ.B.OUTCLG.AUT.b`

**Routine**: `BAN.ENQ.B.OUTCLG.AUT` (BATCH (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ CLEARED OR (CHQ.STATUS EQ 'RETURNED' AND LT.RET.COD.CHQ NE '')
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ CLEARED OR (CHQ.STATUS EQ 'RETURNED' AND LT.RET.COD.CHQ NE '')
```

**Table**: `CHEQUE.COLLECTION$NAU`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `LT.RET.COD.CHQ`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,2>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CHEQUE.COLLECTION'
-   INFO: LOCAL.REF fields found: LT.RET.COD.CHQ - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
WHERE CHQ_STATUS = 'CLEARED'
```

---

#### SELECT #375 - Line 74

**File**: `BAN.I.FT.INPUT.FW.b`

**Routine**: `BAN.I.FT.INPUT.FW` (Unknown)

**Variable**: `SEL.WITH.BANK.ACC`

**AS PER CODE**:
```
SELECT F.AGENCY WITH ABA.NUMBER EQ {Y.ABA}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AGENCY WITH ABA.NUMBER EQ //FW
```

**Table**: `AGENCY`

**Fields** (1):
-  `ABA.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AGENCY
WHERE ABA_NUMBER = '//FW'
```

---

#### SELECT #376 - Line 61

**File**: `BAN.I.OUTCLG.CLEARED.VAL.b`

**Routine**: `BAN.I.OUTCLG.CLEARED.VAL` (Unknown)

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.OUT.CLEARING.CHQRET.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #377 - Line 103

**File**: `BAN.I.RETURN.CODE.b`

**Routine**: `BAN.I.RETURN.CODE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.ERROR WITH @ID EQ {EREPLACE(Y.IDS.LST,@VM," ")}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.ERROR WITH @ID EQ {EREPLACE(Y.IDS.LST,@VM," ")}
```

**Table**: `EB.ERROR`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: EREPLACE(Y.IDS.LST,@VM," ")

**Translated SQL**:
```sql
SELECT *
FROM EB_ERROR
WHERE ID = '{EREPLACE(Y.IDS.LST,@VM,'
```

---

#### SELECT #378 - Line 61

**File**: `BAN.OUTCLG.CLDCC.b`

**Routine**: `BAN.OUTCLG.CLDCC` (Unknown)

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.CC.ID NE ''
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.CC.ID NE ''
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (1):
-  `LT.CC.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,31>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   INFO: LOCAL.REF fields found: LT.CC.ID - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #379 - Line 91

**File**: `BAN.S.CHQ.CLG.CHQ.GER.b`

**Routine**: `BAN.S.CHQ.CLG.CHQ.GER` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.TYPE WITH ASSIGNED.CATEGORY EQ {R.ACCOUNT<AC.AccountOpening.Account.Category>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.TYPE WITH ASSIGNED.CATEGORY EQ {R.ACCOUNT<AC.AccountOpening.Account.Category>}
```

**Table**: `CHEQUE.TYPE`

**Fields** (1):
-  `ASSIGNED.CATEGORY`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_TYPE
WHERE ASSIGNED_CATEGORY = '{R.ACCOUNT<AC.AccountOpening.Account.Category>}'
```

---

#### SELECT #380 - Line 48

**File**: `BAN.S.CHQ.VERIFY.USR.b`

**Routine**: `BAN.S.CHQ.VERIFY.USR` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OTHER.OFFICER WITH ID.USER EQ {Y.USER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OTHER.OFFICER WITH ID.USER EQ VALUE123
```

**Table**: `BAN.OTHER.OFFICER`

**Fields** (1):
-  `ID.USER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USER

**Translated SQL**:
```sql
SELECT *
FROM BAN_OTHER_OFFICER
WHERE ID_USER = 'VALUE123'
```

---

#### SELECT #381 - Line 43

**File**: `BAN.S.CLG.BAN.SORT.CODE.b`

**Routine**: `BAN.S.CLG.BAN.SORT.CODE` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BC.SORT.CODE WITH LT.BANK.FROM EQ 'PRP'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BC.SORT.CODE WITH LT.BANK.FROM EQ 'PRP'
```

**Table**: `BC.SORT.CODE`

**Fields** (1):
-  `LT.BANK.FROM`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.BANK.FROM - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM BC_SORT_CODE
WHERE LT_BANK_FROM = 'PRP'
```

---

#### SELECT #382 - Line 97

**File**: `BAPA.B.VAL.ACT.PAYMENT.CHG.LOAD.b`

**Routine**: `BAPA.B.VAL.ACT.PAYMENT.CHG.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TAX
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TAX
```

**Table**: `TAX`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM TAX
```

---

#### SELECT #383 - Line 135

**File**: `BAPA.E.NOF.ALL.TFS.b`

**Routine**: `BAPA.E.NOF.ALL.TFS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER WITH @ID NE '' AND CO.CODE EQ {Y.CO.CODE} AND TRANSACTION.CODE EQ {Y.TXN} AND (TELLER.ID.1 EQ {Y.TT} OR TELLER.ID.2 EQ {Y.TT}) BY CO.CODE 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER WITH @ID NE '' AND CO.CODE EQ VALUE123 AND TRANSACTION.CODE EQ VALUE123 AND (TELLER.ID.1 EQ VALUE123 OR TELLER.ID.2 EQ VALUE123) BY CO.CODE 
```

**Table**: `TELLER`

**Fields** (4):
-  `TELLER.ID.2`  Type: D
-  `CO.CODE`  Type: D
-  `TRANSACTION.CODE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CO.CODE, Y.TXN, Y.TT

**Translated SQL**:
```sql
SELECT *
FROM TELLER
WHERE CO_CODE = 'VALUE123' AND TRANSACTION_CODE = 'VALUE123'
ORDER BY CO_CODE ASC
```

---

#### SELECT #384 - Line 324

**File**: `BAPA.E.NOF.ALL.TFS.b`

**Routine**: `BAPA.E.NOF.ALL.TFS` (NOFILE (inferred))

**Variable**: `SELECT.CHQ.COLLE`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH TXN.ID EQ {FIELDS(Y.KEY.ID,"|",4)}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH TXN.ID EQ {FIELDS(Y.KEY.ID,"|",4)}
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (1):
-  `TXN.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FIELDS(Y.KEY.ID,"|",4)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE TXN_ID = '{FIELDS(Y.KEY.ID,'
```

---

#### SELECT #385 - Line 168

**File**: `BAPA.E.NOF.COMP.TT.ING.b`

**Routine**: `BAPA.E.NOF.COMP.TT.ING` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.TELLER.ID WITH USER EQ {Y.USER} AND STATUS EQ OPEN
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.ID WITH USER EQ VALUE123 AND STATUS EQ OPEN
```

**Table**: `TELLER.ID`

**Fields** (2):
-  `USER`  Type: D
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USER

**Translated SQL**:
```sql
SELECT *
FROM TELLER_ID
WHERE USER = 'VALUE123' AND STATUS = 'OPEN'
```

---

#### SELECT #386 - Line 197

**File**: `BAPA.E.NOF.COMP.TT.ING.b`

**Routine**: `BAPA.E.NOF.COMP.TT.ING` (NOFILE (inferred))

**Variable**: `SELECT.TT`

**AS PER CODE**:
```
SELECT F.TELLER WITH TELLER.ID.1 EQ {TELLER.ID.LIST}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER WITH TELLER.ID.1 EQ SAMPLE_VALUE
```

**Table**: `TELLER`

**Fields** (1):
-  `TELLER.ID.1`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: TELLER.ID.LIST

**Translated SQL**:
```sql
SELECT *
FROM TELLER
WHERE TELLER_ID_1 = 'SAMPLE_VALUE'
```

---

#### SELECT #387 - Line 133

**File**: `BAPA3M.B.INTF.CHQ.STATUS.EXT.b`

**Routine**: `BAPA3M.B.INTF.CHQ.STATUS.EXT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAPA3M.CONCAT.CHEQUE.PROC
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAPA3M.CONCAT.CHEQUE.PROC
```

**Table**: `BAPA3M.CONCAT.CHEQUE.PROC`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAPA3M_CONCAT_CHEQUE_PROC
```

---

#### SELECT #388 - Line 45

**File**: `BAPA3M.B.INTF.STOPPED.SELECT.b`

**Routine**: `BAPA3M.B.INTF.STOPPED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CONCAT.CMD`

**AS PER CODE**:
```
SELECT BAPA3M.CONCAT.CHEQUE.PROC
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA3M.CONCAT.CHEQUE.PROC
```

**Table**: `BAPA3M.CONCAT.CHEQUE.PROC`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAPA3M_CONCAT_CHEQUE_PROC
```

---

#### SELECT #389 - Line 80

**File**: `BAPA3M.I.VALIDATE.CHECK.BOOK.TYPE.b`

**Routine**: `BAPA3M.I.VALIDATE.CHECK.BOOK.TYPE` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.PARAMETERS.CHEQUE.BOOK WITH VALID.REQUEST EQ {FIELD(ID.NEW,'.',1)}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PARAMETERS.CHEQUE.BOOK WITH VALID.REQUEST EQ {FIELD(ID.NEW,'.',1)}
```

**Table**: `BAN.PARAMETERS.CHEQUE.BOOK`

**Fields** (1):
-  `VALID.REQUEST`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'VALID.REQUEST' used in condition (cannot create index on M fields)
-   Unresolved variables: FIELD(ID.NEW,'.',1)

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAMETERS_CHEQUE_BOOK
WHERE VALID_REQUEST = '{FIELD(ID.NEW,'
```

---

#### SELECT #390 - Line 87

**File**: `BAPA3M.V.VAL.CHQ.ACT.INTF.b`

**Routine**: `BAPA3M.V.VAL.CHQ.ACT.INTF` (VERSION (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {F.STOCK.REGISTER} WITH @ID LIKE CHQ.{EB.SystemTables.getIdCompany()}...
```

**SIMULATED AT RUNTIME**:
```
SELECT STOCK.REGISTER WITH @ID LIKE CHQ.ID.COMPANY...
```

**Table**: `STOCK.REGISTER`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: F.STOCK.REGISTER

**Translated SQL**:
```sql
SELECT *
FROM STOCK_REGISTER
WHERE ID LIKE 'CHQ.ID.COMPANY%'
```

---

#### SELECT #391 - Line 40

**File**: `BCM.B.CHQ.CERT.STATUS.SELECT.b`

**Routine**: `BCM.B.CHQ.CERT.STATUS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ ISSUED AND LT.CH.C.VALIDAC EQ CERT
```

**SIMULATED AT RUNTIME**:
```
SELECT CHEQUE.REGISTER.SUPPLEMENT WITH STATUS EQ ISSUED AND LT.CH.C.VALIDAC EQ CERT
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (2):
-  `LT.CH.C.VALIDAC`  Type: I (Formula: `LOCAL.REF<1,1>`)
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LT.CH.C.VALIDAC' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE STATUS = 'ISSUED' AND LT_CH_C_VALIDAC = 'CERT'
```

---

#### SELECT #392 - Line 110

**File**: `BCM.B.RH.UP.PAYMENT.LOAD.b`

**Routine**: `BCM.B.RH.UP.PAYMENT.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamInputDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamInputDir>
```

---

#### SELECT #393 - Line 118

**File**: `BCM.E.NOF.RH.PAY.RESULT.b`

**Routine**: `BCM.E.NOF.RH.PAY.RESULT` (NOFILE (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ PROCESSED ERROR.PROCESS BY STATUS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ PROCESSED ERROR.PROCESS BY STATUS
```

**Table**: `BCM.RH.PAYROLL`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BCM_RH_PAYROLL
WHERE STATUS = 'PROCESSED'
ORDER BY STATUS ASC
```

---

#### SELECT #394 - Line 141

**File**: `BCM.I.VALID.TDC.b`

**Routine**: `BCM.I.VALID.TDC` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE EB.CARD.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE EB.CARD.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'EB.CARD.TYPE*%'
```

---

#### SELECT #395 - Line 121

**File**: `BCM.POST.MV.UP.PAY.b`

**Routine**: `BCM.POST.MV.UP.PAY` (Unknown)

**Variable**: `SELECT.S`

**AS PER CODE**:
```
SELECT F.BCM.RH.PAYROLL BY CREDIT.ACCOUNT BY AMOUNT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.RH.PAYROLL BY CREDIT.ACCOUNT BY AMOUNT
```

**Table**: `BCM.RH.PAYROLL`

**Fields** (2):
-  `AMOUNT`  Type: D
-  `CREDIT.ACCOUNT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_RH_PAYROLL
ORDER BY CREDIT_ACCOUNT ASC, AMOUNT ASC
```

---

#### SELECT #396 - Line 43

**File**: `BPA.B.ACH.FILE.REMOVE.HEADER.b`

**Routine**: `BPA.B.ACH.FILE.REMOVE.HEADER` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #397 - Line 40

**File**: `BPA.B.ADQU.CHARGE.PRE.b`

**Routine**: `BPA.B.ADQU.CHARGE.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.IN.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.IN.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #398 - Line 65

**File**: `BPA.B.ADQU.CONCAT.FILE.b`

**Routine**: `BPA.B.ADQU.CONCAT.FILE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED AND HEADER.FILE.NAME EQ {Y.FILE.PROCESSED}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.PROCESSED

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'FAILED' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #399 - Line 73

**File**: `BPA.B.ADQU.CONCAT.FILE.b`

**Routine**: `BPA.B.ADQU.CONCAT.FILE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ SUCCESS AND HEADER.FILE.NAME EQ {Y.FILE.PROCESSED}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ SUCCESS AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.PROCESSED

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'SUCCESS' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #400 - Line 289

**File**: `BPA.B.ADQU.FAILED.REP.b`

**Routine**: `BPA.B.ADQU.FAILED.REP` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.TRAIL WITH REMISION.AFIL.ID EQ {BPA.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.TRAIL WITH REMISION.AFIL.ID EQ SAMPLE_VALUE
```

**Table**: `BPA.ADQU.POS.TXN.TRAIL`

**Fields** (1):
-  `REMISION.AFIL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: BPA.ID

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_TRAIL
WHERE REMISION_AFIL_ID = 'SAMPLE_VALUE'
```

---

#### SELECT #401 - Line 53

**File**: `BPA.B.ADQU.FAILED.REP.SELECT.b`

**Routine**: `BPA.B.ADQU.FAILED.REP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED AND HEADER.FILE.NAME EQ {Y.FILE.PROCESSED}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.PROCESSED

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'FAILED' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #402 - Line 19

**File**: `BPA.B.ADQU.PRE.ACCOUNT.SELECT.b`

**Routine**: `BPA.B.ADQU.PRE.ACCOUNT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CONCAT.ADQU
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CONCAT.ADQU
```

**Table**: `BAN.CONCAT.ADQU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAN.CONCAT.ADQU' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.CONCAT.ADQU

**Translated SQL**:
```sql
SELECT *
FROM BAN_CONCAT_ADQU
```

---

#### SELECT #403 - Line 57

**File**: `BPA.B.ADQU.PRE.PROCESS.b`

**Routine**: `BPA.B.ADQU.PRE.PROCESS` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ PENDING AND HEADER.FILE.NAME EQ {Y.FILE}AND AFILIADO.SUC EQ {AFI.SUC.REC}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ PENDING AND HEADER.FILE.NAME EQ VALUE123AND AFILIADO.SUC EQ SAMPLE_VALUE
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (3):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D
-  `AFILIADO.SUC`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE, AFI.SUC.REC

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'PENDING' AND HEADER_FILE_NAME = 'VALUE123AND'
```

---

#### SELECT #404 - Line 46

**File**: `BPA.B.ADQU.PRE.PROCESS.SELECT.b`

**Routine**: `BPA.B.ADQU.PRE.PROCESS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ PENDING AND HEADER.FILE.NAME EQ {Y.FILE}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ PENDING AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'PENDING' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #405 - Line 45

**File**: `BPA.B.ADQU.PROCESS.ERR.TXN.SELECT.b`

**Routine**: `BPA.B.ADQU.PROCESS.ERR.TXN.SELECT` (BATCH (inferred))

**Variable**: `BPA.B.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED AND HEADER.FILE.NAME EQ {Y.FILE}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'FAILED' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #406 - Line 54

**File**: `BPA.B.ADQU.PROCESS.TXN.b`

**Routine**: `BPA.B.ADQU.PROCESS.TXN` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH AFILIADO.SUC EQ {Y.AC.ID} AND HEADER.FILE.NAME EQ {Y.FILE}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH AFILIADO.SUC EQ VALUE123 AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `HEADER.FILE.NAME`  Type: D
-  `AFILIADO.SUC`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AC.ID, Y.FILE

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE AFILIADO_SUC = 'VALUE123' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #407 - Line 143

**File**: `BPA.B.ADQU.PROCESS.TXN.b`

**Routine**: `BPA.B.ADQU.PROCESS.TXN` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.TRAIL WITH REMISION.AFIL.ID EQ {Y.HEAD.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.TRAIL WITH REMISION.AFIL.ID EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.TRAIL`

**Fields** (1):
-  `REMISION.AFIL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_TRAIL
WHERE REMISION_AFIL_ID = 'VALUE123'
```

---

#### SELECT #408 - Line 54

**File**: `BPA.B.ADQU.PROCESS.TXN.SELECT.b`

**Routine**: `BPA.B.ADQU.PROCESS.TXN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CONCAT.ADQU.AC
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CONCAT.ADQU.AC
```

**Table**: `BAN.CONCAT.ADQU.AC`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAN.CONCAT.ADQU.AC' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.CONCAT.ADQU.AC

**Translated SQL**:
```sql
SELECT *
FROM BAN_CONCAT_ADQU_AC
```

---

#### SELECT #409 - Line 62

**File**: `BPA.B.ADQU.SUCESS.REP.SELECT.b`

**Routine**: `BPA.B.ADQU.SUCESS.REP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ SUCCESS AND HEADER.FILE.NAME EQ {Y.FILE.PROCESSED}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ SUCCESS AND HEADER.FILE.NAME EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (2):
-  `OVERALL.STATUS`  Type: D
-  `HEADER.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FILE.PROCESSED

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'SUCCESS' AND HEADER_FILE_NAME = 'VALUE123'
```

---

#### SELECT #410 - Line 87

**File**: `BPA.B.BUILD.DATA.CHQ.OUTCLG.b`

**Routine**: `BPA.B.BUILD.DATA.CHQ.OUTCLG` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_87`

**AS PER CODE**:
```
SELECT F.IN.FILE.DIR
```

**SIMULATED AT RUNTIME**:
```
SELECT F.IN.FILE.DIR
```

**Table**: `IN.FILE.DIR`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'IN.FILE.DIR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/IN.FILE.DIR

**Translated SQL**:
```sql
SELECT *
FROM IN_FILE_DIR
```

---

#### SELECT #411 - Line 226

**File**: `BPA.B.BUILD.DATA.CHQ.OUTCLG.b`

**Routine**: `BPA.B.BUILD.DATA.CHQ.OUTCLG` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.HEAD WITH FILE.DATE EQ TODAY
```

**Table**: `BAN.OUT.CLEARING.CHQRET.HEAD`

**Fields** (1):
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_HEAD
WHERE FILE_DATE = 'TODAY'
```

---

#### SELECT #412 - Line 138

**File**: `BPA.B.FT.BULK.MULTIFILE.b`

**Routine**: `BPA.B.FT.BULK.MULTIFILE` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT EB.FILE.UPLOAD WITH SYSTEM.FILE.NAME EQ {Y.NEW.FN}
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.FILE.UPLOAD WITH SYSTEM.FILE.NAME EQ VALUE123
```

**Table**: `EB.FILE.UPLOAD`

**Fields** (1):
-  `SYSTEM.FILE.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.NEW.FN

**Translated SQL**:
```sql
SELECT *
FROM EB_FILE_UPLOAD
WHERE SYSTEM_FILE_NAME = 'VALUE123'
```

---

#### SELECT #413 - Line 43

**File**: `BPA.B.FT.BULK.MULTIFILE.SELECT.b`

**Routine**: `BPA.B.FT.BULK.MULTIFILE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.FN.PLANILLA.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.FN.PLANILLA.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #414 - Line 97

**File**: `BPA.B.INCLG.CHQ.DEV.b`

**Routine**: `BPA.B.INCLG.CHQ.DEV` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH FILE.DATE EQ {EB.SystemTables.getToday()} AND CHQ.STATUS EQ DEVUELTO AND FILE.RETURN EQ ""
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH FILE.DATE EQ TODAY AND CHQ.STATUS EQ DEVUELTO AND FILE.RETURN EQ ""
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (3):
-  `CHQ.STATUS`  Type: D
-  `FILE.RETURN`  Type: D
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE FILE_DATE = 'TODAY' AND CHQ_STATUS = 'DEVUELTO'
```

---

#### SELECT #415 - Line 110

**File**: `BPA.B.OUTCLG.CHQ.TXN.b`

**Routine**: `BPA.B.OUTCLG.CHQ.TXN` (BATCH (inferred))

**Variable**: `SEL.CMD.FT`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER WITH DEBIT.VALUE.DATE EQ {EB.SystemTables.getToday()} AND TRANSACTION.TYPE EQ {Y.FT.TXN} BY CO.CODE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER WITH DEBIT.VALUE.DATE EQ TODAY AND TRANSACTION.TYPE EQ VALUE123 BY CO.CODE
```

**Table**: `FUNDS.TRANSFER`

**Fields** (3):
-  `CO.CODE`  Type: D
-  `TRANSACTION.TYPE`  Type: D
-  `DEBIT.VALUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FT.TXN

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER
WHERE DEBIT_VALUE_DATE = 'TODAY' AND TRANSACTION_TYPE = 'VALUE123'
ORDER BY CO_CODE ASC
```

---

#### SELECT #416 - Line 134

**File**: `BPA.B.OUTCLG.CHQ.TXN.b`

**Routine**: `BPA.B.OUTCLG.CHQ.TXN` (BATCH (inferred))

**Variable**: `SEL.CMD.TT`

**AS PER CODE**:
```
SELECT F.TELLER WITH VALUE.DATE.1 EQ {EB.SystemTables.getToday()} AND TRANSACTION.CODE EQ {Y.TELLER.TXN} {Y.COUNT.INTER.AS} BY CO.CODE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER WITH VALUE.DATE.1 EQ TODAY AND TRANSACTION.CODE EQ VALUE123 VALUE123 BY CO.CODE
```

**Table**: `TELLER`

**Fields** (3):
-  `CO.CODE`  Type: D
-  `TRANSACTION.CODE`  Type: D
-  `VALUE.DATE.1`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TELLER.TXN, Y.COUNT.INTER.AS

**Translated SQL**:
```sql
SELECT *
FROM TELLER
WHERE VALUE_DATE_1 = 'TODAY' AND TRANSACTION_CODE = 'VALUE123'
ORDER BY CO_CODE ASC
```

---

#### SELECT #417 - Line 162

**File**: `BPA.B.OUTCLG.CHQ.TXN.b`

**Routine**: `BPA.B.OUTCLG.CHQ.TXN` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT.CH`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH ORIG.VALUE.DATE EQ {EB.SystemTables.getToday()} AND CHQ.STATUS EQ DEPOSITED BY CO.CODE BY BANK.SORT.CODE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH ORIG.VALUE.DATE EQ TODAY AND CHQ.STATUS EQ DEPOSITED BY CO.CODE BY BANK.SORT.CODE
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (4):
-  `ORIG.VALUE.DATE`  Type: D
-  `CHQ.STATUS`  Type: D
-  `BANK.SORT.CODE`  Type: D
-  `CO.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE ORIG_VALUE_DATE = 'TODAY' AND CHQ_STATUS = 'DEPOSITED'
ORDER BY CO_CODE ASC, BANK_SORT_CODE ASC
```

---

#### SELECT #418 - Line 67

**File**: `BPA.B.OUTCLG.DATAMAE.POST.b`

**Routine**: `BPA.B.OUTCLG.DATAMAE.POST` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_67`

**AS PER CODE**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**SIMULATED AT RUNTIME**:
```
SELECT Y.TEMP.FILE.POINTER.AUX
```

**Table**: `Y.TEMP.FILE.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'Y.TEMP.FILE.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/Y.TEMP.FILE.POINTER

**Translated SQL**:
```sql
SELECT *
FROM Y_TEMP_FILE_POINTER
```

---

#### SELECT #419 - Line 48

**File**: `BPA.B.OUTCLG.DATAMAE.SELECT.b`

**Routine**: `BPA.B.OUTCLG.DATAMAE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS BY LINKED.APPL.ID
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS BY LINKED.APPL.ID
```

**Table**: `AA.ARRANGEMENT`

**Fields** (2):
-  `LINKED.APPL.ID`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS'
ORDER BY LINKED_APPL_ID ASC
```

---

#### SELECT #420 - Line 171

**File**: `BPA.B.OUTCLG.DATATRN.b`

**Routine**: `BPA.B.OUTCLG.DATATRN` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BPA.CONCAT.TXN BY CO.CODE.TXN BY CHQ.BANK
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.CONCAT.TXN BY CO.CODE.TXN BY CHQ.BANK
```

**Table**: `BPA.CONCAT.TXN`

**Fields** (2):
-  `CO.CODE.TXN`  Type: D
-  `CHQ.BANK`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_CONCAT_TXN
ORDER BY CO_CODE_TXN ASC, CHQ_BANK ASC
```

---

#### SELECT #421 - Line 58

**File**: `BPA.B.PURGE.TOT.DATATXN.b`

**Routine**: `BPA.B.PURGE.TOT.DATATXN` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.TOT.DATATRN
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TOT.DATATRN
```

**Table**: `BPA.TOT.DATATRN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_TOT_DATATRN
```

---

#### SELECT #422 - Line 16

**File**: `BPA.B.REJ.PAY.ACCT.SELECT.b`

**Routine**: `BPA.B.REJ.PAY.ACCT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LATAM.ACH.EXCEPTION WITH @ID LIKE ...{Y.SEARCH.EXCEP}...
```

**SIMULATED AT RUNTIME**:
```
SELECT LATAM.ACH.EXCEPTION WITH @ID LIKE ...VALUE123...
```

**Table**: `LATAM.ACH.EXCEPTION`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.SEARCH.EXCEP

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_EXCEPTION
WHERE ID LIKE '%VALUE123%'
```

---

#### SELECT #423 - Line 72

**File**: `BPA.B.TOT.DATATRN.b`

**Routine**: `BPA.B.TOT.DATATRN` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.CONCAT.TXN  WITH CHQ.BANK EQ 1033
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.CONCAT.TXN  WITH CHQ.BANK EQ 1033
```

**Table**: `BPA.CONCAT.TXN`

**Fields** (1):
-  `CHQ.BANK`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_CONCAT_TXN
WHERE CHQ_BANK = '1033'
```

---

#### SELECT #424 - Line 84

**File**: `BPA.B.TOT.DATATRN.b`

**Routine**: `BPA.B.TOT.DATATRN` (BATCH (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.BPA.TOT.DATATRN
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.TOT.DATATRN
```

**Table**: `BPA.TOT.DATATRN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_TOT_DATATRN
```

---

#### SELECT #425 - Line 247

**File**: `BPA.B.UPLOAD.PLANILLA.b`

**Routine**: `BPA.B.UPLOAD.PLANILLA` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BENEF.PROD.TYPE*... AND OTHER.INFO EQ {Y.ACCT.TYPE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BENEF.PROD.TYPE*... AND OTHER.INFO EQ VALUE123
```

**Table**: `EB.LOOKUP`

**Fields** (2):
-  `OTHER.INFO`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCT.TYPE

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BENEF.PROD.TYPE*%' AND OTHER_INFO = 'VALUE123'
```

---

#### SELECT #426 - Line 84

**File**: `BPA.B.UPLOAD.PLANILLA.POST.b`

**Routine**: `BPA.B.UPLOAD.PLANILLA.POST` (BATCH (inferred))

**Variable**: `SEL.COMMAND`

**AS PER CODE**:
```
SELECT F.BAN.FT.BULK.MULTIFILE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.FT.BULK.MULTIFILE
```

**Table**: `BAN.FT.BULK.MULTIFILE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_FT_BULK_MULTIFILE
```

---

#### SELECT #427 - Line 41

**File**: `BPA.B.UPLOAD.PLANILLA.SELECT.b`

**Routine**: `BPA.B.UPLOAD.PLANILLA.SELECT` (BATCH (inferred))

**Variable**: `SEL.COMMAND`

**AS PER CODE**:
```
SELECT BAN.FT.BULK.MULTIFILE
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.FT.BULK.MULTIFILE
```

**Table**: `BAN.FT.BULK.MULTIFILE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_FT_BULK_MULTIFILE
```

---

#### SELECT #428 - Line 61

**File**: `BPA.DOMTDC.PAY.POST.b`

**Routine**: `BPA.DOMTDC.PAY.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.FILE.POINTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT FILE.POINTER
```

**Table**: `FILE.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'FILE.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FILE.POINTER
-   Unresolved variables: F.FILE.POINTER

**Translated SQL**:
```sql
SELECT *
FROM FILE_POINTER
```

---

#### SELECT #429 - Line 50

**File**: `BPA.E.CNV.ACH.BANK.b`

**Routine**: `BPA.E.CNV.ACH.BANK` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.BANK WITH @ID LIKE {Y.LATAM.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.BANK WITH @ID LIKE VALUE123...
```

**Table**: `LATAM.ACH.BANK`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LATAM.ID

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_BANK
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #430 - Line 91

**File**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Routine**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.OTHER.OFFICER WITH ID.USER EQ {EB.SystemTables.getOperator()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OTHER.OFFICER WITH ID.USER EQ OPERATOR
```

**Table**: `BAN.OTHER.OFFICER`

**Fields** (1):
-  `ID.USER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OTHER_OFFICER
WHERE ID_USER = 'OPERATOR'
```

---

#### SELECT #431 - Line 103

**File**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Routine**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET` (NOFILE (inferred))

**Variable**: `SEL.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED AND LT.RET.COD.CC NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED AND LT.RET.COD.CC NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

**Table**: `CHEQUE.COLLECTION$NAU`

**Fields** (3):
-  `CHQ.STATUS`  Type: D
-  `RECORD.STATUS`  Type: D
-  `LT.RET.COD.CC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CHEQUE.COLLECTION'
-   INFO: LOCAL.REF fields found: LT.RET.COD.CC - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
WHERE CHQ_STATUS = 'RETURNED'
```

---

#### SELECT #432 - Line 106

**File**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET.b`

**Routine**: `BPA.E.NOF.CHQ.OUTCLG.AUT.RET` (NOFILE (inferred))

**Variable**: `SEL.FT`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.RET.COD.CC NE "" AND LT.CC.ID NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH LT.RET.COD.CC NE "" AND LT.CC.ID NE "" AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO)
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (3):
-  `LT.RET.COD.CC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,25>`)
-  `LT.CC.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,31>`)
-  `RECORD.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   INFO: LOCAL.REF fields found: LT.RET.COD.CC, LT.CC.ID - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
```

---

#### SELECT #433 - Line 92

**File**: `BPA.E.NOF.CHQ.OUTCLG.NO.RET.b`

**Routine**: `BPA.E.NOF.CHQ.OUTCLG.NO.RET` (NOFILE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH LOAD.STATUS EQ RECHAZADO OR CHQ.STATUS EQ ERROR AND FILE.DATE EQ {FILE.DATE.VAL} AND FILE.DATE NE {FILE.DATE.VAL} AND FILE.DATE LK ...{FILE.DATE.VAL}... AND CHQ.BANK EQ {CHQ.BANK.VAL} AND CHQ.BANK NE {CHQ.BANK.VAL} AND CHQ.BANK LK ...{CHQ.BANK.VAL}... AND BE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OUT.CLEARING.CHQRET.DET WITH LOAD.STATUS EQ RECHAZADO OR CHQ.STATUS EQ ERROR AND FILE.DATE EQ SAMPLE_VALUE AND FILE.DATE NE SAMPLE_VALUE AND FILE.DATE LK ...SAMPLE_VALUE... AND CHQ.BANK EQ SAMPLE_VALUE AND CHQ.BANK NE SAMPLE_VALUE AND CHQ.BANK LK ...SAMPLE_VALUE... AND BEN.BRANCH EQ SAM
```

**Table**: `BAN.OUT.CLEARING.CHQRET.DET`

**Fields** (7):
-  `CHQ.STATUS`  Type: D
-  `BEN.BRANCH`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `CHQ.RET.COD.CC`  Type: D
-  `CHQ.BANK`  Type: D
-  `LOAD.STATUS`  Type: D
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FILE.DATE.VAL, CHQ.BANK.VAL, BEN.BRANCH.VAL, CHQ.ACCOUNT.VAL, CHQ.RET.COD.CC.VAL

**Translated SQL**:
```sql
SELECT *
FROM BAN_OUT_CLEARING_CHQRET_DET
WHERE LOAD_STATUS = 'RECHAZADO' AND FILE_DATE = 'SAMPLE_VALUE' AND FILE_DATE != 'SAMPLE_VALUE' AND CHQ_BANK = 'SAMPLE_VALUE' AND CHQ_BANK != 'SAMPLE_VALUE' AND BEN_BRANCH = 'SAMPLE_VALUE' AND BEN_BRANCH != 'SAMPLE_VALUE' AND CHQ_ACCOUNT = 'SAMPLE_VALUE' AND CHQ_ACCOUNT != 'SAMPLE_VALUE' AND CHQ_RET_COD_CC = 'SAMPLE_VALUE' AND CHQ_RET_COD_CC != 'SAMPLE_VALUE'
```

---

#### SELECT #434 - Line 93

**File**: `BPA.E.NOF.CHQ.OUTCLG.NO.RET.b`

**Routine**: `BPA.E.NOF.CHQ.OUTCLG.NO.RET` (NOFILE (inferred))

**Variable**: `SEL.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO) AND BANK.SORT.CODE NE {BC.CODE} AND STATUS.DATE EQ {FILE.DATE.VAL} AND STATUS.DATE NE {FILE.DATE.VAL} AND STATUS.DATE LK ...{FILE.DATE.VAL}... AND BANK.SORT.CODE EQ {CHQ.BANK.VAL} AND BANK
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION$NAU WITH CHQ.STATUS EQ RETURNED AND (RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO) AND BANK.SORT.CODE NE SAMPLE_VALUE AND STATUS.DATE EQ SAMPLE_VALUE AND STATUS.DATE NE SAMPLE_VALUE AND STATUS.DATE LK ...SAMPLE_VALUE... AND BANK.SORT.CODE EQ SAMPLE_VALUE AND BANK.SORT.CO
```

**Table**: `CHEQUE.COLLECTION$NAU`

**Fields** (7):
-  `CHQ.STATUS`  Type: D
-  `STATUS.DATE`  Type: D
-  `LT.CHEQUE.ACC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,3>`)
-  `LT.RET.COD.CC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)
-  `RECORD.STATUS`  Type: D
-  `CO.CODE`  Type: D
-  `BANK.SORT.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'CHEQUE.COLLECTION'
-   INFO: LOCAL.REF fields found: LT.CHEQUE.ACC, LT.RET.COD.CC - Physical fields in database (TAFJ compatible)
-   Unresolved variables: BC.CODE, FILE.DATE.VAL, CHQ.BANK.VAL, BEN.BRANCH.VAL, CHQ.ACCOUNT.VAL

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION$NAU
WHERE CHQ_STATUS = 'RETURNED' AND BANK_SORT_CODE != 'SAMPLE_VALUE' AND STATUS_DATE = 'SAMPLE_VALUE' AND STATUS_DATE != 'SAMPLE_VALUE' AND BANK_SORT_CODE = 'SAMPLE_VALUE' AND BANK_SORT_CODE != 'SAMPLE_VALUE' AND CO_CODE = 'SAMPLE_VALUE' AND CO_CODE != 'SAMPLE_VALUE' AND LT_CHEQUE_ACC = 'SAMPLE_VALUE' AND LT_CHEQUE_ACC != 'SAMPLE_VALUE' AND LT_RET_COD_CC = 'SAMPLE_VALUE' AND LT_RET_COD_CC != 'SAMPLE_VALUE'
```

---

#### SELECT #435 - Line 86

**File**: `BPA.E.NOF.FT.MAIN.OFF.b`

**Routine**: `BPA.E.NOF.FT.MAIN.OFF` (NOFILE (inferred))

**Variable**: `SEL.BAN`

**AS PER CODE**:
```
SELECT F.BAN.OTHER.OFFICER WITH ID.USER EQ {EB.SystemTables.getOperator()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.OTHER.OFFICER WITH ID.USER EQ OPERATOR
```

**Table**: `BAN.OTHER.OFFICER`

**Fields** (1):
-  `ID.USER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_OTHER_OFFICER
WHERE ID_USER = 'OPERATOR'
```

---

#### SELECT #436 - Line 110

**File**: `BPA.E.NOF.FT.MAIN.OFF.b`

**Routine**: `BPA.E.NOF.FT.MAIN.OFF` (NOFILE (inferred))

**Variable**: `SEL.FT`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH RECORD.STATUS EQ INAU OR RECORD.STATUS EQ INAO
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (1):
-  `RECORD.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE RECORD_STATUS = 'INAU'
```

---

#### SELECT #437 - Line 212

**File**: `BPA.E.NOF.OUTCLG.RET.TOT.b`

**Routine**: `BPA.E.NOF.OUTCLG.RET.TOT` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION.HIST WITH CHQ.STATUS EQ RETURNED
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION.HIST WITH CHQ.STATUS EQ RETURNED
```

**Table**: `CHEQUE.COLLECTION.HIST`

**Fields** (1):
-  `CHQ.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION_HIST
WHERE CHQ_STATUS = 'RETURNED'
```

---

#### SELECT #438 - Line 70

**File**: `BPA.E.NOF.RH.PAYROLL.b`

**Routine**: `BPA.E.NOF.RH.PAYROLL` (NOFILE (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ ERROR ERROR.PROCESS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ ERROR ERROR.PROCESS
```

**Table**: `BCM.RH.PAYROLL`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BCM_RH_PAYROLL
WHERE STATUS = 'ERROR'
```

---

#### SELECT #439 - Line 74

**File**: `BPA.E.NOF.RH.PAYROLL.b`

**Routine**: `BPA.E.NOF.RH.PAYROLL` (NOFILE (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.BCM.RH.PAYROLL$NAU
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.RH.PAYROLL$NAU
```

**Table**: `BCM.RH.PAYROLL$NAU`

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'BCM.RH.PAYROLL'
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_RH_PAYROLL$NAU
```

---

#### SELECT #440 - Line 80

**File**: `BPA.E.NOF.RH.PAYROLL.b`

**Routine**: `BPA.E.NOF.RH.PAYROLL` (NOFILE (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ UPLOAD
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ UPLOAD
```

**Table**: `BCM.RH.PAYROLL`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BCM_RH_PAYROLL
WHERE STATUS = 'UPLOAD'
```

---

#### SELECT #441 - Line 189

**File**: `BPA.I.VAL.PLANILLA.b`

**Routine**: `BPA.I.VAL.PLANILLA` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.EXTERNAL.USER WITH CUSTOMER EQ {Y.MASTER.CUST} AND CHANNEL.PERMISSION EQ {Y.MASTER.CUST}-MASTER
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.EXTERNAL.USER WITH CUSTOMER EQ VALUE123 AND CHANNEL.PERMISSION EQ VALUE123-MASTER
```

**Table**: `EB.EXTERNAL.USER`

**Fields** (2):
-  `CUSTOMER`  Type: D
-  `CHANNEL.PERMISSION`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CHANNEL.PERMISSION' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.MASTER.CUST

**Translated SQL**:
```sql
SELECT *
FROM EB_EXTERNAL_USER
WHERE CUSTOMER = 'VALUE123' AND CHANNEL_PERMISSION = 'VALUE123-MASTER'
```

---

#### SELECT #442 - Line 164

**File**: `BPA.I.VAL.PLANILLA.ITEM.b`

**Routine**: `BPA.I.VAL.PLANILLA.ITEM` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE EB.CARD.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE EB.CARD.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'EB.CARD.TYPE*%'
```

---

#### SELECT #443 - Line 229

**File**: `BPA.INWARD.PRE.PROCESS.b`

**Routine**: `BPA.INWARD.PRE.PROCESS` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.IN.FILE.DIR}
```

**SIMULATED AT RUNTIME**:
```
SELECT IN.FILE.DIR
```

**Table**: `IN.FILE.DIR`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'IN.FILE.DIR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/IN.FILE.DIR
-   Unresolved variables: F.IN.FILE.DIR

**Translated SQL**:
```sql
SELECT *
FROM IN_FILE_DIR
```

---

#### SELECT #444 - Line 272

**File**: `BPA.INWARD.PRE.PROCESS.b`

**Routine**: `BPA.INWARD.PRE.PROCESS` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.IN.FILE.DIR}
```

**SIMULATED AT RUNTIME**:
```
SELECT IN.FILE.DIR
```

**Table**: `IN.FILE.DIR`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'IN.FILE.DIR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/IN.FILE.DIR
-   Unresolved variables: F.IN.FILE.DIR

**Translated SQL**:
```sql
SELECT *
FROM IN_FILE_DIR
```

---

#### SELECT #445 - Line 75

**File**: `BPA.NOFILE.ADQU.RETURN.REP.b`

**Routine**: `BPA.NOFILE.ADQU.RETURN.REP` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.ADQU.POS.TXN.HEAD WITH OVERALL.STATUS EQ FAILED
```

**Table**: `BPA.ADQU.POS.TXN.HEAD`

**Fields** (1):
-  `OVERALL.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_HEAD
WHERE OVERALL_STATUS = 'FAILED'
```

---

#### SELECT #446 - Line 113

**File**: `BPA.NOFILE.ADQU.RETURN.REP.b`

**Routine**: `BPA.NOFILE.ADQU.RETURN.REP` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.ADQU.POS.TXN.TRAIL WITH REMISION.AFIL.ID EQ {Y.HEAD.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.ADQU.POS.TXN.TRAIL WITH REMISION.AFIL.ID EQ VALUE123
```

**Table**: `BPA.ADQU.POS.TXN.TRAIL`

**Fields** (1):
-  `REMISION.AFIL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_ADQU_POS_TXN_TRAIL
WHERE REMISION_AFIL_ID = 'VALUE123'
```

---

#### SELECT #447 - Line 60

**File**: `BRD.E.NOF.RH.PAYROLL.b`

**Routine**: `BRD.E.NOF.RH.PAYROLL` (NOFILE (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ UPLOAD
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.RH.PAYROLL WITH STATUS EQ UPLOAD
```

**Table**: `BCM.RH.PAYROLL`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BCM_RH_PAYROLL
WHERE STATUS = 'UPLOAD'
```

---

#### SELECT #448 - Line 107

**File**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET.b`

**Routine**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET` (SUBROUTINE (inferred))

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND CREDIT.ACC.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdBenAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.B
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND CREDIT.ACC.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdBenAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.B
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (3):
-  `CHEQUE.NO`  Type: D
-  `AMOUNT`  Type: D
-  `CREDIT.ACC.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'AMOUNT' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHEQUE_NO = '{R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>}' AND CREDIT_ACC_NO = '{R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdBenAccount>}' AND AMOUNT = '{R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAmount>}'
```

---

#### SELECT #449 - Line 119

**File**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET.b`

**Routine**: `BRD.S.CHQ.OUTCLG.FILE.VAL.RET` (SUBROUTINE (inferred))

**Variable**: `NEW.SEL.STMT`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND LT.CHEQUE.ACC EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.B
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHEQUE.NO EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>} AND LT.CHEQUE.ACC EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAccount>} AND AMOUNT EQ {R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.B
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (3):
-  `CHEQUE.NO`  Type: D
-  `AMOUNT`  Type: D
-  `LT.CHEQUE.ACC`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,3>`)

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'AMOUNT' used in condition (cannot create index on M fields)
-   INFO: LOCAL.REF fields found: LT.CHEQUE.ACC - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHEQUE_NO = '{R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqNumber>}' AND LT_CHEQUE_ACC = '{R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAccount>}' AND AMOUNT = '{R.CHQRET<BAPALOCALTABLE.MigTablas3.BanOutClearingChqretDet.BanOccdChqAmount>}'
```

---

#### SELECT #450 - Line 145

**File**: `E.BAN.AC.CASH.GROUPS.b`

**Routine**: `E.BAN.AC.CASH.GROUPS` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.SHARED.ACCOUNT WITH MAIN.ACCT EQ {Y.ACCOUNT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.SHARED.ACCOUNT WITH MAIN.ACCT EQ VALUE123
```

**Table**: `AC.SHARED.ACCOUNT`

**Fields** (1):
-  `MAIN.ACCT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_SHARED_ACCOUNT
WHERE MAIN_ACCT = 'VALUE123'
```

---

#### SELECT #451 - Line 169

**File**: `E.BAN.AC.CASH.GROUPS.b`

**Routine**: `E.BAN.AC.CASH.GROUPS` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.SHARED.ACCOUNT WITH CP.ID NE ""
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.SHARED.ACCOUNT WITH CP.ID NE ""
```

**Table**: `AC.SHARED.ACCOUNT`

**Fields** (1):
-  `CP.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CP.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AC_SHARED_ACCOUNT
```

---

#### SELECT #452 - Line 210

**File**: `E.BAN.AC.CASH.GROUPS.b`

**Routine**: `E.BAN.AC.CASH.GROUPS` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CASH.POOL WITH LAST.MAINT.DATE EQ {R.AC.ACCOUNT.SWEEP.HIST<ST.Sweeping.AcAccountSweepHist.AcSwHistSweepDate,POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CASH.POOL WITH LAST.MAINT.DATE EQ {R.AC.ACCOUNT.SWEEP.HIST<ST.Sweeping.AcAccountSweepHist.AcSwHistSweepDate,POS>}
```

**Table**: `AC.CASH.POOL`

**Fields** (1):
-  `LAST.MAINT.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_CASH_POOL
WHERE LAST_MAINT_DATE = '{R.AC.ACCOUNT.SWEEP.HIST<ST.Sweeping.AcAccountSweepHist.AcSwHistSweepDate,POS>}'
```

---

#### SELECT #453 - Line 222

**File**: `E.BAN.AC.CASH.GROUPS.b`

**Routine**: `E.BAN.AC.CASH.GROUPS` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CASH.POOL WITH SWEEP.CANCEL.DATE EQ {EB.Reports.getDRangeAndValue()<ENDDATE.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CASH.POOL WITH SWEEP.CANCEL.DATE EQ {EB.Reports.getDRangeAndValue()<ENDDATE.POS>}
```

**Table**: `AC.CASH.POOL`

**Fields** (1):
-  `SWEEP.CANCEL.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_CASH_POOL
WHERE SWEEP_CANCEL_DATE = '{EB.Reports.getDRangeAndValue()<ENDDATE.POS>}'
```

---

#### SELECT #454 - Line 24

**File**: `BAN.PAYROLL.AUTH.FT.SELECT.b`

**Routine**: `BAN.PAYROLL.AUTH.FT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAFT.Framework.getFnFundsTransferNau(1)} WITH TRANSACTION.TYPE EQ ACNO AND RECORD.STATUS EQ INAU
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER$NAU WITH TRANSACTION.TYPE EQ ACNO AND RECORD.STATUS EQ INAU
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (2):
-  `RECORD.STATUS`  Type: D
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE TRANSACTION_TYPE = 'ACNO' AND RECORD_STATUS = 'INAU'
```

---

#### SELECT #455 - Line 27

**File**: `BAPA.A.LEGITIMACION.COFRE.SELECT.b`

**Routine**: `BAPA.A.LEGITIMACION.COFRE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FUNDS.TRANSFER$NAU WITH INPUTTER LIKE ...{Y.PAL.FT}...
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER$NAU WITH INPUTTER LIKE ...BAPA.FT.COFRE...
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (1):
-  `INPUTTER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'INPUTTER' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE INPUTTER LIKE '%BAPA.FT.COFRE%'
```

---

#### SELECT #456 - Line 55

**File**: `BAPA.B.DEVO.FT.b`

**Routine**: `BAPA.B.DEVO.FT` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_55`

**AS PER CODE**:
```
SELECT FILE.PATH.1
```

**SIMULATED AT RUNTIME**:
```
SELECT FILE.PATH.1
```

**Table**: `FILE.PATH.1`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'FILE.PATH.1' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FILE.PATH.1

**Translated SQL**:
```sql
SELECT *
FROM FILE_PATH_1
```

---

#### SELECT #457 - Line 119

**File**: `BAPA.NOF.ENQ.FT.OT03.b`

**Routine**: `BAPA.NOF.ENQ.FT.OT03` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH DEBIT.ACCT.NO EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND TRANSACTION.TYPE EQ OT03 AND PROCESSING.DATE GE {EB.Reports.getDRangeAndValue()<Y.POS>} AND PROCESSING.DATE LE {EB.Reports.getDRangeAndValue()<Y.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$NAU WITH DEBIT.ACCT.NO EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND TRANSACTION.TYPE EQ OT03 AND PROCESSING.DATE GE {EB.Reports.getDRangeAndValue()<Y.POS>} AND PROCESSING.DATE LE {EB.Reports.getDRangeAndValue()<Y.POS>}
```

**Table**: `FUNDS.TRANSFER$NAU`

**Fields** (3):
-  `DEBIT.ACCT.NO`  Type: D
-  `PROCESSING.DATE`  Type: D
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$NAU
WHERE DEBIT_ACCT_NO = '{EB.Reports.getDRangeAndValue()<Y.POS>}' AND TRANSACTION_TYPE = 'OT03' AND PROCESSING_DATE >= '{EB.Reports.getDRangeAndValue()<Y.POS>}' AND PROCESSING_DATE <= '{EB.Reports.getDRangeAndValue()<Y.POS>}'
```

---

#### SELECT #458 - Line 129

**File**: `BAPA.NOF.ENQ.FT.OT03.b`

**Routine**: `BAPA.NOF.ENQ.FT.OT03` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH DEBIT.ACCT.NO EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND TRANSACTION.TYPE EQ OT03 AND PROCESSING.DATE GE {EB.Reports.getDRangeAndValue()<Y.POS>} AND PROCESSING.DATE LE {EB.Reports.getDRangeAndValue()<Y.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.FUNDS.TRANSFER$DEL WITH DEBIT.ACCT.NO EQ {EB.Reports.getDRangeAndValue()<Y.POS>} AND TRANSACTION.TYPE EQ OT03 AND PROCESSING.DATE GE {EB.Reports.getDRangeAndValue()<Y.POS>} AND PROCESSING.DATE LE {EB.Reports.getDRangeAndValue()<Y.POS>}
```

**Table**: `FUNDS.TRANSFER$DEL`

**Fields** (3):
-  `DEBIT.ACCT.NO`  Type: D
-  `PROCESSING.DATE`  Type: D
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$DEL' detected - Using dictionary from base table 'FUNDS.TRANSFER'

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$DEL
WHERE DEBIT_ACCT_NO = '{EB.Reports.getDRangeAndValue()<Y.POS>}' AND TRANSACTION_TYPE = 'OT03' AND PROCESSING_DATE >= '{EB.Reports.getDRangeAndValue()<Y.POS>}' AND PROCESSING_DATE <= '{EB.Reports.getDRangeAndValue()<Y.POS>}'
```

---

#### SELECT #459 - Line 66

**File**: `BAPA.M.WRITE.GRACE.DATE.b`

**Routine**: `BAPA.M.WRITE.GRACE.DATE` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE {Y.ARR}-MINBALFEE-... BY-DSND @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE VALUE123-MINBALFEE-... BY-DSND @ID
```

**Table**: `AA.ARR.CHARGE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ARR

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_CHARGE
WHERE ID LIKE 'VALUE123-MINBALFEE-%'
ORDER BY ID DESC
```

---

#### SELECT #460 - Line 28

**File**: `BAPA.B.DELETE.BENEFICIARY.SELECT.b`

**Routine**: `BAPA.B.DELETE.BENEFICIARY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT DE.BIC WITH NID.EXPIRY.DATE EQ {Y.NEXT.WORKING.DATE} OR NID.EXPIRY.DATE EQ {Y.TODAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT DE.BIC WITH NID.EXPIRY.DATE EQ VALUE123 OR NID.EXPIRY.DATE EQ VALUE123
```

**Table**: `DE.BIC`

**Fields** (1):
-  `NID.EXPIRY.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.NEXT.WORKING.DATE, Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM DE_BIC
WHERE NID_EXPIRY_DATE = 'VALUE123'
```

---

#### SELECT #461 - Line 49

**File**: `BAPA.B.DELETE.BENEFICIARY.SELECT.b`

**Routine**: `BAPA.B.DELETE.BENEFICIARY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BENEFICIARY WITH BIC EQ {Y.ID.BIC}
```

**SIMULATED AT RUNTIME**:
```
SELECT BENEFICIARY WITH BIC EQ VALUE123
```

**Table**: `BENEFICIARY`

**Fields** (1):
-  `BIC`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BENEFICIARY
WHERE BIC = 'VALUE123'
```

---

#### SELECT #462 - Line 48

**File**: `BAPA.S.DE.GET.CARD.TYPE.b`

**Routine**: `BAPA.S.DE.GET.CARD.TYPE` (SUBROUTINE (inferred))

**Variable**: `SelectStatement`

**AS PER CODE**:
```
SELECT {yFnCI} WITH @ID LIKE ...{yPanId}
```

**SIMULATED AT RUNTIME**:
```
SELECT CARD.ISSUE WITH @ID LIKE ...{yPanId}
```

**Table**: `CARD.ISSUE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CARD_ISSUE
WHERE ID LIKE '%{yPanId}'
```

---

#### SELECT #463 - Line 62

**File**: `BAN.B.ACC.WB.TDC.DUE.POST.b`

**Routine**: `BAN.B.ACC.WB.TDC.DUE.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.OUT.DIR}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.OUT.DIR

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #464 - Line 107

**File**: `BAN.B.ACC.WB.TDC.DUE.POST.b`

**Routine**: `BAN.B.ACC.WB.TDC.DUE.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.POINTER2}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.POINTER2

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #465 - Line 82

**File**: `BAN.B.ACCT.WB.TDC.DUE.b`

**Routine**: `BAN.B.ACCT.WB.TDC.DUE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.LOOKUP WITH @ID LIKE CUS.LEGAL.DOC.NAME*...
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.LOOKUP WITH @ID LIKE CUS.LEGAL.DOC.NAME*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'CUS.LEGAL.DOC.NAME*%'
```

---

#### SELECT #466 - Line 60

**File**: `BAN.B.ACCT.WB.TDC.DUE.SELECT.b`

**Routine**: `BAN.B.ACCT.WB.TDC.DUE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.IN.DIR}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.IN.DIR

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #467 - Line 47

**File**: `BAN.B.MOVCTA.LEGACYLIVE.SELECT.b`

**Routine**: `BAN.B.MOVCTA.LEGACYLIVE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.MOVCTA.LEGACYLIVE WITH ESTADO EQ NEW
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.MOVCTA.LEGACYLIVE WITH ESTADO EQ NEW
```

**Table**: `BAN.MOVCTA.LEGACYLIVE`

**Fields** (1):
-  `ESTADO`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_MOVCTA_LEGACYLIVE
WHERE ESTADO = 'NEW'
```

---

#### SELECT #468 - Line 72

**File**: `BAN.B.MOVCTA.MANTEARCHGEN.b`

**Routine**: `BAN.B.MOVCTA.MANTEARCHGEN` (BATCH (inferred))

**Variable**: `SEL`

**AS PER CODE**:
```
SELECT F.BAN.MOVCTA.LEGACYLIVE WITH (ESTADO EQ 'COMPLETADO') OR (ESTADO EQ 'ERROR') OR (ESTADO EQ 'CANCELADO')
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.MOVCTA.LEGACYLIVE WITH (ESTADO EQ 'COMPLETADO') OR (ESTADO EQ 'ERROR') OR (ESTADO EQ 'CANCELADO')
```

**Table**: `BAN.MOVCTA.LEGACYLIVE`

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_MOVCTA_LEGACYLIVE
```

---

#### SELECT #469 - Line 44

**File**: `BAN.B.MOVCTA.PURGE.FILES.SELECT.b`

**Routine**: `BAN.B.MOVCTA.PURGE.FILES.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.MOVCTA.LEGACYLIVE WITH ESTADO NE NEW
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.MOVCTA.LEGACYLIVE WITH ESTADO NE NEW
```

**Table**: `BAN.MOVCTA.LEGACYLIVE`

**Fields** (1):
-  `ESTADO`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_MOVCTA_LEGACYLIVE
WHERE ESTADO != 'NEW'
```

---

#### SELECT #470 - Line 45

**File**: `BAN.E.BLD.COUNTRY.CODE.b`

**Routine**: `BAN.E.BLD.COUNTRY.CODE` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.COUNTRY WITH LT.PHONE.CODE EQ {Y.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.COUNTRY WITH LT.PHONE.CODE EQ 12345
```

**Table**: `COUNTRY`

**Fields** (1):
-  `LT.PHONE.CODE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.PHONE.CODE - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM COUNTRY
WHERE LT_PHONE_CODE = '12345'
```

---

#### SELECT #471 - Line 55

**File**: `BAN.E.BLD.CUS.LEGAL.ID.b`

**Routine**: `BAN.E.BLD.CUS.LEGAL.ID` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ CUS.LEGAL.DOC.NAME
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ CUS.LEGAL.DOC.NAME
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `VIRTUAL.TABLE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE VIRTUAL_TABLE = 'CUS.LEGAL.DOC.NAME'
```

---

#### SELECT #472 - Line 33

**File**: `BAN.E.BLD.RSK.QAL.b`

**Routine**: `BAN.E.BLD.RSK.QAL` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.RISK.QUALIFY BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.RISK.QUALIFY BY @ID
```

**Table**: `BAN.RISK.QUALIFY`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_RISK_QUALIFY
ORDER BY ID ASC
```

---

#### SELECT #473 - Line 39

**File**: `BAN.E.CONV.CARD.TYPE.b`

**Routine**: `BAN.E.CONV.CARD.TYPE` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE "{Y.LUP.ID}..."
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE "EB.CARD.TYPE*..."
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'EB.CARD.TYPE*%'
```

---

#### SELECT #474 - Line 37

**File**: `BAN.E.CONV.MANDATE.DETS.b`

**Routine**: `BAN.E.CONV.MANDATE.DETS` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.EB.MANDATE WITH @ID LIKE {Y.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.MANDATE WITH @ID LIKE 12345...
```

**Table**: `EB.MANDATE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM EB_MANDATE
WHERE ID LIKE '12345%'
```

---

#### SELECT #475 - Line 44

**File**: `BAN.E.CONV.OTHER.OFF.b`

**Routine**: `BAN.E.CONV.OTHER.OFF` (ENQUIRY (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CR.OTHER.PRODUCTS CUSTOMER LIKE {FIELD(O.DATA,'#',1)}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CR.OTHER.PRODUCTS CUSTOMER LIKE {FIELD(O.DATA,'#',1)}...
```

**Table**: `CR.OTHER.PRODUCTS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: FIELD(O.DATA,'#',1)

**Translated SQL**:
```sql
SELECT *
FROM CR_OTHER_PRODUCTS
```

---

#### SELECT #476 - Line 113

**File**: `BAN.E.NOF.AA.DEPOSITS.PRINT.b`

**Routine**: `BAN.E.NOF.AA.DEPOSITS.PRINT` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CUS.LEGAL.ID WITH @ID LIKE {Y.CUS.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUS.LEGAL.ID WITH @ID LIKE VALUE123...
```

**Table**: `CUS.LEGAL.ID`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'CUS.LEGAL.ID' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/CUS.LEGAL.ID
-   Unresolved variables: Y.CUS.ID

**Translated SQL**:
```sql
SELECT *
FROM CUS_LEGAL_ID
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #477 - Line 248

**File**: `BAN.E.NOF.AA.DEPOSITS.PRINT.b`

**Routine**: `BAN.E.NOF.AA.DEPOSITS.PRINT` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {R.CUS.LEGAL.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ SAMPLE_VALUE
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CUSTOMER' used in condition (cannot create index on M fields)
-   Unresolved variables: R.CUS.LEGAL.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE CUSTOMER = 'SAMPLE_VALUE'
```

---

#### SELECT #478 - Line 156

**File**: `BAN.E.NOF.AA.LENDING.PRINT.b`

**Routine**: `BAN.E.NOF.AA.LENDING.PRINT` (NOFILE (inferred))

**Variable**: `SEL.CMD.REPORT`

**AS PER CODE**:
```
SELECT F.BAN.REPORTING.PRINT REPORT.NAME EQ {Y.EI.NAME}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.REPORTING.PRINT REPORT.NAME EQ VALUE123
```

**Table**: `BAN.REPORTING.PRINT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.EI.NAME

**Translated SQL**:
```sql
SELECT *
FROM BAN_REPORTING_PRINT
```

---

#### SELECT #479 - Line 286

**File**: `BAN.E.NOF.AA.LENDING.PRINT.b`

**Routine**: `BAN.E.NOF.AA.LENDING.PRINT` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.EB.LOOKUP} WITH @ID LIKE CUS.LEGAL.DOC.NAME...
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.LOOKUP WITH @ID LIKE CUS.LEGAL.DOC.NAME...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FN.EB.LOOKUP

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'CUS.LEGAL.DOC.NAME%'
```

---

#### SELECT #480 - Line 78

**File**: `BAN.E.NOF.CUSTOMER.CARDS.b`

**Routine**: `BAN.E.NOF.CUSTOMER.CARDS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CARD.ISSUE WITH ACCOUNT EQ {Y.ACCT.LIST}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CARD.ISSUE WITH ACCOUNT EQ VALUE123
```

**Table**: `CARD.ISSUE`

**Fields** (1):
-  `ACCOUNT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ACCOUNT' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCT.LIST

**Translated SQL**:
```sql
SELECT *
FROM CARD_ISSUE
WHERE ACCOUNT = 'VALUE123'
```

---

#### SELECT #481 - Line 263

**File**: `BAN.E.NOF.TELLER.PRINT.b`

**Routine**: `BAN.E.NOF.TELLER.PRINT` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BAN.REFER.REQUEST WITH RR.ACCOUNT EQ {Y.AA.ARRANGEMENT.ID} AND @ID LIKE {Y.CUSTOMER.ID}....
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.REFER.REQUEST WITH RR.ACCOUNT EQ VALUE123 AND @ID LIKE VALUE123....
```

**Table**: `BAN.REFER.REQUEST`

**Fields** (2):
-  `RR.ACCOUNT`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'RR.ACCOUNT' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.AA.ARRANGEMENT.ID, Y.CUS.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_REFER_REQUEST
WHERE RR_ACCOUNT = 'VALUE123' AND ID LIKE 'VALUE123%.'
```

---

#### SELECT #482 - Line 116

**File**: `BAN.I.ACCHARGE.REQUEST.b`

**Routine**: `BAN.I.ACCHARGE.REQUEST` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ {Y.CUENTA}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `LINKED.APPL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CUENTA

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE LINKED_APPL_ID = 'VALUE123'
```

---

#### SELECT #483 - Line 87

**File**: `BAN.S.TDD.FINAL.FILE.b`

**Routine**: `BAN.S.TDD.FINAL.FILE` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.TEMP.FOLDER.POINTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT TEMP.FOLDER.POINTER
```

**Table**: `TEMP.FOLDER.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'TEMP.FOLDER.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/TEMP.FOLDER.POINTER
-   Unresolved variables: F.TEMP.FOLDER.POINTER

**Translated SQL**:
```sql
SELECT *
FROM TEMP_FOLDER_POINTER
```

---

#### SELECT #484 - Line 63

**File**: `BAN.V.USR.ACTDIR.b`

**Routine**: `BAN.V.USR.ACTDIR` (VERSION (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.USER WITH SIGN.ON.NAME EQ {Y.COMI}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.USER WITH SIGN.ON.NAME EQ VALUE123
```

**Table**: `USER`

**Fields** (1):
-  `SIGN.ON.NAME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.COMI

**Translated SQL**:
```sql
SELECT *
FROM USER
WHERE SIGN_ON_NAME = 'VALUE123'
```

---

#### SELECT #485 - Line 29

**File**: `BAPA.B.FECI.UPDATE.SELECT.b`

**Routine**: `BAPA.B.FECI.UPDATE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.CUS.JOB WITH INCOME.LEVEL EQ 5
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.CUS.JOB WITH INCOME.LEVEL EQ 5
```

**Table**: `BCM.CUS.JOB`

**Fields** (1):
-  `INCOME.LEVEL`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BCM_CUS_JOB
WHERE INCOME_LEVEL = '5'
```

---

#### SELECT #486 - Line 47

**File**: `BAPA.B.INCOME.LEVEL.UPDATE.SELECT.b`

**Routine**: `BAPA.B.INCOME.LEVEL.UPDATE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CUSTOMER WITH DATE.OF.BIRTH LE {END.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT CUSTOMER WITH DATE.OF.BIRTH LE 55Y
```

**Table**: `CUSTOMER`

**Fields** (1):
-  `DATE.OF.BIRTH`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
WHERE DATE_OF_BIRTH <= '55Y'
```

---

#### SELECT #487 - Line 100

**File**: `BAPA.E.NOF.EVENT.CUS.b`

**Routine**: `BAPA.E.NOF.EVENT.CUS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.IF.EVENTS.INTERFACE.TABLE WITH EVENT.TYPE LIKE UpdatedCus... AND CREATION.DATE GE {Y.FECHA.INICIAL} AND CREATION.DATE LE {Y.FECHA.FINAL}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.IF.EVENTS.INTERFACE.TABLE WITH EVENT.TYPE LIKE UpdatedCus... AND CREATION.DATE GE VALUE123 AND CREATION.DATE LE VALUE123
```

**Table**: `IF.EVENTS.INTERFACE.TABLE`

**Fields** (2):
-  `CREATION.DATE`  Type: D
-  `EVENT.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FECHA.INICIAL, Y.FECHA.FINAL

**Translated SQL**:
```sql
SELECT *
FROM IF_EVENTS_INTERFACE_TABLE
WHERE EVENT_TYPE LIKE 'UpdatedCus%' AND CREATION_DATE >= 'VALUE123' AND CREATION_DATE <= 'VALUE123'
```

---

#### SELECT #488 - Line 118

**File**: `BAPA.V.GET.SEE.CUS.PENDING.b`

**Routine**: `BAPA.V.GET.SEE.CUS.PENDING` (VERSION (inferred))

**Variable**: `STMT.CUSTOMER`

**AS PER CODE**:
```
SELECT F.CUSTOMER WITH CUSTOMER.STATUS EQ 1 AND ACCOUNT.OFFICER NE 1 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER WITH CUSTOMER.STATUS EQ 1 AND ACCOUNT.OFFICER NE 1 
```

**Table**: `CUSTOMER`

**Fields** (2):
-  `ACCOUNT.OFFICER`  Type: D
-  `CUSTOMER.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
WHERE CUSTOMER_STATUS = '1' AND ACCOUNT_OFFICER != '1'
```

---

#### SELECT #489 - Line 83

**File**: `BCM.B.AC.STMT.SELECT.b`

**Routine**: `BCM.B.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACCOUNT.STATEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.STATEMENT
```

**Table**: `ACCOUNT.STATEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_STATEMENT
```

---

#### SELECT #490 - Line 93

**File**: `BCM.B.AC.STMT.SELECT.b`

**Routine**: `BCM.B.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `YCMD`

**AS PER CODE**:
```
SELECT ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE LIKE {Y.END.DATE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE LIKE VALUE123...
```

**Table**: `ACCOUNT.CLOSED`

**Fields** (1):
-  `ACCT.CLOSE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.END.DATE

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_CLOSED
WHERE ACCT_CLOSE_DATE LIKE 'VALUE123%'
```

---

#### SELECT #491 - Line 31

**File**: `BCM.B.PROCESS.AML.DATA.SELECT.b`

**Routine**: `BCM.B.PROCESS.AML.DATA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.AML.REPORT.RECORDS
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.AML.REPORT.RECORDS
```

**Table**: `BCM.AML.REPORT.RECORDS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_AML_REPORT_RECORDS
```

---

#### SELECT #492 - Line 85

**File**: `BCM.B.TDD.LIQ.DEB.POST.b`

**Routine**: `BCM.B.TDD.LIQ.DEB.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.FILE.POINTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT FILE.POINTER
```

**Table**: `FILE.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'FILE.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FILE.POINTER
-   Unresolved variables: F.FILE.POINTER

**Translated SQL**:
```sql
SELECT *
FROM FILE_POINTER
```

---

#### SELECT #493 - Line 204

**File**: `BCM.B.TDD.LIQ.DEB.POST.b`

**Routine**: `BCM.B.TDD.LIQ.DEB.POST` (BATCH (inferred))

**Variable**: `SEL.CMD.ID`

**AS PER CODE**:
```
SELECT F.EB.BAPA.ID.PENDING.CHG
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.ID.PENDING.CHG
```

**Table**: `EB.BAPA.ID.PENDING.CHG`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_ID_PENDING_CHG
```

---

#### SELECT #494 - Line 44

**File**: `BCM.B.TDD.RPOS.LIQ.SELECT.b`

**Routine**: `BCM.B.TDD.RPOS.LIQ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.TMP.TDD.LIQ.DEB
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.TMP.TDD.LIQ.DEB
```

**Table**: `BCM.TMP.TDD.LIQ.DEB`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BCM.TMP.TDD.LIQ.DEB' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BCM.TMP.TDD.LIQ.DEB

**Translated SQL**:
```sql
SELECT *
FROM BCM_TMP_TDD_LIQ_DEB
```

---

#### SELECT #495 - Line 53

**File**: `BCM.E.BLD.CUST.IVR.b`

**Routine**: `BCM.E.BLD.CUST.IVR` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH @ID LIKE {Y.CUSTOMER.ID}... BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TCIB.AFFILIATION WITH @ID LIKE VALUE123... BY @ID
```

**Table**: `BAN.TCIB.AFFILIATION`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUSTOMER.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_TCIB_AFFILIATION
WHERE ID LIKE 'VALUE123%'
ORDER BY ID ASC
```

---

#### SELECT #496 - Line 184

**File**: `BCM.ENQ.NOF.CLICTA.ACCT.LIST.WS.b`

**Routine**: `BCM.ENQ.NOF.CLICTA.ACCT.LIST.WS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.ACCT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #497 - Line 105

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Routine**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ {Y.ACCT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `LINKED.APPL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE LINKED_APPL_ID = 'VALUE123'
```

---

#### SELECT #498 - Line 114

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Routine**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ {Y.ACCT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #499 - Line 118

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Routine**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ {Y.ACCOUNT.NO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `LINKED.APPL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCOUNT.NO

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE LINKED_APPL_ID = 'VALUE123'
```

---

#### SELECT #500 - Line 153

**File**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS.b`

**Routine**: `BCM.ENQ.NOF.CLICTA.CUSTM.LIST.WS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.ACCOUNT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #501 - Line 349

**File**: `BCM.I.CUS.COUNTRY.b`

**Routine**: `BCM.I.CUS.COUNTRY` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CITIES WITH COUNTRY.ID EQ '{Y.COUNTRY}' AND PROVINCE EQ '{Y.PROVINCE.VE.CO}' AND DESCRIPTION EQ '{Y.TOWN.COUNTRY}'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CITIES WITH COUNTRY.ID EQ 'VALUE123' AND PROVINCE EQ 'VALUE123' AND DESCRIPTION EQ 'VALUE123'
```

**Table**: `BAN.CITIES`

**Fields** (3):
-  `DESCRIPTION`  Type: D
-  `PROVINCE`  Type: D
-  `COUNTRY.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.COUNTRY, Y.PROVINCE.VE.CO, Y.TOWN.COUNTRY

**Translated SQL**:
```sql
SELECT *
FROM BAN_CITIES
WHERE COUNTRY_ID = 'VALUE123' AND PROVINCE = 'VALUE123' AND DESCRIPTION = 'VALUE123'
```

---

#### SELECT #502 - Line 356

**File**: `BCM.I.CUS.COUNTRY.b`

**Routine**: `BCM.I.CUS.COUNTRY` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CITIES WITH COUNTRY.ID EQ '{Y.COUNTRY}' AND DESCRIPTION EQ '{Y.TOWN.COUNTRY}'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CITIES WITH COUNTRY.ID EQ 'VALUE123' AND DESCRIPTION EQ 'VALUE123'
```

**Table**: `BAN.CITIES`

**Fields** (2):
-  `DESCRIPTION`  Type: D
-  `COUNTRY.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.COUNTRY, Y.TOWN.COUNTRY

**Translated SQL**:
```sql
SELECT *
FROM BAN_CITIES
WHERE COUNTRY_ID = 'VALUE123' AND DESCRIPTION = 'VALUE123'
```

---

#### SELECT #503 - Line 32

**File**: `BCM.S.PROTOCOL.DATA.UPD.SELECT.b`

**Routine**: `BCM.S.PROTOCOL.DATA.UPD.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BCM.AML.REPORT.RECORDS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BCM.AML.REPORT.RECORDS
```

**Table**: `BCM.AML.REPORT.RECORDS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_AML_REPORT_RECORDS
```

---

#### SELECT #504 - Line 36

**File**: `BCM.S.PROTOCOL.DATA.UPDL.SELECT.b`

**Routine**: `BCM.S.PROTOCOL.DATA.UPDL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT PROTOCOL WITH APPLICATION EQ ENQUIRY.SELECT
```

**SIMULATED AT RUNTIME**:
```
SELECT PROTOCOL WITH APPLICATION EQ ENQUIRY.SELECT
```

**Table**: `PROTOCOL`

**Fields** (1):
-  `APPLICATION`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM PROTOCOL
WHERE APPLICATION = 'ENQUIRY.SELECT'
```

---

#### SELECT #505 - Line 69

**File**: `BPA.E.NOF.CUST.N.UPD.b`

**Routine**: `BPA.E.NOF.CUST.N.UPD` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.DFE.INTRF.LOG WITH INTERFACE.CODE LIKE BPA.CUSTOMER.ACCT.OFF AND VALUE.DATE LIKE {Y.VALUE.DATE} AND REQUEST.STATUS LIKE Failed
```

**SIMULATED AT RUNTIME**:
```
SELECT F.DFE.INTRF.LOG WITH INTERFACE.CODE LIKE BPA.CUSTOMER.ACCT.OFF AND VALUE.DATE LIKE VALUE123 AND REQUEST.STATUS LIKE Failed
```

**Table**: `DFE.INTRF.LOG`

**Fields** (3):
-  `INTERFACE.CODE`  Type: D
-  `REQUEST.STATUS`  Type: D
-  `VALUE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.VALUE.DATE

**Translated SQL**:
```sql
SELECT *
FROM DFE_INTRF_LOG
WHERE INTERFACE_CODE LIKE '%BPA.CUSTOMER.ACCT.OFF%' AND VALUE_DATE LIKE '%VALUE123%' AND REQUEST_STATUS LIKE '%Failed%'
```

---

#### SELECT #506 - Line 81

**File**: `BRD.I.CUS.PERSON.TYPE.SB.b`

**Routine**: `BRD.I.CUS.PERSON.TYPE.SB` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BRD.PERSON.TYPE.SIB WITH ID.CONCAT EQ {Y.PERSON.TYPE}-{Y.LT.DOC}-{Y.GENDER}-{Y.NATIONALITY}-{Y.RESIDENCE}-{Y.CAT.ECON.ACT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BRD.PERSON.TYPE.SIB WITH ID.CONCAT EQ VALUE123-VALUE123-VALUE123-VALUE123-VALUE123-VALUE123
```

**Table**: `BRD.PERSON.TYPE.SIB`

**Fields** (1):
-  `ID.CONCAT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.PERSON.TYPE, Y.LT.DOC, Y.GENDER, Y.NATIONALITY, Y.RESIDENCE

**Translated SQL**:
```sql
SELECT *
FROM BRD_PERSON_TYPE_SIB
WHERE ID_CONCAT = 'VALUE123-VALUE123-VALUE123-VALUE123-VALUE123-VALUE123'
```

---

#### SELECT #507 - Line 26

**File**: `BAPA.B.CR.RISK.ASSESSMENT.SELECT.b`

**Routine**: `BAPA.B.CR.RISK.ASSESSMENT.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS EQ "PROCESSED"
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CREATE.CUS.ACC WITH PROCESS.CUS EQ "PROCESSED"
```

**Table**: `BAN.CREATE.CUS.ACC`

**Fields** (1):
-  `PROCESS.CUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CREATE_CUS_ACC
WHERE PROCESS_CUS = 'PROCESSED'
```

---

#### SELECT #508 - Line 494

**File**: `BAPA.I.CR.RISK.ASSESSMENT.b`

**Routine**: `BAPA.I.CR.RISK.ASSESSMENT` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH CUSTOMER EQ {Y.NUM.CUST}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH CUSTOMER EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.NUM.CUST

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE CUSTOMER = 'VALUE123'
```

---

#### SELECT #509 - Line 551

**File**: `BAPA.I.CR.RISK.ASSESSMENT.JUR.b`

**Routine**: `BAPA.I.CR.RISK.ASSESSMENT.JUR` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH CUSTOMER EQ {Y.NUM.CUST}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH CUSTOMER EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.NUM.CUST

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE CUSTOMER = 'VALUE123'
```

---

#### SELECT #510 - Line 73

**File**: `BAPA.I.UPD.CHQ.INWRD.CLR.b`

**Routine**: `BAPA.I.UPD.CHQ.INWRD.CLR` (Unknown)

**Variable**: `SEL.INWARD.CLEARING`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID LIKE {EB.SystemTables.getToday()}... AND CHQ.STATUS EQ DEVUELTO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID LIKE TODAY... AND CHQ.STATUS EQ DEVUELTO
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID LIKE 'TODAY%' AND CHQ_STATUS = 'DEVUELTO'
```

---

#### SELECT #511 - Line 94

**File**: `BAPA.B.INCLG.CHQ.APPLY.POST2.b`

**Routine**: `BAPA.B.INCLG.CHQ.APPLY.POST2` (BATCH (inferred))

**Variable**: `SelCmdPo`

**AS PER CODE**:
```
SELECT {FnBapaChqWrk}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAPA.B.CHQ.WRK.LIST
```

**Table**: `BAPA.B.CHQ.WRK.LIST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAPA.B.CHQ.WRK.LIST' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAPA.B.CHQ.WRK.LIST

**Translated SQL**:
```sql
SELECT *
FROM BAPA_B_CHQ_WRK_LIST
```

---

#### SELECT #512 - Line 82

**File**: `BAPA.I.COBROCOMISION.b`

**Routine**: `BAPA.I.COBROCOMISION` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TAX WITH @ID LIKE {Y.TAX.CODE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TAX WITH @ID LIKE VALUE123...
```

**Table**: `TAX`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TAX.CODE

**Translated SQL**:
```sql
SELECT *
FROM TAX
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #513 - Line 74

**File**: `BAPA.I.UPD.CHQ.INWRD.CLR.b`

**Routine**: `BAPA.I.UPD.CHQ.INWRD.CLR` (Unknown)

**Variable**: `SEL.INWARD.CLEARING`

**AS PER CODE**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID LIKE {EB.SystemTables.getToday()}... AND CHQ.STATUS EQ DEVUELTO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.INWARD.CLEARING WITH @ID LIKE TODAY... AND CHQ.STATUS EQ DEVUELTO
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID LIKE 'TODAY%' AND CHQ_STATUS = 'DEVUELTO'
```

---

#### SELECT #514 - Line 199

**File**: `BAPA.V.EXISTS.ID.STMT.PRINTED.b`

**Routine**: `BAPA.V.EXISTS.ID.STMT.PRINTED` (VERSION (inferred))

**Variable**: `STMT.SEL`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING WITH @ID LIKE {EB.SystemTables.getToday()}... AND CHQ.ACCOUNT EQ {R.BAN.INWARD<BAPALOCALTABLE.MigTablas2.BanInwardClearing.BanIcChqAccount>} AND CHQ.STATUS EQ 'PAGADO' AND HEAD.ID EQ {R.BAN.INWARD<BAPALOCALTABLE.MigTablas2.BanInwardClearing.BanIcHeadId>}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING WITH @ID LIKE TODAY... AND CHQ.ACCOUNT EQ {R.BAN.INWARD<BAPALOCALTABLE.MigTablas2.BanInwardClearing.BanIcChqAccount>} AND CHQ.STATUS EQ 'PAGADO' AND HEAD.ID EQ {R.BAN.INWARD<BAPALOCALTABLE.MigTablas2.BanInwardClearing.BanIcHeadId>}
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (4):
-  `HEAD.ID`  Type: D
-  `CHQ.STATUS`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID LIKE 'TODAY%' AND CHQ_ACCOUNT = '{R.BAN.INWARD<BAPALOCALTABLE.MigTablas2.BanInwardClearing.BanIcChqAccount>}' AND CHQ_STATUS = 'PAGADO' AND HEAD_ID = '{R.BAN.INWARD<BAPALOCALTABLE.MigTablas2.BanInwardClearing.BanIcHeadId>}'
```

---

#### SELECT #515 - Line 50

**File**: `BAPA.V.EXISTS.ID.STMT.PRINTED.SELECT.b`

**Routine**: `BAPA.V.EXISTS.ID.STMT.PRINTED.SELECT` (BATCH (inferred))

**Variable**: `CMD.OFS.LIST`

**AS PER CODE**:
```
SELECT F.BPA.INCLG.CHQ.OFS.LIST
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.INCLG.CHQ.OFS.LIST
```

**Table**: `BPA.INCLG.CHQ.OFS.LIST`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BPA.INCLG.CHQ.OFS.LIST' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BPA.INCLG.CHQ.OFS.LIST

**Translated SQL**:
```sql
SELECT *
FROM BPA_INCLG_CHQ_OFS_LIST
```

---

#### SELECT #516 - Line 55

**File**: `BAPA.V.EXISTS.ID.STMT.PRINTED.SELECT.b`

**Routine**: `BAPA.V.EXISTS.ID.STMT.PRINTED.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING WITH @ID LIKE {EB.SystemTables.getToday()}... AND CHQ.STATUS EQ 'PAGADO' AND HEAD.ID EQ {R.BATCH<EB.Service.Batch.BatData,1>}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING WITH @ID LIKE TODAY... AND CHQ.STATUS EQ 'PAGADO' AND HEAD.ID EQ {R.BATCH<EB.Service.Batch.BatData,1>}
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (3):
-  `HEAD.ID`  Type: D
-  `CHQ.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID LIKE 'TODAY%' AND CHQ_STATUS = 'PAGADO' AND HEAD_ID = '{R.BATCH<EB.Service.Batch.BatData,1>}'
```

---

#### SELECT #517 - Line 49

**File**: `BPA.B.CLEAR.SALDOS.CHQ.SELECT.b`

**Routine**: `BPA.B.CLEAR.SALDOS.CHQ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.L.ACCT.VAL.TEM
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.ACCT.VAL.TEM
```

**Table**: `EB.BAPA.L.ACCT.VAL.TEM`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_ACCT_VAL_TEM
```

---

#### SELECT #518 - Line 47

**File**: `BPA.B.PRE.TOTALES.CHQ.SELECT.b`

**Routine**: `BPA.B.PRE.TOTALES.CHQ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ {Y.TODAY} AND FILE.STATUS EQ PROCESADO
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING.HEAD WITH FILE.DATE EQ VALUE123 AND FILE.STATUS EQ PROCESADO
```

**Table**: `BAN.INWARD.CLEARING.HEAD`

**Fields** (2):
-  `FILE.STATUS`  Type: D
-  `FILE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING_HEAD
WHERE FILE_DATE = 'VALUE123' AND FILE_STATUS = 'PROCESADO'
```

---

#### SELECT #519 - Line 68

**File**: `BPA.B.PRE.TOTALES.CHQ.SELECT.b`

**Routine**: `BPA.B.PRE.TOTALES.CHQ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.INWARD.CLEARING WITH @ID LIKE {Y.ANIO}... AND FILE.NAME EQ {Y.FILE.NAME}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.INWARD.CLEARING WITH @ID LIKE VALUE123... AND FILE.NAME EQ VALUE123
```

**Table**: `BAN.INWARD.CLEARING`

**Fields** (2):
-  `FILE.NAME`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ANIO, Y.FILE.NAME

**Translated SQL**:
```sql
SELECT *
FROM BAN_INWARD_CLEARING
WHERE ID LIKE 'VALUE123%' AND FILE_NAME = 'VALUE123'
```

---

#### SELECT #520 - Line 49

**File**: `BPA.B.SALDOS.CHQ.SELECT.b`

**Routine**: `BPA.B.SALDOS.CHQ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.L.ACCT.VAL.TEM
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.ACCT.VAL.TEM
```

**Table**: `EB.BAPA.L.ACCT.VAL.TEM`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_ACCT_VAL_TEM
```

---

#### SELECT #521 - Line 172

**File**: `BAPA.AA.CANCEL.CLOSED.b`

**Routine**: `BAPA.AA.CANCEL.CLOSED` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.COLLATERAL WITH @ID LIKE {COLL.RIGHT.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.COLLATERAL WITH @ID LIKE SAMPLE_VALUE...
```

**Table**: `COLLATERAL`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
WHERE ID LIKE 'SAMPLE_VALUE%'
```

---

#### SELECT #522 - Line 324

**File**: `BAPA.AA.CANCEL.CLOSED.b`

**Routine**: `BAPA.AA.CANCEL.CLOSED` (Unknown)

**Variable**: `SEL.CMD.MD`

**AS PER CODE**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH MD.DEAL.ID EQ {BAN.COLLATERAL.RECORD<BAN.BC.MD.DEAL.ID>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH MD.DEAL.ID EQ {BAN.COLLATERAL.RECORD<BAN.BC.MD.DEAL.ID>}
```

**Table**: `BAN.BANESCO.COLLATERAL`

**Fields** (1):
-  `MD.DEAL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
WHERE MD_DEAL_ID = '{BAN.COLLATERAL.RECORD<BAN.BC.MD.DEAL.ID>}'
```

---

#### SELECT #523 - Line 37

**File**: `BAN.AUTH.UPDATE.CONCAT.ALE.b`

**Routine**: `BAN.AUTH.UPDATE.CONCAT.ALE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS
```

**Table**: `AC.LOCKED.EVENTS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
```

---

#### SELECT #524 - Line 45

**File**: `BAN.B.AA.PRODUCT.VARIATION.b`

**Routine**: `BAN.B.AA.PRODUCT.VARIATION` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE MARITAL.STATUS*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE MARITAL.STATUS*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'MARITAL.STATUS*%'
```

---

#### SELECT #525 - Line 45

**File**: `BAN.B.COLLECT.TYPE.b`

**Routine**: `BAN.B.COLLECT.TYPE` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.COLLECT.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.COLLECT.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BPA.COLLECT.TYPE*%'
```

---

#### SELECT #526 - Line 45

**File**: `BAN.B.COMPANY.TYPE.b`

**Routine**: `BAN.B.COMPANY.TYPE` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.COMPANY.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.COMPANY.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BPA.COMPANY.TYPE*%'
```

---

#### SELECT #527 - Line 45

**File**: `BAN.B.CUS.GENDER.b`

**Routine**: `BAN.B.CUS.GENDER` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE GENDER*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE GENDER*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'GENDER*%'
```

---

#### SELECT #528 - Line 45

**File**: `BAN.B.CUS.INCOME.SOURCE.b`

**Routine**: `BAN.B.CUS.INCOME.SOURCE` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BCM.CUS.INCOME.SOURCE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BCM.CUS.INCOME.SOURCE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BCM.CUS.INCOME.SOURCE*%'
```

---

#### SELECT #529 - Line 45

**File**: `BAN.B.CUS.PLAN.b`

**Routine**: `BAN.B.CUS.PLAN` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE CUS.BAN.PLAN*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE CUS.BAN.PLAN*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'CUS.BAN.PLAN*%'
```

---

#### SELECT #530 - Line 45

**File**: `BAN.B.MARITAL.STATUS.b`

**Routine**: `BAN.B.MARITAL.STATUS` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE MARITAL.STATUS*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE MARITAL.STATUS*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'MARITAL.STATUS*%'
```

---

#### SELECT #531 - Line 45

**File**: `BAN.B.PAYM.TYPE.b`

**Routine**: `BAN.B.PAYM.TYPE` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE PA.PAYM.TYPE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE PA.PAYM.TYPE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'PA.PAYM.TYPE*%'
```

---

#### SELECT #532 - Line 45

**File**: `BAN.B.RECFUNDS.b`

**Routine**: `BAN.B.RECFUNDS` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.RECFUNDS*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.RECFUNDS*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BPA.RECFUNDS*%'
```

---

#### SELECT #533 - Line 45

**File**: `BAN.B.RELATION.BANK.b`

**Routine**: `BAN.B.RELATION.BANK` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE RELATION.BANK*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE RELATION.BANK*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'RELATION.BANK*%'
```

---

#### SELECT #534 - Line 45

**File**: `BAN.B.ROUTE.CODE.b`

**Routine**: `BAN.B.ROUTE.CODE` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.ROUTE.CODE*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH @ID LIKE BPA.ROUTE.CODE*...
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE ID LIKE 'BPA.ROUTE.CODE*%'
```

---

#### SELECT #535 - Line 33

**File**: `BAN.DW.EB.LOOKUP.SEL.RTN.b`

**Routine**: `BAN.DW.EB.LOOKUP.SEL.RTN` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.EB.LOOKUP} WITH VIRTUAL.TABLE EQ {Y.LOOKUP.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.LOOKUP WITH VIRTUAL.TABLE EQ VALUE123
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `VIRTUAL.TABLE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LOOKUP.ID

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE VIRTUAL_TABLE = 'VALUE123'
```

---

#### SELECT #536 - Line 53

**File**: `BAPA.B.EXTRACT.REFERE.CANCEL.SELECT.b`

**Routine**: `BAPA.B.EXTRACT.REFERE.CANCEL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING AND ARR.STATUS EQ PENDING.CLOSURE AND START.DATE LE {Y.LAST.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING AND ARR.STATUS EQ PENDING.CLOSURE AND START.DATE LE VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (3):
-  `START.DATE`  Type: D
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LAST.DAY

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING' AND ARR_STATUS = 'PENDING.CLOSURE' AND START_DATE <= 'VALUE123'
```

---

#### SELECT #537 - Line 204

**File**: `BCM.B.EXTRACT.ACMST.b`

**Routine**: `BCM.B.EXTRACT.ACMST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.CHARGE.DETAILS WITH @ID LIKE {Y.AA.ID}... BY-DSND PAYMENT.DATE
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.CHARGE.DETAILS WITH @ID LIKE VALUE123... BY-DSND PAYMENT.DATE
```

**Table**: `AA.CHARGE.DETAILS`

**Fields** (2):
-  `@ID`  Type: D
-  `PAYMENT.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PAYMENT.DATE' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.AA.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_CHARGE_DETAILS
WHERE ID LIKE 'VALUE123%'
ORDER BY PAYMENT_DATE DESC
```

---

#### SELECT #538 - Line 36

**File**: `BCM.B.EXTRACT.ACMST.SELECT.b`

**Routine**: `BCM.B.EXTRACT.ACMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH START.DATE LE {EB.SystemTables.getRDates(EB.Utility.Dates.DatLastWorkingDay)}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH START.DATE LE RDATES
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `START.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE START_DATE <= 'RDATES'
```

---

#### SELECT #539 - Line 58

**File**: `BCM.B.EXTRACT.APCLS.SELECT.b`

**Routine**: `BCM.B.EXTRACT.APCLS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT RE.STAT.REP.LINE
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.STAT.REP.LINE
```

**Table**: `RE.STAT.REP.LINE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_REP_LINE
```

---

#### SELECT #540 - Line 81

**File**: `BCM.B.EXTRACT.CPRBL.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CPRBL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT MD.DEAL
```

**SIMULATED AT RUNTIME**:
```
SELECT MD.DEAL
```

**Table**: `MD.DEAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM MD_DEAL
```

---

#### SELECT #541 - Line 32

**File**: `BCM.B.EXTRACT.CUFIN.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUFIN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CUSTOMER
```

**SIMULATED AT RUNTIME**:
```
SELECT CUSTOMER
```

**Table**: `CUSTOMER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
```

---

#### SELECT #542 - Line 31

**File**: `BCM.B.EXTRACT.CUMAD.AA.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.AA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #543 - Line 23

**File**: `BCM.B.EXTRACT.CUMAD.BENEF.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.BENEF.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #544 - Line 23

**File**: `BCM.B.EXTRACT.CUMAD.COLL.TIT.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.COLL.TIT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT COLLATERAL
```

**Table**: `COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
```

---

#### SELECT #545 - Line 30

**File**: `BCM.B.EXTRACT.CUMAD.COLLATERAL.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.COLLATERAL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT COLLATERAL
```

**Table**: `COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
```

---

#### SELECT #546 - Line 29

**File**: `BCM.B.EXTRACT.CUMAD.COMPANY.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.COMPANY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.CUS.COMPANY
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.CUS.COMPANY
```

**Table**: `BCM.CUS.COMPANY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_CUS_COMPANY
```

---

#### SELECT #547 - Line 29

**File**: `BCM.B.EXTRACT.CUMAD.CUSTOMER.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.CUSTOMER.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CUSTOMER
```

**SIMULATED AT RUNTIME**:
```
SELECT CUSTOMER
```

**Table**: `CUSTOMER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
```

---

#### SELECT #548 - Line 46

**File**: `BCM.B.EXTRACT.CUMAD.PEP.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.PEP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.CUS.PEP
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.CUS.PEP
```

**Table**: `BCM.CUS.PEP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_CUS_PEP
```

---

#### SELECT #549 - Line 29

**File**: `BCM.B.EXTRACT.CUMAD.REFERENCE.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.REFERENCE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.CUS.REFERENCE
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.CUS.REFERENCE
```

**Table**: `BCM.CUS.REFERENCE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_CUS_REFERENCE
```

---

#### SELECT #550 - Line 28

**File**: `BCM.B.EXTRACT.CUMAD.SIGNERS.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMAD.SIGNERS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.SIGNATORY.GROUP
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.SIGNATORY.GROUP
```

**Table**: `EB.SIGNATORY.GROUP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_SIGNATORY_GROUP
```

---

#### SELECT #551 - Line 36

**File**: `BCM.B.EXTRACT.CUMST.SELECT.b`

**Routine**: `BCM.B.EXTRACT.CUMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CUSTOMER
```

**SIMULATED AT RUNTIME**:
```
SELECT CUSTOMER
```

**Table**: `CUSTOMER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
```

---

#### SELECT #552 - Line 174

**File**: `BCM.B.EXTRACT.DEALS.LOAD.b`

**Routine**: `BCM.B.EXTRACT.DEALS.LOAD` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.PRD.DES.INTEREST WITH NR.TYPE EQ MINIMUM OR NR.TYPE EQ MAXIMUM BY-DSND @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.PRD.DES.INTEREST WITH NR.TYPE EQ MINIMUM OR NR.TYPE EQ MAXIMUM BY-DSND @ID
```

**Table**: `AA.PRD.DES.INTEREST`

**Fields** (2):
-  `NR.TYPE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'NR.TYPE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_PRD_DES_INTEREST
WHERE NR_TYPE = 'MINIMUM'
ORDER BY ID DESC
```

---

#### SELECT #553 - Line 50

**File**: `BCM.B.EXTRACT.DEALS.SELECT.b`

**Routine**: `BCM.B.EXTRACT.DEALS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #554 - Line 104

**File**: `BCM.B.EXTRACT.DLCNT.LOAD.b`

**Routine**: `BCM.B.EXTRACT.DLCNT.LOAD` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ CREDIT.CLASS AND OTHER.INFO EQ C
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ CREDIT.CLASS AND OTHER.INFO EQ C
```

**Table**: `EB.LOOKUP`

**Fields** (2):
-  `VIRTUAL.TABLE`  Type: D
-  `OTHER.INFO`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE VIRTUAL_TABLE = 'CREDIT.CLASS' AND OTHER_INFO = 'C'
```

---

#### SELECT #555 - Line 48

**File**: `BCM.B.EXTRACT.DLCNT.SELECT.b`

**Routine**: `BCM.B.EXTRACT.DLCNT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING'
```

---

#### SELECT #556 - Line 35

**File**: `BCM.B.EXTRACT.DLITP.SELECT.b`

**Routine**: `BCM.B.EXTRACT.DLITP.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #557 - Line 46

**File**: `BCM.B.EXTRACT.DLPMT.SELECT.b`

**Routine**: `BCM.B.EXTRACT.DLPMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #558 - Line 48

**File**: `BCM.B.EXTRACT.DLSDE.SELECT.b`

**Routine**: `BCM.B.EXTRACT.DLSDE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #559 - Line 36

**File**: `BCM.B.EXTRACT.EUSER.SELECT.b`

**Routine**: `BCM.B.EXTRACT.EUSER.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.EXTERNAL.USER
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.EXTERNAL.USER
```

**Table**: `EB.EXTERNAL.USER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_EXTERNAL_USER
```

---

#### SELECT #560 - Line 42

**File**: `BCM.B.EXTRACT.LCMST.SELECT.b`

**Routine**: `BCM.B.EXTRACT.LCMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT MD.DEAL
```

**SIMULATED AT RUNTIME**:
```
SELECT MD.DEAL
```

**Table**: `MD.DEAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM MD_DEAL
```

---

#### SELECT #561 - Line 52

**File**: `BCM.B.EXTRACT.LCMST.SELECT.b`

**Routine**: `BCM.B.EXTRACT.LCMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LETTER.OF.CREDIT
```

**SIMULATED AT RUNTIME**:
```
SELECT LETTER.OF.CREDIT
```

**Table**: `LETTER.OF.CREDIT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LETTER_OF_CREDIT
```

---

#### SELECT #562 - Line 36

**File**: `BCM.B.EXTRACT.LDMST.SELECT.b`

**Routine**: `BCM.B.EXTRACT.LDMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #563 - Line 46

**File**: `BCM.B.EXTRACT.LNECR.SELECT.b`

**Routine**: `BCM.B.EXTRACT.LNECR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LIMIT
```

**SIMULATED AT RUNTIME**:
```
SELECT LIMIT
```

**Table**: `LIMIT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LIMIT
```

---

#### SELECT #564 - Line 52

**File**: `BCM.B.EXTRACT.RCOLL.SELECT.b`

**Routine**: `BCM.B.EXTRACT.RCOLL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**Table**: `BAN.BANESCO.COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
```

---

#### SELECT #565 - Line 47

**File**: `BCM.B.EXTRACT.ROCIN.SELECT.b`

**Routine**: `BCM.B.EXTRACT.ROCIN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**Table**: `BAN.BANESCO.COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
```

---

#### SELECT #566 - Line 36

**File**: `BCM.B.EXTRACT.ROCOL.SELECT.b`

**Routine**: `BCM.B.EXTRACT.ROCOL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.BANESCO.COLLATERAL
```

**Table**: `BAN.BANESCO.COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
```

---

#### SELECT #567 - Line 49

**File**: `BCM.B.EXTRACT.SIB.AUDIT.SELECT.b`

**Routine**: `BCM.B.EXTRACT.SIB.AUDIT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TELLER$HIS WITH @ID LIKE TT{Y.TO.RUN}... 
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER$HIS WITH @ID LIKE TTVALUE123... 
```

**Table**: `TELLER$HIS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'TELLER'
-   Unresolved variables: Y.TO.RUN

**Translated SQL**:
```sql
SELECT *
FROM TELLER$HIS
WHERE ID LIKE 'TTVALUE123%'
```

---

#### SELECT #568 - Line 66

**File**: `BCM.B.EXTRACT.SIB.AUDIT.SELECT.b`

**Routine**: `BCM.B.EXTRACT.SIB.AUDIT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FUNDS.TRANSFER$HIS WITH @ID LIKE FT{Y.TO.RUN}... 
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER$HIS WITH @ID LIKE FTVALUE123... 
```

**Table**: `FUNDS.TRANSFER$HIS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'FUNDS.TRANSFER'
-   Unresolved variables: Y.TO.RUN

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER$HIS
WHERE ID LIKE 'FTVALUE123%'
```

---

#### SELECT #569 - Line 33

**File**: `BCM.B.EXTRACT.TRANS.SELECT.b`

**Routine**: `BCM.B.EXTRACT.TRANS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH @ID LIKE ...{EB.SystemTables.getRDates(EB.Utility.Dates.DatLastWorkingDay)}
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH @ID LIKE ...RDATES
```

**Table**: `BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE ID LIKE '%RDATES'
```

---

#### SELECT #570 - Line 146

**File**: `BCM.B.TDD.REPORLIQ.LOAD.b`

**Routine**: `BCM.B.TDD.REPORLIQ.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CARD.TYPE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CARD.TYPE
```

**Table**: `CARD.TYPE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CARD_TYPE
```

---

#### SELECT #571 - Line 61

**File**: `BCM.B.TDD.REPORLIQ.SELECT.b`

**Routine**: `BCM.B.TDD.REPORLIQ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BCM.TDD.LIQ.DEB.TMP
```

**SIMULATED AT RUNTIME**:
```
SELECT BCM.TDD.LIQ.DEB.TMP
```

**Table**: `BCM.TDD.LIQ.DEB.TMP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BCM_TDD_LIQ_DEB_TMP
```

---

#### SELECT #572 - Line 90

**File**: `BCM.CONV.ROCOL.COL.PLACED.b`

**Routine**: `BCM.CONV.ROCOL.COL.PLACED` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ {Y.ID.AA}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ VALUE123
```

**Table**: `BAN.BANESCO.COLLATERAL`

**Fields** (1):
-  `LOAN.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LOAN.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ID.AA

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
WHERE LOAN_ID = 'VALUE123'
```

---

#### SELECT #573 - Line 68

**File**: `BCM.CUFIN.SELECT.RTN.b`

**Routine**: `BCM.CUFIN.SELECT.RTN` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.CUSTOMER WITH LT.TCIB.TYPE NE PROSPECT AND CUSTOMER.TYPE NE PROSPECT AND LT.PERSON.TYPE EQ 1
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER WITH LT.TCIB.TYPE NE PROSPECT AND CUSTOMER.TYPE NE PROSPECT AND LT.PERSON.TYPE EQ 1
```

**Table**: `CUSTOMER`

**Fields** (3):
-  `LT.PERSON.TYPE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,11>`)
-  `CUSTOMER.TYPE`  Type: D
-  `LT.TCIB.TYPE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,33>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.PERSON.TYPE, LT.TCIB.TYPE - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
WHERE LT_TCIB_TYPE != 'PROSPECT' AND CUSTOMER_TYPE != 'PROSPECT' AND LT_PERSON_TYPE = '1'
```

---

#### SELECT #574 - Line 66

**File**: `BCM.LDMST.SELECT.RTN.b`

**Routine**: `BCM.LDMST.SELECT.RTN` (Unknown)

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS NE UNAUTH
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS NE UNAUTH
```

**Table**: `AA.ARRANGEMENT`

**Fields** (2):
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ARR_STATUS != 'UNAUTH'
```

---

#### SELECT #575 - Line 75

**File**: `BCM.POST.MON.FILE.b`

**Routine**: `BCM.POST.MON.FILE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>}
```

**SIMULATED AT RUNTIME**:
```
SELECT {R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>}
```

**Table**: `R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/R.DFE.PARAMETER<EB.Utility.DfeParameter.DfeParamArchiveDir>

**Translated SQL**:
```sql
SELECT *
FROM R_DFE_PARAMETER<EB_Utility_DfeParameter_DfeParamArchiveDir>
```

---

#### SELECT #576 - Line 45

**File**: `BPA.ATOM.GL.ACCOUNT.PRE.b`

**Routine**: `BPA.ATOM.GL.ACCOUNT.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.RE.STAT.REP.LINE WITH TYPE EQ DETAIL AND ASSET1 NE '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.RE.STAT.REP.LINE WITH TYPE EQ DETAIL AND ASSET1 NE '' 
```

**Table**: `RE.STAT.REP.LINE`

**Fields** (2):
-  `ASSET1`  Type: D
-  `TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ASSET1' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_REP_LINE
WHERE TYPE = 'DETAIL'
```

---

#### SELECT #577 - Line 39

**File**: `BPA.B.ATOM.GL.ACCOUNT.SELECT.b`

**Routine**: `BPA.B.ATOM.GL.ACCOUNT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT RE.STAT.REP.LINE WITH TYPE EQ DETAIL AND ASSET1 NE '' AND DESC LIKE 8... 
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.STAT.REP.LINE WITH TYPE EQ DETAIL AND ASSET1 NE '' AND DESC LIKE 8... 
```

**Table**: `RE.STAT.REP.LINE`

**Fields** (3):
-  `ASSET1`  Type: D
-  `TYPE`  Type: D
-  `DESC`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ASSET1' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'DESC' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_REP_LINE
WHERE TYPE = 'DETAIL' AND DESC LIKE '8%'
```

---

#### SELECT #578 - Line 59

**File**: `BPA.B.EXTRACT.CLIENTE.SELECT.b`

**Routine**: `BPA.B.EXTRACT.CLIENTE.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {FN.GENERICO}
```

**SIMULATED AT RUNTIME**:
```
SELECT GENERICO
```

**Table**: `GENERICO`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'GENERICO' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/GENERICO
-   Unresolved variables: FN.GENERICO

**Translated SQL**:
```sql
SELECT *
FROM GENERICO
```

---

#### SELECT #579 - Line 40

**File**: `BPA.B.EXTRACT.HSBACMST.PRE.b`

**Routine**: `BPA.B.EXTRACT.HSBACMST.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED OR CHQ.STATUS EQ CLEARING
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CHQ.STATUS EQ DEPOSITED OR CHQ.STATUS EQ CLEARING
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (1):
-  `CHQ.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CHQ_STATUS = 'DEPOSITED'
```

---

#### SELECT #580 - Line 37

**File**: `BPA.B.EXTRACT.HSBACMST.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBACMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH START.DATE LE {EB.SystemTables.getRDates(EB.Utility.Dates.DatLastWorkingDay)}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH START.DATE LE RDATES
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `START.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE START_DATE <= 'RDATES'
```

---

#### SELECT #581 - Line 58

**File**: `BPA.B.EXTRACT.HSBAPCLS.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBAPCLS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT RE.STAT.REP.LINE
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.STAT.REP.LINE
```

**Table**: `RE.STAT.REP.LINE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_REP_LINE
```

---

#### SELECT #582 - Line 39

**File**: `BPA.B.EXTRACT.HSBAUDIT.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBAUDIT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TELLER$HIS WITH RECORD.STATUS EQ MAT AND VALUE.DATE.1 EQ {EB.SystemTables.getRDates(EB.Utility.Dates.DatLastWorkingDay)}
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER$HIS WITH RECORD.STATUS EQ MAT AND VALUE.DATE.1 EQ RDATES
```

**Table**: `TELLER$HIS`

**Fields** (2):
-  `RECORD.STATUS`  Type: D
-  `VALUE.DATE.1`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'TELLER'

**Translated SQL**:
```sql
SELECT *
FROM TELLER$HIS
WHERE RECORD_STATUS = 'MAT' AND VALUE_DATE_1 = 'RDATES'
```

---

#### SELECT #583 - Line 62

**File**: `BPA.B.EXTRACT.HSBCPBRL.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBCPBRL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT MD.DEAL
```

**SIMULATED AT RUNTIME**:
```
SELECT MD.DEAL
```

**Table**: `MD.DEAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM MD_DEAL
```

---

#### SELECT #584 - Line 36

**File**: `BPA.B.EXTRACT.HSBCUMST.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBCUMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT CUSTOMER
```

**SIMULATED AT RUNTIME**:
```
SELECT CUSTOMER
```

**Table**: `CUSTOMER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
```

---

#### SELECT #585 - Line 46

**File**: `BPA.B.EXTRACT.HSBDEALC.PRE.b`

**Routine**: `BPA.B.EXTRACT.HSBDEALC.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS
```

**Table**: `AC.LOCKED.EVENTS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
```

---

#### SELECT #586 - Line 40

**File**: `BPA.B.EXTRACT.HSBDEALC.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBDEALC.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #587 - Line 54

**File**: `BPA.B.EXTRACT.HSBDEALS.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBDEALS.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH START.DATE LE {EB.SystemTables.getRDates(EB.Utility.Dates.DatLastWorkingDay)}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH START.DATE LE RDATES
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `START.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE START_DATE <= 'RDATES'
```

---

#### SELECT #588 - Line 106

**File**: `BPA.B.EXTRACT.HSBEJECUTOR.LOAD.b`

**Routine**: `BPA.B.EXTRACT.HSBEJECUTOR.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD.B`

**AS PER CODE**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ CUS.LEGAL.DOC.NAME
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.LOOKUP WITH VIRTUAL.TABLE EQ CUS.LEGAL.DOC.NAME
```

**Table**: `EB.LOOKUP`

**Fields** (1):
-  `VIRTUAL.TABLE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_LOOKUP
WHERE VIRTUAL_TABLE = 'CUS.LEGAL.DOC.NAME'
```

---

#### SELECT #589 - Line 52

**File**: `BPA.B.EXTRACT.HSBEJECUTOR.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBEJECUTOR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT TELLER$HIS WITH RECORD.STATUS EQ MAT AND VALUE.DATE.1 EQ {EB.SystemTables.getRDates(EB.Utility.Dates.DatLastWorkingDay)}
```

**SIMULATED AT RUNTIME**:
```
SELECT TELLER$HIS WITH RECORD.STATUS EQ MAT AND VALUE.DATE.1 EQ RDATES
```

**Table**: `TELLER$HIS`

**Fields** (2):
-  `RECORD.STATUS`  Type: D
-  `VALUE.DATE.1`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'TELLER'

**Translated SQL**:
```sql
SELECT *
FROM TELLER$HIS
WHERE RECORD_STATUS = 'MAT' AND VALUE_DATE_1 = 'RDATES'
```

---

#### SELECT #590 - Line 48

**File**: `BPA.B.EXTRACT.HSBGARANT.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBGARANT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT COLLATERAL
```

**Table**: `COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
```

---

#### SELECT #591 - Line 37

**File**: `BPA.B.EXTRACT.HSBLCMST.PRE.b`

**Routine**: `BPA.B.EXTRACT.HSBLCMST.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CUSTOMER.RELATIONSHIP
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER.RELATIONSHIP
```

**Table**: `CUSTOMER.RELATIONSHIP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER_RELATIONSHIP
```

---

#### SELECT #592 - Line 44

**File**: `BPA.B.EXTRACT.HSBLCMST.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBLCMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT MD.DEAL
```

**SIMULATED AT RUNTIME**:
```
SELECT MD.DEAL
```

**Table**: `MD.DEAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM MD_DEAL
```

---

#### SELECT #593 - Line 54

**File**: `BPA.B.EXTRACT.HSBLCMST.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBLCMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LETTER.OF.CREDIT
```

**SIMULATED AT RUNTIME**:
```
SELECT LETTER.OF.CREDIT
```

**Table**: `LETTER.OF.CREDIT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LETTER_OF_CREDIT
```

---

#### SELECT #594 - Line 47

**File**: `BPA.B.EXTRACT.HSBLNECR.PRE.b`

**Routine**: `BPA.B.EXTRACT.HSBLNECR.PRE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LIMIT WITH RECORD.PARENT NE '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LIMIT WITH RECORD.PARENT NE '' 
```

**Table**: `BAN.CONCAT.LIMIT`

**Fields** (1):
-  `RECORD.PARENT`  Type: Unknown

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_CONCAT_LIMIT
```

---

#### SELECT #595 - Line 32

**File**: `BPA.B.EXTRACT.HSBLNECR.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBLNECR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LIMIT WITH RECORD.PARENT NE '' 
```

**SIMULATED AT RUNTIME**:
```
SELECT LIMIT WITH RECORD.PARENT NE '' 
```

**Table**: `LIMIT`

**Fields** (1):
-  `RECORD.PARENT`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM LIMIT
```

---

#### SELECT #596 - Line 62

**File**: `BPA.B.EXTRACT.HSBLNECR.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBLNECR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LIMIT
```

**SIMULATED AT RUNTIME**:
```
SELECT LIMIT
```

**Table**: `LIMIT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LIMIT
```

---

#### SELECT #597 - Line 85

**File**: `BPA.B.EXTRACT.HSBOFMST.LOAD.b`

**Routine**: `BPA.B.EXTRACT.HSBOFMST.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CURRENCY
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CURRENCY
```

**Table**: `CURRENCY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CURRENCY
```

---

#### SELECT #598 - Line 44

**File**: `BPA.B.EXTRACT.HSBOFMST.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBOFMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FUNDS.TRANSFER WITH TRANSACTION.TYPE LIKE AC... AND DEBIT.ACCT.NO UNLIKE {LCCY.LIST}
```

**SIMULATED AT RUNTIME**:
```
SELECT FUNDS.TRANSFER WITH TRANSACTION.TYPE LIKE AC... AND DEBIT.ACCT.NO UNLIKE SAMPLE_VALUE
```

**Table**: `FUNDS.TRANSFER`

**Fields** (1):
-  `TRANSACTION.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: LCCY.LIST

**Translated SQL**:
```sql
SELECT *
FROM FUNDS_TRANSFER
WHERE TRANSACTION_TYPE LIKE 'AC%' AND DEBIT_ACCT_NO NOT LIKE '%SAMPLE_VALUE%'
```

---

#### SELECT #599 - Line 46

**File**: `BPA.B.EXTRACT.HSBOINACTIVOS.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBOINACTIVOS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT ACCT.ENT.TODAY
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCT.ENT.TODAY
```

**Table**: `ACCT.ENT.TODAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCT_ENT_TODAY
```

---

#### SELECT #600 - Line 49

**File**: `BPA.B.EXTRACT.HSBPLANV.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBPLANV.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #601 - Line 36

**File**: `BPA.B.EXTRACT.HSBPLMST.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBPLMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT MD.DEAL
```

**SIMULATED AT RUNTIME**:
```
SELECT MD.DEAL
```

**Table**: `MD.DEAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM MD_DEAL
```

---

#### SELECT #602 - Line 49

**File**: `BPA.B.EXTRACT.HSBRCOLL.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBRCOLL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT COLLATERAL
```

**SIMULATED AT RUNTIME**:
```
SELECT COLLATERAL
```

**Table**: `COLLATERAL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
```

---

#### SELECT #603 - Line 46

**File**: `BPA.B.EXTRACT.HSBTITULARES.SELECT.b`

**Routine**: `BPA.B.EXTRACT.HSBTITULARES.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #604 - Line 52

**File**: `BPA.B.EXTRACT.REFERE.SELECT.b`

**Routine**: `BPA.B.EXTRACT.REFERE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING AND (ARR.STATUS NE AUTH AND ARR.STATUS NE UNAUTH) AND START.DATE LE {Y.LAST.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ LENDING AND (ARR.STATUS NE AUTH AND ARR.STATUS NE UNAUTH) AND START.DATE LE VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (3):
-  `START.DATE`  Type: D
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LAST.DAY

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING' AND ARR_STATUS != 'UNAUTH)' AND START_DATE <= 'VALUE123'
```

---

#### SELECT #605 - Line 37

**File**: `BAPA.B.CLEAR.LOG.AD.b`

**Routine**: `BAPA.B.CLEAR.LOG.AD` (BATCH (inferred))

**Variable**: `SEL.ARR`

**AS PER CODE**:
```
SELECT F.EB.BAPA.AA.LOG.ERRS.API.BUS WITH DATE LE {Y.TODAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.AA.LOG.ERRS.API.BUS WITH DATE LE VALUE123
```

**Table**: `EB.BAPA.AA.LOG.ERRS.API.BUS`

**Fields** (1):
-  `DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_AA_LOG_ERRS_API_BUS
WHERE DATE <= 'VALUE123'
```

---

#### SELECT #606 - Line 42

**File**: `BAPA.B.REACT.INACTIVE.ACCT.SELECT.b`

**Routine**: `BAPA.B.REACT.INACTIVE.ACCT.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.CMDD`

**AS PER CODE**:
```
SELECT {F.IN.DIR}
```

**SIMULATED AT RUNTIME**:
```
SELECT IN.DIR
```

**Table**: `IN.DIR`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'IN.DIR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/IN.DIR
-   Unresolved variables: F.IN.DIR

**Translated SQL**:
```sql
SELECT *
FROM IN_DIR
```

---

#### SELECT #607 - Line 99

**File**: `BAPA.V.AC.SIMPLIFI.b`

**Routine**: `BAPA.V.AC.SIMPLIFI` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ {Y.CUSTOMER.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH CUSTOMER EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `CUSTOMER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CUSTOMER' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CUSTOMER.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE CUSTOMER = 'VALUE123'
```

---

#### SELECT #608 - Line 23

**File**: `BAPA.B.DEL.ACH.C.CERR.SELECT.b`

**Routine**: `BAPA.B.DEL.ACH.C.CERR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT LATAM.ACH.DD.MANDATE
```

**SIMULATED AT RUNTIME**:
```
SELECT LATAM.ACH.DD.MANDATE
```

**Table**: `LATAM.ACH.DD.MANDATE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_DD_MANDATE
```

---

#### SELECT #609 - Line 25

**File**: `BAPA.B.FT.PENDIENT.ACC.VAL.SELECT.b`

**Routine**: `BAPA.B.FT.PENDIENT.ACC.VAL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FBNK.EB.BAPA.ACH.PRES.CAST WITH STATUS EQ PEVA
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.EB.BAPA.ACH.PRES.CAST WITH STATUS EQ PEVA
```

**Table**: `FBNK.EB.BAPA.ACH.PRES.CAST`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'EB.BAPA.ACH.PRES.CAST'

**Translated SQL**:
```sql
SELECT *
FROM FBNK_EB_BAPA_ACH_PRES_CAST
WHERE STATUS = 'PEVA'
```

---

#### SELECT #610 - Line 33

**File**: `BAPA.E.LATAM.ACH.DD.MAN.REVE.b`

**Routine**: `BAPA.E.LATAM.ACH.DD.MAN.REVE` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.LATAM.ACH.DD.MANDATE$HIS WITH DATE.TIME GE {Y.STAMP.FIN} AND RECORD.STATUS EQ REVE AND INPUTTER LK ...{Y.OFS}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.LATAM.ACH.DD.MANDATE$HIS WITH DATE.TIME GE VALUE123 AND RECORD.STATUS EQ REVE AND INPUTTER LK ...LATAM.ACH...
```

**Table**: `LATAM.ACH.DD.MANDATE$HIS`

**Fields** (2):
-  `RECORD.STATUS`  Type: D
-  `DATE.TIME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'LATAM.ACH.DD.MANDATE'
-   Unresolved variables: Y.STAMP.FIN

**Translated SQL**:
```sql
SELECT *
FROM LATAM_ACH_DD_MANDATE$HIS
WHERE DATE_TIME >= 'VALUE123' AND RECORD_STATUS = 'REVE'
```

---

#### SELECT #611 - Line 35

**File**: `BAPA.ENQ.FT.PAPR.ACH.PAPR.b`

**Routine**: `BAPA.ENQ.FT.PAPR.ACH.PAPR` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE {Y.STAMP.FIN} AND STATUS EQ PAPR OR STATUS EQ PAFA
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE VALUE123 AND STATUS EQ PAPR OR STATUS EQ PAFA
```

**Table**: `EB.BAPA.ACH.PRES.CAST`

**Fields** (2):
-  `STATUS`  Type: D
-  `DATE.TIME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.STAMP.FIN

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_ACH_PRES_CAST
WHERE DATE_TIME >= 'VALUE123' AND STATUS = 'PAPR'
```

---

#### SELECT #612 - Line 35

**File**: `BAPA.ENQ.FT.PAPR.ACH.PEND.b`

**Routine**: `BAPA.ENQ.FT.PAPR.ACH.PEND` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE {Y.STAMP.FIN} AND STATUS EQ DEPR OR STATUS EQ REOP
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE VALUE123 AND STATUS EQ DEPR OR STATUS EQ REOP
```

**Table**: `EB.BAPA.ACH.PRES.CAST`

**Fields** (2):
-  `STATUS`  Type: D
-  `DATE.TIME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.STAMP.FIN

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_ACH_PRES_CAST
WHERE DATE_TIME >= 'VALUE123' AND STATUS = 'DEPR'
```

---

#### SELECT #613 - Line 35

**File**: `BAPA.ENQ.FT.PAPR.ACH.PEVA.b`

**Routine**: `BAPA.ENQ.FT.PAPR.ACH.PEVA` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE {Y.STAMP.FIN} AND STATUS EQ PEVA
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.ACH.PRES.CAST WITH DATE.TIME GE VALUE123 AND STATUS EQ PEVA
```

**Table**: `EB.BAPA.ACH.PRES.CAST`

**Fields** (2):
-  `STATUS`  Type: D
-  `DATE.TIME`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE.TIME' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.STAMP.FIN

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_ACH_PRES_CAST
WHERE DATE_TIME >= 'VALUE123' AND STATUS = 'PEVA'
```

---

#### SELECT #614 - Line 74

**File**: `BAN.B.DEL.LOG.OFFPRINCIPAL.b`

**Routine**: `BAN.B.DEL.LOG.OFFPRINCIPAL` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT
```

**Table**: `EB.BPA.LOG.OFFPRINCIPALINT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BPA_LOG_OFFPRINCIPALINT
```

---

#### SELECT #615 - Line 103

**File**: `BAN.B.DEL.LOG.OFFPRINCIPAL.b`

**Routine**: `BAN.B.DEL.LOG.OFFPRINCIPAL` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH DATE LE {Y.YEAR}{Y.MES.AUX}{Y.DIAS}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH DATE LE VALUE123VALUE123VALUE123
```

**Table**: `EB.BPA.LOG.OFFPRINCIPALINT`

**Fields** (1):
-  `DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'DATE' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.YEAR, Y.MES.AUX, Y.DIAS

**Translated SQL**:
```sql
SELECT *
FROM EB_BPA_LOG_OFFPRINCIPALINT
WHERE DATE <= 'VALUE123VALUE123VALUE123'
```

---

#### SELECT #616 - Line 44

**File**: `BAN.B.RR.ADJUST.OFFPRINCIPAL.SELECT.b`

**Routine**: `BAN.B.RR.ADJUST.OFFPRINCIPAL.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {BAPAAA.Framework.getFnStBapaSuspendEntries(1)}
```

**SIMULATED AT RUNTIME**:
```
SELECT ST.BAPA.SUSPEND.ENTRIES
```

**Table**: `ST.BAPA.SUSPEND.ENTRIES`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ST_BAPA_SUSPEND_ENTRIES
```

---

#### SELECT #617 - Line 56

**File**: `BAN.B.WRITE.LOG.OFFPRINCIPAL.b`

**Routine**: `BAN.B.WRITE.LOG.OFFPRINCIPAL` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH @ID LIKE TEM-SUS-...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH @ID LIKE TEM-SUS-...
```

**Table**: `EB.BPA.LOG.OFFPRINCIPALINT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BPA_LOG_OFFPRINCIPALINT
WHERE ID LIKE 'TEM-SUS-%'
```

---

#### SELECT #618 - Line 66

**File**: `BAN.B.WRITE.LOG.OFFPRINCIPAL.b`

**Routine**: `BAN.B.WRITE.LOG.OFFPRINCIPAL` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH @ID LIKE TEM-PAY-...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BPA.LOG.OFFPRINCIPALINT WITH @ID LIKE TEM-PAY-...
```

**Table**: `EB.BPA.LOG.OFFPRINCIPALINT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BPA_LOG_OFFPRINCIPALINT
WHERE ID LIKE 'TEM-PAY-%'
```

---

#### SELECT #619 - Line 46

**File**: `BAPA.AA.CHAN.PROD.PLEDGE.b`

**Routine**: `BAPA.AA.CHAN.PROD.PLEDGE` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARR.ACCOUNT WITH @ID LIKE {Y.ARR}-BALANCE-... BY-DSND @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.ACCOUNT WITH @ID LIKE VALUE123-BALANCE-... BY-DSND @ID
```

**Table**: `AA.ARR.ACCOUNT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ARR

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_ACCOUNT
WHERE ID LIKE 'VALUE123-BALANCE-%'
ORDER BY ID DESC
```

---

#### SELECT #620 - Line 42

**File**: `BAPA.AA.MAN.GRACE.DATE.b`

**Routine**: `BAPA.AA.MAN.GRACE.DATE` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE {Y.ARR}-MINBALFEE-... BY-DSND @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE VALUE123-MINBALFEE-... BY-DSND @ID
```

**Table**: `AA.ARR.CHARGE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ARR

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_CHARGE
WHERE ID LIKE 'VALUE123-MINBALFEE-%'
ORDER BY ID DESC
```

---

#### SELECT #621 - Line 41

**File**: `BAPA.B.CHG.UPD.SELECT.b`

**Routine**: `BAPA.B.CHG.UPD.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.TEMP.BILL.REPORT WITH BILL.DATE NE {Y.TODAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.TEMP.BILL.REPORT WITH BILL.DATE NE VALUE123
```

**Table**: `EB.BAPA.TEMP.BILL.REPORT`

**Fields** (1):
-  `BILL.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_TEMP_BILL_REPORT
WHERE BILL_DATE != 'VALUE123'
```

---

#### SELECT #622 - Line 34

**File**: `BAPA.B.UPD.DAILY.CH.AMT.SELECT.b`

**Routine**: `BAPA.B.UPD.DAILY.CH.AMT.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT EB.BAPA.LOANS.AMORT.DETAILS WITH EXPIRY.DATE NE '' AND EXPIRY.DATE GT '{EB.SystemTables.getToday()}'
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.LOANS.AMORT.DETAILS WITH EXPIRY.DATE NE '' AND EXPIRY.DATE GT 'TODAY'
```

**Table**: `EB.BAPA.LOANS.AMORT.DETAILS`

**Fields** (1):
-  `EXPIRY.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_LOANS_AMORT_DETAILS
WHERE EXPIRY_DATE > 'TODAY'
```

---

#### SELECT #623 - Line 32

**File**: `BAPA.B.UPD.FT.ADJ.SELECT.b`

**Routine**: `BAPA.B.UPD.FT.ADJ.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BAPA.TEMP.AUTOM.COM WITH STATUS EQ {Y.DATA}
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.TEMP.AUTOM.COM WITH STATUS EQ 20231210
```

**Table**: `EB.BAPA.TEMP.AUTOM.COM`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATA

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_TEMP_AUTOM_COM
WHERE STATUS = '20231210'
```

---

#### SELECT #624 - Line 40

**File**: `BAPA.E.NOF.AA.PRIN.UPD.b`

**Routine**: `BAPA.E.NOF.AA.PRIN.UPD` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BAPA.REPORT.AUTOM.COM WITH ARRANGEMENT.ID EQ {EB.Reports.getDRangeAndValue()<POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.REPORT.AUTOM.COM WITH ARRANGEMENT.ID EQ {EB.Reports.getDRangeAndValue()<POS>}
```

**Table**: `EB.BAPA.REPORT.AUTOM.COM`

**Fields** (1):
-  `ARRANGEMENT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_REPORT_AUTOM_COM
WHERE ARRANGEMENT_ID = '{EB.Reports.getDRangeAndValue()<POS>}'
```

---

#### SELECT #625 - Line 67

**File**: `BAPA.E.NOF.REEST.UPD.b`

**Routine**: `BAPA.E.NOF.REEST.UPD` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BAPA.UPD.REEST.REPORT WITH DATE EQ {Y.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BAPA.UPD.REEST.REPORT WITH DATE EQ VALUE123
```

**Table**: `EB.BAPA.UPD.REEST.REPORT`

**Fields** (1):
-  `DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATE

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_UPD_REEST_REPORT
WHERE DATE = 'VALUE123'
```

---

#### SELECT #626 - Line 26

**File**: `BAN.CUADRO.DEL.ACCT.CLOSED.SELECT.b`

**Routine**: `BAN.CUADRO.DEL.ACCT.CLOSED.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ {LAST.WORKING.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ SAMPLE_VALUE
```

**Table**: `ACCOUNT.CLOSED`

**Fields** (1):
-  `ACCT.CLOSE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: LAST.WORKING.DAY

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_CLOSED
WHERE ACCT_CLOSE_DATE = 'SAMPLE_VALUE'
```

---

#### SELECT #627 - Line 26

**File**: `BAN.CUADRO.DPF.DEL.ACCT.CLOSED.SELECT.b`

**Routine**: `BAN.CUADRO.DPF.DEL.ACCT.CLOSED.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ {LAST.WORKING.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ SAMPLE_VALUE
```

**Table**: `ACCOUNT.CLOSED`

**Fields** (1):
-  `ACCT.CLOSE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: LAST.WORKING.DAY

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_CLOSED
WHERE ACCT_CLOSE_DATE = 'SAMPLE_VALUE'
```

---

#### SELECT #628 - Line 70

**File**: `BAN.CUADRO.DPF.POST.b`

**Routine**: `BAN.CUADRO.DPF.POST` (BATCH (inferred))

**Variable**: `SELECT.CUADRO.LIST`

**AS PER CODE**:
```
SELECT F.BAN.CUADRO.DPF.LIST BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CUADRO.DPF.LIST BY @ID
```

**Table**: `BAN.CUADRO.DPF.LIST`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BAN.CUADRO.DPF.LIST' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BAN.CUADRO.DPF.LIST

**Translated SQL**:
```sql
SELECT *
FROM BAN_CUADRO_DPF_LIST
ORDER BY ID ASC
```

---

#### SELECT #629 - Line 28

**File**: `BAN.CUADRO.DPF.SELECT.b`

**Routine**: `BAN.CUADRO.DPF.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'DEPOSITS'
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'DEPOSITS'
```

**Table**: `AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'DEPOSITS'
```

---

#### SELECT #630 - Line 29

**File**: `BAN.CUADRO.SELECT.b`

**Routine**: `BAN.CUADRO.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'LENDING'
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'LENDING'
```

**Table**: `AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING'
```

---

#### SELECT #631 - Line 152

**File**: `BAN.E.NOF.PREST.MOV.LOG.b`

**Routine**: `BAN.E.NOF.PREST.MOV.LOG` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD} WITH {CHANGE(SEL.CMD.FILTER, @FM, ' AND ')} BY FECHA.PROCESO WITH {CHANGE(SEL.CMD.FILTER, @FM, ' AND ')} BY FECHA.PROCESO
```

**SIMULATED AT RUNTIME**:
```
SELECT  WITH SAMPLE_VALUE BY FECHA.PROCESO WITH {CHANGE(SEL.CMD.FILTER, @FM, ' AND ')} BY FECHA.PROCESO WITH {CHANGE(SEL.CMD.FILTER, @FM, ' AND ')} BY FECHA.PROCESO
```

**Table**: `WITH`

**Fields** (1):
-  `FECHA.PROCESO`  Type: Unknown

**TAFJ Compatible**:  No

**Warnings**:
- Invalid operator: BY
-   WARNING: Dictionary not found for table 'WITH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/WITH
-   Unresolved variables: CHANGE(SEL.CMD.FILTER, @FM, ' AND '), SEL.CMD.FILTER

**Translated SQL**:
```sql
SELECT *
FROM WITH
ORDER BY FECHA_PROCESO ASC, FECHA_PROCESO ASC, FECHA_PROCESO ASC
```

---

#### SELECT #632 - Line 88

**File**: `BAPA.B.ADJ.LOAN.CURBALANCE.b`

**Routine**: `BAPA.B.ADJ.LOAN.CURBALANCE` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_88`

**AS PER CODE**:
```
SELECT FILE.PATH
```

**SIMULATED AT RUNTIME**:
```
SELECT FILE.PATH
```

**Table**: `FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM FILE_PATH
```

---

#### SELECT #633 - Line 52

**File**: `BAPA.B.ADJ.LOAN.CURBALANCE.SELECT.b`

**Routine**: `BAPA.B.ADJ.LOAN.CURBALANCE.SELECT` (BATCH (inferred))

**Variable**: `INTERNAL_SELECT_LINE_52`

**AS PER CODE**:
```
SELECT FILE.PATH
```

**SIMULATED AT RUNTIME**:
```
SELECT FILE.PATH
```

**Table**: `FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM FILE_PATH
```

---

#### SELECT #634 - Line 19

**File**: `BAPA.B.CAP.UPDATE.AAA.SELECT.b`

**Routine**: `BAPA.B.CAP.UPDATE.AAA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.L.TABLE`

**AS PER CODE**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**Table**: `EB.BAPA.L.CAP.TEMP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

#### SELECT #635 - Line 20

**File**: `BAPA.B.FT.UPDATE.AAA.SELECT.b`

**Routine**: `BAPA.B.FT.UPDATE.AAA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.L.TABLE`

**AS PER CODE**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**Table**: `EB.BAPA.L.CAP.TEMP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

#### SELECT #636 - Line 19

**File**: `BAPA.B.INFO.UPDATE.AAA.SELECT.b`

**Routine**: `BAPA.B.INFO.UPDATE.AAA.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.L.TABLE`

**AS PER CODE**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**Table**: `EB.BAPA.L.CAP.TEMP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

#### SELECT #637 - Line 19

**File**: `BAPA.B.REVERSE.CHARGE.SELECT.b`

**Routine**: `BAPA.B.REVERSE.CHARGE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.L.TABLE`

**AS PER CODE**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BAPA.L.CAP.TEMP
```

**Table**: `EB.BAPA.L.CAP.TEMP`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BAPA_L_CAP_TEMP
```

---

#### SELECT #638 - Line 24

**File**: `BAPA.B.UPD.LIMIT.ARR.SELECT.b`

**Routine**: `BAPA.B.UPD.LIMIT.ARR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAAAL.MigPrestamos.getFnCustomerArr()} WITH PRODUCT.LINE EQ LENDING
```

**SIMULATED AT RUNTIME**:
```
SELECT CUSTOMER.ARR WITH PRODUCT.LINE EQ LENDING
```

**Table**: `CUSTOMER.ARR`

**Fields** (1):
-  `PRODUCT.LINE`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'CUSTOMER.ARR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/CUSTOMER.ARR

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER_ARR
WHERE PRODUCT_LINE = 'LENDING'
```

---

#### SELECT #639 - Line 90

**File**: `BAPA.CANCEL.COLLATERAL.b`

**Routine**: `BAPA.CANCEL.COLLATERAL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.COLLATERAL WITH @ID LIKE {COLL.RIGHT.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.COLLATERAL WITH @ID LIKE SAMPLE_VALUE...
```

**Table**: `COLLATERAL`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
WHERE ID LIKE 'SAMPLE_VALUE%'
```

---

#### SELECT #640 - Line 252

**File**: `BAPA.CANCEL.COLLATERAL.b`

**Routine**: `BAPA.CANCEL.COLLATERAL` (Unknown)

**Variable**: `SEL.LOCKED.EVENTS.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH LT.TYPE.BLOCK EQ PIGN AND ACCOUNT.NUMBER EQ {DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH LT.TYPE.BLOCK EQ PIGN AND ACCOUNT.NUMBER EQ {DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (2):
-  `LT.TYPE.BLOCK`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.TYPE.BLOCK - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE LT_TYPE_BLOCK = 'PIGN' AND ACCOUNT_NUMBER = '{DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}'
```

---

#### SELECT #641 - Line 82

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.b`

**Routine**: `BAPA.DESVINC.GARANT.PEND.CLOSURE` (Unknown)

**Variable**: `SEL.CMD.LIM`

**AS PER CODE**:
```
SELECT LIMIT WITH @ID LIKE {Y.CUSTOMER}...
```

**SIMULATED AT RUNTIME**:
```
SELECT LIMIT WITH @ID LIKE VALUE123...
```

**Table**: `LIMIT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CUSTOMER

**Translated SQL**:
```sql
SELECT *
FROM LIMIT
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #642 - Line 93

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.b`

**Routine**: `BAPA.DESVINC.GARANT.PEND.CLOSURE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT COLLATERAL WITH @ID LIKE {COLL.RIGHT.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT COLLATERAL WITH @ID LIKE SAMPLE_VALUE...
```

**Table**: `COLLATERAL`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM COLLATERAL
WHERE ID LIKE 'SAMPLE_VALUE%'
```

---

#### SELECT #643 - Line 120

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.b`

**Routine**: `BAPA.DESVINC.GARANT.PEND.CLOSURE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ {ARRANGEMENT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ SAMPLE_VALUE
```

**Table**: `BAN.BANESCO.COLLATERAL`

**Fields** (1):
-  `LOAN.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LOAN.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: ARRANGEMENT.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
WHERE LOAN_ID = 'SAMPLE_VALUE'
```

---

#### SELECT #644 - Line 266

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.b`

**Routine**: `BAPA.DESVINC.GARANT.PEND.CLOSURE` (Unknown)

**Variable**: `SEL.LOCKED.EVENTS.CMD`

**AS PER CODE**:
```
SELECT AC.LOCKED.EVENTS WITH LT.TYPE.BLOCK EQ PIGN AND ACCOUNT.NUMBER EQ {DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

**SIMULATED AT RUNTIME**:
```
SELECT AC.LOCKED.EVENTS WITH LT.TYPE.BLOCK EQ PIGN AND ACCOUNT.NUMBER EQ {DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (2):
-  `LT.TYPE.BLOCK`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.TYPE.BLOCK - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE LT_TYPE_BLOCK = 'PIGN' AND ACCOUNT_NUMBER = '{DEPOSIT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}'
```

---

#### SELECT #645 - Line 20

**File**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.SELECT.b`

**Routine**: `BAPA.DESVINC.GARANT.PEND.CLOSURE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH ARR.STATUS EQ PENDING.CLOSURE
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH ARR.STATUS EQ PENDING.CLOSURE
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `ARR.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE ARR_STATUS = 'PENDING.CLOSURE'
```

---

#### SELECT #646 - Line 48

**File**: `BPA.B.ARC.DETAILS.SELECT.b`

**Routine**: `BPA.B.ARC.DETAILS.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BPA.PRT.PLAM.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.PRT.PLAM.DETAILS
```

**Table**: `BPA.PRT.PLAM.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_PRT_PLAM_DETAILS
```

---

#### SELECT #647 - Line 40

**File**: `BPA.B.ARC.SUMMARY.SELECT.b`

**Routine**: `BPA.B.ARC.SUMMARY.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BPA.PRT.PLAM.SUMMARY
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.PRT.PLAM.SUMMARY
```

**Table**: `BPA.PRT.PLAM.SUMMARY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_PRT_PLAM_SUMMARY
```

---

#### SELECT #648 - Line 40

**File**: `BPA.B.EMPAPROD.CLEAN.SELECT.b`

**Routine**: `BPA.B.EMPAPROD.CLEAN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAAAL.MigPrestamos.getFnBpaEmpaprodLog()} WITH FECHA.PROCESO LT {LIMIT.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.EMPAPROD.LOG WITH FECHA.PROCESO LT YMESESM
```

**Table**: `BPA.EMPAPROD.LOG`

**Fields** (1):
-  `FECHA.PROCESO`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_EMPAPROD_LOG
WHERE FECHA_PROCESO < 'YMESESM'
```

---

#### SELECT #649 - Line 39

**File**: `BPA.B.PREST.PLAM.PAYMENT.SELECT.b`

**Routine**: `BPA.B.PREST.PLAM.PAYMENT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD.SUM`

**AS PER CODE**:
```
SELECT BPA.PRT.PLAM.SUMMARY WITH STATUS EQ APROBADO RECHAZADO
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.PRT.PLAM.SUMMARY WITH STATUS EQ APROBADO RECHAZADO
```

**Table**: `BPA.PRT.PLAM.SUMMARY`

**Fields** (1):
-  `STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_PRT_PLAM_SUMMARY
WHERE STATUS = 'APROBADO'
```

---

#### SELECT #650 - Line 63

**File**: `BPA.B.PREST.PLAM.PAYMENT.SELECT.b`

**Routine**: `BPA.B.PREST.PLAM.PAYMENT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD} AND ENTIDAD LK {Y.ENTIDAD}... AND ENTIDAD LK {Y.ENTIDAD}...
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**Table**: `AND`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND
-   Unresolved variables: Y.ENTIDAD

**Translated SQL**:
```sql
SELECT *
FROM AND
```

---

#### SELECT #651 - Line 89

**File**: `BPA.BA.PRT.PLAM.UPL.LOTE.b`

**Routine**: `BPA.BA.PRT.PLAM.UPL.LOTE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD} AND ENTIDAD LK {Y.ENTIDAD}... AND ENTIDAD LK {Y.ENTIDAD}...
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**Table**: `AND`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND
-   Unresolved variables: Y.ENTIDAD

**Translated SQL**:
```sql
SELECT *
FROM AND
```

---

#### SELECT #652 - Line 94

**File**: `BPA.E.NOF.EMPAPROD.CRED.b`

**Routine**: `BPA.E.NOF.EMPAPROD.CRED` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.EMPAPROD.LOG WITH FILE.TYPE EQ CREDITO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.EMPAPROD.LOG WITH FILE.TYPE EQ CREDITO
```

**Table**: `BPA.EMPAPROD.LOG`

**Fields** (1):
-  `FILE.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_EMPAPROD_LOG
WHERE FILE_TYPE = 'CREDITO'
```

---

#### SELECT #653 - Line 94

**File**: `BPA.E.NOF.EMPAPROD.PAS.b`

**Routine**: `BPA.E.NOF.EMPAPROD.PAS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.EMPAPROD.LOG WITH FILE.TYPE EQ PASIVO
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.EMPAPROD.LOG WITH FILE.TYPE EQ PASIVO
```

**Table**: `BPA.EMPAPROD.LOG`

**Fields** (1):
-  `FILE.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_EMPAPROD_LOG
WHERE FILE_TYPE = 'PASIVO'
```

---

#### SELECT #654 - Line 98

**File**: `BPA.E.NOF.PAYMENT.DETAILS.b`

**Routine**: `BPA.E.NOF.PAYMENT.DETAILS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD} AND ENTIDAD LK {Y.ENTITY}... AND ENTIDAD LK {Y.ENTITY}...
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**Table**: `AND`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND
-   Unresolved variables: Y.ENTITY

**Translated SQL**:
```sql
SELECT *
FROM AND
```

---

#### SELECT #655 - Line 89

**File**: `BPA.E.NOF.PAYMENT.DETAILS.HIST.b`

**Routine**: `BPA.E.NOF.PAYMENT.DETAILS.HIST` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD} AND ENTIDAD LK {Y.ENTITY}... AND ENTIDAD LK {Y.ENTITY}...
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**Table**: `AND`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND
-   Unresolved variables: Y.ENTITY

**Translated SQL**:
```sql
SELECT *
FROM AND
```

---

#### SELECT #656 - Line 51

**File**: `BPA.PREST.PAGOMOV.REPORT.SELECT.b`

**Routine**: `BPA.PREST.PAGOMOV.REPORT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.PREST.FILE.UPLOAD WITH ESTADO EQ AUTORIZADO
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.PREST.FILE.UPLOAD WITH ESTADO EQ AUTORIZADO
```

**Table**: `BPA.PREST.FILE.UPLOAD`

**Fields** (1):
-  `ESTADO`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_PREST_FILE_UPLOAD
WHERE ESTADO = 'AUTORIZADO'
```

---

#### SELECT #657 - Line 65

**File**: `BPA.S.GET.CHQ.TYPE.b`

**Routine**: `BPA.S.GET.CHQ.TYPE` (SUBROUTINE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH ACCOUNT.NO EQ {Y.LINKED.APPL.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH ACCOUNT.NO EQ VALUE123
```

**Table**: `CHEQUE.ISSUE`

**Fields** (1):
-  `ACCOUNT.NO`  Type: I-PHYSICAL.REF

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: ACCOUNT.NO - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.LINKED.APPL.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE ACCOUNT_NO = 'VALUE123'
```

---

#### SELECT #658 - Line 70

**File**: `BPA.S.GET.COD.OFFICE.b`

**Routine**: `BPA.S.GET.COD.OFFICE` (SUBROUTINE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LK {Y.LINKED.APPL.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LK VALUE123
```

**Table**: `CHEQUE.ISSUE`

**TAFJ Compatible**:  No

**Warnings**:
- Invalid operator: LK
-   Unresolved variables: Y.LINKED.APPL.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
```

---

#### SELECT #659 - Line 60

**File**: `BPA.S.GET.EFFECTIVE.DATE.b`

**Routine**: `BPA.S.GET.EFFECTIVE.DATE` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `LINKED.APPL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE LINKED_APPL_ID = 'VALUE123'
```

---

#### SELECT #660 - Line 53

**File**: `BPA.S.GET.ID.GROUP.b`

**Routine**: `BPA.S.GET.ID.GROUP` (SUBROUTINE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CUSTOMER.REL.GROUP WITH CUSTOMER.NO EQ {Y.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER.REL.GROUP WITH CUSTOMER.NO EQ 12345
```

**Table**: `CUSTOMER.REL.GROUP`

**Fields** (1):
-  `CUSTOMER.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER_REL_GROUP
WHERE CUSTOMER_NO = '12345'
```

---

#### SELECT #661 - Line 85

**File**: `BPA.S.GET.MOBILIZATION.b`

**Routine**: `BPA.S.GET.MOBILIZATION` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `LINKED.APPL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE LINKED_APPL_ID = 'VALUE123'
```

---

#### SELECT #662 - Line 69

**File**: `BPA.S.GET.NO.CHQ.BOOK.b`

**Routine**: `BPA.S.GET.NO.CHQ.BOOK` (SUBROUTINE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LK {Y.LINKED.APPL.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LK VALUE123
```

**Table**: `CHEQUE.ISSUE`

**TAFJ Compatible**:  No

**Warnings**:
- Invalid operator: LK
-   Unresolved variables: Y.LINKED.APPL.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
```

---

#### SELECT #663 - Line 85

**File**: `BPA.S.GET.ST.ACCT.b`

**Routine**: `BPA.S.GET.ST.ACCT` (SUBROUTINE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARRANGEMENT WITH LINKED.APPL.ID EQ VALUE123
```

**Table**: `AA.ARRANGEMENT`

**Fields** (1):
-  `LINKED.APPL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LINKED.APPL.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE LINKED_APPL_ID = 'VALUE123'
```

---

#### SELECT #664 - Line 70

**File**: `BPA.V.GET.PAYMENT.INFO.b`

**Routine**: `BPA.V.GET.PAYMENT.INFO` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD} AND ENTIDAD LK {Y.ENTIDAD}... AND ENTIDAD LK {Y.ENTIDAD}...
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123... AND ENTIDAD LK VALUE123...
```

**Table**: `AND`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND
-   Unresolved variables: Y.ENTIDAD

**Translated SQL**:
```sql
SELECT *
FROM AND
```

---

#### SELECT #665 - Line 166

**File**: `BAN.A.AA.UPDATE.AC.SETTLE.b`

**Routine**: `BAN.A.AA.UPDATE.AC.SETTLE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.PENDING.BILL.AC WITH ARR.ACCT.NO EQ {Y.CUENTA}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PENDING.BILL.AC WITH ARR.ACCT.NO EQ VALUE123
```

**Table**: `BAN.PENDING.BILL.AC`

**Fields** (1):
-  `ARR.ACCT.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ARR.ACCT.NO' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CUENTA

**Translated SQL**:
```sql
SELECT *
FROM BAN_PENDING_BILL_AC
WHERE ARR_ACCT_NO = 'VALUE123'
```

---

#### SELECT #666 - Line 69

**File**: `BAN.A.ACCOUNT.CLOSURE.b`

**Routine**: `BAN.A.ACCOUNT.CLOSURE` (Unknown)

**Variable**: `SEL.BAN`

**AS PER CODE**:
```
SELECT F.BAN.COMM.PENDING WITH @ID LIKE {Y.ACT.ID}....
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.COMM.PENDING WITH @ID LIKE VALUE123....
```

**Table**: `BAN.COMM.PENDING`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACT.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PENDING
WHERE ID LIKE 'VALUE123%.'
```

---

#### SELECT #667 - Line 57

**File**: `BAN.B.COMM.PEND.PAYMENT.b`

**Routine**: `BAN.B.COMM.PEND.PAYMENT` (BATCH (inferred))

**Variable**: `SEL.BAN`

**AS PER CODE**:
```
SELECT BAN.COMM.PENDING WITH @ID LIKE {Y.ACCT}.... BY COMM.DATE.LIMIT
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.COMM.PENDING WITH @ID LIKE VALUE123.... BY COMM.DATE.LIMIT
```

**Table**: `BAN.COMM.PENDING`

**Fields** (2):
-  `@ID`  Type: D
-  `COMM.DATE.LIMIT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCT

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PENDING
WHERE ID LIKE 'VALUE123%.'
ORDER BY COMM_DATE_LIMIT ASC
```

---

#### SELECT #668 - Line 39

**File**: `BAN.B.COMM.PEND.PAYMENT.SELECT.b`

**Routine**: `BAN.B.COMM.PEND.PAYMENT.SELECT` (BATCH (inferred))

**Variable**: `SEL.BAN`

**AS PER CODE**:
```
SELECT BAN.COMM.PENDING BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.COMM.PENDING BY @ID
```

**Table**: `BAN.COMM.PENDING`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PENDING
ORDER BY ID ASC
```

---

#### SELECT #669 - Line 86

**File**: `BAN.BA.COMM.PEND.REVE.b`

**Routine**: `BAN.BA.COMM.PEND.REVE` (Unknown)

**Variable**: `SEL.STMT`

**AS PER CODE**:
```
SELECT F.BAN.COMM.PENDING WITH @ID LIKE {Y.CTA.ALT}... AND TXN.REFERENCE EQ {Y.ID.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.COMM.PENDING WITH @ID LIKE VALUE123... AND TXN.REFERENCE EQ VALUE123
```

**Table**: `BAN.COMM.PENDING`

**Fields** (2):
-  `TXN.REFERENCE`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CTA.ALT, Y.ID.REF

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PENDING
WHERE ID LIKE 'VALUE123%' AND TXN_REFERENCE = 'VALUE123'
```

---

#### SELECT #670 - Line 314

**File**: `BAN.I.CAL.VAL.COMM.PEND.b`

**Routine**: `BAN.I.CAL.VAL.COMM.PEND` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.COMM.PENDING WITH @ID LIKE {Y.CCT.ID}.... BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.COMM.PENDING WITH @ID LIKE VALUE123.... BY @ID
```

**Table**: `BAN.COMM.PENDING`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CCT.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PENDING
WHERE ID LIKE 'VALUE123%.'
ORDER BY ID ASC
```

---

#### SELECT #671 - Line 318

**File**: `BAN.I.CAL.VAL.COMM.PEND.b`

**Routine**: `BAN.I.CAL.VAL.COMM.PEND` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.COMM.PEND.EXPIRED WITH @ID LIKE {Y.CCT.ID}.... BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.COMM.PEND.EXPIRED WITH @ID LIKE VALUE123.... BY @ID
```

**Table**: `BAN.COMM.PEND.EXPIRED`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CCT.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PEND_EXPIRED
WHERE ID LIKE 'VALUE123%.'
ORDER BY ID ASC
```

---

#### SELECT #672 - Line 322

**File**: `BAN.I.CAL.VAL.COMM.PEND.b`

**Routine**: `BAN.I.CAL.VAL.COMM.PEND` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.COMM.PEND.PAID WITH @ID LIKE {Y.CCT.ID}.... BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.COMM.PEND.PAID WITH @ID LIKE VALUE123.... BY @ID
```

**Table**: `BAN.COMM.PEND.PAID`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CCT.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_COMM_PEND_PAID
WHERE ID LIKE 'VALUE123%.'
ORDER BY ID ASC
```

---

#### SELECT #673 - Line 98

**File**: `BAN.S.AA.POST.DPF.RELATION.b`

**Routine**: `BAN.S.AA.POST.DPF.RELATION` (SUBROUTINE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BAN.AL.DPF WITH @ID LIKE {Y.ARR.ID.DPF}*...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.AL.DPF WITH @ID LIKE VALUE123*...
```

**Table**: `BAN.AL.DPF`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ARR.ID.DPF

**Translated SQL**:
```sql
SELECT *
FROM BAN_AL_DPF
WHERE ID LIKE 'VALUE123*%'
```

---

#### SELECT #674 - Line 30

**File**: `BPA.B.APPLY.SHEET.DETAILS.SELECT.b`

**Routine**: `BPA.B.APPLY.SHEET.DETAILS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.SHEET.HEADER WITH SHEET.STATUS EQ APPLY
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.SHEET.HEADER WITH SHEET.STATUS EQ APPLY
```

**Table**: `BPA.SHEET.HEADER`

**Fields** (1):
-  `SHEET.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_SHEET_HEADER
WHERE SHEET_STATUS = 'APPLY'
```

---

#### SELECT #675 - Line 26

**File**: `BPA.B.COL.AGRSUBSIDY.SELECT.b`

**Routine**: `BPA.B.COL.AGRSUBSIDY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.AGRSUBSIDY
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.AGRSUBSIDY
```

**Table**: `BPA.AGRSUBSIDY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_AGRSUBSIDY
```

---

#### SELECT #676 - Line 87

**File**: `BPA.B.LOAN.COMM.AMORT.REP.POST.b`

**Routine**: `BPA.B.LOAN.COMM.AMORT.REP.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.AMPRT.TEMP.RPT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.AMPRT.TEMP.RPT
```

**Table**: `BPA.AMPRT.TEMP.RPT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'BPA.AMPRT.TEMP.RPT' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/BPA.AMPRT.TEMP.RPT

**Translated SQL**:
```sql
SELECT *
FROM BPA_AMPRT_TEMP_RPT
```

---

#### SELECT #677 - Line 18

**File**: `BPA.B.MRTG.FISCAL.LOAN.SELECT.b`

**Routine**: `BPA.B.MRTG.FISCAL.LOAN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.MRTG.PREF
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.MRTG.PREF
```

**Table**: `BPA.MRTG.PREF`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_MRTG_PREF
```

---

#### SELECT #678 - Line 41

**File**: `BPA.B.MRTG.PREF.DISB.b`

**Routine**: `BPA.B.MRTG.PREF.DISB` (BATCH (inferred))

**Variable**: `SEL.CMD.BAN`

**AS PER CODE**:
```
SELECT BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ {Y.ID.ARR.NEW}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.BANESCO.COLLATERAL WITH LOAN.ID EQ VALUE123
```

**Table**: `BAN.BANESCO.COLLATERAL`

**Fields** (1):
-  `LOAN.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LOAN.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
WHERE LOAN_ID = 'VALUE123'
```

---

#### SELECT #679 - Line 19

**File**: `BPA.B.MRTG.PREF.DISB.SELECT.b`

**Routine**: `BPA.B.MRTG.PREF.DISB.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.MRTG.BY.PERIOD WITH @ID EQ {Y.PERIOD}
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.MRTG.BY.PERIOD WITH @ID EQ VALUE123
```

**Table**: `BPA.MRTG.BY.PERIOD`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.PERIOD

**Translated SQL**:
```sql
SELECT *
FROM BPA_MRTG_BY_PERIOD
WHERE ID = 'VALUE123'
```

---

#### SELECT #680 - Line 25

**File**: `BPA.B.PAY.FECI.SELECT.b`

**Routine**: `BPA.B.PAY.FECI.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.FECI.ARRANGEMENTS
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.FECI.ARRANGEMENTS
```

**Table**: `BPA.FECI.ARRANGEMENTS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_FECI_ARRANGEMENTS
```

---

#### SELECT #681 - Line 21

**File**: `BPA.B.UPD.AGRSUBSIDY.SELECT.b`

**Routine**: `BPA.B.UPD.AGRSUBSIDY.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BPA.AGRSUBSIDY
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.AGRSUBSIDY
```

**Table**: `BPA.AGRSUBSIDY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_AGRSUBSIDY
```

---

#### SELECT #682 - Line 21

**File**: `BPA.B.UPD.DLY.LN.COM.AMORT.SELECT.b`

**Routine**: `BPA.B.UPD.DLY.LN.COM.AMORT.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL`

**AS PER CODE**:
```
SELECT BPA.LOAN.COMMISSION.AMORT WITH EXPIRY.DATE NE '' AND EXPIRY.DATE GT '{EB.SystemTables.getToday()}'
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.LOAN.COMMISSION.AMORT WITH EXPIRY.DATE NE '' AND EXPIRY.DATE GT 'TODAY'
```

**Table**: `BPA.LOAN.COMMISSION.AMORT`

**Fields** (1):
-  `EXPIRY.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_LOAN_COMMISSION_AMORT
WHERE EXPIRY_DATE > 'TODAY'
```

---

#### SELECT #683 - Line 115

**File**: `BPA.E.AL.ENDORSEMENT.POLICIES.b`

**Routine**: `BPA.E.AL.ENDORSEMENT.POLICIES` (ENQUIRY (inferred))

**Variable**: `SEL.CMD.BAN`

**AS PER CODE**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH MAT.DATE LE {Y.TO.DATE} AND MAT.DATE GE {Y.FROM.DATE} AND POLICY EQ {Y.POLICY.ID} AND INSURE.ID EQ {Y.INSURE.ID} AND POLICY.CCY EQ {Y.CCY.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.BANESCO.COLLATERAL WITH MAT.DATE LE VALUE123 AND MAT.DATE GE VALUE123 AND POLICY EQ VALUE123 AND INSURE.ID EQ VALUE123 AND POLICY.CCY EQ VALUE123
```

**Table**: `BAN.BANESCO.COLLATERAL`

**Fields** (4):
-  `POLICY.CCY`  Type: D
-  `POLICY`  Type: D
-  `MAT.DATE`  Type: D
-  `INSURE.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'POLICY.CCY' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'POLICY' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'MAT.DATE' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'INSURE.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.TO.DATE, Y.FROM.DATE, Y.POLICY.ID, Y.INSURE.ID, Y.CCY.ID

**Translated SQL**:
```sql
SELECT *
FROM BAN_BANESCO_COLLATERAL
WHERE MAT_DATE <= 'VALUE123' AND MAT_DATE >= 'VALUE123' AND POLICY = 'VALUE123' AND INSURE_ID = 'VALUE123' AND POLICY_CCY = 'VALUE123'
```

---

#### SELECT #684 - Line 159

**File**: `BPA.E.AL.ENDORSEMENT.POLICIES.b`

**Routine**: `BPA.E.AL.ENDORSEMENT.POLICIES` (ENQUIRY (inferred))

**Variable**: `SEL.CMD.BAL`

**AS PER CODE**:
```
SELECT F.AC.BALANCE.TYPE WITH @ID LIKE ...ACCOUNT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.BALANCE.TYPE WITH @ID LIKE ...ACCOUNT
```

**Table**: `AC.BALANCE.TYPE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_BALANCE_TYPE
WHERE ID LIKE '%ACCOUNT'
```

---

#### SELECT #685 - Line 71

**File**: `BPA.E.NOF.SHEET.BALANCE.b`

**Routine**: `BPA.E.NOF.SHEET.BALANCE` (NOFILE (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.SHEET.HEADER WITH SHEET.DATE EQ {Y.SHT.D} AND USER EQ {Y.USER} AND SHEET.STATUS EQ DONE BY COMPANY.CODE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.SHEET.HEADER WITH SHEET.DATE EQ VALUE123 AND USER EQ VALUE123 AND SHEET.STATUS EQ DONE BY COMPANY.CODE
```

**Table**: `BPA.SHEET.HEADER`

**Fields** (4):
-  `SHEET.DATE`  Type: D
-  `SHEET.STATUS`  Type: D
-  `USER`  Type: D
-  `COMPANY.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.SHT.D, Y.USER

**Translated SQL**:
```sql
SELECT *
FROM BPA_SHEET_HEADER
WHERE SHEET_DATE = 'VALUE123' AND USER = 'VALUE123' AND SHEET_STATUS = 'DONE'
ORDER BY COMPANY_CODE ASC
```

---

#### SELECT #686 - Line 71

**File**: `BPA.E.NOF.SHEET.COMPANY.b`

**Routine**: `BPA.E.NOF.SHEET.COMPANY` (NOFILE (inferred))

**Variable**: `Y.SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.SHEET.HEADER WITH COMPANY.CODE EQ {Y.CO.CODE} SHEET.STATUS EQ CANCEL BY.DSND CONSEC
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.SHEET.HEADER WITH COMPANY.CODE EQ VALUE123 SHEET.STATUS EQ CANCEL BY.DSND CONSEC
```

**Table**: `BPA.SHEET.HEADER`

**Fields** (1):
-  `COMPANY.CODE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CO.CODE

**Translated SQL**:
```sql
SELECT *
FROM BPA_SHEET_HEADER
WHERE COMPANY_CODE = 'VALUE123'
```

---

#### SELECT #687 - Line 84

**File**: `BPA.E.NOF.SHEET.STATUS.b`

**Routine**: `BPA.E.NOF.SHEET.STATUS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BPA.SHEET.DETAILS WITH @ID EQ {R.BPA.SHEET.CONCAT} BY PAY.STATUS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.SHEET.DETAILS WITH @ID EQ {BAPAAAL.MigCredito.BpaSheetConcat.Read(Y.CONCAT.ID, ERR.CONT)} BY PAY.STATUS
```

**Table**: `BPA.SHEET.DETAILS`

**Fields** (2):
-  `PAY.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: BAPAAAL.MigCredito.BpaSheetConcat.Read(Y.CONCAT.ID, ERR.CONT)

**Translated SQL**:
```sql
SELECT *
FROM BPA_SHEET_DETAILS
WHERE ID = '{BAPAAAL.MigCredito.BpaSheetConcat.Read(Y.CONCAT.ID,'
ORDER BY PAY_STATUS ASC
```

---

#### SELECT #688 - Line 154

**File**: `BPA.MINBALFEE.CORRECT.b`

**Routine**: `BPA.MINBALFEE.CORRECT` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAAAL.MigCredito.getFnFt()} WITH PAYMENT.DETAILS EQ '{FIELD(BAN.AA.CHG.PENDING.ID, ".", 2, 1)}'
```

**SIMULATED AT RUNTIME**:
```
SELECT FT WITH PAYMENT.DETAILS EQ '{FIELD(BAN.AA.CHG.PENDING.ID, ".", 2, 1)}'
```

**Table**: `FT`

**Fields** (1):
-  `PAYMENT.DETAILS`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'FT' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FT
-   Unresolved variables: FIELD(BAN.AA.CHG.PENDING.ID, ".", 2, 1)

**Translated SQL**:
```sql
SELECT *
FROM FT
WHERE PAYMENT_DETAILS = '{FIELD(BAN.AA.CHG.PENDING.ID,'
```

---

#### SELECT #689 - Line 167

**File**: `BPA.MINBALFEE.CORRECT.b`

**Routine**: `BPA.MINBALFEE.CORRECT` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAAAL.MigCredito.getFnFtHis()} WITH PAYMENT.DETAILS EQ '{FIELD(BAN.AA.CHG.PENDING.ID, ".", 2, 1)}'
```

**SIMULATED AT RUNTIME**:
```
SELECT FT$HIS WITH PAYMENT.DETAILS EQ '{FIELD(BAN.AA.CHG.PENDING.ID, ".", 2, 1)}'
```

**Table**: `FT$HIS`

**Fields** (1):
-  `PAYMENT.DETAILS`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$HIS' detected - Using dictionary from base table 'FT'
-   WARNING: Dictionary not found for table 'FT' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FT
-   Unresolved variables: FIELD(BAN.AA.CHG.PENDING.ID, ".", 2, 1)

**Translated SQL**:
```sql
SELECT *
FROM FT$HIS
WHERE PAYMENT_DETAILS = '{FIELD(BAN.AA.CHG.PENDING.ID,'
```

---

#### SELECT #690 - Line 74

**File**: `BPA.SHEET.HEADER.ID.b`

**Routine**: `BPA.SHEET.HEADER.ID` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BPA.SHEET.HEADER WITH @ID LIKE {EB.SystemTables.getIdNew()}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.SHEET.HEADER WITH @ID LIKE ID.NEW...
```

**Table**: `BPA.SHEET.HEADER`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BPA_SHEET_HEADER
WHERE ID LIKE 'ID.NEW%'
```

---

#### SELECT #691 - Line 60

**File**: `BPA.V.AC.CHQ.TYPE.DEBIT.ACCT.b`

**Routine**: `BPA.V.AC.CHQ.TYPE.DEBIT.ACCT` (VERSION (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BPA.AC.CHQ.TYPE WITH CHQ.TYPE EQ {Y.DESICION.L.P}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BPA.AC.CHQ.TYPE WITH CHQ.TYPE EQ VALUE123
```

**Table**: `BPA.AC.CHQ.TYPE`

**Fields** (1):
-  `CHQ.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DESICION.L.P

**Translated SQL**:
```sql
SELECT *
FROM BPA_AC_CHQ_TYPE
WHERE CHQ_TYPE = 'VALUE123'
```

---

#### SELECT #692 - Line 160

**File**: `BPA.V.PARTICIPANTS.b`

**Routine**: `BPA.V.PARTICIPANTS` (VERSION (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CUSTOMER WITH LEGAL.ID EQ {Y.LEGAL.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER WITH LEGAL.ID EQ VALUE123
```

**Table**: `CUSTOMER`

**Fields** (1):
-  `LEGAL.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'LEGAL.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.LEGAL.ID

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
WHERE LEGAL_ID = 'VALUE123'
```

---

#### SELECT #693 - Line 54

**File**: `BAN.A.TT.CHQ.CONTROL.REVE.b`

**Routine**: `BAN.A.TT.CHQ.CONTROL.REVE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TT.CHQ.CONTROL WITH @ID  LIKE ...{EB.SystemTables.getIdNew()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TT.CHQ.CONTROL WITH @ID  LIKE ...ID.NEW
```

**Table**: `BAN.TT.CHQ.CONTROL`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_TT_CHQ_CONTROL
WHERE ID LIKE '%ID.NEW'
```

---

#### SELECT #694 - Line 117

**File**: `BAN.B.AVRG.BALANCES.b`

**Routine**: `BAN.B.AVRG.BALANCES` (BATCH (inferred))

**Variable**: `SEL.CUST.ARR`

**AS PER CODE**:
```
SELECT F.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ DEPOSITS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ DEPOSITS
```

**Table**: `AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'DEPOSITS'
```

---

#### SELECT #695 - Line 59

**File**: `BAN.B.OUTCLG.LCLINTL.BALANCES.SELECT.b`

**Routine**: `BAN.B.OUTCLG.LCLINTL.BALANCES.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {BAPAAAD.MigDepositos.getFnAccount()} @ID LIKE {EB.SystemTables.getLccy()}{ID.CATEGORY}0001...
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT @ID LIKE LCCYSAMPLE_VALUE0001...
```

**Table**: `ACCOUNT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
```

---

#### SELECT #696 - Line 28

**File**: `BAN.B.TT.CHQ.CRACC.APL.SELECT.b`

**Routine**: `BAN.B.TT.CHQ.CRACC.APL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.TT.CHQ.STMT
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TT.CHQ.STMT
```

**Table**: `BAN.TT.CHQ.STMT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TT_CHQ_STMT
```

---

#### SELECT #697 - Line 151

**File**: `BAN.B.TT.CHQ.STMT.b`

**Routine**: `BAN.B.TT.CHQ.STMT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT STMT.ENTRY WITH @ID LIKE {Y.STMT.NO}... AND ACCOUNT.NUMBER EQ {Y.CREDIT.ACCT} AND TRANS.REFERENCE LIKE {Y.ID.STMT}...
```

**SIMULATED AT RUNTIME**:
```
SELECT STMT.ENTRY WITH @ID LIKE VALUE123... AND ACCOUNT.NUMBER EQ VALUE123 AND TRANS.REFERENCE LIKE VALUE123...
```

**Table**: `STMT.ENTRY`

**Fields** (3):
-  `TRANS.REFERENCE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.STMT.NO, Y.CREDIT.ACCT

**Translated SQL**:
```sql
SELECT *
FROM STMT_ENTRY
WHERE ID LIKE 'VALUE123%' AND ACCOUNT_NUMBER = 'VALUE123' AND TRANS_REFERENCE LIKE 'VALUE123%'
```

---

#### SELECT #698 - Line 175

**File**: `BAN.B.TT.CHQ.STMT.b`

**Routine**: `BAN.B.TT.CHQ.STMT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT STMT.ENTRY WITH @ID LIKE {Y.STMT.NO}... AND ACCOUNT.NUMBER EQ {Y.CREDIT.ACCT} AND TRANS.REFERENCE LIKE {Y.CHQ.DET.DB.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT STMT.ENTRY WITH @ID LIKE VALUE123... AND ACCOUNT.NUMBER EQ VALUE123 AND TRANS.REFERENCE LIKE VALUE123...
```

**Table**: `STMT.ENTRY`

**Fields** (3):
-  `TRANS.REFERENCE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.STMT.NO, Y.CREDIT.ACCT, Y.CHQ.DET.DB.ID

**Translated SQL**:
```sql
SELECT *
FROM STMT_ENTRY
WHERE ID LIKE 'VALUE123%' AND ACCOUNT_NUMBER = 'VALUE123' AND TRANS_REFERENCE LIKE 'VALUE123%'
```

---

#### SELECT #699 - Line 205

**File**: `BAN.B.TT.CHQ.STMT.b`

**Routine**: `BAN.B.TT.CHQ.STMT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT STMT.ENTRY WITH @ID LIKE {Y.STMT.NO}... AND ACCOUNT.NUMBER EQ {Y.ACCOUNT} AND TRANS.REFERENCE LIKE {Y.ID.STMT}...
```

**SIMULATED AT RUNTIME**:
```
SELECT STMT.ENTRY WITH @ID LIKE VALUE123... AND ACCOUNT.NUMBER EQ VALUE123 AND TRANS.REFERENCE LIKE VALUE123...
```

**Table**: `STMT.ENTRY`

**Fields** (3):
-  `TRANS.REFERENCE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.STMT.NO, Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM STMT_ENTRY
WHERE ID LIKE 'VALUE123%' AND ACCOUNT_NUMBER = 'VALUE123' AND TRANS_REFERENCE LIKE 'VALUE123%'
```

---

#### SELECT #700 - Line 215

**File**: `BAN.B.TT.CHQ.STMT.b`

**Routine**: `BAN.B.TT.CHQ.STMT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT STMT.ENTRY.DETAIL WITH @ID LIKE {Y.STMT.NO}... AND ACCOUNT.NUMBER EQ {Y.ACCOUNT} AND TRANS.REFERENCE LIKE {Y.ID.STMT}...
```

**SIMULATED AT RUNTIME**:
```
SELECT STMT.ENTRY.DETAIL WITH @ID LIKE VALUE123... AND ACCOUNT.NUMBER EQ VALUE123 AND TRANS.REFERENCE LIKE VALUE123...
```

**Table**: `STMT.ENTRY.DETAIL`

**Fields** (3):
-  `TRANS.REFERENCE`  Type: D
-  `ACCOUNT.NUMBER`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.STMT.NO, Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM STMT_ENTRY_DETAIL
WHERE ID LIKE 'VALUE123%' AND ACCOUNT_NUMBER = 'VALUE123' AND TRANS_REFERENCE LIKE 'VALUE123%'
```

---

#### SELECT #701 - Line 28

**File**: `BAN.B.TT.CHQ.STMT.SELECT.b`

**Routine**: `BAN.B.TT.CHQ.STMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.TT.CHQ.STMT
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.TT.CHQ.STMT
```

**Table**: `BAN.TT.CHQ.STMT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TT_CHQ_STMT
```

---

#### SELECT #702 - Line 66

**File**: `BAN.CK.TT.DENOM.LOAD.b`

**Routine**: `BAN.CK.TT.DENOM.LOAD` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER.DENOMINATION WITH DENOM.TYPE EQ {Y.DR.DENOM.TYPE} BY-DSND VALUE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.DENOMINATION WITH DENOM.TYPE EQ VALUE123 BY-DSND VALUE
```

**Table**: `TELLER.DENOMINATION`

**Fields** (2):
-  `VALUE`  Type: D
-  `DENOM.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DR.DENOM.TYPE

**Translated SQL**:
```sql
SELECT *
FROM TELLER_DENOMINATION
WHERE DENOM_TYPE = 'VALUE123'
ORDER BY VALUE DESC
```

---

#### SELECT #703 - Line 42

**File**: `BAN.E.CNV.TT.CHQ.GET.DETID.b`

**Routine**: `BAN.E.CNV.TT.CHQ.GET.DETID` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.TELLER.FINANCIAL.SERVICES$NAU WITH LT.TT.CHQ.CRTL EQ {Y.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.TELLER.FINANCIAL.SERVICES$NAU WITH LT.TT.CHQ.CRTL EQ 12345
```

**Table**: `TELLER.FINANCIAL.SERVICES$NAU`

**Fields** (1):
-  `LT.TT.CHQ.CRTL`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,33>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 special file suffix '$NAU' detected - Using dictionary from base table 'TELLER.FINANCIAL.SERVICES'
-   INFO: LOCAL.REF fields found: LT.TT.CHQ.CRTL - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ID

**Translated SQL**:
```sql
SELECT *
FROM TELLER_FINANCIAL_SERVICES$NAU
WHERE LT_TT_CHQ_CRTL = '12345'
```

---

#### SELECT #704 - Line 60

**File**: `BAN.I.TT.CHQ.CLOSE.TILL.b`

**Routine**: `BAN.I.TT.CHQ.CLOSE.TILL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TT.CHQ.CONTROL @ID LIKE {EB.SystemTables.getIdNew()}-... AND CHQ.PEND.AMT GT 0
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TT.CHQ.CONTROL @ID LIKE ID.NEW-... AND CHQ.PEND.AMT GT 0
```

**Table**: `BAN.TT.CHQ.CONTROL`

**Fields** (1):
-  `CHQ.PEND.AMT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_TT_CHQ_CONTROL
WHERE CHQ_PEND_AMT > '0'
```

---

#### SELECT #705 - Line 76

**File**: `BAN.I.TT.CHQ.CLOSE.TILL.b`

**Routine**: `BAN.I.TT.CHQ.CLOSE.TILL` (Unknown)

**Variable**: `SEL.CMD.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ {EB.SystemTables.getIdNew()} AND CO.CODE EQ {EB.SystemTables.getIdCompany()} AND BANK.SORT.CODE EQ {SORT.BANESCO<2>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION CHQ.STATUS EQ DEPOSITED AND LT.DEP.TT.ID EQ ID.NEW AND CO.CODE EQ ID.COMPANY AND BANK.SORT.CODE EQ {SORT.BANESCO<2>}
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (3):
-  `CO.CODE`  Type: D
-  `BANK.SORT.CODE`  Type: D
-  `LT.DEP.TT.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,4>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.DEP.TT.ID - Physical fields in database (TAFJ compatible)
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE LT_DEP_TT_ID = 'ID.NEW' AND CO_CODE = 'ID.COMPANY' AND BANK_SORT_CODE = '{SORT.BANESCO<2>}'
```

---

#### SELECT #706 - Line 102

**File**: `BAN.I.TT.CHQ.PRP.VALID.b`

**Routine**: `BAN.I.TT.CHQ.PRP.VALID` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.TT.CHQ.CONTROL.DETAIL WITH @ID LIKE {Y.LT.TT.CHQ.CRTL}... AND CHQ.ACCOUNT EQ {Y.CHQ.ACCOUNT} AND CHQ.NUMBER EQ {Y.CHQ.NUMBER}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.TT.CHQ.CONTROL.DETAIL WITH @ID LIKE VALUE123... AND CHQ.ACCOUNT EQ VALUE123 AND CHQ.NUMBER EQ VALUE123
```

**Table**: `BAN.TT.CHQ.CONTROL.DETAIL`

**Fields** (3):
-  `CHQ.NUMBER`  Type: D
-  `CHQ.ACCOUNT`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LT.TT.CHQ.CRTL, Y.CHQ.ACCOUNT, Y.CHQ.NUMBER

**Translated SQL**:
```sql
SELECT *
FROM BAN_TT_CHQ_CONTROL_DETAIL
WHERE ID LIKE 'VALUE123%' AND CHQ_ACCOUNT = 'VALUE123' AND CHQ_NUMBER = 'VALUE123'
```

---

#### SELECT #707 - Line 177

**File**: `BAN.E.NOF.ACCT.BALANCES.DETAILS.b`

**Routine**: `BAN.E.NOF.ACCT.BALANCES.DETAILS` (NOFILE (inferred))

**Variable**: `Y.SEL.CC`

**AS PER CODE**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ {Y.ACCT.ID} AND CHQ.STATUS NE CLEARED AND CHQ.STATUS NE RETURNED
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.COLLECTION WITH CREDIT.ACC.NO EQ VALUE123 AND CHQ.STATUS NE CLEARED AND CHQ.STATUS NE RETURNED
```

**Table**: `CHEQUE.COLLECTION`

**Fields** (2):
-  `CHQ.STATUS`  Type: D
-  `CREDIT.ACC.NO`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CREDIT.ACC.NO' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_COLLECTION
WHERE CREDIT_ACC_NO = 'VALUE123' AND CHQ_STATUS != 'CLEARED' AND CHQ_STATUS != 'RETURNED'
```

---

#### SELECT #708 - Line 329

**File**: `BAN.E.NOF.ACCT.BALANCES.DETAILS.b`

**Routine**: `BAN.E.NOF.ACCT.BALANCES.DETAILS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.ACCT.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCT.ID

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #709 - Line 30

**File**: `BACM3M.B.ACCOUNTING.TXNS.DEL.SELECT.b`

**Routine**: `BACM3M.B.ACCOUNTING.TXNS.DEL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT FBNK.BACM3M.ACCOUNTING.TXNS.DETAILS WITH BOOKING.DATE LE {Y.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT FBNK.BACM3M.ACCOUNTING.TXNS.DETAILS WITH BOOKING.DATE LE VALUE123
```

**Table**: `FBNK.BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `BOOKING.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBNK.' detected - Using dictionary from core table 'BACM3M.ACCOUNTING.TXNS.DETAILS'
-   Unresolved variables: Y.DATE

**Translated SQL**:
```sql
SELECT *
FROM FBNK_BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE BOOKING_DATE <= 'VALUE123'
```

---

#### SELECT #710 - Line 105

**File**: `BACM3M.B.ACCT.TXN.DET.EXTRACT.b`

**Routine**: `BACM3M.B.ACCT.TXN.DET.EXTRACT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
{SEL.CMD}{SEL.CMD.AND} AND WITH {Y.SEL.FLD<I.VAR>} {Y.SEL.OPE<I.VAR>} {Y.SEL.LIST<I.VAR>}{SEL.CMD.AND} AND WITH {Y.SEL.FLD<I.VAR>} {Y.SEL.OPE<I.VAR>} {Y.SEL.LIST<I.VAR>}
```

**SIMULATED AT RUNTIME**:
```
SELECT SAMPLE_VALUE AND WITH {Y.SEL.FLD<I.VAR>} {Y.SEL.OPE<I.VAR>} {Y.SEL.LIST<I.VAR>} AND WITH {Y.SEL.FLD<I.VAR>} {Y.SEL.OPE<I.VAR>} {Y.SEL.LIST<I.VAR>}SAMPLE_VALUE AND WITH {Y.SEL.FLD<I.VAR>} {Y.SEL.OPE<I.VAR>} {Y.SEL.LIST<I.VAR>} AND WITH {Y.SEL.FLD<I.VAR>} {Y.SEL.OPE<I.VAR>} {Y.SEL.LIST<I.VAR>} 
```

**Table**: `SAMPLE_VALUE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'SAMPLE_VALUE' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/SAMPLE_VALUE
-   Unresolved variables: SEL.CMD.AND

**Translated SQL**:
```sql
SELECT *
FROM SAMPLE_VALUE
```

---

#### SELECT #711 - Line 135

**File**: `BACM3M.B.ACCT.TXN.DET.EXTRACT.b`

**Routine**: `BACM3M.B.ACCT.TXN.DET.EXTRACT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.RE.STAT.LINE.CONT WITH ASST.CONSOL.KEY EQ {Y.CONSOL.KEY}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.RE.STAT.LINE.CONT WITH ASST.CONSOL.KEY EQ VALUE123
```

**Table**: `RE.STAT.LINE.CONT`

**Fields** (1):
-  `ASST.CONSOL.KEY`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ASST.CONSOL.KEY' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CONSOL.KEY

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_LINE_CONT
WHERE ASST_CONSOL_KEY = 'VALUE123'
```

---

#### SELECT #712 - Line 20

**File**: `BACM3M.B.FINAL.FILE.GEN.SELECT.b`

**Routine**: `BACM3M.B.FINAL.FILE.GEN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.DATA.FINAL.GEN
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.DATA.FINAL.GEN
```

**Table**: `BACM3M.DATA.FINAL.GEN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_DATA_FINAL_GEN
```

---

#### SELECT #713 - Line 57

**File**: `BACM3M.B.RE.LINE.WORKFILE.SELECT.b`

**Routine**: `BACM3M.B.RE.LINE.WORKFILE.SELECT` (BATCH (inferred))

**Variable**: `STAT.SEL.CMD`

**AS PER CODE**:
```
SELECT RE.STAT.LINE.CONT WITH TYPE EQ DETAIL
```

**SIMULATED AT RUNTIME**:
```
SELECT RE.STAT.LINE.CONT WITH TYPE EQ DETAIL
```

**Table**: `RE.STAT.LINE.CONT`

**Fields** (1):
-  `TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM RE_STAT_LINE_CONT
WHERE TYPE = 'DETAIL'
```

---

#### SELECT #714 - Line 78

**File**: `BACM3M.B.REPORT.ACCOUNTING.b`

**Routine**: `BACM3M.B.REPORT.ACCOUNTING` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BACM3M.ACCOUNTING.TXNS.DETAILS WITH @ID LIKE ...{Y.DATE.1}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BACM3M.ACCOUNTING.TXNS.DETAILS WITH @ID LIKE ...VALUE123
```

**Table**: `BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATE.1

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE ID LIKE '%VALUE123'
```

---

#### SELECT #715 - Line 21

**File**: `BACM3M.B.SUM.ACCOUNTING.SELECT.b`

**Routine**: `BACM3M.B.SUM.ACCOUNTING.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...{Y.DATE.FINAL}
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...VALUE123
```

**Table**: `BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATE.FINAL

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE ID LIKE '%VALUE123'
```

---

#### SELECT #716 - Line 68

**File**: `BACM3M.B.TXNS.SELECTION.COLLECT.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECTION.COLLECT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {Y.OUT.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT VALUE123
```

**Table**: `VALUE123`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'VALUE123' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/VALUE123
-   Unresolved variables: Y.OUT.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM VALUE123
```

---

#### SELECT #717 - Line 95

**File**: `BACM3M.B.TXNS.SELECTION.FINAL.SELECT.b`

**Routine**: `BACM3M.B.TXNS.SELECTION.FINAL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...{Y.LWD} BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT BACM3M.ACCOUNTING.TXNS.DETAILS WITH  @ID LIKE  ...VALUE123 BY @ID
```

**Table**: `BACM3M.ACCOUNTING.TXNS.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LWD

**Translated SQL**:
```sql
SELECT *
FROM BACM3M_ACCOUNTING_TXNS_DETAILS
WHERE ID LIKE '%VALUE123'
ORDER BY ID ASC
```

---

#### SELECT #718 - Line 88

**File**: `BACM3M.B.VAL.INI.ACCOUNTING.b`

**Routine**: `BACM3M.B.VAL.INI.ACCOUNTING` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.FILE.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT FILE.PATH
```

**Table**: `FILE.PATH`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'FILE.PATH' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/FILE.PATH
-   Unresolved variables: F.FILE.PATH

**Translated SQL**:
```sql
SELECT *
FROM FILE_PATH
```

---

#### SELECT #719 - Line 118

**File**: `BACM3M.B.VAL.INI.ACCOUNTING.b`

**Routine**: `BACM3M.B.VAL.INI.ACCOUNTING` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BATCH WITH @ID LIKE {Y.CMP.MNE}/... AND BATCH.STAGE NE "" AND PROCESS.STATUS NE 0
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BATCH WITH @ID LIKE VALUE123/... AND BATCH.STAGE NE "" AND PROCESS.STATUS NE 0
```

**Table**: `BATCH`

**Fields** (3):
-  `BATCH.STAGE`  Type: D
-  `PROCESS.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CMP.MNE

**Translated SQL**:
```sql
SELECT *
FROM BATCH
WHERE ID LIKE 'VALUE123/%' AND PROCESS_STATUS != '0'
```

---

#### SELECT #720 - Line 70

**File**: `BAN.A.AA.AC.STATUS.CANCEL.UPDATE.b`

**Routine**: `BAN.A.AA.AC.STATUS.CANCEL.UPDATE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.AC.STATUS.CANCEL.UPDATE WITH ACCOUNT EQ {Y.ACCT.REF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.AC.STATUS.CANCEL.UPDATE WITH ACCOUNT EQ VALUE123
```

**Table**: `BAN.AC.STATUS.CANCEL.UPDATE`

**Fields** (1):
-  `ACCOUNT`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCT.REF

**Translated SQL**:
```sql
SELECT *
FROM BAN_AC_STATUS_CANCEL_UPDATE
WHERE ACCOUNT = 'VALUE123'
```

---

#### SELECT #721 - Line 153

**File**: `BAN.A.AA.CREATION.CALL.AC.STMT.b`

**Routine**: `BAN.A.AA.CREATION.CALL.AC.STMT` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BAN.PARAM.AC.STATEMENT WITH @ID LIKE {Y.FIN.COM}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PARAM.AC.STATEMENT WITH @ID LIKE VALUE123...
```

**Table**: `BAN.PARAM.AC.STATEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.FIN.COM

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAM_AC_STATEMENT
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #722 - Line 175

**File**: `BAN.AA.AUTO.PYMT.STOP.START.b`

**Routine**: `BAN.AA.AUTO.PYMT.STOP.START` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.BLOCK.CLOSURE WITH ACCOUNT.NUMBER EQ '{AA.Framework.getC_aaloclinkedaccount()}'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.BLOCK.CLOSURE WITH ACCOUNT.NUMBER EQ 'C'
```

**Table**: `AC.BLOCK.CLOSURE`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_BLOCK_CLOSURE
WHERE ACCOUNT_NUMBER = 'C'
```

---

#### SELECT #723 - Line 46

**File**: `BAN.B.ACCOUNTS.AUTM.STATUS.SELECT.b`

**Routine**: `BAN.B.ACCOUNTS.AUTM.STATUS.SELECT` (BATCH (inferred))

**Variable**: `SEL.ARRANGEMENT.CUS`

**AS PER CODE**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS
```

**Table**: `AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS'
```

---

#### SELECT #724 - Line 38

**File**: `BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Routine**: `BAN.B.BATCH.CALL.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.PARAM.AC.STATEMENT WITH AMEND.DATE LIKE ...{Y.CHECK.DATE}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.PARAM.AC.STATEMENT WITH AMEND.DATE LIKE ...VALUE123...
```

**Table**: `BAN.PARAM.AC.STATEMENT`

**Fields** (1):
-  `AMEND.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHECK.DATE

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAM_AC_STATEMENT
WHERE AMEND_DATE LIKE '%VALUE123%'
```

---

#### SELECT #725 - Line 88

**File**: `BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Routine**: `BAN.B.BATCH.CALL.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.ACCOUNT.STATEMENT}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.STATEMENT
```

**Table**: `ACCOUNT.STATEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: F.ACCOUNT.STATEMENT

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_STATEMENT
```

---

#### SELECT #726 - Line 122

**File**: `BAN.B.BATCH.CALL.AC.STMT.SELECT.b`

**Routine**: `BAN.B.BATCH.CALL.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.ACCOUNT.STATEMENT}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.STATEMENT
```

**Table**: `ACCOUNT.STATEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: F.ACCOUNT.STATEMENT

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_STATEMENT
```

---

#### SELECT #727 - Line 54

**File**: `BAN.B.BATCH.CANCEL.CALL.AC.STMT.SELECT.b`

**Routine**: `BAN.B.BATCH.CANCEL.CALL.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT BAN.PARAM.AC.STATEMENT WITH @ID LIKE {EB.SystemTables.getIdCompany()}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.PARAM.AC.STATEMENT WITH @ID LIKE ID.COMPANY...
```

**Table**: `BAN.PARAM.AC.STATEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAM_AC_STATEMENT
WHERE ID LIKE 'ID.COMPANY%'
```

---

#### SELECT #728 - Line 42

**File**: `BAN.B.BATCH.CLEAN.T.AC.OD.SELECT.b`

**Routine**: `BAN.B.BATCH.CLEAN.T.AC.OD.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.ACCT.OD.DAY
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.ACCT.OD.DAY
```

**Table**: `BAN.ACCT.OD.DAY`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_ACCT_OD_DAY
```

---

#### SELECT #729 - Line 50

**File**: `BAN.B.BATCH.STATUS.CALL.AC.STMT.SELECT.b`

**Routine**: `BAN.B.BATCH.STATUS.CALL.AC.STMT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.BAN.PARAM.AC.STATEMENT} WITH @ID LIKE {EB.SystemTables.getIdCompany()}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.PARAM.AC.STATEMENT WITH @ID LIKE ID.COMPANY...
```

**Table**: `BAN.PARAM.AC.STATEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: F.BAN.PARAM.AC.STATEMENT

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAM_AC_STATEMENT
WHERE ID LIKE 'ID.COMPANY%'
```

---

#### SELECT #730 - Line 29

**File**: `BAN.B.CMX.EXPIRED.TXN.SELECT.b`

**Routine**: `BAN.B.CMX.EXPIRED.TXN.SELECT` (BATCH (inferred))

**Variable**: `Y.SEL.LIV`

**AS PER CODE**:
```
SELECT BAN.CMX.EXPIRED.TXN @ID EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.CMX.EXPIRED.TXN @ID EQ TODAY
```

**Table**: `BAN.CMX.EXPIRED.TXN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_CMX_EXPIRED_TXN
```

---

#### SELECT #731 - Line 39

**File**: `BAN.B.CUST.FUND.RISE.ENTRY.SELECT.b`

**Routine**: `BAN.B.CUST.FUND.RISE.ENTRY.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.L.CUSTODY.FUND WITH STATUS.FLAG EQ OPEN AND NEXT.CHARGE.DATE LIKE {Y.ANIO.MES}...
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.L.CUSTODY.FUND WITH STATUS.FLAG EQ OPEN AND NEXT.CHARGE.DATE LIKE VALUE123...
```

**Table**: `BAN.L.CUSTODY.FUND`

**Fields** (2):
-  `STATUS.FLAG`  Type: D
-  `NEXT.CHARGE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ANIO.MES

**Translated SQL**:
```sql
SELECT *
FROM BAN_L_CUSTODY_FUND
WHERE STATUS_FLAG = 'OPEN' AND NEXT_CHARGE_DATE LIKE 'VALUE123%'
```

---

#### SELECT #732 - Line 27

**File**: `BAN.B.DELETE.ONLINE.CLEARED.BAL.SELECT.b`

**Routine**: `BAN.B.DELETE.ONLINE.CLEARED.BAL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.BAN.NO.MONTHS.AC}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.NO.MONTHS.AC
```

**Table**: `BAN.NO.MONTHS.AC`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: F.BAN.NO.MONTHS.AC

**Translated SQL**:
```sql
SELECT *
FROM BAN_NO_MONTHS_AC
```

---

#### SELECT #733 - Line 31

**File**: `BAN.B.OD.MONTHS.YEAR.SELECT.b`

**Routine**: `BAN.B.OD.MONTHS.YEAR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.OD.ACCT.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.OD.ACCT.DETAILS
```

**Table**: `BPA.OD.ACCT.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_OD_ACCT_DETAILS
```

---

#### SELECT #734 - Line 165

**File**: `BAN.B.REVAL.REVERSE.POS.b`

**Routine**: `BAN.B.REVAL.REVERSE.POS` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT F.CATEG.ENT.LWORK.DAY WITH @ID LIKE {BAPAAAC.MigCuentas.getYRevPlCateg()}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CATEG.ENT.LWORK.DAY WITH @ID LIKE YREV.PL.CATEG...
```

**Table**: `CATEG.ENT.LWORK.DAY`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CATEG_ENT_LWORK_DAY
WHERE ID LIKE 'YREV.PL.CATEG%'
```

---

#### SELECT #735 - Line 72

**File**: `BAN.B.REVAL.REVERSE.SELECT.b`

**Routine**: `BAN.B.REVAL.REVERSE.SELECT` (BATCH (inferred))

**Variable**: `SELECT.CMD`

**AS PER CODE**:
```
SELECT {BAPAAAC.MigCuentas.getFnSpecEntry()} WITH TRANSACTION.CODE EQ {BAPAAAC.MigCuentas.getYTxnCode()} AND BOOKING.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT SPEC.ENTRY WITH TRANSACTION.CODE EQ YTXN.CODE AND BOOKING.DATE EQ TODAY
```

**Table**: `SPEC.ENTRY`

**Fields** (2):
-  `TRANSACTION.CODE`  Type: Unknown
-  `BOOKING.DATE`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'SPEC.ENTRY' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/SPEC.ENTRY

**Translated SQL**:
```sql
SELECT *
FROM SPEC_ENTRY
WHERE TRANSACTION_CODE = 'YTXN.CODE' AND BOOKING_DATE = 'TODAY'
```

---

#### SELECT #736 - Line 65

**File**: `BAN.B.UPD.AVL.AMT.b`

**Routine**: `BAN.B.UPD.AVL.AMT` (BATCH (inferred))

**Variable**: `Y.SEL.LIV2`

**AS PER CODE**:
```
SELECT F.BAN.STR.TXN.AMT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.STR.TXN.AMT
```

**Table**: `BAN.STR.TXN.AMT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_STR_TXN_AMT
```

---

#### SELECT #737 - Line 52

**File**: `BAN.B.UPD.BAL.EXCEDLINE.SELECT.b`

**Routine**: `BAN.B.UPD.BAL.EXCEDLINE.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT BAN.T.ACCT.LIM.OD
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.T.ACCT.LIM.OD
```

**Table**: `BAN.T.ACCT.LIM.OD`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_T_ACCT_LIM_OD
```

---

#### SELECT #738 - Line 33

**File**: `BAN.B.UPDATE.CUSTODY.FUND.STATUS.SELECT.b`

**Routine**: `BAN.B.UPDATE.CUSTODY.FUND.STATUS.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.L.CUSTODY.FUND WITH INACTIVE.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.L.CUSTODY.FUND WITH INACTIVE.DATE EQ TODAY
```

**Table**: `BAN.L.CUSTODY.FUND`

**Fields** (1):
-  `INACTIVE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_L_CUSTODY_FUND
WHERE INACTIVE_DATE = 'TODAY'
```

---

#### SELECT #739 - Line 33

**File**: `BAN.B.UPDATE.ONLINE.CLEARED.BAL.SELECT.b`

**Routine**: `BAN.B.UPDATE.ONLINE.CLEARED.BAL.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT PRODUCT.LINE EQ ACCOUNTS
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT PRODUCT.LINE EQ ACCOUNTS
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #740 - Line 116

**File**: `BAN.CONT.FILE.FINAL.b`

**Routine**: `BAN.CONT.FILE.FINAL` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {F.TEMP.FOLDER.POINTER}
```

**SIMULATED AT RUNTIME**:
```
SELECT TEMP.FOLDER.POINTER
```

**Table**: `TEMP.FOLDER.POINTER`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'TEMP.FOLDER.POINTER' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/TEMP.FOLDER.POINTER
-   Unresolved variables: F.TEMP.FOLDER.POINTER

**Translated SQL**:
```sql
SELECT *
FROM TEMP_FOLDER_POINTER
```

---

#### SELECT #741 - Line 55

**File**: `BAN.CR.REQUEST.CHECK.BOOK.PREVIOUS.b`

**Routine**: `BAN.CR.REQUEST.CHECK.BOOK.PREVIOUS` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.BAN.CHEQUE.REGISTER.ASSIGNED WITH @ID LIKE ...{Y.CHQ.ACC}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CHEQUE.REGISTER.ASSIGNED WITH @ID LIKE ...VALUE123
```

**Table**: `BAN.CHEQUE.REGISTER.ASSIGNED`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHQ.ACC

**Translated SQL**:
```sql
SELECT *
FROM BAN_CHEQUE_REGISTER_ASSIGNED
WHERE ID LIKE '%VALUE123'
```

---

#### SELECT #742 - Line 143

**File**: `BAN.E.NOF.AC.OVERDRAWN.b`

**Routine**: `BAN.E.NOF.AC.OVERDRAWN` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.ACCOUNT.OVERDRAWN
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT.OVERDRAWN
```

**Table**: `ACCOUNT.OVERDRAWN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_OVERDRAWN
```

---

#### SELECT #743 - Line 122

**File**: `BAN.E.NOF.AC.OVERDRAWN.LC.b`

**Routine**: `BAN.E.NOF.AC.OVERDRAWN.LC` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.ACCT.OVERDRAWN
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.ACCT.OVERDRAWN
```

**Table**: `BAN.ACCT.OVERDRAWN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_ACCT_OVERDRAWN
```

---

#### SELECT #744 - Line 137

**File**: `BAN.E.NOF.ACCR.NO.FIN.TXN.b`

**Routine**: `BAN.E.NOF.ACCR.NO.FIN.TXN` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID NE '' AND LT.NFT.ID NE 'EMCHQ' AND CHARGE.DATE GE {Y.CHARGE.FROM} AND CHARGE.DATE LE {Y.CHARGE.TO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID NE '' AND LT.NFT.ID NE 'EMCHQ' AND CHARGE.DATE GE VALUE123 AND CHARGE.DATE LE VALUE123
```

**Table**: `AC.CHARGE.REQUEST`

**Fields** (2):
-  `CHARGE.DATE`  Type: D
-  `LT.NFT.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-  PATH-DEPENDENT: CASE Y.CHARGE.FROM  NE "" (line 128)
-   INFO: LOCAL.REF fields found: LT.NFT.ID - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CHARGE.FROM, Y.CHARGE.TO

**Translated SQL**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST
WHERE LT_NFT_ID != 'EMCHQ' AND CHARGE_DATE >= 'VALUE123' AND CHARGE_DATE <= 'VALUE123'
```

---

#### SELECT #745 - Line 137

**File**: `BAN.E.NOF.ACCR.NO.FIN.TXN.b`

**Routine**: `BAN.E.NOF.ACCR.NO.FIN.TXN` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID NE '' AND LT.NFT.ID NE 'EMCHQ' AND CHARGE.DATE LE {Y.CHARGE.TO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID NE '' AND LT.NFT.ID NE 'EMCHQ' AND CHARGE.DATE LE VALUE123
```

**Table**: `AC.CHARGE.REQUEST`

**Fields** (2):
-  `CHARGE.DATE`  Type: D
-  `LT.NFT.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-  PATH-DEPENDENT: CASE Y.CHARGE.TO  NE "" (line 134)
-   INFO: LOCAL.REF fields found: LT.NFT.ID - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CHARGE.TO

**Translated SQL**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST
WHERE LT_NFT_ID != 'EMCHQ' AND CHARGE_DATE <= 'VALUE123'
```

---

#### SELECT #746 - Line 105

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD1`

**AS PER CODE**:
```
{SEL.CMD1} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND @ID EQ SAMPLE_VALUE AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>}
```

**Table**: `AND`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND

**Translated SQL**:
```sql
SELECT *
FROM AND
WHERE ID = 'SAMPLE_VALUE' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}'
```

---

#### SELECT #747 - Line 121

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ {Y.CATEG}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123
```

**Table**: `CHEQUE.TYPE`

**Fields** (1):
-  `CATEGORY`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CATEGORY' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CATEG

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_TYPE
WHERE CATEGORY = 'VALUE123'
```

---

#### SELECT #748 - Line 156

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD.ISS`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE {CHQ.TYPE.ID}{Z}{ID.AC}... AND CHEQUE.STATUS EQ 50
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE SAMPLE_VALUE.SAMPLE_VALUE... AND CHEQUE.STATUS EQ 50
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `CHEQUE.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE ID LIKE 'SAMPLE_VALUE.SAMPLE_VALUE%' AND CHEQUE_STATUS = '50'
```

---

#### SELECT #749 - Line 190

**File**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.ACTIVE.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ {Y.LINK.APP.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.LINK.APP.ID

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #750 - Line 120

**File**: `BAN.E.NOF.CHQBK.SUSP.ACT.b`

**Routine**: `BAN.E.NOF.CHQBK.SUSP.ACT` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 90 AND ACCOUNT.NO EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 90 AND ACCOUNT.NO EQ VALUE123
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `ACCOUNT.NO`  Type: I-PHYSICAL.REF
-  `CHEQUE.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: ACCOUNT.NO - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE CHEQUE_STATUS = '90' AND ACCOUNT_NO = 'VALUE123'
```

---

#### SELECT #751 - Line 227

**File**: `BAN.E.NOF.CHQBK.SUSP.ACT.b`

**Routine**: `BAN.E.NOF.CHQBK.SUSP.ACT` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {FIELDS(Y.CHEQ.ISS.ID,".",1)}.{FIELDS(Y.CHEQ.ISS.ID,".",2)}...  BY @ID
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.REGISTER.SUPPLEMENT WITH @ID LIKE {FIELDS(Y.CHEQ.ISS.ID,".",1)}.{FIELDS(Y.CHEQ.ISS.ID,".",2)}...  BY @ID
```

**Table**: `CHEQUE.REGISTER.SUPPLEMENT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FIELDS(Y.CHEQ.ISS.ID,".",1), FIELDS(Y.CHEQ.ISS.ID,".",2)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_REGISTER_SUPPLEMENT
WHERE ID LIKE '%{FIELDS(Y.CHEQ.ISS.ID,%'
ORDER BY ID ASC
```

---

#### SELECT #752 - Line 157

**File**: `BAN.E.NOF.CI.CHQBK.REQ.b`

**Routine**: `BAN.E.NOF.CI.CHQBK.REQ` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH LT.ISSUE.DATE GE {Y.ISSUE.FROM.DATE} AND LT.ISSUE.DATE LE {Y.ISSUE.TO.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH LT.ISSUE.DATE GE 19000101 AND LT.ISSUE.DATE LE 29991231
```

**Table**: `CHEQUE.ISSUE`

**Fields** (1):
-  `LT.ISSUE.DATE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,7>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.ISSUE.DATE - Physical fields in database (TAFJ compatible)

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE LT_ISSUE_DATE >= '19000101' AND LT_ISSUE_DATE <= '29991231'
```

---

#### SELECT #753 - Line 159

**File**: `BAN.E.NOF.CI.CHQBK.SUSP.b`

**Routine**: `BAN.E.NOF.CI.CHQBK.SUSP` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 89 AND LT.ISSUE.DATE GE {Y.ISSUE.FROM} AND LT.ISSUE.DATE LE {Y.ISSUE.TO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 89 AND LT.ISSUE.DATE GE VALUE123 AND LT.ISSUE.DATE LE VALUE123
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `LT.ISSUE.DATE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,7>`)
-  `CHEQUE.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-  PATH-DEPENDENT: CASE Y.ISSUE.FROM  NE "" (line 146)
-   INFO: LOCAL.REF fields found: LT.ISSUE.DATE - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ISSUE.FROM, Y.ISSUE.TO

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE CHEQUE_STATUS = '89' AND LT_ISSUE_DATE >= 'VALUE123' AND LT_ISSUE_DATE <= 'VALUE123'
```

---

#### SELECT #754 - Line 159

**File**: `BAN.E.NOF.CI.CHQBK.SUSP.b`

**Routine**: `BAN.E.NOF.CI.CHQBK.SUSP` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 89 AND LT.ISSUE.DATE LE {Y.ISSUE.TO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 89 AND LT.ISSUE.DATE LE VALUE123
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `LT.ISSUE.DATE`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,7>`)
-  `CHEQUE.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-  PATH-DEPENDENT: CASE Y.ISSUE.TO  NE "" (line 152)
-   INFO: LOCAL.REF fields found: LT.ISSUE.DATE - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ISSUE.TO

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE CHEQUE_STATUS = '89' AND LT_ISSUE_DATE <= 'VALUE123'
```

---

#### SELECT #755 - Line 82

**File**: `BAN.E.NOF.CONTFILE.LOG.b`

**Routine**: `BAN.E.NOF.CONTFILE.LOG` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CONTFILE.LOG WITH INDICADOR EQ ERROR AND USUARIO EQ {Y.USUARIO} AND USUARIO EQ {Y.USUARIO} AND APLICACION EQ {Y.APLICACION<1>} AND APLICACION EQ {Y.APLICACION<1>} AND PROCESS.DATE EQ {Y.TODAY} AND PROCESS.DATE EQ {Y.TODAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CONTFILE.LOG WITH INDICADOR EQ ERROR AND USUARIO EQ VALUE123 AND USUARIO EQ VALUE123 AND APLICACION EQ {Y.APLICACION<1>} AND APLICACION EQ {Y.APLICACION<1>} AND PROCESS.DATE EQ VALUE123 AND PROCESS.DATE EQ VALUE123
```

**Table**: `BAN.CONTFILE.LOG`

**Fields** (4):
-  `USUARIO`  Type: D
-  `PROCESS.DATE`  Type: D
-  `INDICADOR`  Type: D
-  `APLICACION`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USUARIO, Y.TODAY

**Translated SQL**:
```sql
SELECT *
FROM BAN_CONTFILE_LOG
WHERE INDICADOR = 'ERROR' AND USUARIO = 'VALUE123' AND USUARIO = 'VALUE123' AND APLICACION = '{Y.APLICACION<1>}' AND APLICACION = '{Y.APLICACION<1>}' AND PROCESS_DATE = 'VALUE123' AND PROCESS_DATE = 'VALUE123'
```

---

#### SELECT #756 - Line 110

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD1`

**AS PER CODE**:
```
{SEL.CMD1} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT  AND @ID EQ SAMPLE_VALUE AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>} AND @ID EQ {EB.Reports.getDRangeAndValue()<ACC.POS>}
```

**Table**: `AND`

**Fields** (1):
-  `@ID`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'AND' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AND

**Translated SQL**:
```sql
SELECT *
FROM AND
WHERE ID = 'SAMPLE_VALUE' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}' AND ID = '{EB.Reports.getDRangeAndValue()<ACC.POS>}'
```

---

#### SELECT #757 - Line 126

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ {Y.CATEG}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123
```

**Table**: `CHEQUE.TYPE`

**Fields** (1):
-  `CATEGORY`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CATEGORY' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.CATEG

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_TYPE
WHERE CATEGORY = 'VALUE123'
```

---

#### SELECT #758 - Line 161

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD.ISS`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE {CHQ.TYPE.ID}{Z}{ID.AC}... AND CHEQUE.STATUS EQ 30
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE SAMPLE_VALUE.SAMPLE_VALUE... AND CHEQUE.STATUS EQ 30
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `CHEQUE.STATUS`  Type: D
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE ID LIKE 'SAMPLE_VALUE.SAMPLE_VALUE%' AND CHEQUE_STATUS = '30'
```

---

#### SELECT #759 - Line 195

**File**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK.b`

**Routine**: `BAN.E.NOF.DELIVER.CHEQUE.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ {Y.LINK.APP.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.LINK.APP.ID

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #760 - Line 100

**File**: `BAN.E.NOF.NFT.NO.GEN.PRT.b`

**Routine**: `BAN.E.NOF.NFT.NO.GEN.PRT` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.BAN.NO.FIN.TXN.NO.PRT WITH @ID EQ {Y.TXNF}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.NO.FIN.TXN.NO.PRT WITH @ID EQ VALUE123
```

**Table**: `BAN.NO.FIN.TXN.NO.PRT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.TXNF

**Translated SQL**:
```sql
SELECT *
FROM BAN_NO_FIN_TXN_NO_PRT
WHERE ID = 'VALUE123'
```

---

#### SELECT #761 - Line 113

**File**: `BAN.E.NOF.NFT.NO.GEN.PRT.b`

**Routine**: `BAN.E.NOF.NFT.NO.GEN.PRT` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.BAN.NO.FIN.TXN.NO.PRT
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.NO.FIN.TXN.NO.PRT
```

**Table**: `BAN.NO.FIN.TXN.NO.PRT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_NO_FIN_TXN_NO_PRT
```

---

#### SELECT #762 - Line 133

**File**: `BAN.E.NOF.PS.CHQ.SUSP.b`

**Routine**: `BAN.E.NOF.PS.CHQ.SUSP` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE {Y.STOP.FRM.DATE} AND STOP.DATE LE {Y.STOP.TO.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE VALUE123 AND STOP.DATE LE VALUE123
```

**Table**: `PAYMENT.STOP`

**Fields** (1):
-  `STOP.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'STOP.DATE' used in condition (cannot create index on M fields)
-  PATH-DEPENDENT: CASE Y.STOP.FRM.DATE NE "" (line 120)
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.STOP.FRM.DATE, Y.STOP.TO.DATE

**Translated SQL**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE >= 'VALUE123' AND STOP_DATE <= 'VALUE123'
```

---

#### SELECT #763 - Line 133

**File**: `BAN.E.NOF.PS.CHQ.SUSP.b`

**Routine**: `BAN.E.NOF.PS.CHQ.SUSP` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE {Y.STOP.TO.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE VALUE123
```

**Table**: `PAYMENT.STOP`

**Fields** (1):
-  `STOP.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'STOP.DATE' used in condition (cannot create index on M fields)
-  PATH-DEPENDENT: CASE Y.STOP.TO.DATE  NE "" (line 126)
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.STOP.TO.DATE

**Translated SQL**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE <= 'VALUE123'
```

---

#### SELECT #764 - Line 141

**File**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Routine**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE {Y.FRM.DATE} AND STOP.DATE LE {Y.STOP.TO.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE GE VALUE123 AND STOP.DATE LE VALUE123
```

**Table**: `PAYMENT.STOP`

**Fields** (1):
-  `STOP.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'STOP.DATE' used in condition (cannot create index on M fields)
-  PATH-DEPENDENT: CASE Y.FRM.DATE NE "" (line 128)
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.FRM.DATE, Y.STOP.TO.DATE

**Translated SQL**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE >= 'VALUE123' AND STOP_DATE <= 'VALUE123'
```

---

#### SELECT #765 - Line 141

**File**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT.b`

**Routine**: `BAN.E.NOF.PS.CHQBK.SUSP.ACT` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE {Y.STOP.TO.DATE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.PAYMENT.STOP AND STOP.DATE LE VALUE123
```

**Table**: `PAYMENT.STOP`

**Fields** (1):
-  `STOP.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'STOP.DATE' used in condition (cannot create index on M fields)
-  PATH-DEPENDENT: CASE Y.STOP.TO.DATE  NE "" (line 134)
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: Y.STOP.TO.DATE

**Translated SQL**:
```sql
SELECT *
FROM PAYMENT_STOP
WHERE STOP_DATE <= 'VALUE123'
```

---

#### SELECT #766 - Line 75

**File**: `BAN.E.NOF.RECEIVED.DRAFT.b`

**Routine**: `BAN.E.NOF.RECEIVED.DRAFT` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.STOCK.ENTRY WITH CHEQUE.TYPE EQ {Y.CHQ.TYPE} AND LT.STATUS.DRAFT EQ REQ AND IN.OUT.DATE EQ {Y.FECHA}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.STOCK.ENTRY WITH CHEQUE.TYPE EQ VALUE123 AND LT.STATUS.DRAFT EQ REQ AND IN.OUT.DATE EQ VALUE123
```

**Table**: `STOCK.ENTRY`

**Fields** (3):
-  `IN.OUT.DATE`  Type: D
-  `CHEQUE.TYPE`  Type: D
-  `LT.STATUS.DRAFT`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CHEQUE.TYPE' used in condition (cannot create index on M fields)
-   INFO: LOCAL.REF fields found: LT.STATUS.DRAFT - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CHQ.TYPE, Y.FECHA

**Translated SQL**:
```sql
SELECT *
FROM STOCK_ENTRY
WHERE CHEQUE_TYPE = 'VALUE123' AND LT_STATUS_DRAFT = 'REQ' AND IN_OUT_DATE = 'VALUE123'
```

---

#### SELECT #767 - Line 77

**File**: `BAN.E.NOF.SUBLOTE.CHQ.RECEIVED.b`

**Routine**: `BAN.E.NOF.SUBLOTE.CHQ.RECEIVED` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.SUBLOTE.CHEQUE.BOOK WITH @ID LIKE {Y.DATE}...{Y.OFF.CODE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.SUBLOTE.CHEQUE.BOOK WITH @ID LIKE VALUE123...VALUE123
```

**Table**: `BAN.SUBLOTE.CHEQUE.BOOK`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.DATE, Y.OFF.CODE

**Translated SQL**:
```sql
SELECT *
FROM BAN_SUBLOTE_CHEQUE_BOOK
WHERE ID LIKE 'VALUE123%VALUE123'
```

---

#### SELECT #768 - Line 125

**File**: `BAN.E.NOF.SUBLOTE.CHQ.RECEIVED.b`

**Routine**: `BAN.E.NOF.SUBLOTE.CHQ.RECEIVED` (NOFILE (inferred))

**Variable**: `SEL.CMD2`

**AS PER CODE**:
```
SELECT F.CHEQUE.TYPE WITH LT.ID.TYPE.CHQ EQ {Y.LT.CHQ.CODE} AND LT.COUNTRY.COD EQ {Y.INI.COMP}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.TYPE WITH LT.ID.TYPE.CHQ EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

**Table**: `CHEQUE.TYPE`

**Fields** (2):
-  `LT.ID.TYPE.CHQ`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,8>`)
-  `LT.COUNTRY.COD`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,9>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: LT.ID.TYPE.CHQ, LT.COUNTRY.COD - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.LT.CHQ.CODE, Y.INI.COMP

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_TYPE
WHERE LT_ID_TYPE_CHQ = 'VALUE123' AND LT_COUNTRY_COD = 'VALUE123'
```

---

#### SELECT #769 - Line 90

**File**: `BAN.I.CK.NO.DUPL.ASSIGNED.b`

**Routine**: `BAN.I.CK.NO.DUPL.ASSIGNED` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.CHEQUE.REGISTER.ASSIGNED WITH @ID LIKE ...{Y.CHQ.ACC}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.CHEQUE.REGISTER.ASSIGNED WITH @ID LIKE ...VALUE123...
```

**Table**: `BAN.CHEQUE.REGISTER.ASSIGNED`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CHQ.ACC

**Translated SQL**:
```sql
SELECT *
FROM BAN_CHEQUE_REGISTER_ASSIGNED
WHERE ID LIKE '%VALUE123%'
```

---

#### SELECT #770 - Line 116

**File**: `BAN.S.GET.BAN.PARAM.ACCT.DETS.b`

**Routine**: `BAN.S.GET.BAN.PARAM.ACCT.DETS` (SUBROUTINE (inferred))

**Variable**: `SEL.PRODUCT`

**AS PER CODE**:
```
SELECT F.AA.PRODUCT.DESIGNER WITH @ID LIKE {Y.AA.PRODUCT.ID}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.PRODUCT.DESIGNER WITH @ID LIKE VALUE123...
```

**Table**: `AA.PRODUCT.DESIGNER`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AA.PRODUCT.ID

**Translated SQL**:
```sql
SELECT *
FROM AA_PRODUCT_DESIGNER
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #771 - Line 188

**File**: `BAPA.AA.BLOQUEO.EMBARGO.b`

**Routine**: `BAPA.AA.BLOQUEO.EMBARGO` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {AA.Framework.getC_aaloclinkedaccount()}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ C
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'C'
```

---

#### SELECT #772 - Line 331

**File**: `BAPA.AA.EMB.PARCIAL.REACT.CHG.b`

**Routine**: `BAPA.AA.EMB.PARCIAL.REACT.CHG` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.PRODUCT.DESIGNER WITH @ID LIKE {Y.PRODUCT}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.PRODUCT.DESIGNER WITH @ID LIKE VALUE123...
```

**Table**: `AA.PRODUCT.DESIGNER`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.PRODUCT

**Translated SQL**:
```sql
SELECT *
FROM AA_PRODUCT_DESIGNER
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #773 - Line 365

**File**: `BAPA.AA.EMB.PARCIAL.REACT.CHG.b`

**Routine**: `BAPA.AA.EMB.PARCIAL.REACT.CHG` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.PRODUCT.DESIGNER WITH @ID LIKE {Y.PARENT.PRODUCT}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.PRODUCT.DESIGNER WITH @ID LIKE VALUE123...
```

**Table**: `AA.PRODUCT.DESIGNER`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.PARENT.PRODUCT

**Translated SQL**:
```sql
SELECT *
FROM AA_PRODUCT_DESIGNER
WHERE ID LIKE 'VALUE123%'
```

---

#### SELECT #774 - Line 192

**File**: `BAPA.AA.UPDATE.LT.EMBARGO.b`

**Routine**: `BAPA.AA.UPDATE.LT.EMBARGO` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARR.ACCOUNT WITH @ID LIKE {ARRANGEMENT.ID}-...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.ACCOUNT WITH @ID LIKE C-...
```

**Table**: `AA.ARR.ACCOUNT`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_ACCOUNT
WHERE ID LIKE 'C-%'
```

---

#### SELECT #775 - Line 85

**File**: `BAPA.B.AC.LOCK.REVE.LOAD.b`

**Routine**: `BAPA.B.AC.LOCK.REVE.LOAD` (BATCH (inferred))

**Variable**: `Y.SEL.CMDD`

**AS PER CODE**:
```
SELECT {F.IN.DIR}
```

**SIMULATED AT RUNTIME**:
```
SELECT IN.DIR
```

**Table**: `IN.DIR`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'IN.DIR' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/IN.DIR
-   Unresolved variables: F.IN.DIR

**Translated SQL**:
```sql
SELECT *
FROM IN_DIR
```

---

#### SELECT #776 - Line 125

**File**: `BAPA.B.ACCOUNT.CLOSURE.b`

**Routine**: `BAPA.B.ACCOUNT.CLOSURE` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AC.BLOCK.CLOSURE WITH ACCOUNT.NUMBER EQ {ARRANGEMENT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

**SIMULATED AT RUNTIME**:
```
SELECT AC.BLOCK.CLOSURE WITH ACCOUNT.NUMBER EQ {ARRANGEMENT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}
```

**Table**: `AC.BLOCK.CLOSURE`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AC_BLOCK_CLOSURE
WHERE ACCOUNT_NUMBER = '{ARRANGEMENT.RECORD<AA.Framework.ArrangementSim.ArrLinkedApplId>}'
```

---

#### SELECT #777 - Line 44

**File**: `BAPA.B.ACCOUNT.CLOSURE.POST.b`

**Routine**: `BAPA.B.ACCOUNT.CLOSURE.POST` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.FILE.UPLOAD WITH UPLOAD.USER EQ '{Y.USER}' AND UPLOAD.TYPE EQ 'BAPA.ACC.CLOSE' AND DESCRIPTION EQ 'CIERRE.CUENTAS'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.FILE.UPLOAD WITH UPLOAD.USER EQ 'VALUE123' AND UPLOAD.TYPE EQ 'BAPA.ACC.CLOSE' AND DESCRIPTION EQ 'CIERRE.CUENTAS'
```

**Table**: `EB.FILE.UPLOAD`

**Fields** (3):
-  `DESCRIPTION`  Type: D
-  `UPLOAD.USER`  Type: D
-  `UPLOAD.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USER

**Translated SQL**:
```sql
SELECT *
FROM EB_FILE_UPLOAD
WHERE UPLOAD_USER = 'VALUE123' AND UPLOAD_TYPE = 'BAPA.ACC.CLOSE' AND DESCRIPTION = 'CIERRE.CUENTAS'
```

---

#### SELECT #778 - Line 25

**File**: `BAPA.B.ACCOUNT.CLOSURE.SELECT.b`

**Routine**: `BAPA.B.ACCOUNT.CLOSURE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.FILE.UPLOAD WITH UPLOAD.USER EQ '{Y.USER}' AND UPLOAD.TYPE EQ 'BAPA.ACC.CLOSE' AND DESCRIPTION EQ 'CIERRE.CUENTAS'
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.FILE.UPLOAD WITH UPLOAD.USER EQ 'VALUE123' AND UPLOAD.TYPE EQ 'BAPA.ACC.CLOSE' AND DESCRIPTION EQ 'CIERRE.CUENTAS'
```

**Table**: `EB.FILE.UPLOAD`

**Fields** (3):
-  `DESCRIPTION`  Type: D
-  `UPLOAD.USER`  Type: D
-  `UPLOAD.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.USER

**Translated SQL**:
```sql
SELECT *
FROM EB_FILE_UPLOAD
WHERE UPLOAD_USER = 'VALUE123' AND UPLOAD_TYPE = 'BAPA.ACC.CLOSE' AND DESCRIPTION = 'CIERRE.CUENTAS'
```

---

#### SELECT #779 - Line 32

**File**: `BAPA.B.INACTIVE.ACCT.CLOSURE.SELECT.b`

**Routine**: `BAPA.B.INACTIVE.ACCT.CLOSURE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS NE CLOSE UNAUTH PENDING.CLOSURE
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS NE CLOSE UNAUTH PENDING.CLOSURE
```

**Table**: `AA.ARRANGEMENT`

**Fields** (2):
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ARR_STATUS != 'CLOSE'
```

---

#### SELECT #780 - Line 105

**File**: `BAPA.B.PROCES.RAING.ACCT.b`

**Routine**: `BAPA.B.PROCES.RAING.ACCT` (BATCH (inferred))

**Variable**: `SEL.CMD.AC`

**AS PER CODE**:
```
SELECT ACCOUNT WITH ALT.ACCT.ID EQ {Y.ID.LINE}
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT WITH ALT.ACCT.ID EQ TF
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'TF'
```

---

#### SELECT #781 - Line 29

**File**: `BAPA.B.PROCES.RAING.ACCT.SELECT.b`

**Routine**: `BAPA.B.PROCES.RAING.ACCT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {IN.PATH}
```

**SIMULATED AT RUNTIME**:
```
SELECT SAMPLE_VALUE
```

**Table**: `SAMPLE_VALUE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   WARNING: Dictionary not found for table 'SAMPLE_VALUE' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/SAMPLE_VALUE
-   Unresolved variables: IN.PATH

**Translated SQL**:
```sql
SELECT *
FROM SAMPLE_VALUE
```

---

#### SELECT #782 - Line 39

**File**: `BAPA.B.UPD.ACCT.REACTIVE.SELECT.b`

**Routine**: `BAPA.B.UPD.ACCT.REACTIVE.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.BAPA.L.ACCOUNT.REACTIVATE WITH NEXT.VERIFY.DATE EQ {EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.BAPA.L.ACCOUNT.REACTIVATE WITH NEXT.VERIFY.DATE EQ TODAY
```

**Table**: `AA.BAPA.L.ACCOUNT.REACTIVATE`

**Fields** (1):
-  `NEXT.VERIFY.DATE`  Type: Unknown

**TAFJ Compatible**:  Yes

**Warnings**:
-   WARNING: Dictionary not found for table 'AA.BAPA.L.ACCOUNT.REACTIVATE' - Field validation skipped
-    Expected dictionary location: BASETABLE/STANDARD.SELECTION/AA.BAPA.L.ACCOUNT.REACTIVATE

**Translated SQL**:
```sql
SELECT *
FROM AA_BAPA_L_ACCOUNT_REACTIVATE
WHERE NEXT_VERIFY_DATE = 'TODAY'
```

---

#### SELECT #783 - Line 26

**File**: `BAPA.B.UPD.CHG.PENDING.SELECT.b`

**Routine**: `BAPA.B.UPD.CHG.PENDING.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BAN.AA.T.CHG.PENDING
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.AA.T.CHG.PENDING
```

**Table**: `BAN.AA.T.CHG.PENDING`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_AA_T_CHG_PENDING
```

---

#### SELECT #784 - Line 33

**File**: `BAPA.B.UPD.CHG.PENDING.SELECT.b`

**Routine**: `BAPA.B.UPD.CHG.PENDING.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS EQ AUTH
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT WITH PRODUCT.LINE EQ ACCOUNTS AND ARR.STATUS EQ AUTH
```

**Table**: `AA.ARRANGEMENT`

**Fields** (2):
-  `ARR.STATUS`  Type: D
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
WHERE PRODUCT_LINE = 'ACCOUNTS' AND ARR_STATUS = 'AUTH'
```

---

#### SELECT #785 - Line 213

**File**: `BAPA.EMB.PARCIAL.SUSP.CHG.b`

**Routine**: `BAPA.EMB.PARCIAL.SUSP.CHG` (Unknown)

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE {ARRANGEMENT.ID}-{ID.CHARGE.NEW}-...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AA.ARR.CHARGE WITH @ID LIKE C-{FIELD(ID.NEW,"-",2)}-...
```

**Table**: `AA.ARR.CHARGE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: FIELD(ID.NEW,"-",2)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARR_CHARGE
WHERE ID LIKE '%C-{FIELD(ID.NEW,%'
```

---

#### SELECT #786 - Line 104

**File**: `BAPA.RETURN.OVERDUE.CAPITAL.b`

**Routine**: `BAPA.RETURN.OVERDUE.CAPITAL` (Unknown)

**Variable**: `INTERNAL_SELECT_LINE_104`

**AS PER CODE**:
```
SELECT F.AC.BALANCE.TYPE
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.BALANCE.TYPE
```

**Table**: `AC.BALANCE.TYPE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AC_BALANCE_TYPE
```

---

#### SELECT #787 - Line 27

**File**: `BCM.B.LAST.CR.ACMST.SELECT.b`

**Routine**: `BCM.B.LAST.CR.ACMST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AA.ARRANGEMENT
```

**SIMULATED AT RUNTIME**:
```
SELECT AA.ARRANGEMENT
```

**Table**: `AA.ARRANGEMENT`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM AA_ARRANGEMENT
```

---

#### SELECT #788 - Line 63

**File**: `BPA.B.OD.DAYS.END.SELECT.b`

**Routine**: `BPA.B.OD.DAYS.END.SELECT` (BATCH (inferred))

**Variable**: `SELECT.BAN.ACCT.OVER`

**AS PER CODE**:
```
SELECT BAN.ACCT.OVERDRAWN.HIST WITH @ID LIKE ...{EB.SystemTables.getToday()}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.ACCT.OVERDRAWN.HIST WITH @ID LIKE ...TODAY
```

**Table**: `BAN.ACCT.OVERDRAWN.HIST`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BAN_ACCT_OVERDRAWN_HIST
WHERE ID LIKE '%TODAY'
```

---

#### SELECT #789 - Line 79

**File**: `BPA.B.OD.DAYS.END.SELECT.b`

**Routine**: `BPA.B.OD.DAYS.END.SELECT` (BATCH (inferred))

**Variable**: `SELECT.ACC.OVERDRAWN`

**AS PER CODE**:
```
SELECT ACCOUNT.OVERDRAWN WITH MOVED.NARR EQ CLEARED
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.OVERDRAWN WITH MOVED.NARR EQ CLEARED
```

**Table**: `ACCOUNT.OVERDRAWN`

**Fields** (1):
-  `MOVED.NARR`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'MOVED.NARR' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_OVERDRAWN
WHERE MOVED_NARR = 'CLEARED'
```

---

#### SELECT #790 - Line 185

**File**: `BPA.B.OD.DAYS.START.b`

**Routine**: `BPA.B.OD.DAYS.START` (BATCH (inferred))

**Variable**: `SEL.BAN.T`

**AS PER CODE**:
```
SELECT BAN.T.ACCT.LIM.OD WITH LIMIT.REFERENCE EQ {Y.LIST}
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.T.ACCT.LIM.OD WITH LIMIT.REFERENCE EQ VALUE123
```

**Table**: `BAN.T.ACCT.LIM.OD`

**Fields** (1):
-  `LIMIT.REFERENCE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.LIST

**Translated SQL**:
```sql
SELECT *
FROM BAN_T_ACCT_LIM_OD
WHERE LIMIT_REFERENCE = 'VALUE123'
```

---

#### SELECT #791 - Line 50

**File**: `BPA.B.OD.DAYS.START.SELECT.b`

**Routine**: `BPA.B.OD.DAYS.START.SELECT` (BATCH (inferred))

**Variable**: `SELECT.BAN.ACCT.OVER`

**AS PER CODE**:
```
SELECT BAN.ACCT.OVERDRAWN
```

**SIMULATED AT RUNTIME**:
```
SELECT BAN.ACCT.OVERDRAWN
```

**Table**: `BAN.ACCT.OVERDRAWN`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BAN_ACCT_OVERDRAWN
```

---

#### SELECT #792 - Line 74

**File**: `BPA.B.OD.DAYS.START.SELECT.b`

**Routine**: `BPA.B.OD.DAYS.START.SELECT` (BATCH (inferred))

**Variable**: `SELECT.ACC.OVERDRAWN`

**AS PER CODE**:
```
SELECT ACCOUNT.OVERDRAWN WITH MOVED.NARR NE CLEARED
```

**SIMULATED AT RUNTIME**:
```
SELECT ACCOUNT.OVERDRAWN WITH MOVED.NARR NE CLEARED
```

**Table**: `ACCOUNT.OVERDRAWN`

**Fields** (1):
-  `MOVED.NARR`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'MOVED.NARR' used in condition (cannot create index on M fields)

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT_OVERDRAWN
WHERE MOVED_NARR != 'CLEARED'
```

---

#### SELECT #793 - Line 31

**File**: `BPA.B.OD.MONTHS.YEAR.SELECT.b`

**Routine**: `BPA.B.OD.MONTHS.YEAR.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT BPA.OD.ACCT.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT BPA.OD.ACCT.DETAILS
```

**Table**: `BPA.OD.ACCT.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM BPA_OD_ACCT_DETAILS
```

---

#### SELECT #794 - Line 116

**File**: `BPA.CR.UPD.ACCT.OPE.b`

**Routine**: `BPA.CR.UPD.ACCT.OPE` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.PARAM.ACCOUNT WITH {Y.FIELD} EQ {Y.PRD.GROUP} AND {Y.VAL}.ACTIVITY EQ {Y.ACTIVITY}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PARAM.ACCOUNT WITH PRODUCT.GROUP EQ VALUE123 AND PG.ACTIVITY EQ ACCOUNTS-ESTADO-CTAOPERATIVA
```

**Table**: `BAN.PARAM.ACCOUNT`

**Fields** (2):
-  `PG.ACTIVITY`  Type: D
-  `PRODUCT.GROUP`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PG.ACTIVITY' used in condition (cannot create index on M fields)
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.GROUP' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.PRD.GROUP

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAM_ACCOUNT
WHERE PRODUCT_GROUP = 'VALUE123' AND PG_ACTIVITY = 'ACCOUNTS-ESTADO-CTAOPERATIVA'
```

---

#### SELECT #795 - Line 185

**File**: `BPA.E.BLD.AC.STMT.AMEND.b`

**Routine**: `BPA.E.BLD.AC.STMT.AMEND` (ENQUIRY (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #796 - Line 130

**File**: `BPA.E.NOF.ACCR.CHQBK.REQ.b`

**Routine**: `BPA.E.NOF.ACCR.CHQBK.REQ` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID EQ EMCHQ AND CHARGE.DATE GE {Y.CHARGE.FROM} AND CHARGE.DATE LE {Y.CHARGE.TO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID EQ EMCHQ AND CHARGE.DATE GE VALUE123 AND CHARGE.DATE LE VALUE123
```

**Table**: `AC.CHARGE.REQUEST`

**Fields** (2):
-  `CHARGE.DATE`  Type: D
-  `LT.NFT.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-  PATH-DEPENDENT: CASE Y.CHARGE.FROM  NE "" (line 121)
-   INFO: LOCAL.REF fields found: LT.NFT.ID - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CHARGE.FROM, Y.CHARGE.TO

**Translated SQL**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST
WHERE LT_NFT_ID = 'EMCHQ' AND CHARGE_DATE >= 'VALUE123' AND CHARGE_DATE <= 'VALUE123'
```

---

#### SELECT #797 - Line 130

**File**: `BPA.E.NOF.ACCR.CHQBK.REQ.b`

**Routine**: `BPA.E.NOF.ACCR.CHQBK.REQ` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID EQ EMCHQ AND CHARGE.DATE LE {Y.CHARGE.TO}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.AC.CHARGE.REQUEST WITH LT.NFT.ID EQ EMCHQ AND CHARGE.DATE LE VALUE123
```

**Table**: `AC.CHARGE.REQUEST`

**Fields** (2):
-  `CHARGE.DATE`  Type: D
-  `LT.NFT.ID`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,1>`)

**TAFJ Compatible**:  Yes

**Warnings**:
-  PATH-DEPENDENT: CASE Y.CHARGE.TO NE "" (line 127)
-   INFO: LOCAL.REF fields found: LT.NFT.ID - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CHARGE.TO

**Translated SQL**:
```sql
SELECT *
FROM AC_CHARGE_REQUEST
WHERE LT_NFT_ID = 'EMCHQ' AND CHARGE_DATE <= 'VALUE123'
```

---

#### SELECT #798 - Line 115

**File**: `BPA.E.NOF.DELIV.CHQBK.SUSP.b`

**Routine**: `BPA.E.NOF.DELIV.CHQBK.SUSP` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 50 AND ACCOUNT.NO EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 50 AND ACCOUNT.NO EQ VALUE123
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `ACCOUNT.NO`  Type: I-PHYSICAL.REF
-  `CHEQUE.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: ACCOUNT.NO - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE CHEQUE_STATUS = '50' AND ACCOUNT_NO = 'VALUE123'
```

---

#### SELECT #799 - Line 76

**File**: `BPA.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BPA.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ {Y.CATEGORY} AND LT.COUNTRY.COD EQ {Y.ID.COM}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

**Table**: `CHEQUE.TYPE`

**Fields** (2):
-  `LT.COUNTRY.COD`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,9>`)
-  `CATEGORY`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CATEGORY' used in condition (cannot create index on M fields)
-   INFO: LOCAL.REF fields found: LT.COUNTRY.COD - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CATEGORY, Y.ID.COM

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_TYPE
WHERE CATEGORY = 'VALUE123' AND LT_COUNTRY_COD = 'VALUE123'
```

---

#### SELECT #800 - Line 130

**File**: `BPA.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BPA.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ {Y.LINK.APP.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.LINK.APP.ID

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #801 - Line 146

**File**: `BPA.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BPA.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE {CHEQUE.TYPE.ID}.{ACCOUNT.ID}.{Y.CONSECUTIVO}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE SAMPLE_VALUE.SAMPLE_VALUE.VALUE123...
```

**Table**: `CHEQUE.ISSUE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.CONSECUTIVO

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE ID LIKE 'SAMPLE_VALUE.SAMPLE_VALUE.VALUE123%'
```

---

#### SELECT #802 - Line 115

**File**: `BRD.E.NOF.DELIV.CHQBK.SUSP.b`

**Routine**: `BRD.E.NOF.DELIV.CHQBK.SUSP` (NOFILE (inferred))

**Variable**: `SELECTION.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 50 AND ACCOUNT.NO EQ {Y.ACCOUNT}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH CHEQUE.STATUS EQ 50 AND ACCOUNT.NO EQ VALUE123
```

**Table**: `CHEQUE.ISSUE`

**Fields** (2):
-  `ACCOUNT.NO`  Type: I-PHYSICAL.REF
-  `CHEQUE.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: LOCAL.REF fields found: ACCOUNT.NO - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.ACCOUNT

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE CHEQUE_STATUS = '50' AND ACCOUNT_NO = 'VALUE123'
```

---

#### SELECT #803 - Line 89

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BRD.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ {Y.CATEGORY} AND LT.COUNTRY.COD EQ {Y.ID.COM}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.TYPE WITH CATEGORY EQ VALUE123 AND LT.COUNTRY.COD EQ VALUE123
```

**Table**: `CHEQUE.TYPE`

**Fields** (2):
-  `LT.COUNTRY.COD`  Type: I-LOCAL.REF (Formula: `LOCAL.REF<1,9>`)
-  `CATEGORY`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'CATEGORY' used in condition (cannot create index on M fields)
-   INFO: LOCAL.REF fields found: LT.COUNTRY.COD - Physical fields in database (TAFJ compatible)
-   Unresolved variables: Y.CATEGORY, Y.ID.COM

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_TYPE
WHERE CATEGORY = 'VALUE123' AND LT_COUNTRY_COD = 'VALUE123'
```

---

#### SELECT #804 - Line 136

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BRD.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD2`

**AS PER CODE**:
```
SELECT F.BRD.SUBTYPE.CHECK.BOOK WITH CHEQUE.TYPE EQ {Y.CHEQUE.TYPE}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BRD.SUBTYPE.CHECK.BOOK WITH CHEQUE.TYPE EQ VALUE123
```

**Table**: `BRD.SUBTYPE.CHECK.BOOK`

**Fields** (1):
-  `CHEQUE.TYPE`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM BRD_SUBTYPE_CHECK_BOOK
WHERE CHEQUE_TYPE = 'VALUE123'
```

---

#### SELECT #805 - Line 148

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BRD.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE {Y.CHEQUE.TYPE}.{Y.ACC.NUM}...
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CHEQUE.ISSUE WITH @ID LIKE VALUE123.VALUE123...
```

**Table**: `CHEQUE.ISSUE`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACC.NUM

**Translated SQL**:
```sql
SELECT *
FROM CHEQUE_ISSUE
WHERE ID LIKE 'VALUE123.VALUE123%'
```

---

#### SELECT #806 - Line 197

**File**: `BRD.E.NOF.REQUEST.CHECK.BOOK.b`

**Routine**: `BRD.E.NOF.REQUEST.CHECK.BOOK` (NOFILE (inferred))

**Variable**: `SEL.CMD.2`

**AS PER CODE**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ {Y.LINK.APP.ID}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.ACCOUNT WITH ALT.ACCT.ID EQ VALUE123
```

**Table**: `ACCOUNT`

**Fields** (1):
-  `ALT.ACCT.ID`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'ALT.ACCT.ID' used in condition (cannot create index on M fields)
-   Unresolved variables: Y.LINK.APP.ID

**Translated SQL**:
```sql
SELECT *
FROM ACCOUNT
WHERE ALT_ACCT_ID = 'VALUE123'
```

---

#### SELECT #807 - Line 79

**File**: `BRD.I.VALIDATE.CHECK.BOOK.TYPE.b`

**Routine**: `BRD.I.VALIDATE.CHECK.BOOK.TYPE` (VERSION (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.BAN.PARAMETERS.CHEQUE.BOOK WITH VALID.REQUEST EQ {FIELD(ID.NEW,'.',1)}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.BAN.PARAMETERS.CHEQUE.BOOK WITH VALID.REQUEST EQ {FIELD(ID.NEW,'.',1)}
```

**Table**: `BAN.PARAMETERS.CHEQUE.BOOK`

**Fields** (1):
-  `VALID.REQUEST`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'VALID.REQUEST' used in condition (cannot create index on M fields)
-   Unresolved variables: FIELD(ID.NEW,'.',1)

**Translated SQL**:
```sql
SELECT *
FROM BAN_PARAMETERS_CHEQUE_BOOK
WHERE VALID_REQUEST = '{FIELD(ID.NEW,'
```

---

#### SELECT #808 - Line 22

**File**: `BAN.CLEAR.SUS.ENTRIES.SELECT.b`

**Routine**: `BAN.CLEAR.SUS.ENTRIES.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {BAPAAAC.AccountingEntries.getFnLocalTable(1)}
```

**SIMULATED AT RUNTIME**:
```
SELECT LOCAL.TABLE
```

**Table**: `LOCAL.TABLE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LOCAL_TABLE
```

---

#### SELECT #809 - Line 22

**File**: `BAN.RAISE.SUS.ENTRIES.SELECT.b`

**Routine**: `BAN.RAISE.SUS.ENTRIES.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT {BAPAAAC.AccountingEntries.getFnLocalTable(1)}
```

**SIMULATED AT RUNTIME**:
```
SELECT LOCAL.TABLE
```

**Table**: `LOCAL.TABLE`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM LOCAL_TABLE
```

---

#### SELECT #810 - Line 113

**File**: `BANV.V.GET.SEE.CUS.PENDING.b`

**Routine**: `BANV.V.GET.SEE.CUS.PENDING` (VERSION (inferred))

**Variable**: `STMT.CUSTOMER`

**AS PER CODE**:
```
SELECT F.CUSTOMER WITH CUSTOMER.STATUS EQ 1 AND ACCOUNT.OFFICER NE 1 
```

**SIMULATED AT RUNTIME**:
```
SELECT F.CUSTOMER WITH CUSTOMER.STATUS EQ 1 AND ACCOUNT.OFFICER NE 1 
```

**Table**: `CUSTOMER`

**Fields** (2):
-  `ACCOUNT.OFFICER`  Type: D
-  `CUSTOMER.STATUS`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM CUSTOMER
WHERE CUSTOMER_STATUS = '1' AND ACCOUNT_OFFICER != '1'
```

---

#### SELECT #811 - Line 251

**File**: `BANV.ACLK.ACCOUNT.b`

**Routine**: `BANV.ACLK.ACCOUNT` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.ACCOUNT.DEBIT.PA}
```

**SIMULATED AT RUNTIME**:
```
SELECT AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.ACCOUNT.DEBIT.PA

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #812 - Line 25

**File**: `BANV.ACLK.ACCOUNT.SELECT.b`

**Routine**: `BANV.ACLK.ACCOUNT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BANV.CUS.ACC.PARAM
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BANV.CUS.ACC.PARAM
```

**Table**: `EB.BANV.CUS.ACC.PARAM`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BANV_CUS_ACC_PARAM
```

---

#### SELECT #813 - Line 73

**File**: `BANV.E.NOF.PAYMENT.DETAILS.b`

**Routine**: `BANV.E.NOF.PAYMENT.DETAILS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BANV.PAYMENT.LOAN.DETAILS
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BANV.PAYMENT.LOAN.DETAILS
```

**Table**: `EB.BANV.PAYMENT.LOAN.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BANV_PAYMENT_LOAN_DETAILS
```

---

#### SELECT #814 - Line 82

**File**: `BANV.E.NOF.PAYMENT.DETAILS.b`

**Routine**: `BANV.E.NOF.PAYMENT.DETAILS` (NOFILE (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT F.EB.BANV.PAYMENT.LOAN.DETAILS WITH @ID LIKE ...{EB.Reports.getDRangeAndValue()<DATE.POS>}
```

**SIMULATED AT RUNTIME**:
```
SELECT F.EB.BANV.PAYMENT.LOAN.DETAILS WITH @ID LIKE ...{EB.Reports.getDRangeAndValue()<DATE.POS>}
```

**Table**: `EB.BANV.PAYMENT.LOAN.DETAILS`

**Fields** (1):
-  `@ID`  Type: D

**TAFJ Compatible**:  Yes

**Translated SQL**:
```sql
SELECT *
FROM EB_BANV_PAYMENT_LOAN_DETAILS
WHERE ID LIKE '%{EB.Reports.getDRangeAndValue()<DATE.POS>}'
```

---

#### SELECT #815 - Line 134

**File**: `BANV.FT.DEBIT.ACCOUNT.b`

**Routine**: `BANV.FT.DEBIT.ACCOUNT` (Unknown)

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ {Y.AC.DEB.PA}
```

**SIMULATED AT RUNTIME**:
```
SELECT AC.LOCKED.EVENTS WITH ACCOUNT.NUMBER EQ VALUE123
```

**Table**: `AC.LOCKED.EVENTS`

**Fields** (1):
-  `ACCOUNT.NUMBER`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   Unresolved variables: Y.AC.DEB.PA

**Translated SQL**:
```sql
SELECT *
FROM AC_LOCKED_EVENTS
WHERE ACCOUNT_NUMBER = 'VALUE123'
```

---

#### SELECT #816 - Line 25

**File**: `BANV.FT.DEBIT.ACCOUNT.SELECT.b`

**Routine**: `BANV.FT.DEBIT.ACCOUNT.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BANV.DEBIT.ACLK.DETAIL
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BANV.DEBIT.ACLK.DETAIL
```

**Table**: `EB.BANV.DEBIT.ACLK.DETAIL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BANV_DEBIT_ACLK_DETAIL
```

---

#### SELECT #817 - Line 25

**File**: `BANV.FT.PAYMENT.LOAN.POST.SELECT.b`

**Routine**: `BANV.FT.PAYMENT.LOAN.POST.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT {FN.EB.BANV.PAYMENT.LOAN.DETAILS}
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BANV.PAYMENT.LOAN.DETAILS
```

**Table**: `EB.BANV.PAYMENT.LOAN.DETAILS`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)
-   Unresolved variables: FN.EB.BANV.PAYMENT.LOAN.DETAILS

**Translated SQL**:
```sql
SELECT *
FROM EB_BANV_PAYMENT_LOAN_DETAILS
```

---

#### SELECT #818 - Line 25

**File**: `BANV.FT.PAYMENT.LOAN.SELECT.b`

**Routine**: `BANV.FT.PAYMENT.LOAN.SELECT` (BATCH (inferred))

**Variable**: `SEL.CMD`

**AS PER CODE**:
```
SELECT EB.BANV.DEBIT.ACLK.DETAIL
```

**SIMULATED AT RUNTIME**:
```
SELECT EB.BANV.DEBIT.ACLK.DETAIL
```

**Table**: `EB.BANV.DEBIT.ACLK.DETAIL`

**TAFJ Compatible**:  Yes

**Warnings**:
-   PERFORMANCE: No WHERE clause - Full table scan (SELECT without WITH clause)

**Translated SQL**:
```sql
SELECT *
FROM EB_BANV_DEBIT_ACLK_DETAIL
```

---

#### SELECT #819 - Line 28

**File**: `BANV.B.CUADRO.DEL.ACCT.CLOSED.SELECT.b`

**Routine**: `BANV.B.CUADRO.DEL.ACCT.CLOSED.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT FBCW.ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ {LAST.WORKING.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT FBCW.ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ SAMPLE_VALUE
```

**Table**: `FBCW.ACCOUNT.CLOSED`

**Fields** (1):
-  `ACCT.CLOSE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBCW.' detected - Using dictionary from core table 'ACCOUNT.CLOSED'
-   Unresolved variables: LAST.WORKING.DAY

**Translated SQL**:
```sql
SELECT *
FROM FBCW_ACCOUNT_CLOSED
WHERE ACCT_CLOSE_DATE = 'SAMPLE_VALUE'
```

---

#### SELECT #820 - Line 21

**File**: `BANV.B.CUADRO.DPF.CLOSED.SELECT.b`

**Routine**: `BANV.B.CUADRO.DPF.CLOSED.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT FBCW.ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ {LAST.WORKING.DAY}
```

**SIMULATED AT RUNTIME**:
```
SELECT FBCW.ACCOUNT.CLOSED WITH ACCT.CLOSE.DATE EQ SAMPLE_VALUE
```

**Table**: `FBCW.ACCOUNT.CLOSED`

**Fields** (1):
-  `ACCT.CLOSE.DATE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
-   INFO: T24 company prefix 'FBCW.' detected - Using dictionary from core table 'ACCOUNT.CLOSED'
-   Unresolved variables: LAST.WORKING.DAY

**Translated SQL**:
```sql
SELECT *
FROM FBCW_ACCOUNT_CLOSED
WHERE ACCT_CLOSE_DATE = 'SAMPLE_VALUE'
```

---

#### SELECT #821 - Line 28

**File**: `BANV.B.CUADRO.DPF.SELECT.b`

**Routine**: `BANV.B.CUADRO.DPF.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT FBCW.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'DEPOSITS'
```

**SIMULATED AT RUNTIME**:
```
SELECT FBCW.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'DEPOSITS'
```

**Table**: `FBCW.AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)
-   INFO: T24 company prefix 'FBCW.' detected - Using dictionary from core table 'AA.CUSTOMER.ARRANGEMENT'

**Translated SQL**:
```sql
SELECT *
FROM FBCW_AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'DEPOSITS'
```

---

#### SELECT #822 - Line 25

**File**: `BANV.B.CUADRO.SELECT.b`

**Routine**: `BANV.B.CUADRO.SELECT` (BATCH (inferred))

**Variable**: `SELECT.STATEMENT`

**AS PER CODE**:
```
SELECT FBCW.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'LENDING'
```

**SIMULATED AT RUNTIME**:
```
SELECT FBCW.AA.CUSTOMER.ARRANGEMENT WITH PRODUCT.LINE EQ 'LENDING'
```

**Table**: `FBCW.AA.CUSTOMER.ARRANGEMENT`

**Fields** (1):
-  `PRODUCT.LINE`  Type: D

**TAFJ Compatible**:  Yes

**Warnings**:
- CRITICAL PERFORMANCE: Multivalue field 'PRODUCT.LINE' used in condition (cannot create index on M fields)
-   INFO: T24 company prefix 'FBCW.' detected - Using dictionary from core table 'AA.CUSTOMER.ARRANGEMENT'

**Translated SQL**:
```sql
SELECT *
FROM FBCW_AA_CUSTOMER_ARRANGEMENT
WHERE PRODUCT_LINE = 'LENDING'
```

---

