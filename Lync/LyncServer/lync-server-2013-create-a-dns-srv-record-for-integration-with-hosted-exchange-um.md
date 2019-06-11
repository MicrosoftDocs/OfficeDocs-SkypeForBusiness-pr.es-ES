---
title: Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f96b8873e7d83b7025b43b111312185b8e5d5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

En este tema se describe cómo configurar el registro SRV de sistema de nombres de dominio (DNS) necesario para que un servidor perimetral de Lync Server 2013 se pueda enrutar a un servicio de Exchange hospedado como Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Para crear un registro SRV de DNS externo para el servicio hospedado de Exchange

1.  Inicie sesión en el servidor DNS externo como miembro del grupo DnsAdmins.

2.  Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **DNS**.

3.  En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**y seleccione el dominio SIP en el que se instalará Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]
    > Debe crear el registro SRV de DNS en el dominio SIP en el que se instalará o se instalará Lync Server. Al crear el registro SRV, el FQDN usado para el host que ofrece este campo de servicio debe ser el FQDN externo del grupo Edge. Por ejemplo, si el nombre completo externo del grupo de servidores perimetrales es edge01.contoso.net, escriba ese valor. También debe estar en el mismo dominio que el registro de hosts DNS (A).

    
    </div>

4.  Haga clic con el botón secundario en el dominio seleccionado y, a continuación, haga clic en **otros registros nuevos**.

5.  En **tipo de registro de recursos**, haga clic en **Ubicación de servicio (SRV)** y, a continuación, haga clic en **crear registro**.

6.  En **nuevo registro de recursos**, haga clic en **servicio**y, a continuación, escriba ** \_sipfederationtls**.

7.  Haga clic en **Protocolo**y, a continuación, escriba ** \_TCP**.

8.  Haga clic en **Número de puerto** y, luego, escriba **5061**.

9.  Haga clic en **host que ofrece este servicio**y, a continuación, escriba el nombre de dominio completo (FQDN) del grupo perimetral de lync Server 2013 que proporciona acceso a su sistema de lync Server 2013 para clientes externos de confianza.
    
    <div>
    

    > [!NOTE]
    > El dominio también debe configurarse como un dominio autorizado y aceptado en la configuración de Exchange Online. Para obtener más información, consulte crear dominios <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>aceptados en.

    
    </div>

10. Haga clic en **Aceptar** y, luego, haga clic en **Listo**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Para comprobar que el registro SRV de DNS se ha creado correctamente

1.  Inicie sesión en un equipo cliente del dominio.

2.  Haga clic en  **Inicio ** y en  **Ejecutar **.

3.  En el símbolo del sistema, ejecute el siguiente comando:
    
        nslookup <FQDN Lync Edge Pool>

4.  Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear registros DNS para servidores de proxy inverso en Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

