---
title: 'Lync Server 2013: Agregar texto personalizado a los mensajes instantáneos'
TOCTitle: Agregar texto personalizado a los mensajes instantáneos
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398847(v=OCS.15)
ms:contentKeyID: 52061762
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar texto personalizado a los mensajes instantáneos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-20_

Agregue una declinación de responsabilidades o una advertencia al inicio de cada conversación de mensajería instantánea de Lync 2013 mediante los cmdlets **New-CSClientPolicy** o **Set-CSClientPolicy**Shell de administración de Lync Server con el parámetro IMWarning.

El comando del siguiente ejemplo agrega un recordatorio de seguridad en la parte superior de la ventana de conversación siempre que se inicia una nueva conversación de mensajería instantánea:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios. Para más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del Shell de administración de Lync Server.

