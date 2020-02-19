---
title: Configurar el servidor de mediación
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 432c1f7d90a81e935876e5bd71cc9d8eedf4a28b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurar el servidor de mediación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

En este procedimiento se detallan los pasos para configurar el grupo de servidores de Lync Server 2013 para usar el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, es necesario haber iniciado sesión como usuario miembro de los grupos Admins del dominio y RTCUniversalServerAdmins. También es posible delegar los derechos y permisos de administrador adecuados para agregar roles de servidor. Para obtener información detallada, consulte Delegate Setup Permissions en la documentación referente a la implementación de servidores Standard Edition o Enterprise Edition. Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.

<div>


> [!NOTE]  
> Para obtener la información más reciente sobre cómo buscar puertas de enlace RTC cualificadas, IP-PBX y servicios de enlace troncal SIP que funcionen con Lync Server 2013, consulte "Microsoft Unified Communications <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>Open Interoperability Program" en.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Para configurar el servidor de mediación mediante el generador de topologías

1.  Abre una topología existente del Generador de topologías.

2.  En el panel de la izquierda, navegue a **Puertas de enlace RTC**.

3.  Haga clic con el botón secundario en **Puertas de enlace RTC ** y, a continuación, haga clic en **Nueva puerta de enlace IP/RTC **.

4.  Complete la página **Definir nueva puerta de enlace IP/RTC ** con la siguiente información:
    
      - Indique el FQDN de puerta de enlace o la dirección IP. El FQDN de la puerta de enlace es obligatorio si la puerta de enlace utiliza el protocolo TLS.
    
      - Acepte el valor predeterminado de la opción **Puerto de escucha para la puerta de enlace IP/RTC** o, si se ha modificado, especifique el nuevo puerto de escucha.
    
      - Establezca el **	Protocolo de transporte SIP**.

5.  En el panel de la izquierda, navegue al **grupo de servidores front-end Enterprise Edition** o al **servidor Standard Edition**.

6.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

7.  En **Servidor de mediación**, defina los **Puertos de escucha**.

8.  A continuación, asocie la puerta de enlace RTC recién creada seleccionándola y haciendo clic en **Agregar**.

9.  En el **Generador de topologías**, seleccione el primer nodo **Lync Server**.

10. En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.

11. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

<div>


> [!NOTE]  
> Es importante que complete el siguiente tema, cambie las <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</A> para asegurarse de que las rutas de voz señalen al servidor de mediación correcto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

