---
title: 'Lync Server 2013: configurar regiones de red para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80a5ec8d02376ae084f1973f47690259cac364d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurar regiones de red para CAC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Si ya ha creado regiones de red para la omisión de E9-1-1 o multimedia, puede modificar las regiones de red existentes agregando configuraciones específicas de control de admisión de llamadas (CAC) mediante el cmdlet <STRONG>set-CsNetworkRegion</STRONG> . Para obtener un ejemplo de cómo modificar una región de red, vea <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync Server 2013</A>.



</div>

Las *regiones de red* son los concentradores de red o las redes troncales que se usan en la configuración de CAC, E9-1-1 y la omisión de medios. Use el procedimiento siguiente para crear regiones de red que se alineen con las regiones de red en la topología de red de ejemplo de CAC. Para ver la topología de red de ejemplo, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación de planeación.

La topología de red de ejemplo para CAC tiene tres regiones: Norteamérica, EMEA y APAC. Cada región tiene un sitio central específico. Para la región de Norteamérica, el sitio central designado se denomina CHICAGO. El siguiente procedimiento muestra un ejemplo de cómo puede usar el cmdlet **New-CsNetworkRegion** para crear la región de Norteamérica.

<div>


> [!NOTE]  
> En el siguiente procedimiento, se usa el shell de administración de Lync Server para crear una región de red. Para obtener detalles sobre el uso del panel de control de Lync Server para crear una región de red, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Para crear una región de red para el control de admisión de llamadas

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para cada región que necesite crear, ejecute el cmdlet **New-CsNetworkRegion** . Por ejemplo, para crear la región de Norteamérica, ejecute:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Repita el paso 2 para crear las regiones de red, EMEA y APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

