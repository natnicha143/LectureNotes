# 8.1 Python & Excel
The openpyxl module allows python programs to read and modify Excel spreadsheet files. 
* The sheet the user is currently viewing (or last viewed) is called the active sheet. 

['A1']['B1'] etc..

Opens an excel workbook and accesses worksheet by name:
```python
import openpyxl
wb = openpyxl.load_workbook('Stocks.xlsx')
print(wb.get_sheet_names())
['Google', 'IBM', 'Microsoft']

sheet = wb.get_sheet_by_name('Microsoft')
sheet
<Worksheet "Microsoft">

type(sheet)
<class 'openpyxl.worksheet.worksheet.Worksheet'>
sheet.title
'Microsoft'

anotherSheet = wb.active
anotherSheet
<Worksheet "Microsoft">
```





# 8.2 NumPy and SciPy