---
title: 'Lync Server 2013: requisitos del servicio Detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515777"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Requisitos del servicio Detección automática para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end y, cuando se publican en DNS, los dispositivos móviles que ejecutan Lync Mobile pueden usar para encontrar los servicios de movilidad. Antes de que los dispositivos móviles que ejecutan Lync Mobile puedan aprovechar la detección automática, debe modificar las listas de nombres alternativos de sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática. Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.

Para obtener información detallada sobre las entradas de nombre alternativo de sujeto que son necesarias para los directores, los servidores front-end y los servidores proxy inversos, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) en Planning for Mobility.

La decisión de usar listas de nombres alternativos de sujeto en proxies inversos se basa en si se publica el servicio Detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**     No es necesario realizar cambios en los certificados si la consulta inicial al servicio Detección automática se produce a través del puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se redirigirán a un director o a un servidor front-end en el puerto 8080 de forma interna. Para obtener más información, vea la sección “Proceso de detección automática inicial usando el puerto 80” más adelante en este tema.

  - **Publicado en el puerto 443**     La lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener un *lyncdiscover. \<sipdomain\> * entrada para cada dominio SIP dentro de la organización.

La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero para certificados públicos usados en la regla de publicación de servicios web, puede resultar caro agregar varias entradas de nombres alternativos de sujeto. Para solucionar este problema, admitimos la conexión de detección automática inicial a través del puerto 80, que luego se redirige al puerto 8080 en el director o el servidor front-end.

Por ejemplo, supongamos que un cliente móvil que ejecuta Lync Mobile está configurado para iniciar sesión en Lync Server 2013 mediante la característica de detección automática usando HTTP para la solicitud inicial.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Proceso de detección automática inicial para dispositivos móviles que usan el puerto 80

1.  Dispositivo móvil que ejecuta Lync Mobile busca lyncdiscover.contoso.com mediante DNS, donde existe un registro A.

2.  El DNS externo devuelve la dirección IP de los servicios web externos al cliente.

3.  Un dispositivo móvil que ejecuta Lync Mobile envía una solicitud http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com al proxy inverso

4.  La regla de publicación de web enlazará la solicitud del puerto 80 externamente al puerto 8080 de forma interna, que la enrutará a un director o a un servidor front-end.
    
    Puesto que la solicitud es HTTP y no HTTPS, no es necesaria ninguna modificación en el certificado de la regla de publicación de los servicios web externos para admitir el servicio Detección automática.

5.  El servicio Detección automática devuelve las direcciones URL del servicio web externo (en formato HTTPS).

6.  El dispositivo móvil que ejecuta Lync Mobile puede volver a conectarse al proxy inverso en el puerto 443 y se redirige a través de 4443 al servicio de movilidad que se ejecuta en el grupo de servidores principales del usuario.
    
    Puesto que la consulta HTTPS es a la dirección URL de servicios web externos frente a la dirección URL del servicio Detección automática, se realiza correctamente porque el certificado ya deberá contener entradas de nombres alternativos de sujeto para los FQDN de servicios web externos.
    
    En este escenario, no hay cambios de certificado necesarios para admitir la movilidad.
    
    <div>
    

    > [!NOTE]  
    > Si el servidor web de destino tiene un certificado que no tiene un valor coincidente para lyncdiscover.contoso.com como valor de lista de nombres alternativos de sujeto:<BR>un. &nbsp; &nbsp; &nbsp; El servidor web responde con un "servidor Hello" y ningún certificado.<BR>b. &nbsp; &nbsp; &nbsp; El dispositivo móvil que ejecuta Lync Mobile finaliza inmediatamente la sesión.<BR>Si el servidor web de destino tiene un certificado que incluye lyncdiscover.contoso.com como valor de lista de nombres alternativos de sujeto:<BR>un. &nbsp; &nbsp; &nbsp; El servidor web responde con un "servidor Hello" y un certificado.<BR>b. &nbsp; &nbsp; &nbsp; El dispositivo móvil que ejecuta Lync Mobile valida el certificado y completa el protocolo de enlace.

    
    </div>

Para admitir una conexión inicial al servicio Detección automática usando el puerto 80 en su servidor proxy inverso, puede crear una regla de publicación http similar a este ejemplo para una regla de publicación de web de proxy inverso de Forefront Threat Management Gateway 2010:

1.  Crear una nueva regla de publicación de web (por ejemplo, **Detección automática de Lync Server (HTTP)**).

2.  En **Nombre público**, escriba lyncdiscover.contoso.com.

3.  En la ficha **Protocolo de puente**, seleccione solo la opción para conectar solicitudes del puerto 80 al puerto 8080.

4.  En la ficha **Autenticación**, seleccione **Sin autenticación** y **El cliente no se puede autenticar directamente**.

5.  Confirme los cambios y mueva la regla a la parte superior de la lista de reglas de Lync (primero en el orden de procesamiento).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Movilidad para la implementación de dominio dividido

Un espacio de direcciones SIP compartido, también conocido como un *dominio dividido* o una *implementación híbrida* es una configuración en la que los usuarios se implementan en toda una implementación local y en un entorno en línea. El resultado deseado es tener un usuario, independientemente de dónde se encuentre su servidor principal (in situ o en línea), para iniciar sesión en la implementación y redirigirse a la ubicación de su servidor principal. Para ello, se usa la característica de detección automática de Microsoft Lync Server 2013 para redirigir el usuario en línea a la topología en línea. Esto se lleva a cabo mediante la configuración del localizador uniforme de recursos (URL) de detección automática mediante el shell de administración de Lync Server y los cmdlets **Get-CsHostingProvider** y **set-CsHostingProvider**.

Necesitará recopilar y registrar los siguientes atributos implementados:

  - Desde el shell de administración de Lync Server, escriba
    
        Get-CsHostingProvider

  - En los resultados, encuentre el proveedor en línea que tenga el atributo **ProxyFQDN**. Por ejemplo, sipfed.online.lync.com

  - Registre el valor del ProxyFQDN

  - Habilitación de la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea

  - Habilite la federación para el proveedor en línea. De manera predeterminada, todos los usuarios en línea están habilitados para la federación de dominios y pueden comunicarse con todos los dominios

  - Si desea definir dominios restringidos y permitidos, determine de manera explícita los dominios que permitirá y los que restringirá

  - Para la federación en línea, debe planificar registros host (A o AAAA, si utiliza IPv6) de DNS, certificados y excepciones de firewall. Asimismo, debe configurar las directivas de federación. Para obtener más información, consulte [Planning for Lync Server 2013 y Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

