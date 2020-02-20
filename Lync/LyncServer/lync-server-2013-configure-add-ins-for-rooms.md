---
title: 'Lync Server 2013: configure Add-Ins for Rooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27dd6ab5cdd6ca67d94071049a9615731735d8aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configurar complementos para salones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En el panel de control de Lync Server 2013, puede usar la sección de **complemento** de la página **chat persistente** para asociar direcciones URL con salones de chat persistente. Estas direcciones URL aparecen en el cliente de Lync 2013 en el salón de chat del panel extensibilidad de conversaciones. Un administrador debe agregar complementos a la lista de complementos registrados y los administradores o creadores de salones de chat tienen que asociar salas con uno de los complementos registrados para que los usuarios puedan ver esta actualización en su cliente de Lync 2013.

Los complementos se usan para ampliar la experiencia en el salón. Un complemento típico puede incluir una dirección URL que apunta a una aplicación de Silverlight que intercepta cuando se publica un tablero de cotizaciones en un salón de chat y muestra el historial de cotizaciones en el panel extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Procedimiento para configurar complementos para salones de chat

1.  Desde una cuenta de usuario asignada al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en un equipo de la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Complemento**.
    
    Para varias implementaciones del grupo de servidores de chat persistente, seleccione el grupo adecuado de la lista desplegable.

4.  En la página **Complemento**, haga clic en **Nuevo**.

5.  En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.

6.  En **Nuevo complemento**, haga lo siguiente:
    
      - En **Nombre **, especifique un nombre para el nuevo complemento.
    
      - En **Dirección URL**, especifique la dirección URL que se va a asociar con el complemento. Las direcciones URL están limitadas a los protocolos http y https.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

