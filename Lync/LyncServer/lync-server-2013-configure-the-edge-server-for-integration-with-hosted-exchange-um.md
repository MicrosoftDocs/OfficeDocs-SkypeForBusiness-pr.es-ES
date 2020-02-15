---
title: Configurar el servidor perimetral para la integración con mensajería unificada de Exchange hospedada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0779612ca4ebf33757f5d392d1619211aeb4a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>Configurar el servidor perimetral para la integración con mensajería unificada de Exchange hospedada

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-23_

Para proporcionar a los usuarios de Lync Server 2013 las funciones de correo de voz en la mensajería unificada (UM) de Exchange hospedada, debe realizar las siguientes tareas de configuración en el servidor perimetral:

  - Configure el servidor perimetral para la federación.

  - Replicar los datos del almacén de administración central en el servidor perimetral y comprobar la replicación.

  - Crear un proveedor de hospedaje en el servidor perimetral.

Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> Debe crear un registro SRV de DNS externo para el servicio Exchange de hospedaje antes de realizar estos pasos. Para obtener más información, vea <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">crear un registro SRV de DNS para la integración con mensajería unificada de Exchange hospedado</A>.



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>Para configurar el servidor perimetral para la federación.

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsAccessEdgeConfiguration para configurar el servidor para la federación. Por ejemplo, ejecute lo siguiente:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **UseDnsSrvRouting** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.
    
      - **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.
    
      - **EnablePartnerDiscovery** especifica si Lync Server usará registros DNS para intentar detectar dominios asociados que no aparecen en la lista de dominios permitidos de Active Directory. Si es false, Lync Server 2013 solo se federarse con los dominios que se encuentran en la lista de dominios permitidos. Este parámetro es necesario si se usa el enrutamiento del servicio DNS. En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>Para replicar los datos en el servidor perimetral y comprobar la replicación.

  - Compruebe que la replicación de datos en el servidor perimetral se haya completado. Para consultar el procedimiento, consulte [Verify Connectivity between Internal Servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>Para crear un proveedor de hospedaje en el servidor perimetral

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsHostingProvider** para configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear, en este ejemplo es **Fabrikam.com**. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor con dicho valor de Identity.
    
      - **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.
    
      - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).
        
        <div>
        

        > [!NOTE]
        > Antes de establecer <CODE>EnableSharedAddressSpace</CODE> en true, intente resolver el registro SRV de Federación internamente. Si este registro no se puede resolver internamente, debe crear los registros _sipfederationtls. _tcp. &lt;domain&gt; y _sip. _tls. &lt;dominio&gt; en el DNS interno. Estos registros deben apuntar a la dirección IP externa de la interfaz de acceso del servidor perimetral.

        
        </div>
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server 2013. Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje, que en este ejemplo es **proxyserver.fabrikam.com**. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server 2013.
    
      - **VerficationLevel** indica el nivel de comprobación permitido para los mensajes enviados a y desde el proveedor de hospedaje. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si no se especifica el nivel, se rechazará el mensaje como no verificable.

</div>

<div>

## <a name="see-also"></a>Vea también


[Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

