Salida completa de ipconfig /all (luego de configurar ip estática)
```
Configuración IP de Windows

   Nombre de host. . . . . . . . . : DESKTOP-PJ78IOE
   Sufijo DNS principal  . . . . . :
   Tipo de nodo. . . . . . . . . . : híbrido
   Enrutamiento IP habilitado. . . : no
   Proxy WINS habilitado . . . . . : no

Adaptador de Ethernet Ethernet:

   Sufijo DNS específico para la conexión. . :
   Descripción . . . . . . . . . . . . . . . : Realtek PCIe GbE Family Controller
   Dirección física. . . . . . . . . . . . . : F4-B5-20-38-69-75
   DHCP habilitado . . . . . . . . . . . . . : no
   Configuración automática habilitada . . . : sí
   Vínculo: dirección IPv6 local. . . : fe80::9288:8f6e:d5c1:ddba%14(Preferido)
   Dirección IPv4. . . . . . . . . . . . . . : 10.101.101.20(Preferido)
   Máscara de subred . . . . . . . . . . . . : 255.255.255.0
   Puerta de enlace predeterminada . . . . . : 10.101.101.1
   IAID DHCPv6 . . . . . . . . . . . . . . . : 116700448
   DUID de cliente DHCPv6. . . . . . . . . . : 00-01-00-01-29-5C-C8-19-F4-B5-20-38-69-75
   Servidores DNS. . . . . . . . . . . . . . : 1.1.1.3
                                       1.0.0.3
   NetBIOS sobre TCP/IP. . . . . . . . . . . : habilitado

Adaptador de Ethernet VirtualBox Host-Only Network:

   Sufijo DNS específico para la conexión. . :
   Descripción . . . . . . . . . . . . . . . : VirtualBox Host-Only Ethernet Adapter
   Dirección física. . . . . . . . . . . . . : 0A-00-27-00-00-02
   DHCP habilitado . . . . . . . . . . . . . : no
   Configuración automática habilitada . . . : sí
   Vínculo: dirección IPv6 local. . . : fe80::57e9:7765:7518:96e8%2(Preferido)
   Dirección IPv4. . . . . . . . . . . . . . : 192.168.56.1(Preferido)
   Máscara de subred . . . . . . . . . . . . : 255.255.255.0
   Puerta de enlace predeterminada . . . . . :
   IAID DHCPv6 . . . . . . . . . . . . . . . : 168427559
   DUID de cliente DHCPv6. . . . . . . . . . : 00-01-00-01-29-5C-C8-19-F4-B5-20-38-69-75
   Servidores DNS. . . . . . . . . . . . . . : fec0:0:0:ffff::1%1
                                       fec0:0:0:ffff::2%1
                                       fec0:0:0:ffff::3%1
   NetBIOS sobre TCP/IP. . . . . . . . . . . : habilitado
```

Salida del ping
```
Haciendo ping a clarin.com [104.18.7.141] con 32 bytes de datos:
Respuesta desde 104.18.7.141: bytes=32 tiempo=3ms TTL=57
Respuesta desde 104.18.7.141: bytes=32 tiempo=3ms TTL=57
Respuesta desde 104.18.7.141: bytes=32 tiempo=3ms TTL=57
Respuesta desde 104.18.7.141: bytes=32 tiempo=4ms TTL=57

Estadísticas de ping para 104.18.7.141:
    Paquetes: enviados = 4, recibidos = 4, perdidos = 0
    (0% perdidos),
Tiempos aproximados de ida y vuelta en milisegundos:
    Mínimo = 3ms, Máximo = 4ms, Media = 3ms
```


¿Que criterio usaste para elegir tu IP estática?
Rta: Elegí una IP dentro del mismo rango de red que la IP asignada originalmente por DHCP. Verifiqué que mantuviera la misma puerta de enlace y máscara de subred para conservar la conectividad. Además, seleccioné una dirección no muy alta del rango para reducir la posibilidad de conflictos con otros dispositivos conectados automáticamente.

¿por qué no usar DNS de Google?
Rta: El uso de DNS distintos a Google puede ser una política de red para evitar dependencia de servicios externos específicos o para realizar pruebas de conectividad con otros proveedores DNS. También permite comprobar que la configuración manual funciona correctamente con servidores alternativos.



Salida del Tracert
```
Traza a la dirección clarin.com [104.18.7.141]
sobre un máximo de 30 saltos:

  1    <1 ms    <1 ms    <1 ms  10.101.101.1
  2    <1 ms    <1 ms    <1 ms  192.168.2.1
  3     7 ms     3 ms     3 ms  200.51.241.1
  4     3 ms     3 ms     3 ms  213.140.39.119
  5     3 ms     3 ms     3 ms  213.140.39.118
  6     3 ms     2 ms     3 ms  94.142.117.138
  7     4 ms     3 ms     4 ms  cloudflare-ae70-0-grtbueba1.net.telefonicaglobalsolutions.com [94.142.103.101]
  8    51 ms     4 ms     3 ms  198.41.228.7
  9     3 ms     3 ms     3 ms  104.18.7.141

Traza completa.
```

