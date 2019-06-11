---
title: 'Lync Server 2013: (Opcional) Comprobar la configuración de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177d8516dcb91272eca2a70b89026fc0e175a73a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>(Opcional) Comprobar la configuración de conferencia de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-11-02_

Como comprobación final de la configuración de las conferencias de acceso telefónico local, puede buscar planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada una región de conferencia de acceso telefónico local. Este paso es opcional.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Para buscar planes de marcado con una región de conferencia de acceso telefónico local que no se usa en un número de acceso

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    Este cmdlet devuelve todos los planes de marcado que tienen una región de conferencia de acceso telefónico local que no es usada por ningún número de acceso.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>Para buscar números de acceso sin regiones asignadas

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    Este cmdlet devuelve todos los números de acceso de conferencia de acceso telefónico local que no están asociados a ninguna región.

</div>

</div>

<span> </span>

</div>

</div>

</div>

