---
title: "Lync Server 2013: Arquitectura de integración mensajería unificada Exchange hospedada"
TOCTitle: Arquitectura de integración de mensajería unificada de Exchange hospedada
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48274228
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-25_

La aplicación Lync Server 2013 ExUM Routing admite la integración con una instalación de Mensajería unificada de Exchange (UM) local, con Exchange UM hospedado por un proveedor de servicios o con una combinación de ambos. En el siguiente diagrama se muestran las tres posibilidades.

**Integración con una instalación de Exchange UM local y dos proveedores Exchange hospedados**

![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")

Se admiten los siguientes modos:

  - **Instalación local :** Lync Server 2013 y la mensajería unificada de Exchange se implementan ambos en servidores locales de la empresa.

  - **Instalación externa :** Lync Server 2013 se instala en servidores locales de la empresa y la mensajería unificada de Exchange se hospeda en las instalaciones de un proveedor de servicios en línea, como el centro de datos de Microsoft Exchange Online.

  - **Instalación mixta :** La instalación de Lync Server 2013 tiene algunos buzones de usuario ubicados en servidores de Exchange locales de su empresa y otros ubicados en un centro de datos de servicio de Exchange hospedado.
    

    > [!NOTE]
    > La instalación mixta se puede usar a modo de solución transitoria durante la evaluación y migración por fases de usuarios a la mensajería unificada de Exchange o como solución permanente si opta por mantener algunos servicios de la mensajería unificada de Exchange de usuarios de forma local después de trasladar otros.



## Espacio de direcciones SIP compartido

Para integrar Lync Server 2013 con una instalación de mensajería unificada de Exchange local, debe conceder permiso a Lync Server 2013 para leer objetos de Servicios de dominio de Active Directory de mensajería unificada de Exchange. No obstante, este procedimiento no funciona para la integración con la mensajería unificada de Exchange hospedada, ya que Lync Server 2013 y la mensajería unificada de Exchange están instalados en bosques independientes sin confianza entre ellos.

Para integrar Lync Server 2013 con la mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido* . En esta configuración, el mismo espacio de dirección de dominio SIP estará disponible para Lync Server 2013 y para el proveedor de servicios de mensajería unificada de Exchange hospedada.


> [!NOTE]
> El uso del espacio de direcciones SIP compartido es similar al que se hace en un entorno de Lync Server 2013 externo, en el que algunos usuarios están hospedados en la instalación local y otros lo están en una instalación hospedada (como, por ejemplo, Lync Online). El dominio SIP se divide entre ellos. Cuando se integre Lync Server 2013 con la mensajería unificada de Exchange hospedada, asegúrese de que se incluye el proveedor de servicios de mensajería unificada de Exchange en el espacio de direcciones SIP compartido.



Para configurar el espacio de direcciones SIP compartido para la integración con un proveedor de servicios de mensajería unificada de Exchange, deberá configurar su servidor perimetral de la siguiente forma:

1.  Configure el servidor perimetral para la federación ejecutando el **Set-CsAccessEdgeConfiguration** cmdlet y estableciendo los siguientes parámetros:
    
      - **UseDnsSrvRouting** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.
    
      - **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.
    
      - **EnablePartnerDiscovery** especifica si Lync Server 2013 utilizará registros DNS para intentar descubrir dominios de socios que no aparecen en la lista de dominios permitidos de Active Directory. Si está definido en False, Lync Server 2013 solo establecerá relaciones de federación con dominios que figuren en la lista de dominios permitidos. Este parámetro es necesario si se usa el enrutamiento del servicio DNS. En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.

2.  Replique el Almacén de administración central en el servidor perimetral y verifique la replicación. Para obtener más información, consulte [Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) en la documentación sobre implementación.

3.  Configure un *proveedor de hospedaje* en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** y estableciendo los siguientes parámetros:
    
      - **Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que se está creando, como, por ejemplo, **Mensajería unificada de Exchange hospedada** .
    
      - **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Debe estar establecido en **True** .
    
      - **EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido. Debe estar establecido en **True** .
    
      - **HostsOCSUsers** indica si se usará el proveedor de hospedaje para hospedar las cuentas de Lync Server 2013. Debe estar establecido en **False** .
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) del servidor proxy que usa el proveedor de hospedaje, como, por ejemplo, **proxyserver.fabrikam.com** . Póngase en contacto con el proveedor de hospedaje para obtener esta información. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **IsLocal** indica si el servidor proxy que usa el proveedor de hospedaje está incluido en la topología de Lync Server 2013. Debe estar establecido en **False**.

