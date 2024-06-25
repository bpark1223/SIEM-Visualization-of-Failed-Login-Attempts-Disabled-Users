# SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users
</p> In this project, I will be visualizing failed login attempts against disabled Windows users </p>
</p> 1. After logging in, I click on the edit option for the preconfigured "SOC-Alerts" dashboard
<img width="1436" alt="Screenshot 2024-06-25 at 3 13 42 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/22ccd194-6065-4ad1-ba0a-121dea49d479"> 
</p> 2. I use the filter option to indicate the data set that I will use which is Windows. Also, I need to output only those ID's that match failed login attempts on Windows systems. Therefore, under field, I put event.code, under operator, I put is, and under value, 4025.
<img width="1440" alt="Screenshot 2024-06-25 at 3 29 50 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/13d18c0e-2c58-49ac-ba74-80149df00b33"> </p>
</p> 3. To specify even further that the failed Windows login attempts must be due to disabled accounts, the winlog.event_SubStatus (reason for failure) must have a value of "0xc0000072"
<img width="1439" alt="Screenshot 2024-06-25 at 3 35 16 PM" src="https://github.com/bpark1223/SIEM-Visualization-of-Failed-Login-Attempts-Disabled-Users/assets/77799235/60b6a987-7434-4e37-9728-7fe29998c2c1">
