---
title: Lync Server 2013; Crear rutas interregional de red
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: be1c28450708660e2322144802c81d5458ded6da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "34821820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Crear rutas interregional de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Una *ruta interregión de red* define la ruta entre un par de regiones de red. Cada pareja de regiones de red en la implementación de control de admisión de llamadas requiere una ruta entre regiones de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.

Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre regiones, una ruta interregion determina qué ruta de acceso vinculada atravesará la conexión de una región a otra.

Para obtener más información sobre cómo trabajar con rutas entre regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

En la topología de ejemplo, las rutas interregións de red deben definirse para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Para crear rutas interregional de red con el shell de administración de Lync Server

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias. Por ejemplo, ejecute lo siguiente:
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > La ruta interregional de la red de Norteamérica/APAC requiere dos vínculos de región de red porque no hay un vínculo de región de red directa entre ellos.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Para crear rutas interregional de red con el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Ruta regional**.

4.  Haga clic en **Nuevo**.

5.  En la página **nueva ruta** de la región, haga clic en **nombre** y, a continuación, escriba un nombre para la ruta interregión de red.

6.  Haga clic en **región \#de red 1**y, a continuación, haga clic en una región de red de la lista \#que quiera enrutar a la región de red 2.

7.  Haga clic en **región \#de red 2**y, a continuación, haga clic en una región de red en la lista \#que quiera enrutar a la región de red 1.

8.  Haga clic en **Agregar** junto al campo **vínculos de región de red** y, a continuación, agregue un vínculo región de red que se usará en la ruta interregión de red.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta interregional de red de Norteamérica/APAC requiere dos vínculos de región de red porque no hay ningún vínculo de región de red directa entre ellos.

    
    </div>

9.  Haga clic en **Confirmar**.

10. Para terminar de crear rutas interregional de red para su topología, repita los pasos 4 a 9 con la configuración de otras rutas interregional de red.

</div>

</div>

<span> </span>

</div>

</div>

</div>

