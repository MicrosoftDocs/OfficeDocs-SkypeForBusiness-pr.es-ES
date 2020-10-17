---
title: 'Lync Server 2013: crear o modificar una región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2ddd7a64da7d0939b7b97099cb12878c272766d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508857"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Crear o modificar una región de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Las *regiones de red * son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios. Use los siguientes procedimientos para crear o modificar regiones de red. Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario que cree nuevas regiones de red; otras características avanzadas de Enterprise Voice usarán las mismas regiones de red. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central. Para obtener más información, consulte [Configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Cualquier requisito específico de la característica para las definiciones de región de red está documentado en los temas sobre implementación para la característica.



</div>

Para obtener información detallada sobre cómo trabajar con regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Crear una región de red

Cree una región de red que sirva para el control de admisión de llamadas, E9-1-1 o el desvío de medios.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Para crear una región de red mediante el shell de administración de Lync Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por ejemplo:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    En este ejemplo, ha creado una región de red denominada "NorthAmerica" que está asociada a un sitio central con el identificador de sitio CHICAGO.

3.  Para terminar de crear regiones de red para la topología, repita el paso 2 con la configuración de cada región de red.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Para crear una región de red mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en **región**.

4.  Haga clic en **Nuevo**.

5.  En la página **región nueva** , haga clic en **nombre** y, a continuación, escriba un nombre para la región de red.

6.  Haga clic en **sitio central**y, a continuación, haga clic en un sitio central de la lista.

7.  Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.

8.  Haga clic en **Confirmar**.

9.  Para terminar de crear regiones de red para la topología, repita los pasos 4 a 8 con la configuración para otras regiones.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Modificar una región de red

Modifique la configuración de una región de red existente para dar cabida a los cambios en la información de región básica o los cambios necesarios para una nueva característica.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Para modificar una región de red mediante el shell de administración de Lync Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por ejemplo:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    En este ejemplo, ha modificado una región de red existente denominada "Norteamérica" (creada con los procedimientos anteriormente en este tema) al cambiar la descripción. Si existía una descripción para la región "NorthAmerica", este comando la sobrescribe con este valor; Si no se ha definido ninguna descripción, este comando la establece.

3.  Para modificar otras regiones de red, repita el paso 2 con opciones de configuración para otras regiones.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Para modificar una región de red mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **región** .

4.  En la tabla, haga clic en la región de red que desee modificar.

5.  Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.

6.  En la página **Editar región** , cambie los valores de la configuración de esta región de red según corresponda.

7.  Haga clic en **Confirmar**.

8.  Para terminar de modificar regiones de red, repita los pasos 4 a 7 con la configuración para otras regiones.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

