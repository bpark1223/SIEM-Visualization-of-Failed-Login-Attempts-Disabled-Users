# SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users
<h2>Description</h2>
In this project, I will be visualizing failed Windows login attempts against disabled users. </p>
<h2>Utilities Used</h2>
- <b>Elastic</b> </p>
- <b>Virtual Box</b>
<h2>Walk-through</h2>
</p> 1. After logging into my Elastic account, I click on the edit option for the preconfigured "SOC-Alerts" dashboard
<img width="1436" alt="Screenshot 2024-06-25 at 3 13 42 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/22ccd194-6065-4ad1-ba0a-121dea49d479"> 
</p> 2. I then click on the "create visualization button" on the left hand side of the page </p> 
<img width="1430" alt="Screenshot 2024-06-25 at 6 03 20 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/b3347b89-cb9f-4a99-b0c7-465926428047">
</p> 3. I then click on the "filter" option to filter the data before creating a graph. I need to output only those ID's that match failed login attempts on Windows systems. Therefore, under field, I put event.code, under operator, I put is, and under value, 4625. </p>
<img width="1426" alt="Screenshot 2024-06-25 at 6 12 36 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/e30067da-d170-4d37-b1a4-241f8ed9832d">
</p> 4. To specify even further that the resulting failed Windows login attempts must be due to disabled accounts, the winlog.event_SubStatus (reason for failure) must have a value of "0xc0000072" (disabled accounts) </p>
<img width="1415" alt="Screenshot 2024-06-25 at 6 17 18 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/175443e9-7230-44ef-89c3-820a44aa59de">
</p>  5. I specify the index (data set) that will be used. In this case, I am using Windows.
<img width="889" alt="Screenshot 2024-06-25 at 6 18 41 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/183fad05-a6ef-4ef1-b5e2-0223b7dd955d">
</p> 6. I use the search bar (under the "index" option) to verify that the field "user.name.keyword" and "host.hostname.keyword" (to show how the machine where the failed logon attempt occurred) are present and discovered within our selected data set. </p>
<img width="327" alt="Screenshot 2024-06-25 at 6 29 18 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/8549ac29-f29d-4499-85b8-d49001b0a8a1">
</p> 7. I selected "table" as my visualization type. </p>
<img width="1339" alt="Screenshot 2024-06-25 at 6 30 24 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/f2c87cea-c3fe-4c03-9c25-fa1a989aba03">
</p> 8. After clicking table, I proceed to click on the "rows" option which allows me to choose the data elements I want to include in the table view. </p>
<img width="1429" alt="Screenshot 2024-06-25 at 6 41 31 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/cbb76189-697f-41d8-933b-e36cdd2328d5">
<img width="318" alt="Screenshot 2024-06-25 at 6 47 56 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/737dccbd-9ae4-441d-aaeb-80a696bb1cc5">
</p> 9. I close the "Rows" window and proceed to enter the "Metrics" configuration where I select count as the function. 
<img width="319" alt="Screenshot 2024-06-25 at 6 48 52 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/90257e7f-1cec-439b-be43-edd048a0b4fd">
</p> I have created a display of the hostname or machine name alongside the count of failed logon attempts
<img width="1425" alt="Screenshot 2024-06-25 at 6 52 24 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/95154c9d-53d8-4489-9b22-fce71b3fcc8c">
</p> What we see now is as follows: </p>
</p> 1. The disabled user whose credentials generated the failed logon attempt event.</p>
</p> 2. The machine on which the logon attempt occurred.</p>
</p> 3. The number of times the event has occurred (based on the specified time frame or the entire data set, depending on the settings).</p>.


