# Install Odoo in MAC OS

This script is based on the install script from Yenthe Van Ginneken (https://github.com/Yenthe666/InstallScript)
This script handle the installation of Odoo under MAC OS

## Installation procedure

##### 1. Download the script:
```
https://raw.githubusercontent.com/OthmaneGhandi/OdooInstallScriptMac/master/odoo_install.sh
```
##### 2. Modify the parameters as you wish.
There are a few things you can configure, this is the most used list:<br/>
```OE_USER``` will be the username for the system user.<br/>
```INSTALL_WKHTMLTOPDF``` set to ```False``` if you do not want to install Wkhtmltopdf, if you want to install it you should set it to ```True```.<br/>
```OE_PORT``` is the port where Odoo should run on, for example 8069.<br/>
```OE_VERSION``` is the Odoo version to install, for example ```13.0``` for Odoo V13.<br/>
```IS_ENTERPRISE``` will install the Enterprise version on top of ```13.0``` if you set it to ```True```, set it to ```False``` if you want the community version of Odoo 13.<br/>
```OE_SUPERADMIN``` is the master password for this Odoo installation.<br/>

#### 3. Make the script executable
```
sudo chmod +x odoo_install.sh
```
##### 4. Execute the script:
```
sudo ./odoo_install.sh
```
##### 5. Manual modifications: (NB : change ${OE_CONFIG} with your config name)
=> Add the password, that you entered for the user when the script was running,inside your conf file : /etc/${OE_CONFIG}.conf
```
db_password = False -> your_password
```
=> Give privileges accesses to your user : (NB : change ${OE_USER} with your user name)
 ```
psql -U postgres
ALTER USER ${OE_USER} WITH SUPERUSER CREATEDB CREATEROLE CREATEUSER LOGIN;
```
