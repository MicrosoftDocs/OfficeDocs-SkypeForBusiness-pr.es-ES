---
title: Configurar el servidor de mediación
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurar el servidor de mediación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 09-2012-28_

Este procedimiento detallan los pasos para configurar el grupo de Lync Server 2013 para usar el servidor de mediación de Lync Server 2013, en lugar del antiguo servidor Office Communications Server 2007 R2 mediación.

Para publicar correctamente, habilitar o deshabilitar una topología al agregar o quitar una función de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos RTCUniversalServerAdmins y administradores de dominio. También es posible delegar los permisos para agregar funciones de servidor y derechos de administrador adecuados. Para obtener información detallada, vea delegar permisos de instalación en el servidor Standard Edition o Enterprise Edition documentación sobre implementación. Otros cambios de configuración, es necesaria sólo pertenencia en el grupo RTCUniversalServerAdmins.

<div>


> [!NOTE]  
> Para obtener la información más reciente sobre la búsqueda de puertas de enlace RTC cualificadas, sistemas IP-PBX y servicios de enlace troncal SIP que funcionan con Lync Server 2013, consulte "Microsoft Unified Communications Open Interoperability Program" en <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Para configurar el generador de topología de uso de servidor de mediación

1.  Abrir una topología existente desde el generador de topología.

2.  En el panel izquierdo, vaya a **puertas de enlace RTC**.

3.  Secundario **puertas de enlace RTC**y, a continuación, haga clic en **Nueva puerta de enlace IP/RTC**.

4.  Complete la página **Definir nueva puerta de enlace IP/RTC** con la siguiente información:
    
      - Escriba el FQDN o la dirección IP de puerta de enlace. El FQDN de la puerta de enlace es necesario si la puerta de enlace usa el protocolo TLS.
    
      - Acepte el valor predeterminado del **puerto de escucha para puerta de enlace IP/RTC** o escriba el puerto de escucha de nuevo si se ha modificado.
    
      - Establecer el **Protocolo de transporte de Sip**.

5.  En el panel izquierdo, desplácese hasta el **grupo de servidores Front-End de Enterprise Edition** o el **Servidor Standard Edition**.

6.  Haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.

7.  En **El servidor de mediación**, establezca los **puertos de escucha**.

8.  A continuación, asocie la puerta de enlace RTC recién creada seleccionándola y haciendo clic en **Agregar**.

9.  En **El generador de topología**, seleccione el nodo de nivel superior **Lync Server**.

10. En el menú **acción** , seleccione **Publicar topología** y, a continuación, haga clic en **siguiente**.

11. Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar** para cerrar al asistente.

<div>


> [!NOTE]  
> Es importante que complete el siguiente tema, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rutas de voz de cambio para usar el nuevo servidor de mediación de Lync Server 2013</A> para asegurarse de que las rutas de voz señalen al servidor de mediación correcto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

