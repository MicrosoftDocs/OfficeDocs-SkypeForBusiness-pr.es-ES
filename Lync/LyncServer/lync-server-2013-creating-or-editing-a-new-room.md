---
title: 'Lync Server 2013: Crear o editar un salón de chat nuevo'
TOCTitle: Crear o editar un salón de chat nuevo
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48276303
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o editar un salón de chat nuevo en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-19_

Los usuarios suelen controlar la configuración de los salones de Chat persistente. Por lo general, los administradores de Chat persistente no configuran ni administran los salones de chat. Los cmdlets del Windows PowerShell para administrar los salones de chat solo están disponibles para los administradores **CsPersistentChatAdministrator**.

Los usuarios que son **creadores** en cualquier categoría determinada pueden usar el cliente de Lync para crear y administrar salones. Los usuarios designados como responsables de un salón de chat específico también pueden realizar tareas de administración continuas en el salón, por ejemplo, modificar las propiedades o los miembros del salón.

> [!TIP]  
> Los administradores de Chat persistente también pueden ser creadores, pero no están sujetos a las restricciones impuestas en los creadores.



Además, si es un administrador de Chat persistente, puede emplear una interfaz de usuario para crear y administrar salones de chat, en lugar de usar los cmdlets de Windows PowerShell. Para ello, habilite para SIP un administrador para el Servidor de chat persistente, y luego use el cliente de Lync para crear y administrar salones de chat.

Si desea crear un flujo de trabajo de administración de salones personalizado para los usuarios, puede establecer la propiedad **RoomManagementUrl** en la configuración del Servidor de chat persistente a fin de redirigir a los usuarios hasta su solución personalizada desde el cliente de Lync.

Para más información sobre cómo configurar salones de chat con la Interfaz de la línea de comandos Windows PowerShell, vea "Administrar salones" en [Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para más información sobre la configuración de salones de chat, vea [Configurar salones en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.

