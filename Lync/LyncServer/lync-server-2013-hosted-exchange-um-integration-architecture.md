---
title: 'Lync Server 2013: arquitectura de integración de mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9905fa6de1f8461d81ffe9d7e5cf79108c35e80c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

La aplicación Lync Server 2013 ExUM de enrutamiento admite la integración con una implementación de mensajería unificada (UM) de Exchange local, con mensajería unificada de Exchange hospedada por un proveedor de servicios o con una combinación de ambos. En el siguiente diagrama se muestran las tres posibilidades.

**Integración con una instalación de Exchange UM local y dos proveedores Exchange hospedados**

![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")

Se admiten los siguientes modos:

  - **Implementación local:** Lync Server 2013 y la mensajería unificada de Exchange se implementan en servidores locales de la empresa.

  - **Implementación entre locales:** Lync Server 2013 se implementa en servidores locales de la empresa y la mensajería unificada de Exchange se hospeda en las instalaciones de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.

  - **Implementación mixta:** La implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores de Exchange locales dentro de su empresa y algunos buzones de correo hospedados en un centro de datos de servicio de Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > La instalación mixta se puede usar a modo de solución transitoria durante la evaluación y migración por fases de usuarios a la mensajería unificada de Exchange o como solución permanente si opta por mantener algunos servicios de la mensajería unificada de Exchange de usuarios de forma local después de trasladar otros.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Espacio de direcciones SIP compartido

Para integrar Lync Server 2013 con una implementación local de mensajería unificada de Exchange, debe conceder el permiso de Lync Server 2013 para leer los objetos de servicios de dominio de Active Directory UM de Exchange. Sin embargo, este enfoque no funciona para la integración con la mensajería unificada de Exchange, ya que Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques independientes que no tienen ninguna confianza entre ellos.

Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido*. En esta configuración, el mismo espacio de direcciones de dominio SIP está disponible para Lync Server 2013 y para el proveedor de servicios de mensajería unificada de Exchange hospedado.

<div>


> [!NOTE]  
> El uso del espacio de direcciones SIP compartido es similar al método usado en un entorno entre locales de Lync Server 2013, en el que algunos usuarios están hospedados en la implementación local y otros están hospedados en una implementación hospedada (como Lync Online). El dominio SIP se divide entre ellos. Al integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, asegúrese de incluir el proveedor de servicios de mensajería unificada de Exchange en el espacio de direcciones SIP compartido.



</div>

Para configurar el espacio de direcciones SIP compartido para la integración con un proveedor de servicios de mensajería unificada de Exchange, deberá configurar su servidor perimetral de la siguiente forma:

1.  Configure el servidor perimetral para la federación ejecutando el **Set-CsAccessEdgeConfiguration** cmdlet y estableciendo los siguientes parámetros:
    
      - **UseDnsSrvRouting** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.
    
      - **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.
    
      - **EnablePartnerDiscovery** especifica si Lync Server 2013 usará registros DNS para intentar detectar dominios asociados que no aparecen en la lista de dominios permitidos de Active Directory. Si es false, Lync Server 2013 se federe solo con los dominios que se encuentran en la lista de dominios permitidos. Este parámetro es necesario si se usa el enrutamiento del servicio DNS. En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.

2.  Replique el almacén de administración central en el servidor perimetral y Compruebe la replicación. Para obtener más información, consulte [exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) en la documentación sobre implementación.

3.  Configure un *proveedor de hospedaje* en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** y estableciendo los siguientes parámetros:
    
      - **Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que se está creando, como, por ejemplo, **Mensajería unificada de Exchange hospedada**.
    
      - **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Debe estar establecido en **True**.
    
      - **EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido. Debe estar establecido en **True**.
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server 2013. Debe estar establecido en **False**.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) del servidor proxy que usa el proveedor de hospedaje, como, por ejemplo, **proxyserver.fabrikam.com**. Póngase en contacto con el proveedor de hospedaje para obtener esta información. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server 2013. Debe estar establecido en **False**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

