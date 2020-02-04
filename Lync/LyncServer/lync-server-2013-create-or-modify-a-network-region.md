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
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Crear o modificar una región de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Las *regiones de red* son los concentradores de red o las redes troncales que se usan en la configuración de control de admisión de llamadas, E9-1-1 y omisión de medios. Use los procedimientos siguientes para crear o modificar regiones de red. Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario crear regiones de red nuevas; otras características avanzadas de telefonía empresarial usarán esas mismas regiones de red. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central. Para obtener más información, vea [configurar regiones de red para CAC en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> En los temas de implementación de la característica se documentan los requisitos específicos de las características de las definiciones de regiones de red.



</div>

Para obtener más información sobre cómo trabajar con regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Crear una región de red

Cree una región de red que pueda usar el control de admisión de llamadas, el E9-1-1 o la omisión de medios.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Para crear una región de red con el shell de administración de Lync Server

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por ejemplo:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    En este ejemplo, ha creado una región de red denominada “NorthAmerica” que está asociada a un sitio central con identificador de sitio CHICAGO.

3.  Para terminar de crear regiones de red para la topología, repita el paso 2 con parámetros para cada región de red.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Para crear una región de red con el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en **Región**

4.  Haga clic en **Nuevo**.

5.  En la página **Región nueva**, haga clic en **Nombre** y escriba un nombre para la región de red.

6.  Haga clic en **Sitio central** y, a continuación, haga clic en un sitio central de la lista.

7.  Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.

8.  Haga clic en **Confirmar**.

9.  Para terminar de crear regiones de red para la topología, repita los pasos del 4 al 8 con parámetros para otras regiones.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Modificar una región de red

Modificar la configuración de una región de red existente para acomodar los cambios en la información de la región básica o los cambios necesarios para una nueva característica.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Para modificar una región de red mediante el shell de administración de Lync Server

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por ejemplo:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    En este ejemplo, ha modificado una región de red existente denominada “NorthAmerica” (creada mediante los procedimientos descritos anteriormente en este tema) cambiando la descripción. Si ya existía una descripción para la región “NorthAmerica”, este comando la sobrescribirá con este valor; si no se había definido ninguna descripción, el comando la definirá.

3.  Para modificar otras regiones de red, repita el paso 2 con parámetros para otras regiones.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Para modificar una región de red con el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Región**.

4.  En la tabla, haga clic en la región de red que desee modificar.

5.  Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.

6.  En la página **Editar región**, modifique los valores de la configuración de esta región de red, según corresponda.

7.  Haga clic en **Confirmar**.

8.  Para terminar de modificar regiones de red, repita los pasos del 4 al 7 con parámetros para otras regiones.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

