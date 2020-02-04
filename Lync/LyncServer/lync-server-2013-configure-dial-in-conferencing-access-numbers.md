---
title: 'Lync Server 2013: Configurar números de conferencia de acceso telefónico'
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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Configurar números de conferencia de acceso telefónico en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2011-07-17_

Cuando se implementa la característica de conferencia de acceso telefónico local, es necesario establecer números de teléfono que los usuarios puedan marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico se muestran en invitaciones a reuniones y en la página web de configuración de conferencia de acceso telefónico local.

Antes de poder crear números de acceso telefónico local, necesita planear las regiones de conferencia de acceso telefónico local y luego configurar planes de marcado con las regiones. Para obtener más información sobre las regiones, consulte requisitos de las [conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación de planeación. Para obtener más información sobre cómo configurar planes de marcado para conferencias de acceso telefónico local, consulte [configurar planes de marcado para conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> No puede usar un nuevo número de acceso telefónico local hasta que se complete la replicación de&nbsp;servicios de dominio de Active Directory (AD DS) de ese número de acceso. La replicación puede prolongarse durante varias horas.



</div>

<div>


> [!NOTE]  
> Una vez creados los números de acceso telefónico local, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory, de modo que los usuarios puedan identificar con mayor facilidad el número de acceso correcto. Use el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar. No modifique los objetos de Active Directory manualmente. Para obtener detalles sobre cómo modificar un número de acceso, consulte la documentación del shell de administración de Lync Server para el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> .



</div>

<div>

## <a name="in-this-section"></a>En esta sección

[Crear o modificar un número de acceso para conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

