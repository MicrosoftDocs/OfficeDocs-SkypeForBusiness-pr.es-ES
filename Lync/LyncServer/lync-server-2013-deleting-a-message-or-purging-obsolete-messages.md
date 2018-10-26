---
title: 'Lync Server 2013: Eliminación de un mensaje o depuración de mensajes obsoletos'
TOCTitle: Eliminación de un mensaje o depuración de mensajes obsoletos
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48275071
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un mensaje o depuración de mensajes obsoletos en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

Un administrador de Chat persistente puede eliminar un mensaje de una sala de Chat persistente (y, si lo desea, sustituirla por otro mensaje). Los administradores también pueden depurar mensajes obsoletos como parte del mantenimiento en curso, para minimizar el crecimiento de la base de datos. Por ejemplo, este comando Windows PowerShell elimina todos los mensajes del salón de chat ITChatRoom que publicó el usuario kenmyer@litwareinc.com:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

Y este ejemplo sustituye los mensajes eliminados por una advertencia de que el mensaje ya no se encuentra disponible:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Remove-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPersistentChatMessage).

