# prikazy
Uzitecne prikazy

/home/sas/security_updates/java/

/sas/sashome/

./install.sh "/sas/sashome"

# VIM příkazy

Uzitecne prikazy:      vi - edituju soubor,

/ - vyhledavam

esc a shift + ; je prikazova radka

q je ukonceni

w je zapis,

x je kombinace w + q,

shit+ a - konec radku + editace

I je kdyz potrebuju neco dopsat,

x- mazu pri jednoum znaku

dd - mazu cely radek

# tar file a untar
compress: tar -zcvf sashome.tar.gz /sas/sashome

extrakt: tar -zxvf sashome.tar.gz

# Unzip in linux
unzip filename.zip

# vypsani velikosti souboru v adresari
du -h /cesta/k/adresari | sort -rh | head -n 10

# zapnutí nebo vypnutí služeb

/sas/sasconfig/Lev1/sas.servers start/stop /status

# zapnutí metadata serveru

/sas/sasconfig/Lev1/SASMeta/MetadataServer/MetadataServer.sh start

# restart konkrétní web app serveru

/sas/sasconfig/Lev1/Web/WebAppServer/SASServer7_1/bin/tcruntime-ctl.sh restart

# Zkontrolovat dokumentaci u hotfixů a zjistit který má možnost Configurace - dá se zjistit v IMPORTANT NOTES v dokumentaci jednotlivých hotfixu

# vypíše produkty co je na serveru nainstalovany

/sas/sashome/InstallMisc/InstallLogs/DeploymentRegistry.txt+ - 

# Vypsani procesu v linuxu ve spojitosti se sas
ps aux | grep sas

# crontab
crontab -l (vypise crontab joby)

# Vygeneruje nové DeploymentRegistry.txt 

cd /sas/sashome/deploymntreg/

/sas/sashome/SASPrivateJavaRuntimeEnvironment/9.4/jre/bin/java -jar sas.tools.viewregistry.jar

# stažení SAS94_HFADD_data.xml

curl https://tshf.sas.com/techsup/download/hotfix/HF2/util01/SASHotFixDLM/data/SAS94_HFADD_data.xml -o SAS94_HFADD_data.xml

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

Začít na 01

1: 
/sas/sasconfig/Lev1/sas.servers.pre start / status / stop

2:
Zapnout SAS Metadata Server
/sas/sasconfig/Lev1/SASMeta/MetadataServer/MetadataServer.sh start

teď se dají zapnout 02 a 03 servery a pak už 

a pak 
/sas/sasconfig/Lev1/sas.servers.mid start

3:
/sas/sasconfig/Lev1/sas.servers start

# V případě že neprojde Redeploy web app, tak zkusit pročistit cache a logy - udělat pak redeploy znovu

# Vypnutí sync s AD z SAS CM
na SAS02 v crontab -e jsou vidět aktuální joby, stačí zakomentovat AD a LDAP sync a restartovat služby
