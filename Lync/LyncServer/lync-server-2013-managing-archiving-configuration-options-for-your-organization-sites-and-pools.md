---
title: 'Lync Server 2013: administración de las opciones de configuración de archivado para la organización, los sitios y los grupos de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498367"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En el panel de control de Lync Server 2013, se usan configuraciones de archivado para especificar cómo se implementa el archivado. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.

Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **configuración de archivado** del grupo **archivado y supervisión** para administrar las configuraciones en el nivel global, el nivel de sitio y el nivel de grupo. Para obtener información detallada sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que se pueden especificar y la jerarquía de las configuraciones de archivado, vea [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.

<div>


> [!NOTE]  
> Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para todos los usuarios hospedados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa. Si usa la integración de Microsoft Exchange, debe habilitar y configurar Exchange 2013 para que admita el archivado para todos los usuarios hospedados en Exchange 2013 cuyos buzones se hayan puesto en retención de In-Place.<BR>Antes de habilitar el archivado, especifique la configuración de archivado adecuada para su implementación y, de forma opcional, para determinas grupos y sitios, tal como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync Server 2013</A> en la documentación sobre implementación.



</div>

**Para ver la información de configuración de archivado con los cmdlets de Windows PowerShell**

  - Puede ver la información de configuración de archivado con Windows PowerShell y el cmdlet **Get-CsArchivingConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    En el shell de administración de Lync Server, use el siguiente comando para ver información sobre todas las opciones de configuración de archivado:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear una configuración de archivado en Lync Server 2013 para administrar el archivado de sitios o grupos de servidores específicos](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia en Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Habilitación o deshabilitación de la purga de datos archivados en Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Habilitación o deshabilitación del modo crítico en Lync Server 2013 para bloquear o permitir sesiones de mensajería instantánea y de conferencias web si se produce un error de archivado](lync-server-2013-enable-disable-critical-mode.md)

  - [Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitación o deshabilitación de la integración de Lync Server 2013 con almacenamiento de Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Eliminación de una configuración de archivado en Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Administración de archivado en Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

