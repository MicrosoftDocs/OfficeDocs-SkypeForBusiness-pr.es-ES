---
title: 'Lync Server 2013: Requisitos del servicio Detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Requisitos del servicio Detección automática para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en el director y los servidores del grupo de servidores front-end, y cuando se publican en DNS, pueden ser usados por dispositivos móviles que ejecutan Lync Mobile para ubicar servicios de movilidad. Antes de que los dispositivos móviles que ejecutan Lync Mobile puedan aprovechar el descubrimiento automático, debe modificar las listas de nombres alternativos del sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática. Además, puede que sea necesario modificar las listas de nombres alternativos del asunto en los certificados que se usan para las reglas de publicación de servicios web externos en los proxies inversos.

Para obtener información sobre las entradas de nombre alternativo de asunto necesarias para directores, servidores front-end y proxy inversos, consulte [requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) en planeamiento de movilidad.

La decisión sobre el uso de listas de nombres alternativos de asunto en proxies inversos se basa en si publica el servicio de detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   no es necesario realizar cambios en los certificados si la consulta inicial para el servicio de detección automática se realiza a través del puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y se redirigirá a un director o servidor front-end en el puerto 8080 de forma interna. Para obtener más información, consulte la sección "proceso inicial de detección automática con el puerto 80" más adelante en este tema.

  - **Publicado en el puerto 443**   la lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios web externos debe contener un *lyncdiscover.\< sipdomain\> * entrada para cada dominio SIP de su organización.

La reemisión de certificados mediante una entidad emisora de certificados interna suele ser un proceso simple, pero para los certificados públicos que se usan en la regla de publicación de servicio Web, agregar varias entradas de nombre alternativo de asunto puede resultar costoso. Para evitar este problema, admitimos la conexión de detección automática inicial en el puerto 80, que luego se le redirige al puerto 8080 en el servidor de director o de front-end.

Por ejemplo, supongamos que un cliente móvil que ejecuta Lync Mobile está configurado para iniciar sesión en Lync Server 2013 con la característica de detección automática mediante HTTP para la solicitud inicial.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Proceso de detección automática inicial para dispositivos móviles que usan el puerto 80

1.  Dispositivo móvil que ejecuta Lync Mobile busca lyncdiscover.contoso.com con DNS, donde existe un registro A.

2.  DNS externo devuelve la dirección IP de los servicios web externos al cliente.

3.  Un dispositivo móvil que ejecuta Lync Mobile http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com envía una solicitud al proxy inverso

4.  La regla de publicación web enviará un puente de la solicitud desde el puerto 80 externamente al puerto 8080 de forma interna, que lo redirigirá a un director o a un servidor front-end.
    
    Puesto que la solicitud es HTTP y no HTTPS, no es necesario realizar modificaciones en el certificado de la regla de publicación de servicio Web externo para admitir el servicio Detección automática.

5.  El servicio Detección automática devuelve las direcciones URL del servicio Web externo (en formato HTTPS).

6.  El dispositivo móvil que ejecuta Lync Mobile se puede volver a conectar al proxy inverso en el puerto 443 y se redirige a través de 4443 al servicio de movilidad que se ejecuta en el grupo de usuarios domésticos.
    
    Dado que la consulta HTTPS es a la dirección URL de los servicios web externos frente a la dirección URL del servicio de detección automática, se realiza correctamente porque el certificado ya contiene entradas de nombre alternativo del sujeto para los nombres de dominio completos (FQDN) de los servicios web externos.
    
    En este escenario, no es necesario realizar cambios en los certificados para admitir la movilidad.
    
    <div>
    

    > [!NOTE]  
    > Si el servidor Web de destino tiene un certificado que no tiene un valor coincidente para lyncdiscover.contoso.com como un valor de lista de nombres alternativos de asunto:<BR>a.&nbsp;&nbsp;&nbsp;el servidor web responde con un "servidor Hola" y no tiene certificado.<BR>b.&nbsp;&nbsp;&nbsp;dispositivo móvil que ejecuta Lync Mobile de inmediato finaliza la sesión.<BR>Si el servidor Web de destino tiene un certificado que incluye lyncdiscover.contoso.com como un valor de lista de nombres alternativos de asunto:<BR>a.&nbsp;&nbsp;&nbsp;el servidor web responde con un certificado "servidor Hola".<BR>b.&nbsp;&nbsp;&nbsp;dispositivo móvil que ejecuta Lync Mobile valida el certificado y completa el protocolo de enlace.

    
    </div>

Para admitir una conexión inicial con el servicio de detección automática con el puerto 80 en el servidor proxy inverso, puede crear una regla de publicación http similar a este ejemplo para una regla de publicación Web de proxy invertida de Forefront Threat Management Gateway 2010:

1.  Cree una nueva regla de publicación de Web (por ejemplo, **detección automática de Lync Server (http)**).

2.  En **nombre público**, escriba lyncdiscover.contoso.com.

3.  En la pestaña **puente** , seleccione solo la opción para enlazar solicitudes desde el puerto 80 al puerto 8080.

4.  En la pestaña **autenticación** , seleccione **sin autenticación**y el **cliente no puede autenticar directamente**.

5.  Confirme los cambios y mueva la regla a la parte superior de la lista de reglas de Lync (en primer lugar en el orden de procesamiento).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Movilidad para la implementación de dominios divididos

Un espacio de direcciones SIP compartido, también conocido como un *dominio dividido*, o una *implementación híbrida* es una configuración en la que los usuarios se implementan en una implementación local y en un entorno en línea. El resultado deseado es tener un usuario, independientemente de dónde se encuentre ubicado su servidor principal (local o en línea), iniciar sesión en la implementación y ser redirigido a la ubicación del servidor local. Para ello, se usa la característica de detección automática de Microsoft Lync Server 2013 para redirigir el usuario en línea a la topología en línea. Esto se realiza mediante la configuración del localizador de recursos uniforme (URL) de detección automática mediante el shell de administración de Lync Server y los cmdlets **Get-CsHostingProvider** y **set-CsHostingProvider**.

Tendrá que recopilar y registrar los siguientes atributos implementados:

  - Desde el shell de administración de Lync Server, escriba
    
        Get-CsHostingProvider

  - En los resultados, busque el proveedor en línea con el atributo **ProxyFQDN**. Por ejemplo, sipfed.online.lync.com

  - Registrar el valor de la ProxyFQDN

  - Habilitar la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea

  - Habilitar la Federación para el proveedor en línea. De forma predeterminada, todos los usuarios conectados están habilitados para la Federación de dominios y pueden comunicarse con todos los dominios.

  - Si va a definir dominios bloqueados y permitidos, determine los dominios que va a permitir o bloquear de forma explícita

  - Para la Federación en línea, debe planear las excepciones del firewall, los certificados y los registros de host DNS (A o AAAA, si usa IPv6). Además, debe configurar directivas de Federación. Para obtener más información, consulte [planificación de Lync server 2013 y Federación de Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

