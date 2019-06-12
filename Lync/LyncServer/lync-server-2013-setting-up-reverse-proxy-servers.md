---
title: 'Lync Server 2013: Configuración de los servidores proxy inversos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef13f2351ab74c0e3b2ba558a9dbf0aef43d71b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configuración de los servidores proxy inversos para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-08_

Para implementaciones de servidor perimetral de Microsoft Lync Server 2013, es necesario un proxy inverso HTTPS en la red perimetral para que los clientes externos tengan acceso a los servicios Web de Lync Server 2013 (denominados *componentes Web* en Office Communications Server) en el director y el grupo de usuarios domésticos. Algunas de las características que requieren acceso externo a través de un proxy inverso son las siguientes:

  - Permitir a los usuarios externos descargar el contenido de la reunión para sus reuniones.

  - Habilitar usuarios externos para expandir grupos de distribución.

  - Permitir a los usuarios remotos descargar archivos desde el servicio de libreta de direcciones.

  - Obtener acceso al cliente de Lync Web App.

  - Acceso a la Página Web de configuración de conferencias de acceso telefónico local.

  - Habilitar dispositivos externos para conectar con el servicio Web de actualización de dispositivos y obtener actualizaciones.

  - Permitir que las aplicaciones móviles descubran y usen automáticamente las direcciones URL de movilidad (MCX) desde Internet.

  - Habilitar el cliente de Lync 2013, la aplicación de la tienda Windows de Lync y el cliente móvil Lync 2013 para ubicar las direcciones URL de detección de Lync (detección automática) y usar la API Web de comunicaciones unificadas (UCWA).

Le recomendamos que configure su proxy HTTP inverso para publicar todos los servicios web en todos los grupos. Publicación de https://ExternalFQDN\* /publica todos los directorios virtuales de IIS para un grupo. Necesita una regla de publicación para cada servidor Standard Edition, grupo de servidores front-end o grupo de directores o directores de su organización.

Además, debe publicar las direcciones URL simples. Si la organización tiene un grupo de directores o directores, el proxy inverso HTTP escucha las solicitudes HTTP/HTTPS a las direcciones URL simples y envíales un proxy al directorio virtual de servicios Web externo del director o grupo de directores. Si no ha implementado un director, debe designar uno para administrar solicitudes a las direcciones URL simples. (Si este no es el grupo de hogar del usuario, lo redirigirá a los servicios web en el grupo de hogar del usuario). Las direcciones URL simples se pueden controlar mediante una regla de publicación de web dedicada o se puede Agregar a los nombres públicos de la regla de publicación web para el director. También necesita publicar la dirección URL del servicio de detección automática externa.

Puede usar Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7,0, 7,5 o 8,0 con enrutamiento de solicitud de aplicación (IIS ARR) como proxy inverso. Los pasos detallados en esta sección describen cómo configurar Forefront Threat Management Gateway 2010, y los pasos para configurar ISA Server 2006 son casi idénticos. También se proporciona una guía para IIS ARR. Si está usando un proxy inverso diferente, consulte la documentación de ese producto y asigne los requisitos definidos aquí a las características asociadas de otros servidores proxy inversos.

<div>


> [!IMPORTANT]  
> El enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) es una opción completamente probada y admitida para implementar un proxy inverso para Lync Server 2010 y Lync Server 2013. En noviembre de 2012, Microsoft ha cesado las ventas de licencias de ForeFront Threat Management Gateway 2010 o TMG. TMG sigue siendo un producto totalmente compatible y aún está disponible para su venta en dispositivos vendidos por terceros. Además, muchos servidores de seguridad y equilibradores de carga de hardware de terceros proporcionan soporte de proxy inverso. Para los equilibradores de carga de hardware y los firewalls que proporcionan características de proxy invertida, consulte a su proveedor para obtener instrucciones específicas sobre cómo configurar su producto para proporcionar soporte inverso de proxy para Lync Server. También puede ver los terceros que han enviado documentación de su producto a Microsoft. El soporte técnico es proporcionado por el tercero para su solución. Para ver los terceros que están activos en la oferta de soluciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=268730">infraestructura cualificada para Microsoft Lync</A>.



</div>

Los siguientes temas y procedimientos usan Forefront Threat Management Gateway 2010 e IIS ARR como la base de los procedimientos de implementación y configuración.

  - [Configurar los nombres de dominio completos (FQDN) de la granja de servidores web para Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurar adaptadores de red en Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS en Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Crear registros DNS para servidores de proxy inverso en Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Comprobar el acceso a través del proxy inverso en Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Antes de empezar

Para implementar correctamente Forefront Threat Management Gateway 2010 como su proxy inverso, necesita configurar y configurar un servidor, usando los requisitos previos y requisitos de hardware definidos en la documentación de la puerta de 2010 enlace de administración de Forefront Threat Management. Vea el tema siguiente configurado para configurar correctamente el hardware e instalar Forefront Threat Management Gateway 2010 en el servidor antes de continuar.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Recomendaciones de hardware de Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)

Para implementar correctamente IIS ARR como su proxy inverso, revise los temas siguientes para configurar el hardware y el software necesario.

  - <span></span>  
    Para instalar IIS en Windows Server 2008 o Windows Server 2008 R2, consulte [instalar IIS 7 en Windows server 2008 o Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Para instalar IIS en Windows Server 2012, consulte [instalar IIS 8 en Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Para instalar IIS en Windows Server 2012 R2, consulte [instalar iis 8,5 en Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Para descargar la extensión de enrutamiento de solicitud de la aplicación para IIS, siga las instrucciones de la [solicitud de enrutamiento v 2.5 de solicitud de aplicación](http://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Para instalar ARR, para las instrucciones en [instalar aplicación solicitud de enrutamiento versión 2](http://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Las instrucciones publicadas actualmente son para ARR 2,0. Para la instalación de la extensión, no hay ninguna diferencia entre las dos versiones.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

