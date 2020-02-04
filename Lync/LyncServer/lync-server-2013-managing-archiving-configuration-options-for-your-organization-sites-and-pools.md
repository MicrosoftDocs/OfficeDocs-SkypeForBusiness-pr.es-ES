---
title: 'Lync Server 2013: administración de las opciones de configuración de archivado para su organización, sitios y grupos'
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
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En el panel de control de Lync Server 2013, se usan configuraciones de archivado para especificar cómo se implementa el archivado. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.

Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **configuración de archivado** del grupo **archivado y supervisión** para administrar las configuraciones a nivel global, nivel de sitio y nivel de grupo. Para obtener detalles sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.

<div>


> [!NOTE]  
> Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos para todos los usuarios alojados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas. Si usa la integración de Microsoft Exchange, debe habilitar y configurar Exchange 2013 para que admita el archivado de todos los usuarios alojados en Exchange 2013 que hayan puesto sus buzones en conservación local.<BR>Antes de habilitar el archivado, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.



</div>

**Para ver la información de configuración de archivado mediante cmdlets de Windows PowerShell**

  - Puede ver la información de configuración de archivado mediante Windows PowerShell y el cmdlet **Get-CsArchivingConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.
    
    En el shell de administración de Lync Server, use el siguiente comando para ver información sobre todas las opciones de configuración de archivado:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>En esta sección

  - [Creación de una configuración de archivado en Lync Server 2013 para administrar el archivado de sitios o grupos específicos](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Habilitar o deshabilitar el archivado de sesiones de mensajería instantánea o de conferencia en Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Habilitar o deshabilitar la purga de datos archivados en Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Habilitar o deshabilitar el modo crítico en Lync Server 2013 para bloquear o permitir sesiones de mensajería instantánea y Web si se produce un error de archivado](lync-server-2013-enable-disable-critical-mode.md)

  - [Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar o deshabilitar la integración de Lync Server 2013 con almacenamiento de Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Eliminar una configuración de archivado en Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de archivado en Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

