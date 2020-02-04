---
title: 'Lync Server 2013: Arquitectura de integración de mensajería unificada de Exchange hospedada'
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
ms.openlocfilehash: 49fbb815514d9a338412b638bdf373a285ebf6f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

La aplicación de enrutamiento ExUM de Lync Server 2013 admite la integración con una implementación local de mensajería unificada (UM) de Exchange, con mensajería unificada de Exchange hospedada por un proveedor de servicios o con una combinación de ambas. En el siguiente diagrama se muestran las tres posibilidades.

**Integración con una implementación local de mensajería unificada de Exchange y dos proveedores de Exchange hospedados**

![Implementación de mensajería unificada de Exchange de Lync Server local](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación de mensajería unificada de Exchange de Lync Server local")

Se admiten los siguientes modos:

  - **Implementación local:** Lync Server 2013 y la mensajería unificada de Exchange se implementan en servidores locales de su empresa.

  - **Implementación entre locales:** Lync Server 2013 se implementa en servidores locales de su empresa y la mensajería unificada de Exchange se hospeda en una instalación de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.

  - **Implementación mixta:** Su implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores locales de Exchange dentro de su empresa y algunos buzones alojados en un centro de datos de servicio de Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > La implementación mixta se puede usar como solución transitoria durante la evaluación y la migración por fases de los usuarios a la mensajería unificada de Exchange hospedada o una solución permanente si opta por mantener locales los servicios de mensajería unificada de Exchange de los usuarios después de transferir otros.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Espacio de direcciones SIP compartido

Para integrar Lync Server 2013 con una implementación local de mensajería unificada de Exchange, debe conceder el permiso de Lync Server 2013 para leer los objetos de servicios de dominio de Active Directory UM de Exchange. Sin embargo, este enfoque no funciona con la integración con la mensajería unificada de Exchange hospedada, ya que Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques independientes sin ninguna confianza entre ellos.

Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido*. En esta configuración, el mismo espacio de direcciones de dominio SIP está disponible para Lync Server 2013 y para el proveedor de servicios de mensajería unificada de Exchange hospedado.

<div>


> [!NOTE]  
> El uso del espacio de direcciones SIP compartido es similar al que se usa en un entorno de Lync Server 2013 entre locales, en el que algunos usuarios se hospedan en la implementación local y algunos están alojados en una implementación hospedada (como Lync Online). El dominio SIP se divide entre ellos. Al integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, asegúrese de incluir el proveedor de servicios de mensajería unificada de Exchange en el espacio de direcciones SIP compartido.



</div>

Para configurar el espacio de direcciones SIP compartido para la integración con un proveedor de servicios de mensajería unificada de Exchange, debe configurar el servidor perimetral de la siguiente manera:

1.  Configure el servidor perimetral para la Federación ejecutando el cmdlet **set-CsAccessEdgeConfiguration** para establecer los siguientes parámetros:
    
      - **UseDnsSrvRouting ** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.
    
      - **AllowFederatedUsers ** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.
    
      - **EnablePartnerDiscovery** especifica si Lync Server 2013 usará registros DNS para intentar descubrir dominios asociados que no se enumeran en la lista de dominios permitidos de Active Directory. Si es falso, Lync Server 2013 solo se va a federar a los dominios que se encuentran en la lista de dominios permitidos. Este parámetro es necesario si se usa el enrutamiento del servicio DNS. En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.

2.  Replique el almacén de administración central en el servidor perimetral y verifique la replicación. Para obtener información detallada, consulte [exportar su topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) en la documentación de implementación.

3.  Configure un *proveedor de hospedaje* en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** para establecer los siguientes parámetros:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando, por ejemplo, **mensajería unificada de Exchange hospedado**.
    
      - **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Debe establecerse en **true**.
    
      - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Debe establecerse en **true**.
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server 2013. Debe establecerse en **false**.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) del servidor proxy usado por el proveedor de hospedaje, por ejemplo, **proxyserver.fabrikam.com**. Póngase en contacto con el proveedor de hospedaje para obtener esta información. Este valor no puede modificarse. Si el proveedor de hospedaje cambia su servidor proxy, tendrá que eliminar y volver a crear la entrada de ese proveedor.
    
      - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en su topología de Lync Server 2013. Debe establecerse en **false**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

