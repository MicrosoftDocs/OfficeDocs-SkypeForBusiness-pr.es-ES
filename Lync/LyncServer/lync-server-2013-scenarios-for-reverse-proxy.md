---
title: 'Lync Server 2013: Escenarios de proxy inverso'
TOCTitle: Escenarios de proxy inverso
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48274493
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Escenarios de proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2013-01-21_

Los servidores proxy inversos son necesarios en Lync Server 2013 para proporcionar acceso a servicios y recursos, como las direcciones URL sencillas de acceso telefónico y de reunión, la libreta de direcciones, el contenido de la reunión, la expansión de lista de distribución, los servicios de movilidad, etc. El escenario de proxy inverso típico en Lync Server 2013 es permitir a los clientes externos (por ejemplo, el cliente de escritorio o el cliente de Lync Web App) el acceso a los servicios web externos de Director o Servidor front-end.

**Proxy inverso y servicios web externos**

![Proxy inverso y servicios web externos](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "Proxy inverso y servicios web externos")

Durante la fase de planeación, se definen los requisitos del proxy inverso en una implementación de Lync Server 2013. El proxy inverso permite el acceso a características para los siguientes clientes externos:

  - Cliente de escritorio de Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Aplicación de la Tienda Windows de Lync

Al planear la implementación de Lync Server 2013, se asignan los requisitos reales de Lync Server 2013 a las características del proxy inverso.

1.  Los clientes externos se conectarán al proxy inverso en el puerto TCP 443 y usarán la Capa de sockets seguros (SSL) o la Seguridad de la capa de transporte (TLS). Los clientes de Microsoft Lync Mobile se pueden conectar en el puerto TCP 80, pero solamente al establecer la conexión inicial con los servicios de detección de Lync y si el administrador ha configurado los registros CNAME (o alias) del Sistema de nombres de dominio (DNS) adecuados y acepta que esta comunicación no se cifrará.

2.  Los servicios web externos de Lync Server 2013 (implementados en el Servidor front-end y/o en el Director) esperan una conexión desde un proxy inverso en el puerto TCP 4443 y que la conexión sea SSL/TLS.
    
    > [!IMPORTANT]  
    > Los puertos de escucha predeterminados sugeridos para los servicios web externos son TCP 8080 para el tráfico HTTP y TCP 4443 para el tráfico HTTPS. La Generador de topologías proporciona una oportunidad para invalidar los valores predeterminados y definir sus propios puertos de escucha para los servicios web externos. Es importante tener en cuenta que el proxy inverso se comunica con los servicios web externos y los clientes externos se comunican con el proxy inverso. Los clientes externos lo hacen en el puerto TCP 443, pero puede redefinir el puerto en el que el proxy inverso se comunica con los servicios web externos. Las opciones de la Generador de topologías para invalidar los puertos de escucha predeterminados de los servicios web le permiten resolver los conflictos en los puertos de escucha que pueden surgir en la infraestructura.
    


3.  Los servicios web externos de Lync Server 2013 esperan un encabezado host sin modificar desde el cliente para identificar el servicio y el directorio de servidores web que intenta usar el cliente. Las solicitudes deben aparecer como si provinieran del proxy inverso.

4.  Los servicios web externos usan directorios virtuales (vDir) de servidor web definidos que proporcionan los servicios ofrecidos a los clientes. Los servicios web identificables como externos específicos son los siguientes:
    
      - El vDir “Meet” para reuniones de conferencia web
    
      - El vDir “Dialin” para acceso telefónico y conferencias telefónicas
    
      - El vDir “Autodiscover” para Aplicación de la Tienda Windows de Lync, Lync Mobile y el cliente de escritorio Lync 2013. La Detección automática en Lync Server 2013 se conoce con el nombre DNS “lyncdiscover”
    
      - Los clientes externos acceden a los servicios no definidos mediante llamadas directas a los servicios web externos. Por ejemplo, se accede a la expansión de grupos de distribución (DLX) y al Servicio de libreta de direcciones (ABS) mediante llamadas directas a los servicios web externos y a los vDirs asociados. El cliente conoce la ruta de acceso real al vDir y construye un Localizador uniforme de recursos (URL) en función de esta información. El cliente podría acceder al Servicio de libreta de direcciones con una dirección URL similar a `https://externalweb.contoso.com/abs/handler`
    
      - En las conferencias, el Servidor Office Web Apps se define y configura como parte de la topología de Lync Server
        

        > [!NOTE]
        > El Servidor Office Web Apps es un servidor de roles independiente y no se configura como parte de los servicios web externos. Este servidor se publica por separado para el acceso del cliente.



5.  Defina el protocolo de puente SSL para cada servicio. El puerto externo TCP 443 se asigna al puerto TCP 4443 de los servicios web externos. En el caso de HTTP sin cifrar, el puerto TCP 80 se asigna al puerto TCP 8080 de los servicios web externos.

6.  Planear la publicación de recursos de servidores web por parte de las escuchas del proxy inverso

7.  Solicite y configure el certificado para el proxy inverso en función de los servicios que se proporcionarán. Si se configura con los nombres alternativos del sujeto correctos, este certificado se puede compartir entre todas las escuchas configuradas en el servidor proxy inverso.

Recursos disponibles para planear la implementación de su proxy inverso:

  - [Recopilación de datos en Lync Server 2013](lync-server-2013-data-collection.md)

  - [Resumen de certificado - Proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Resumen de puerto - Proxy inverso en Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Resumen DNS - Proxy inverso en Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