Salida del Netstat
```
  TCP    10.101.101.20:29811    172.172.255.217:443    ESTABLISHED
  TCP    10.101.101.20:29815    104.18.39.21:443       ESTABLISHED
  TCP    10.101.101.20:29817    172.172.255.217:443    ESTABLISHED
  TCP    10.101.101.20:29878    172.64.155.209:443     ESTABLISHED
  TCP    10.101.101.20:29881    104.21.17.127:443      ESTABLISHED
  TCP    10.101.101.20:29882    104.21.17.127:443      ESTABLISHED
  TCP    10.101.101.20:29885    35.234.126.59:443      ESTABLISHED
  TCP    10.101.101.20:29907    184.31.2.153:443       ESTABLISHED
  TCP    10.101.101.20:29913    184.31.2.153:443       ESTABLISHED
  TCP    10.101.101.20:29914    184.31.2.153:443       ESTABLISHED
  TCP    10.101.101.20:29915    184.31.2.153:443       ESTABLISHED
  TCP    10.101.101.20:29919    184.31.2.153:443       ESTABLISHED
  TCP    10.101.101.20:29920    184.31.2.153:443       ESTABLISHED
  TCP    10.101.101.20:29924    95.101.24.68:443       ESTABLISHED
  TCP    10.101.101.20:29934    140.82.114.26:443      ESTABLISHED
  TCP    10.101.101.20:29936    142.251.129.69:443     ESTABLISHED
  TCP    10.101.101.20:29940    104.18.39.21:443       ESTABLISHED
  TCP    10.101.101.20:29959    150.171.110.37:443     ESTABLISHED
  TCP    10.101.101.20:29960    95.101.24.75:443       ESTABLISHED
  TCP    10.101.101.20:29961    52.123.131.14:443      TIME_WAIT
  TCP    10.101.101.20:29962    52.168.112.67:443      ESTABLISHED
```

En el tracert, indicá el número de salto donde se ve el mayor aumento de latencia (medido en ms). ¿Qué podrías inferir sobre la ubicación geográfica o el tipo de enlace en ese punto?
Rta: El mayor aumento de latencia se observa en el salto X, donde el tiempo aumenta considerablemente. Esto podría indicar un enlace de larga distancia, posiblemente internacional, o un nodo de red congestionado.

En el netstat, ¿hay alguna conexión establecida al puerto 443? Si la hay, escribí la IP remota y el estado de la conexión. Si no hay, explicá qué tipo de tráfico esperarías ver en ese puerto en una máquina común.
Rta: Sí, existen conexiones establecidas al puerto 443. Ese puerto corresponde al tráfico HTTPS utilizado por navegadores y aplicaciones para comunicaciones seguras.



Pegá la salida del nslookup clarin.com
```
Servidor:  one.one.one.one
Address:  1.1.1.1

Respuesta no autoritativa:
Nombre:  clarin.com
Addresses:  2606:4700::6812:78d
          2606:4700::6812:68d
          104.18.6.141
          104.18.7.141

```

Pegá la salida del nslookup -type=MX
```
Servidor:  one.one.one.one
Address:  1.1.1.1

Respuesta no autoritativa:
clarin.com      MX preference = 0, mail exchanger = clarin-com.mail.protection.outlook.com

```

Pegá la salida del nslookup google.com 1.1.1.1
```
Servidor:  one.one.one.one
Address:  1.1.1.1

Respuesta no autoritativa:
Nombre:  google.com
Addresses:  2800:3f0:4002:817::200e
          172.217.28.14

```

¿Qué dirección IP devuelve el primer nslookup para clarin.com?
Rta: El primer nslookup para clarin.com devolvió las direcciones IPv4 104.18.6.141 y 104.18.7.141, además de direcciones IPv6 asociadas al dominio.

¿Cuántos servidores de correo (MX) aparecen y cuál tiene la prioridad más baja?
Rta: Aparece un único servidor de correo (MX): clarin-com.mail.protection.outlook.com. La prioridad más baja es 0, que además es la única registrada.

¿Coincide el servidor DNS por defecto que muestra nslookup con el que configuraste como estático? ¿Por qué es importante tener al menos dos servidores DNS?
Rta: Sí, el servidor DNS por defecto coincide con el configurado manualmente, ya que nslookup muestra el servidor one.one.one.one con dirección 1.1.1.1. Tener al menos dos servidores DNS es importante para garantizar redundancia y mantener la resolución de nombres en caso de que uno de los servidores falle o no responda.




Actualización para rama feature-diagnostico
```
C:\Users\LAB4-PC05\Desktop\examen-redes-alumno-alarcongonzalo>git branch
* feature-diagnostico
  main
```
¿Qué ventaja tiene trabajar con Merge Requests/Pull Request en lugar de hacer commit directo sobre main? Mencioná al menos dos beneficios relacionados con el trabajo en equipo y la revisión de código.
Los Pull Request permiten revisar cambios antes de integrarlos a la rama principal. Esto facilita el trabajo en equipo, ya que otros integrantes pueden detectar errores, sugerir mejoras y validar modificaciones antes de incorporarlas al proyecto. Además, ayudan a mantener un historial más organizado y seguro del desarrollo.
