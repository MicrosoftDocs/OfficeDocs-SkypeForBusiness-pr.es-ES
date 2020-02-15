---
title: 'Lync Server 2013: crear o editar un salón nuevo'
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
ms.openlocfilehash: c445513cf112b335ce900ab8e39660210f0b5ef4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Crear o editar un salón nuevo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-03-19_

La configuración de salones de chat persistente suele ser controlada por los usuarios; un administrador de chat persistente no suele configurar ni administrar salones de chat. Los cmdlets de Windows PowerShell para administrar salas solo están disponibles para los administradores de **CsPersistentChatAdministrator** .

Los usuarios que son **creadores** en una categoría concreta pueden usar el cliente Lync para crear y administrar salones. Los usuarios designados como responsables de un salón de chat específico también pueden realizar tareas de administración continuas en el salón, por ejemplo, modificar las propiedades o los miembros del salón.

<div>


> [!TIP]  
> Los administradores de chat persistente también pueden ser creadores y no están sujetos a las restricciones impuestas en los creadores.



</div>

Opcionalmente, si es un administrador de chat persistente, puede usar una interfaz de usuario para crear y administrar salones de chat en lugar de usar los cmdlets de Windows PowerShell. Para ello, habilite SIP para el servidor de chat persistente y, a continuación, use el cliente Lync para crear y administrar salones de chat.

Si desea crear un flujo de trabajo de administración de salones personalizado para sus usuarios, puede establecer la propiedad **RoomManagementUrl** en la configuración del servidor de chat persistente para redirigir a los usuarios a la solución personalizada desde el cliente de Lync.

Para obtener más información sobre cómo configurar salones de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obtener más información sobre cómo configurar salones de chat, vea [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación sobre implementación.

<div>


> [!NOTE]  
> El servidor de chat persistente permite a los usuarios crear y administrar salones de chat para un sitio específico. Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología. Asegúrese de especificar los creadores y creadores de salones de chat para todos los sitios de la organización.



</div>

<div>


> [!NOTE]  
> Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

