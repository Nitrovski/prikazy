# prikazy
Uzitecne prikazy

/home/sas/security_updates/java/

/sas/sashome/

./install.sh "/sas/sashome"

# zapnutí nebo vypnutí služeb

/sas/sasconfig/Lev1/sas.servers start/stop /status

# zapnutí metadata serveru

/sas/sasconfig/Lev1/SASMeta/MetadataServer/MetadataServer.sh start

# Zkontrolovat dokumentaci u hotfixů a zjistit který má možnost Configurace - dá se zjistit v IMPORTANT NOTES v dokumentaci jednotlivých hotfixu

# vypíše produkty co je na serveru nainstalovany

/sas/sashome/InstallMisc/InstallLogs/DeploymentRegistry.txt+ - 

# Vygeneruje nové DeploymentRegistry.txt 

cd /sas/sashome/deploymntreg/
java -jar sas.tools.viewregistry.jar


# Zkopírování dat z jednoho serveru na druhý
scp sas-security-update-2023-03-M7.zip sas@sas01prod.id.prod:/sas/sashome/InstallMisc/HotFixes/SecurityUpdates/

# Viya 3.5
/sas/viya/config/var/ logy

# SAS Java umístění
/sas/sashome/SASPrivateJavaRuntimeEnvironment/9.4/jre/bin/java

# power shell
přejmenování textu v datech

(Get-Content C:\Users\czetov\curl_script.txt).replace('../DEPLOY_SASHFADD_2023_6_02_15.57.47', 'C:/users/czetov/hotfixy') | Set-Content C:\Users\czetov\curl_script2.txt

# Zjištění verze oracle
 yum list installed | grep instantclient

# Jak spouštět SAS 9.4 služby ve správném pořadí

Začít na 01 serveru meta data

1: 
/sas/sasconfig/Lev1/sas.servers.pre start / status / stop

2:
Zapnout SAS Metadata Server
a pak 
/sas/sasconfig/Lev1/sas.servers.mid start

teď se dají zapnout 02 a 03 servery a pak už 

3:
/sas/sasconfig/Lev1/sas.servers.mid start

# V případě že neprojde Redeploy web app, tak zkusit pročistit cache a logy - udělat pak redeploy znovu
