# anteo-external-api
Api available to Anteo customers, to get their own data in Anteo structured as json.
## Accessibility
You need a Bearer token provided by Anteo for your company.
Contact info for token: support@anteo.no
## External api v01
**Url:** https://admin.anteo.no/service/extapi/v01/
### Endpoints
**sites**  
> **Parameters:** None  
**Returns:** List of every site owned by company

**fishctrlcounttypes**  
> **Parameters:**   
from: Date on format yyyy-mm-dd. Defaults to first day in previous month       
to: Date on format yyyy-mm-dd. Defaults to last day in previous month    
Maximum time span for query is 90 days.  
**Returns:**  
List of every count type delivered in selected time span, included list of sites per count type.  
```
[
	{
		"countTypeId": "autopsy",
		"countTypeName": "Obduksjon",
		"numReports": "17",
		"siteIds": [
			"xxxxx",
			"xxxxx",
			"xxxxx"
		]
	}
]  
```
**fishctrlresults**  
> **Parameters:**   
countTypeId: (*Required*) countTypeId fetched from *fishctrlcounttypes*  
siteId:  (*Required*)  siteId fetched from siteIds array in *fishctrlcounttypes*     
from: Date on format yyyy-mm-dd. Defaults to first day in previous month       
to: Date on format yyyy-mm-dd. Defaults to last day in previous month   
Maximum time span for query is 90 days.  
**Returns:**  
Complete list of reports with selected count type, including all data for selected site in selected time span, included from and to date.

**fishctrlmatrixcsv**  
> **Parameters:**       
from: Optional Date on format yyyy-mm-dd.     
to: Optional Date on format yyyy-mm-dd.  
**Returns:**  
Named csv-file with all FishCtrl results for chosen time span
