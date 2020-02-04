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
ms.openlocfilehash: bcb5a709e896b66a1c8cd33a930bfeed5e05644f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Mover los usuarios restantes a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Puede mover usuarios a la nueva implementación de Lync Server 2013 con el panel de control de Lync Server o el shell de administración de Lync Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Lync Server 2013. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [configurar clientes para la migración](configure-clients-for-migration_1.md). Para conocer los pasos detallados sobre cómo mover usuarios, consulte [fase 6: mover usuarios a la agrupación piloto](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> No puede usar el complemento usuarios y equipos de Active Directory o las herramientas administrativas de Microsoft Office Communications Server 2007 R2 para mover usuarios de su entorno heredado a Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> El cmdlet <STRONG>Move-CsLegacyUser</STRONG> requiere que los nombres de usuario estén formados correctamente y no tengan espacios iniciales ni finales. No puede mover una cuenta de usuario mediante el cmdlet <STRONG>Move-CsLegacyUser</STRONG> si contiene espacios iniciales o finales.



</div>

Al mover un usuario a un grupo de servidores de Lync Server 2013, los datos del usuario se mueven a la base de datos back-end asociada con el nuevo grupo.

<div>


> [!IMPORTANT]  
> Esto incluye las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario heredado ha configurado una conferencia de <STRONG>reunión</STRONG> , dicha conferencia seguirá estando disponible en el nuevo grupo de Lync Server 2013, después de que se haya movido al usuario. Los detalles para acceder a la reunión seguirán siendo la misma <STRONG>dirección URL de conferencia y</STRONG>el mismo identificador de conferencia. La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Lync Server 2013, y no en el grupo de Office Communications Server 2007 R2.



</div>

<div>


> [!NOTE]  
> El alojamiento de usuarios en Lync Server 2013 no requiere que implemente clientes actualizados al mismo tiempo. Las nuevas funcionalidades estarán disponibles solo para los usuarios cuando se actualicen al nuevo software de cliente.



</div>

<div>

## <a name="post-migration-task"></a>Tarea posterior a la migración

1.  Después de mover usuarios, Compruebe la Directiva de conferencia que tiene asignada.

2.  Para asegurarse de que las reuniones organizadas por usuarios alojados en Lync Server 2013 funcionan sin problemas con usuarios federados alojados en Office Communications Server 2007 R2, la Directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.

3.  Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Lync Server 2013 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **verdadero** en el resultado del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Lync Server.

4.  Para obtener detalles sobre la configuración de la Directiva de Conferencia mediante el shell de administración de Lync Server, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) en la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

