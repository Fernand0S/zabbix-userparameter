# Zabbix Userparameter

- Scripts zabbix userparameter para realizar checagem de serviços Linux 

#Checa processo com maior uso de Memoria no servidor linux
Userparameter=checa_memoria,ps -e -o pmem,pid,user,time,args | awk '{print $1, $2, $3, $4, $5}' | sort -n -k 1 -r | head

#Checa processo com maior uso de CPU no servidor linux
Userparameter=checa_cpu,ps -e -o pcpu,pid,user,time,args | awk '{print $1, $2, $3, $4, $5}' | sort -n -k 1 -r | head

#Verifica os 10 Ultimos registro de logon no servidor com seu usuário, mês, dia, horario e tempo de sessão 
Userparameter=Checa_Usuarios_Logados,last | head -10 | sort | awk '{print $1,  $5, $6, $7, $10}'
