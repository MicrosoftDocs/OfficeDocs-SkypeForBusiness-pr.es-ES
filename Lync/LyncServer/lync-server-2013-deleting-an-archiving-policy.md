---
title: 'Lync Server 2013: eliminación de una directiva de archivado'
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
ms.openlocfilehash: 387c7dcbf1d53b99bb3dd31b308ff4786f8f5803
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525427"
---
# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Eliminación de una directiva de archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Es posible eliminar directivas de usuario o de sitio. Las directivas globales no se pueden quitar. Si intenta eliminar la directiva global, Lync Server 2013 restablece automáticamente la Directiva a los valores predeterminados.

<div>


> [!NOTE]  
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios hospedados en Exchange 2013 y para los que sus buzones se han puesto en espera In-Place. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>Para eliminar una directiva de usuario o de sitio para archivado

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.

4.  En la lista de directivas, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, a continuación, en **Eliminar**.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Eliminación de directivas de archivado con los cmdlets de Windows PowerShell

Las directivas de archivado se pueden eliminar con Windows PowerShell y el cmdlet **Remove-CsArchivingPolicy** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>Para quitar una directiva de archivado especificada

  - Como ejemplo, **Remove-CsArchivingPolicy** elimina la directiva con el sitio de identidad: Redmond. Tenga en cuenta que, cuando se elimina una directiva configurada en el ámbito de aplicación de sitio, los usuarios anteriormente administrados por la directiva del sitio, en su lugar, se regirán automáticamente por la directiva global de archivado. El comando siguiente quita el archivado aplicado en el sitio Redmond:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>Para quitar todas las directivas de archivado aplicadas al ámbito por usuario

  - Este comando quita todas las directivas de archivado aplicadas al ámbito por usuario:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>Para quitar todas las directivas de archivado que deshabilitan el archivado interno

  - Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Administración del archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

