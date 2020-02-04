---
title: 'Lync Server 2013: Crear o editar un salón de chat nuevo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Crear o editar un salón de chat nuevo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-03-19_

La configuración de los salones de chat persistentes es común para los usuarios; un administrador de chat persistente, por lo general, no configura ni administra salones de chat. Los cmdlets de Windows PowerShell para administrar salas solo están disponibles para los administradores de **CsPersistentChatAdministrator** .

Los usuarios que son **creadores** de cualquier categoría pueden usar el cliente de Lync para crear y administrar salas. Los usuarios que se han designado como administradores de un salón de chat específico también pueden realizar la administración continuada de la sala, como editar las propiedades de la sala o la pertenencia.

<div>


> [!TIP]  
> Los administradores de chats persistentes también pueden ser creadores, y no están sujetos a las restricciones impuestas a los creadores.



</div>

De manera opcional, si es un administrador de chat persistente, puede usar una interfaz de usuario para crear y administrar salones de chat en lugar de usar cmdlets de Windows PowerShell. Para ello, habilite SIP para el servidor de chat persistente y, a continuación, use el cliente de Lync para crear y administrar los salones de chat.

Si desea crear un flujo de trabajo de administración de salas personalizado para los usuarios, puede establecer la propiedad **RoomManagementUrl** en la configuración del servidor de chat persistente para redirigir a los usuarios a la solución personalizada desde el cliente de Lync.

Para obtener detalles sobre la configuración de salones de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salas" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obtener más información sobre cómo configurar salones de chat, consulte [configurar salas en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.

<div>


> [!NOTE]  
> El servidor de chat persistente permite a los usuarios crear y administrar el salón de chat para un sitio específico. Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología. Asegúrese de especificar los creadores y administradores del salón de chat de todos los sitios de su organización.



</div>

<div>


> [!NOTE]  
> Los usuarios que estén alojados en un equipo con la aplicación de Lync Server superviviente no pueden crear nuevos salones de chat o ver la tarjeta de la sala de las habitaciones existentes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

