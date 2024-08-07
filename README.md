# Zabbix Userparameter

- Scripts zabbix userparameter para realizar checagem de serviços Linux 

#Checa processo com maior uso de Memoria no servidor linux
Userparameter=checa_memoria,ps -e -o pmem,pid,user,time,args | awk '{print $1, $2, $3, $4, $5}' | sort -n -k 1 -r | head

#Checa processo com maior uso de CPU no servidor linux
Userparameter=checa_cpu,ps -e -o pcpu,pid,user,time,args | awk '{print $1, $2, $3, $4, $5}' | sort -n -k 1 -r | head

#Verifica os 10 Ultimos registro de logon no servidor com seu usuário, mês, dia, horario e tempo de sessão 
Userparameter=Checa_Usuarios_Logados,last | head -10 | sort | awk '{print $1,  $5, $6, $7, $10}'

#Verificar o pool de conexões do PHP 
UserParameter=count_connections, ps -aux | grep 'php' | wc -l 

#Verificar o pool de conexões do Zabbix
UserParameter=pool_connections_zabbix, ps -aux | grep 'zabbix' | wc -l 

#Verificar o pool de conexões do Mysql
UserParameter=check_connections_mysql, netstat -an | grep 3306 | wc -l 
