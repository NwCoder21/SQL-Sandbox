# Installation

<!-- Lesson 9 - Installation: START HERE!-->

Firstly, will install MySQL Server. We can then interact with it in different ways.

* When we can interact with it in different ways. Via the terminal/command line.  
* MySQL Workbench - this allows me to write my queries in files, save them in files, and then execute them when i'm ready. Can't do this when using the command line. 

---

Go to (https://dev.mysql.com/doc/refman/8.0/en/windows-installation.html)

---

![image](https://user-images.githubusercontent.com/107522496/204855345-48633f5c-eb9b-4210-b71c-71dd35531861.png)

I will be using the MySQL Installer Method. Click on the (https://dev.mysql.com/downloads/installer/) link

---

![image](https://user-images.githubusercontent.com/107522496/204856030-bbfc0fce-fe1e-458d-8c10-944285c3247e.png)

Click on the `Download` button 

---

![image](https://user-images.githubusercontent.com/107522496/204856311-88503ace-4395-4109-b4fa-628eda20f1fe.png)

No need to log in, just start the download.

---

![image](https://user-images.githubusercontent.com/107522496/205020678-12884f5b-b6db-4622-8ad4-555797de2069.png)

Click on `Custom` and then `Next`

---

![image](https://user-images.githubusercontent.com/107522496/205021299-c804a669-d7cc-49f9-b9f9-63a2f03c0987.png)

Expand the `MySQL Servers` section and click on the latest version (at the time of writing this, it is version 8.0.31). and pass it over to the `Products to be Installed` section by clicking on the right green arrow. 

---

The same for MySQL Workbench and Shell 

![image](https://user-images.githubusercontent.com/107522496/205022579-a1c874c0-9a00-4e93-b787-164fadb9d07b.png)

![image](https://user-images.githubusercontent.com/107522496/205022386-439d88a5-ff3a-49eb-bcf8-62f6825571cc.png)

---

![image](https://user-images.githubusercontent.com/107522496/205022995-5c399c8f-7a42-4349-b657-3cb3272cfd56.png)

And then expand `MySQL Connectors` - and select `Connector/ODBC` and move it over to the right 

---

![image](https://user-images.githubusercontent.com/107522496/205024249-2f0fb850-1d55-47be-b3ff-3fe22619b826.png)

This is what it will look like. Once done, ckick on `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205025251-c9f8b949-0043-4473-a249-b0b00cbe577f.png)

Click on `Execute` to download the products. Once downloaded, click on `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205025443-54e86335-75de-4277-83c5-458b3409bcc1.png)

Then click on Execute to install the products 

---

# Product Cnfiguration 

![image](https://user-images.githubusercontent.com/107522496/205025979-e588333d-a785-4ab5-9c27-ec212fd80bb8.png)

Then it is time to configure the products.

---

![image](https://user-images.githubusercontent.com/107522496/205026144-a030d2c9-9010-46cc-a9f0-d91cee0d7d07.png)

For the server configuration, leave as it is and click on `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205026365-85ea230c-ba32-4624-8cf2-62226d62d40c.png)

Important: leave this part checked and click on `Next`

---

![image](https://user-images.githubusercontent.com/107522496/205026793-536adf33-cd15-42ac-b0f1-c4f1b2f7e0c8.png)

Add a password for the root account and then click on `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205027950-a3c35cb5-ed0e-497f-96b9-2b38133f6a46.png)

Here, will tick the box for `Configure MySQL Server as a Windows Service` and the `Start the MySQL Server at System Startup` and `Standard System Account`

Then click `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205028226-1b10a4b5-8c09-4734-adb3-f093d95b7671.png)

Select `grant full access to the user` option and then `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205028663-b51db69a-edaf-4a57-9d1b-4510e3ebc3b9.png)

And then click on `Execute`, and once done, click on `Finish`

![image](https://user-images.githubusercontent.com/107522496/205028714-8a37d2af-4722-489f-8e41-017b9475c6d4.png)

---

![image](https://user-images.githubusercontent.com/107522496/205028990-9fa89a00-8c19-4d94-a33c-e2762dc7f928.png)

Then some more configuration will be displayed. Click on `Next`

---

![image](https://user-images.githubusercontent.com/107522496/205029416-8052c952-3d6a-41fe-aa3a-396cbf430277.png)

Here it will ask for your username. Can leave as root and enter the password we created previously. Then click `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205029577-26a359d6-8678-4738-8024-1a79b6685225.png)

Click on `Execute`. Once done, click on `Finish`.

---

![image](https://user-images.githubusercontent.com/107522496/205029866-f90eacae-6a4c-45e9-9c0b-f6891374bad0.png)

Click on `Next`.

---

![image](https://user-images.githubusercontent.com/107522496/205030198-5a083a81-f1e6-4158-9f69-f04a5482b1ed.png)

Click on `Finish`.

---

![image](https://user-images.githubusercontent.com/107522496/205030446-d832498e-745e-4b11-84ce-d3ff90237571.png)

Keep both options slected and click on `Finish`.

---

# Starting up the Command Line Client 

![image](https://user-images.githubusercontent.com/107522496/205031357-7c47290b-5adb-421b-899c-81334cc11c54.png)

Search for the MySQL Command Line Client.

![image](https://user-images.githubusercontent.com/107522496/205031550-a4c805ab-73b8-4771-8447-7ce2f297357d.png)

Once inside, will ask for the root password set up in the initial set-up process. Once entered, you will have command line access.

---

![image](https://user-images.githubusercontent.com/107522496/205032389-a545b528-0e0e-46c2-abbf-2d170a478f6a.png)

Can now run SQL commands from the command line. To quit, enter `quit;`

---

# Writiing Code 

To be ableto write and save code, click here: 

![image](https://user-images.githubusercontent.com/107522496/205033185-ecc82217-e62a-4b6e-af16-530a294dba4e.png)

---

![image](https://user-images.githubusercontent.com/107522496/205033354-f4a127c8-a8e2-44d2-83c1-c021c3cc76ef.png)

And then enter yoour root password:

---

![image](https://user-images.githubusercontent.com/107522496/205033586-512eb911-f391-45f1-9127-ed43b32cd481.png)

This will then connect you to your MySQL Server. 

---

![image](https://user-images.githubusercontent.com/107522496/205034711-89958fd6-f60e-46b3-94fa-f800db5a033e.png)


Here, I am testing a command. To execute the program, click on the execute button (the lightning symbol, red box in above screenshot).
The Results Grid, the blue box, is the area where the results are output.

---

![image](https://user-images.githubusercontent.com/107522496/205035598-d68604dd-2342-421d-a29e-4fff69065269.png)

To only run the command where the cursor is placed, click on the lightening bolt with a cursor symbol on it. 

---

# Saving File 

To save the file, go to `File` and select `Sace Script`












