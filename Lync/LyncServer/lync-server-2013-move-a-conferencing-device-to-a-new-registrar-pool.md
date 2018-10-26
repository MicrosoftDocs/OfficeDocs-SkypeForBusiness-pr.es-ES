---
title: "Déplacer un disp. de conf. vers un nouveau pool de serveurs d’inscriptions"
TOCTitle: "Déplacer un disp. de conf. vers un nouveau pool de serveurs d’inscriptions"
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994025(v=OCS.15)
ms:contentKeyID: 52061620
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover un dispositivo de conferencia a un grupo de registradores nuevo

 

_**Última modificación del tema:** 2013-02-20_

Mueva un dispositivo de conferencias de un grupo de registradores a otro mediante el cmdlet **Move-CsMeetingRoom**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Traslado de un dispositivo de conferencias a un nuevo grupo de registradores

  - Para mover un dispositivo de conferencias, debe especificar la identidad de la sala que se moverá y, a continuación, establecer el parámetro Target en el nombre de dominio completo (FQDN) del grupo de registradores al cual se moverá el dispositivo. Por ejemplo:
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

Para obtener información detallada, consulte el tema de Ayuda acerca del cmdlet [Move-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsMeetingRoom).

