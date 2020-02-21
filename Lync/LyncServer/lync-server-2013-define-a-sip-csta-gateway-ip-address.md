---
title: 'Lync Server 2013: definir una dirección IP de puerta de enlace SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59b2d236cc9a261f07b2f2e9dc26102efff908f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Si Lync Server se conectará a la puerta de enlace SIP/CSTA que implementó para el control remoto de llamadas mediante una conexión de protocolo de control de transmisión (TCP), debe definir la dirección IP de la puerta de enlace en el generador de topologías. Este paso no es necesario para puertas de enlace compatibles con conexiones de Seguridad de la capa de transporte (TLS). Para cualquier puerta de enlace que admita conexiones TLS, puede omitir este procedimiento y continuar con la implementación del control remoto de llamadas siguiendo los pasos descritos en [Habilitar usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Para definir la dirección IP de la puerta de enlace SIP/CSTA con el Generador de topologías

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

3.  Elija la opción para descargar una topología existente.

4.  Expanda el nodo **Servidores de aplicaciones de confianza**.

5.  Haga clic con el botón secundario en el grupo de aplicaciones de confianza que ha creado, como se describe en [configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)y, a continuación, haga clic en **Editar propiedades**.

6.  Desactive la casilla **Habilitar replicación de datos de configuración en este grupo de servidores**.

7.  Haga clic en **Limitar el uso del servicio a las direcciones IP seleccionadas**. La configuración predeterminada es **Usar todas las direcciones IP configuradas**.

8.  En el cuadro de texto **Dirección IP principal**, escriba la dirección IP de la puerta de enlace SIP/CSTA.

9.  Para actualizar la topología en el almacén de administración central, en el árbol de la consola, haga clic en **Lync Server** y, desde el panel **Acciones**, haga clic en **Publicar**.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

