---
title: 'Lync Server 2013: escenarios de proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 767df1e427cd29e9437b4bd04d2859b382b48267
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510837"
---
# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Escenarios de proxy inverso en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-21_

Los proxies inversos son necesarios en Lync Server 2013 para permitir el acceso a servicios y recursos como la reunión y las direcciones URL sencillas de acceso telefónico, la libreta de direcciones, el contenido de la reunión, la expansión de la lista de distribución, los servicios de movilidad y otros. El escenario típico de proxy inverso en Lync Server 2013 es permitir que los clientes externos (por ejemplo, el cliente de escritorio o el cliente de Lync Web App) tengan acceso al director o a los servicios web externos del servidor front-end.

**Proxy inverso y servicios web externos**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

Durante la fase de planeación, defina los requisitos para el proxy inverso en una implementación de Lync Server 2013. El proxy inverso permite el acceso a características para los siguientes clientes externos:

  - Cliente de escritorio de Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Aplicación Lync de la tienda Windows

Al planear la implementación de Lync Server 2013, debe asignar los requisitos reales para Lync Server 2013 a las características de proxy inverso.

1.  Los clientes externos se conectarán al proxy inverso en el puerto TCP 443 y usarán la capa de sockets seguros (SSL) o la seguridad de la capa de transporte (TLS). Los clientes móviles de Microsoft Lync pueden conectarse en el puerto TCP 80, pero solo cuando se realiza la conexión inicial a los servicios de detección de Lync y el administrador ha configurado los registros CNAME (o alias) del sistema de nombres de dominio (DNS) adecuados y se acepta que esta comunicación no se cifrará.

2.  Lync Server 2013 servicios web externos (implementados en el servidor front-end o el director) esperan una conexión de un proxy inverso en el puerto TCP 4443 y espera que la conexión sea SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > Los puertos de escucha predeterminados sugeridos para los servicios web externos son TCP 8080 para tráfico HTTP y TCP 4443 para el tráfico HTTPS. El generador de topologías proporciona una oportunidad para reemplazar los valores predeterminados y definir sus propios puertos de escucha para los servicios web externos. Es importante tener en cuenta que el proxy inverso se comunica con los servicios web externos y que los clientes externos se comunican con el proxy inverso. El cliente externo se comunica con el proxy inverso en el puerto TCP 443, pero puede redefinir el puerto en el que se comunica el proxy inverso con los servicios web externos. Las opciones del generador de topologías para invalidar los puertos de escucha predeterminados para los servicios web le permiten resolver los conflictos de puertos de escucha que pueden surgir en la infraestructura.

    
    </div>

3.  Lync Server 2013 servicios web externos esperan un encabezado host sin modificar del cliente para identificar qué servicio y el directorio del servidor web está intentando usar el cliente. Las solicitudes deben aparecer como si proceden del proxy inverso

4.  Los servicios web externos usan directorios virtuales de servidor Web (vDir) definidos que proporcionan los servicios ofrecidos a los clientes. Los servicios Web específicos que pueden identificarse externamente son:
    
      - El vDir "reunirse" para las reuniones de conferencia Web
    
      - El vDir de "marcado" para el acceso telefónico y la conferencia telefónica
    
      - El vDir "detección automática" de la aplicación de la tienda Windows de Lync, Lync Mobile y el cliente de escritorio Lync 2013. La detección automática en Lync Server 2013 se conoce con el nombre DNS "lyncdiscover"
    
      - El cliente externo tiene acceso a los servicios no definidos por llamadas directas a los servicios web externos. Por ejemplo, las llamadas directas a los servicios web externos y los vDirs asociados tienen acceso a la expansión del grupo de distribución (DLX) y al servicio de libreta de direcciones (ABS). El cliente conoce la ruta de acceso real al vDir y crea un localizador uniforme de registros (URL) en función de esta información. El cliente tendría acceso al servicio de libreta de direcciones mediante una dirección URL similar a `https://externalweb.contoso.com/abs/handler`
    
      - Office Web Apps Server cuando se definen y configuran conferencias como parte de la topología de Lync Server
        
        <div>
        

        > [!NOTE]  
        > El servidor de Office Web Apps es un servidor de roles independiente y no está configurado como parte de los servicios web externos. Este servidor se publica por separado para el acceso de clientes.

        
        </div>

5.  Definir el puente SSL para cada servicio. El puerto externo TCP 443 está asignado al puerto de servicios Web externo TCP 4443. Para HTTP sin cifrar, el puerto TCP 80 está asignado al puerto de servicios Web externo TCP 8080

6.  Planeación de escuchas de proxy inverso para publicar recursos de servidor Web

7.  Solicite y configure el certificado para el proxy inverso en función de los servicios que se ofrecerán. Si se configura con los nombres alternativos de sujeto correctos, todos los agentes de escucha configurados en el servidor de proxy inverso pueden compartir este certificado.

Recursos disponibles para planear la implementación de su proxy inverso:

  - [Recopilación de datos en Lync Server 2013](lync-server-2013-data-collection.md)

  - [Resumen de certificado-proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Resumen de Puerto-proxy inverso en Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Resumen de DNS-proxy inverso en Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

