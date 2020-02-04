---
title: 'Lync Server 2013: eliminar una directiva de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Eliminar una directiva de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede eliminar una directiva de usuario o una directiva de sitio. No se puede quitar la directiva global. Si intenta eliminar la directiva global, Lync Server 2013 restablece automáticamente la Directiva a los valores predeterminados.

<div>


> [!NOTE]  
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en la retención local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>Para eliminar un usuario o una directiva de sitio para archivar

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  En la lista de directivas de archivado, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, luego, en **Eliminar**.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Quitar directivas de archivado mediante cmdlets de Windows PowerShell

Las directivas de archivado se pueden eliminar mediante Windows PowerShell y el cmdlet **Remove-CsArchivingPolicy** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>Para quitar una directiva de archivado especificada

  - A modo de ejemplo, **Remove-CsArchivingPolicy** elimina la Directiva con el sitio de identidad: Redmond. Tenga en cuenta que, cuando se elimina una directiva configurada en el ámbito del sitio, los usuarios administrados previamente por la Directiva del sitio se regirán automáticamente por la Directiva de archivado global. El siguiente comando quita el archivado aplicado al sitio de Redmond:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>Para quitar todas las directivas de archivado aplicadas al ámbito de cada usuario

  - Este comando quita todas las directivas de archivado aplicadas al ámbito de cada usuario:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>Para quitar todas las directivas de archivado que deshabilitan el archivado interno

  - Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar el archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

