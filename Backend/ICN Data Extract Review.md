
See `~resources/general/ICN Client/capability-data-extact-for-navigator.xlsx` 

## Data Quality Challenges

### Missing Data

Missing address / address details:

![[Pasted image 20250906175409.png]]
 

Almost duplicate data (only differers by Organisation Capability ID)

![[Pasted image 20250906180715.png]]

Weird duplicate with Sector Mapping ID

![[Pasted image 20250906203458.png]]

Empty Item ID records (line 13582 to end)

![[Pasted image 20250906181335.png]]

Test entries?

![[Pasted image 20250906190918.png]]

![[Pasted image 20250906190903.png]]

![[Pasted image 20250906190831.png]]
## Stats

### ID Ranges

| ID                  | Low           | High          | Range  | Duplicates |
| ------------------- | ------------- | ------------- | ------ | ---------- |
| `Detailed Item ID`  | `DITM-000002` | `DITM-000530` | ~500   | NO         |
| `Item ID`           | `ITM-001397`  | `ITM-010000`  | ~9000  | YES        |
| `Org Capability`    | `OC-000002`   | `OC-018243`   | ~20000 |            |
| `Sector Mapping ID` | `SM-00000`    | `SM-000523`   | ~500   | NO         |

### Other

* Appears to be provided in descending order of `Detailed Item ID`
* `Orgnisation Name` has been anonymised (we could auto generate some random ones)
