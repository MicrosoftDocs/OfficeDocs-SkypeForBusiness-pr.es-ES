---
title: 'Lync Server 2013: Definir una dirección IP de puerta de enlace SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Si Lync Server se conecta a la puerta de enlace SIP/CSTA que ha implementado para el control remoto de llamadas mediante una conexión de protocolo de control de transmisión (TCP), debe definir la dirección IP de la puerta de enlace en el generador de topología. Este paso no es necesario para las puertas de enlace que admiten conexiones de seguridad de la capa de transporte (TLS). Para cualquier puerta de enlace que admita conexiones TLS, puede omitir este procedimiento y continuar con la implementación de control de llamada remota siguiendo los pasos de [Habilitar usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Para definir la dirección IP de la puerta de enlace SIP/CSTA con el generador de topología

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

3.  Elija la opción para descargar una topología existente.

4.  Expanda el nodo **servidores de aplicaciones de confianza** .

5.  Haga clic con el botón secundario en el grupo de aplicaciones de confianza que ha creado, como se describe en [configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)y, a continuación, haga clic en **Editar propiedades**.

6.  Desactive la casilla **Habilitar la replicación de datos de configuración en este grupo** .

7.  Haga clic en **limitar el uso del servicio a las direcciones IP seleccionadas**. La configuración predeterminada es **usar todas las direcciones IP**configuradas.

8.  En el cuadro de texto **dirección IP principal** , escriba la dirección IP de la puerta de enlace SIP/CSTA.

9.  Para actualizar la topología en el almacén central de administración, en el árbol de consola, haga clic en **Lync Server**y, a continuación, en el panel **acciones** , haga clic en **publicar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

