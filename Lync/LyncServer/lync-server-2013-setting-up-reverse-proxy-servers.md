---
title: 'Lync Server 2013: configuración de servidores proxy inversos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd5b57c29a622b7c0f051b00bb0ef30e265743e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configuración de servidores proxy inversos para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-08_

Para las implementaciones del servidor perimetral 2013 de Microsoft Lync Server, se requiere un proxy inverso HTTPS en la red perimetral para que los clientes externos tengan acceso a los servicios Web de Lync Server 2013 (denominados *componentes Web* en Office Communications Server) en el director y en el grupo de servidores principales del usuario. Algunas de las características que requieren un acceso externo a través de un proxy inverso incluyen lo siguiente:

  - Habilitación de los usuarios externos para descargar el contenido de la reunión para sus reuniones.

  - Habilitación de los usuarios externos para expandir grupos de distribución.

  - Habilitación de los usuarios remotos para descargar archivos desde el servicio de libreta de direcciones.

  - Obtener acceso al cliente de Lync Web App.

  - Acceso a la página web de configuración de conferencia de acceso telefónico local.

  - Habilitación de los dispositivos externos para conectarse al servicio web de actualización de dispositivos y obtener actualizaciones.

  - Habilitación de aplicaciones móviles para que detecten y usen las direcciones URL de movilidad (MCX) automáticamente desde Internet.

  - Habilitar el cliente de Lync 2013, la aplicación de la tienda Windows de Lync y el cliente móvil de Lync 2013 para localizar las direcciones URL de detección de Lync (detección automática) y usar la API Web de comunicaciones unificadas (UCWA).

Se recomienda configurar el proxy inverso HTTP para publicar todos los servicios web en todos los grupos. Publishing https://ExternalFQDN\* /publica todos los directorios virtuales de IIS para un grupo de servidores. Se necesita una regla de publicación para cada servidor Standard Edition, cada grupo de servidores front-end o cada director o grupo de directores de la organización.

Además, deberá publicar las direcciones URL sencillas. Si la organización tiene un director o un grupo de directores, el proxy inverso HTTP escucha las solicitudes de HTTP/HTTPS para direcciones URL sencillas y las envía al directorio virtual de servicios web externos del director o grupo de directores. Si no se ha implementado ningún director, deberá designar un grupo para administrar las solicitudes para las URL sencillas. (Si este no es el grupo principal del usuario, las redireccionará a los servicios web del grupo principal del usuario). Las URL sencillas pueden administrarse mediante una regla de publicación web dedicada, o bien puede agregarlas a los nombres públicos de la regla de publicación web para el director. También tiene que publicar la dirección URL externa del servicio Detección automática.

Puede usar Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, o Internet Information Server 7,0, 7,5 o 8,0 con enrutamiento de solicitud de aplicación (IIS ARR) como proxy inverso. Los pasos detallados de esta sección describen cómo configurar Forefront Threat Management Gateway 2010 y los pasos para configurar ISA Server 2006 son casi idénticos. También se proporciona una guía para IIS ARR. Si usa un proxy inverso diferente, consulte la documentación de ese producto y asigne los requisitos definidos aquí a las características asociadas de otros proxy inversos.

<div>


> [!IMPORTANT]  
> El enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) es una opción completamente probada y admitida para implementar un proxy inverso para Lync Server 2010 y Lync Server 2013. En noviembre de 2012, Microsoft ha cesado las ventas de licencias de ForeFront Threat Management Gateway 2010 o TMG. TMG sigue siendo un producto totalmente compatible y sigue disponible para la venta en los dispositivos que venden otros fabricantes. Además, muchos equilibradores de carga de hardware y firewalls de terceros proporcionan compatibilidad con proxy inverso. Para los equilibradores de carga de hardware y los firewalls que proporcionan características de proxy inverso, consulte al proveedor para obtener instrucciones específicas sobre cómo configurar su producto para proporcionar compatibilidad con un proxy inverso para Lync Server. También puede ver a Microsoft otros fabricantes que han enviado documentación sobre su producto. El soporte técnico es proporcionado por el tercero para su soluci? a. Para ver los terceros que están activos en la oferta de soluciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=268730">infraestructura apta para Microsoft Lync</A>.



</div>

Los siguientes temas y procedimientos usan Forefront Threat Management Gateway 2010 e IIS ARR como base para los procedimientos de implementación y configuración.

  - [Configurar FQDN de granja de servidores web para Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurar adaptadores de red en Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS en Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Crear registros DNS para servidores de proxy inverso en Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Comprobar el acceso a través del proxy inverso en Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Antes de empezar

Para implementar correctamente Forefront Threat Management Gateway 2010 como su proxy inverso, debe instalar y configurar un servidor, usando los requisitos previos y los requisitos de hardware definidos en la documentación de Forefront Threat Management Gateway 2010. Consulte el siguiente tema establecido para configurar correctamente el hardware e instalar Forefront Threat Management Gateway 2010 en el servidor antes de continuar.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Recomendaciones de hardware de Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)

Para implementar correctamente IIS ARR como su proxy inverso, revise los siguientes temas para configurar el hardware y el software necesario como requisito previo.

  - <span></span>  
    Para instalar IIS en Windows Server 2008 o Windows Server 2008 R2, vea [instalación de IIS 7 en Windows server 2008 o Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Para instalar IIS en Windows Server 2012, vea [instalar IIS 8 en Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Para instalar IIS en Windows Server 2012 R2, vea [Installing iis 8,5 on Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Para descargar la extensión de enrutamiento de solicitudes de aplicación para IIS, siga las instrucciones que se indican en [descarga de enrutamiento de solicitud de aplicación v 2.5](http://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Para instalar ARR, siga las instrucciones de [install Application request Routing Routing version 2](http://go.microsoft.com/fwlink/?linkid=291299) .
    
    <div>
    

    > [!NOTE]  
    > Las instrucciones que se han publicado actualmente son para ARR 2,0. Para la instalación de la extensión, no hay ninguna diferencia entre las dos versiones.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

