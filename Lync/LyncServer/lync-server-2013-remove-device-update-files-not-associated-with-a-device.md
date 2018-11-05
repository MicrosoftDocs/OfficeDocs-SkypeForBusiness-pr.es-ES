---
title: "Quitar archivos de actualización de dispositivos no asociados a un dispositivo"
TOCTitle: "Supp. fichiers de màj de périph. plus associés à aucun périphérique"
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994084(v=OCS.15)
ms:contentKeyID: 52061959
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar los archivos de actualización de dispositivos que no estén asociados a un dispositivo

 

_**Última modificación del tema:** 2013-02-20_

Cada vez que se carga una nueva actualización de dispositivo en el sistema, se crea la regla de actualización de dispositivo correspondiente. Estas nuevas reglas de actualización de dispositivo se asignan de forma predeterminada en estado pendiente. Esto quiere decir que las reglas se pueden descargar e instalar en dispositivos de prueba, pero no en dispositivos de producción, de modo que las actualizaciones se pueden comprobar antes de ponerlas a disposición del usuario. Según las pruebas, se puede aceptar e implementar la actualización, o bien rechazarla y eliminarla. Cuando una actualización se rechaza, la actualización de dispositivo deja de estar asociada a la regla de actualización de dispositivo.


Los archivos de actualización de dispositivo que ya no estén asociados a un dispositivo también se pueden eliminar mediante Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateFile**. Este cmdlet se ejecuta desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




  - Por ejemplo, con el siguiente comando se eliminan todas las reglas de actualización de dispositivo del servidor web atl-cs-001.litwareinc.com que ya no estén asociadas a un dispositivo:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

Para más información detallada, vea el tema de ayuda relativo al cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateFile).

