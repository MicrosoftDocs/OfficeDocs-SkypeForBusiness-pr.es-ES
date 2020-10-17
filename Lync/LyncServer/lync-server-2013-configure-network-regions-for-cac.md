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
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520547"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurar regiones de red para CAC en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Si ya ha creado regiones de red para E9-1-1 o para el desvío de medios, puede modificar las regiones de red existentes mediante la adición de parámetros específicos de control de admisión de llamadas con el cmdlet Set-<STRONG>Set-CsNetworkRegion</STRONG>. Para ver un ejemplo sobre cómo modificar una región de red, vea <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync Server 2013</A>.



</div>

*Las regiones de red* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios. Siga estos procedimientos para crear regiones de red que se correspondan con las regiones de red del ejemplo de topología de red para controlar la admisión de llamadas. Para ver la topología de red de ejemplo, consulte [ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación referente a la planeación.

La topología de red de ejemplo para el control de admisión de llamadas tiene tres regiones: Norteamérica, EMEA y APAC. Cada región tiene un sitio central especificado. Para la región de Norteamérica, el sitio central designado se denomina CHICAGO. En el procedimiento siguiente se muestra un ejemplo de cómo puede usar el cmdlet  **New-CsNetworkRegion** para crear la región de Norteamérica.

<div>


> [!NOTE]  
> En el siguiente procedimiento, el shell de administración de Lync Server se usa para crear una región de red. Para obtener información detallada sobre cómo usar el panel de control de Lync Server para crear una región de red, vea <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Para crear una región de red para el control de admisión de llamadas

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Para cada región que necesite crear, ejecute el cmdlet **New-CsNetworkRegion**. Por ejemplo, para crear la región de Norteamérica, ejecute:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Repita el segundo paso para crear regiones de red de EMEA y APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

