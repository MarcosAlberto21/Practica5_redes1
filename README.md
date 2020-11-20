# Practica5_redes1

## Topología 1

#### Conguración de la red
     VLAN	 Dirección de red	       Primera Direccion asignable	     Última dirección asignable          Dirrección de Broadcast
     10      192.168.10.0/24	        192.168.10.1/24	                 192.168.10.254/24	                  192.168.10.254/24
     50      192.168.50.0/24	        192.168.50.1/24	                 192.168.50.254/24	                  192.168.20.254/24
     70      192.168.70.0/24	        192.168.70.1/24	                 192.168.70.254/24	                  192.168.50.254/24
     
     conexion hacia la topología 2
     
     10.0.8.2
     
     

#### Modelo

 ![image](https://drive.google.com/uc?export=view&id=1BQ-fCsdt3CxOaAj7pNRfwsAWSO6mHVYn)
 
 
 
 ### Congiguración ETHERNETSWITCH 
 
      Se crean las vlans
      
      comandos:
      
           vlan database
           !
           vlan 10 name PROFESORES
           !
           vlan 50 name ESTUDIANTES
           !
           vlan 70 name INVITADOS
           exit
           !
           write
           !
           
       Se configuran los puertos en modo trunk 
       
       comandos:
               conf t
               interface range fastEthernet 1/0 - 15 
               speed 100
               duplex full
               switchport mode trunk
               no shutdown
               exit
               exit
               write
               !
   ![image](https://drive.google.com/uc?export=view&id=1R5gkwkz9ZBy0ILA1zgjpWAEQPnvulqk7)
 

 ### Congiguración ROUTER
 
 
     comandos:
          conf t
           interface fastEthernet 0/0
           no shutdown
           exit

           interface fastEthernet 0/0.10
           encapsulation dot1Q 10
           ip address 192.168.10.254 255.255.255.0
           exit

           interface fastEthernet 0/0.50
           encapsulatio dot1Q 50
           ip address 192.168.50.254 255.255.255.0
          exit

           interface fastEthernet 0/0.70
           encapsulatio dot1Q 70
           ip address 192.168.70.254 255.255.255.0
          exit
          
 ![image](https://drive.google.com/uc?export=view&id=1h8oF78V82xnxguth4ged-qLR5LPD791d)   
     
 
