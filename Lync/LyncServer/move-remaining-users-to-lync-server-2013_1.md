---
title: Mover los usuarios restantes a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afb495a3500491bb85e9107770ec12f9544832b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Mover los usuarios restantes a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Puede mover usuarios a la nueva implementación de Lync Server 2013 mediante el panel de control de Lync Server o el shell de administración de Lync Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Lync Server 2013. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configure clients for Migration](configure-clients-for-migration_1.md). Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte [Phase 6: Move users to the Pilot Pool](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> No puede usar el complemento usuarios y equipos de Active Directory o las herramientas administrativas de Microsoft Office Communications Server 2007 R2 para mover usuarios de su entorno heredado a Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> El cmdlet <STRONG>Move-CsLegacyUser</STRONG> requiere que los nombres de usuario se formen debidamente y que no tengan espacios en blanco al principio o al final. No puede transferir cuentas de usuario con el cmdlet <STRONG>Move-CsLegacyUser</STRONG> si tiene espacios en blanco al principio o al final.



</div>

Al mover un usuario a un grupo de servidores de Lync Server 2013, los datos del usuario se mueven a la base de datos back-end asociada al nuevo grupo.

<div>


> [!IMPORTANT]  
> Estos datos incluyen las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario heredado ha configurado una conferencia de <STRONG>mi reunión</STRONG> , esa Conferencia seguirá disponible en el nuevo grupo de servidores de Lync Server 2013, una vez que se haya movido al usuario. Los datos de acceso de esa reunión continuarán siendo los mismos <STRONG>URL de conferencia e ID de conferencia</STRONG>. La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Lync Server 2013 y no en el grupo de servidores de Office Communications Server 2007 R2.



</div>

<div>


> [!NOTE]  
> El alojamiento de usuarios en Lync Server 2013 no requiere que se implementen clientes actualizados al mismo tiempo. La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente.



</div>

<div>

## <a name="post-migration-task"></a>Tarea posterior a la migración

1.  Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada.

2.  Para asegurarse de que las reuniones organizadas por usuarios hospedados en Lync Server 2013 funcionan sin problemas con usuarios federados alojados en Office Communications Server 2007 R2, la Directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.

3.  Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Lync Server 2013 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **true** en el resultado del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Lync Server.

4.  Para obtener más información sobre cómo configurar la Directiva de conferencias mediante el shell de administración de Lync Server, vea [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) en la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

