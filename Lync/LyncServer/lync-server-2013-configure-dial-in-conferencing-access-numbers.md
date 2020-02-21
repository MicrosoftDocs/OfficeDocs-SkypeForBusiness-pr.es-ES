---
title: 'Lync Server 2013: configurar los números de acceso de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ca47596106a3c2a6395f90ccaab2905c1a4599
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Configurar los números de acceso de conferencia de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2011-07-17_

Al implementar la Conferencia de acceso telefónico local, debe configurar los números de teléfono que los usuarios pueden marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico aparecen en las invitaciones a reuniones y en la Página Web de configuración de conferencia de acceso telefónico local.

Antes de poder crear números de acceso telefónico local, primero debe planear las regiones de conferencia de acceso telefónico local y, a continuación, configurar los planes de marcado con las regiones. Para obtener más información sobre las regiones, consulte [requisitos de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación referente a la planeación. Para obtener más información sobre cómo configurar planes de marcado para las conferencias de acceso telefónico local, consulte [configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> No se puede usar un nuevo número de acceso telefónico hasta que se complete la replicación de&nbsp;servicios de dominio de Active Directory (AD DS) de ese número de acceso. La replicación puede tardar varias horas en completarse.



</div>

<div>


> [!NOTE]  
> Después de crear los números de acceso telefónico local, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory para que los usuarios puedan identificar más fácilmente el número de acceso correcto. Use el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar. No debe modificar los objetos de Active Directory de forma manual. Para obtener información detallada sobre cómo modificar un número de acceso, consulte Lync Server Management Shell Documentation for the <STRONG>set-CsDialInConferencingAccessNumber</STRONG> cmdlet.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

[Crear o modificar un número de acceso de conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>Consulta también


[Requisitos de conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

