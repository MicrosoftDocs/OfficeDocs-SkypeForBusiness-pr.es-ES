---
title: 'Lync Server 2013: Escenarios de proxy inverso'
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
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Escenarios de proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-21_

Los proxies inversos son necesarios en Lync Server 2013 para proporcionar acceso a servicios y recursos como la reunión y las direcciones URL simples de acceso telefónico, la libreta de direcciones, el contenido de la reunión, la expansión de la lista de distribución, los servicios de movilidad y otros. El escenario típico de proxy inverso en Lync Server 2013 es permitir que los clientes externos (por ejemplo, el cliente de escritorio o el cliente de Lync Web App) tengan acceso al director o a los servicios web externos del servidor front-end.

**Proxy inverso y servicios web externos**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

Durante la fase de planeación, se definen los requisitos para el proxy inverso en una implementación de Lync Server 2013. El proxy inverso permite el acceso a características para los siguientes clientes externos:

  - Cliente de escritorio de Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Aplicación de la Tienda Windows de Lync

Al planear la implementación de Lync Server 2013, se asignan los requisitos reales para Lync Server 2013 a las características de proxy inverso.

1.  Los clientes externos se conectarán al proxy inverso en el puerto TCP 443 y usarán nivel de socket seguro (SSL) o seguridad de la capa de transporte (TLS). Los clientes móviles de Microsoft Lync se pueden conectar en el puerto TCP 80, pero solo cuando se realiza la conexión inicial a los servicios Discover de Lync y el administrador ha configurado los registros CNAME (o alias) del sistema de nombres de dominio (DNS) apropiados y acepta que este la comunicación no se cifrará.

2.  Lync Server 2013 los servicios web externos (implementados en el servidor front-end o el director) esperan una conexión de un proxy inverso en el puerto TCP 4443 y espera que la conexión sea SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > Los puertos de escucha predeterminada sugeridos para los servicios web externos son TCP 8080 para tráfico HTTP y TCP 4443 para tráfico HTTPS. El generador de topología proporciona una oportunidad para reemplazar los valores predeterminados y definir sus propios puertos de escucha para los servicios web externos. Es importante tener en cuenta que el proxy inverso se comunica con los servicios web externos y los clientes externos se comunican con el proxy inverso. El cliente externo se comunica con el proxy inverso en el puerto TCP 443, pero puede redefinir el puerto en el que se comunica el proxy inverso con los servicios web externos. Las opciones del generador de topologías para invalidar los puertos de escucha predeterminados para los servicios web le permiten resolver conflictos de puertos de escucha que pueden surgir en su infraestructura.

    
    </div>

3.  Lync Server 2013 los servicios web externos esperan un encabezado de host sin modificar del cliente para identificar qué servicio y el directorio de servidor web está intentando usar el cliente. Las solicitudes deberían mostrarse como si proceden del proxy inverso

4.  Los servicios web externos usan directorios virtuales de servidor Web (vDir) definidos que proporcionan los servicios ofrecidos a los clientes. Los servicios web identificables externamente son:
    
      - El vDir "reunirse" para reuniones de conferencia Web
    
      - El envuelvedo "vDir" para el acceso telefónico y las conferencias telefónicas
    
      - El servicio de "detección automática" de la aplicación Lync de la tienda Windows, Lync Mobile y el cliente de escritorio Lync 2013. La detección automática de Lync Server 2013 se conoce en el nombre DNS "lyncdiscover"
    
      - El cliente externo tiene acceso a los servicios no definidos a través de llamadas directas a los servicios web externos. Por ejemplo, se obtiene acceso a la expansión del grupo de distribución (DLX) y al servicio de libreta de direcciones (ABS) mediante llamadas directas a los servicios web externos y la vDirs asociada. El cliente conoce la ruta de acceso real al vDir y construye un localizador de registros (URL) uniforme en función de esta información. El cliente tendría acceso al servicio de libreta de direcciones mediante una dirección URL similar a`https://externalweb.contoso.com/abs/handler`
    
      - El servidor de Office Web Apps cuando se define una conferencia y se configura como parte de la topología de Lync Server
        
        <div>
        

        > [!NOTE]  
        > El servidor de Office Web Apps es un servidor de roles independiente y no está configurado como parte de los servicios web externos. Este servidor se ha publicado por separado para el acceso de los clientes.

        
        </div>

5.  Defina los puentes SSL para cada servicio. El puerto externo TCP 443 se asigna al puerto de servicios Web externo TCP 4443. Para HTTP sin cifrar, el puerto TCP 80 se asigna al puerto de servicios Web externo TCP 8080

6.  Planificación de escuchas de proxy invertidas para publicar recursos de servidor Web

7.  Solicite y configure el certificado para el proxy inverso en función de los servicios que se ofrecerán. Si se ha configurado con los nombres alternativos de asunto correctos, el certificado puede ser compartido por todos los agentes de escucha configurados en el servidor proxy inverso.

Recursos disponibles para planear la implementación del proxy inverso:

  - [Recopilación de datos en Lync Server 2013](lync-server-2013-data-collection.md)

  - [Resumen de certificado - Proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Resumen de puerto - Proxy inverso en Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Resumen DNS - Proxy inverso en Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

