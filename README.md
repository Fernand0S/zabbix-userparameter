# Zabbix Userparameter

- Checa processo com maior uso de Memoria no servidor linux

#Checa processo com maior uso de Memoria no servidor linux
UserParameter=checa_memoria,ps -e -o pmem,pid,user,time,args | awk '{print $1, $2, $3, $4, $5}' | sort -n -k 1 -r | head
