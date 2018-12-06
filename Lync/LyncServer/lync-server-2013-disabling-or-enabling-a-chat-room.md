---
title: 'Lync Server 2013: Habilitar o deshabilitar un salón de chat'
TOCTitle: Habilitar o deshabilitar un salón de chat
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48276890
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar un salón de chat en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

Si el tema de un salón de Chat persistente ya no es pertinente, deshabilítelo para los usuarios. Cuando se deshabilita una salón de chat, todos los miembros se desconectan inmediatamente del salón. Después de deshabilitar un salón de chat, los usuarios no pueden unirse a él o encontrarlo en las búsquedas de salones de chat.

Un administrador de Chat persistente puede habilitar más tarde un salón de chat deshabilitado. Si un salón de chat está deshabilitado, su lista de pertenencia y otras configuraciones se conservan. Si vuelve a habilitar el salón, necesitará volver a crear manualmente la configuración.

Si el historial del salón de chat persiste (la persistencia del historial del salón de chat es una configuración opcional en una categoría que se aplica a todos los salones de la categoría; la persistencia es el valor predeterminado, pero puede desactivarse configurando la **habilitación del historial del chat** en falso), el contenido se conserva cuando se deshabilita el salón de chat. No obstante, ese contenido no aparecerá en las búsquedas durante el tiempo que el salón de chat permanezca deshabilitado. Si más tarde habilita el salón de chat, los usuarios pueden buscar mensajes que se publicaron antes de que lo deshabilitara.

Para más información sobre la deshabilitación y habilitación de salones de chat con Interfaz de la línea de comandos Windows PowerShell, consulte "Administración de salones" en [Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Para deshabilitar un salón de chat, use un comando similar al siguiente:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Para habilitar un salón de chat, defina la propiedad Disabled en False:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Observe que los salones de chat no se pueden habilitar ni deshabilitar con Panel de control de Lync Server.

Para más información sobre la configuración de salones de chat, vea [Configurar salones en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.

