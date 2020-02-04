---
title: 'Lync Server 2013: Configurar complementos para salones'
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
ms.openlocfilehash: 8389f72394be26057eb12560c054bd5292b528f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configurar complementos para salones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En el panel de control de Lync Server 2013, puede usar la sección de **complemento** de la página de **chat persistente** para asociar direcciones URL a salas de chat persistentes. Estas direcciones URL aparecen en el cliente de Lync 2013, en el salón de chat del panel extensibilidad de conversaciones. Un administrador debe agregar complementos a la lista de complementos registrados y los administradores o creadores de salones de chat tienen que asociar salas a uno de los complementos registrados para que los usuarios puedan ver esta actualización en su cliente de Lync 2013.

Los complementos sirven para ampliar la experiencia en el salón. Un complemento típico puede incluir una dirección URL que señala a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones está publicado en un salón de chat y muestra el historial de cotizaciones en el panel extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar complementos para salones de chat

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.
    
    Para varias implementaciones del grupo de servidores de chat persistentes, seleccione el grupo adecuado de la lista desplegable.

4.  En la página **Complemento**, haga clic en **Nuevo**.

5.  En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro o compartirse entre diferentes grupos.

6.  En **Complemento nuevo**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para el nuevo complemento.
    
      - En **URL**, especifique la dirección URL que se va a asociar al complemento. Las direcciones URL se limitan a protocolos http y https.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

