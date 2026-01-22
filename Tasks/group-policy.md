# Setting GPO policy
This document outlines the steps to set up a shared wallpaper for the **Engineering Department** in the IT Home Lab
```
Ticket request: Set up a wallpaper for the Engineering Department
```
##### 1. Dowload or create a wallpaper
- Create a wallpaper and saved as jpeg on windows server.

##### 2. Copy as UNC path
- open Server Manager → File and Storage Services → Shares → NETLOGON → Openshare
- find the jpeg image and click 'copy as path'
<img width="865" height="662" alt="Screenshot 2026-01-22 123419" src="https://github.com/user-attachments/assets/b0541b45-3b8f-4ec5-a5d1-a9bd3ccdf1f8" />

##### 3. Create a GPO 
- Open Group Policy Management
- Navigate to Engineering Department OU → New → Create GPO in this domain & Link it here
- GPO name: SetEngineeringWallpaper
<img width="812" height="569" alt="Screenshot 2026-01-22 123600" src="https://github.com/user-attachments/assets/ec27e514-ad28-416c-a677-59e2496f21b8" />

##### 4. Adding Wallpaper
- Select Edit → User Configuration → Polices → Administrative Temp → Desktop → Desktop Wallpaper
- Select 'Enabled' and paste the UNC path of the image.
- Confimed
<img width="704" height="639" alt="Screenshot 2026-01-22 131958" src="https://github.com/user-attachments/assets/7f506f8f-a331-4156-9d2d-84745818bbb5" />

##### 5. Verification
- login as engineering user on CLIENT01.
- Conform that the wallpaper is applied!
<img width="996" height="663" alt="Screenshot 2026-01-22 132453" src="https://github.com/user-attachments/assets/80af5bba-d119-47c7-9f05-8f8e68537671" />
