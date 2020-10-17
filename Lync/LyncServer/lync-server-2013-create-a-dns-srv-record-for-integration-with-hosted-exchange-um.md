---
title: Crear un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada
description: Cree un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542146"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Crear un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

En este tema se describe cómo configurar el registro SRV del sistema de nombres de dominio (DNS) necesario para que un servidor perimetral de Lync Server 2013 pueda enrutar a un servicio de Exchange hospedado como Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Para crear un registro SRV de DNS externo para el servicio Exchange hospedado

1.  Inicie sesión en el servidor DNS externo como miembro del grupo DnsAdmins.

2.  Haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y seleccione el dominio SIP en el que se instalará Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]
    > Debe crear el registro SRV de DNS en el dominio SIP en que se va a instalar Lync Server. Al crear el registro SRV, el FQDN usado para el host que ofrece este campo de servicio debe ser el FQDN externo del grupo de servidores perimetrales. Por ejemplo, si el FQDN externo de su grupo de servidores perimetrales es edge01.contoso.net, escriba ese valor. Este debe estar también en el mismo dominio que el registro de host (A) de DNS.

    
    </div>

4.  Haga clic con el botón secundario en el dominio seleccionado y haga clic en **Registros nuevos**.

5.  En **Tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y en **Crear registro**.

6.  En **nuevo registro de recursos**, haga clic en **servicio**y, a continuación, escriba ** \_ sipfederationtls**.

7.  Haga clic en **Protocolo**y, a continuación, escriba ** \_ TCP**.

8.  Haga clic en **Número de puerto** y escriba **5061**.

9.  Haga clic en **host que ofrece este servicio**y, a continuación, escriba el nombre de dominio completo (FQDN) del grupo de servidores perimetrales de lync Server 2013 que proporciona acceso al sistema de lync Server 2013 para clientes externos de confianza.
    
    <div>
    

    > [!NOTE]
    > El dominio también debe estar configurado como un dominio aceptado y autoritativo en la configuración de Exchange Online. Para obtener más información, consulte crear dominios aceptados en <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> .

    
    </div>

10. Haga clic en **Aceptar** y en **Listo**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Para comprobar que el registro SRV de DNS se ha creado correctamente

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

3.  En el símbolo del sistema, ejecute el comando siguiente:
    
        nslookup <FQDN Lync Edge Pool>

4.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Crear registros DNS para servidores de proxy inverso en Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

