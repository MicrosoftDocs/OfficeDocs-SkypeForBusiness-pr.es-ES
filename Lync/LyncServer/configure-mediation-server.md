---
title: Configurar servidor de mediación
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurar servidor de mediación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Este procedimiento detalla los pasos para configurar el grupo de servidores de Lync 2013 para que usen el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins. También es posible delegar los derechos y permisos de administrador adecuados para agregar roles de servidor. Para obtener más información, consulte permisos de configuración de delegación en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.

<div>


> [!NOTE]  
> Para obtener la información más reciente sobre la búsqueda de puertas de enlace RTC calificadas, IP-PBX y los servicios de Troncalización SIP que funcionan con Lync Server 2013, consulte "programa de <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>interoperabilidad abierto de comunicaciones unificadas de Microsoft" en.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Para configurar el servidor de mediación con el generador de topología

1.  Abra una topología existente desde el generador de topología.

2.  En el panel de la izquierda, vaya a **puertas de enlace RTC**.

3.  Haga clic con el botón secundario en **puertas de enlace RTC**y luego haga clic en **nueva puerta de enlace IP/PSTN**.

4.  Complete la página **definir nueva puerta de enlace IP/RTC** con la siguiente información:
    
      - Escriba la dirección IP o el FQDN de la puerta de enlace. El FQDN de la puerta de enlace es obligatorio si la puerta de enlace usa el protocolo TLS.
    
      - Acepte el valor predeterminado del **Puerto de escucha para la puerta de enlace IP/PSTN** o introduzca el nuevo puerto de escucha si se modificó.
    
      - Configurar el **Protocolo de transporte SIP**.

5.  En el panel de la izquierda, navegue hasta el **grupo de servidores front-end Enterprise Edition** o el **servidor Standard Edition**.

6.  Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.

7.  En **servidor**de mediación, configure los **puertos de escucha**.

8.  A continuación, para asociar la puerta de enlace RTC recién creada, selecciónela y haga clic en **Agregar**.

9.  En el **generador**de topologías, seleccione el nodo de nivel superior de **Lync Server**.

10. En el menú **acción** , seleccione **publicar topología** y, a continuación, haga clic en **siguiente**.

11. Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.

<div>


> [!NOTE]  
> Es importante que complete el siguiente tema, cambie las <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rutas de voz para usar el nuevo servidor de mediación de Lync server 2013</A> para asegurarse de que las rutas de voz apuntan al servidor de mediación correcto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

