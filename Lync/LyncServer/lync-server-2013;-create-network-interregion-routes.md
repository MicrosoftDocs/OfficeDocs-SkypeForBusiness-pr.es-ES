---
title: Lync Server 2013; Crear rutas entre regiones de red
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 4ab490479e02e92811878a9125c7b318732eeb83
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Crear rutas entre regiones de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Una *ruta entre regiones de red* define la ruta entre un par de regiones de red. Cada par de regiones de red de la implementación del servicio de control de admisión de llamadas precisa una ruta entre regiones de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.

Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones, una ruta entre regiones determina la ruta de acceso vinculada que atravesará la conexión de una región a otra.

Para obtener información detallada sobre cómo trabajar con rutas entre regiones de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

En el ejemplo de topología, hay que definir rutas entre regiones de red para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Para crear rutas entre regiones de red mediante el shell de administración de Lync Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias. Por ejemplo, ejecute lo siguiente:
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > La ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red debido a que no hay un vínculo de región de red directo entre ellas.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Para crear rutas entre regiones de red mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Ruta regional**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nueva ruta regional**, haga clic en **Nombre** y escriba un nombre para la ruta entre regiones de red.

6.  Haga clic en **región \#de red 1**y, a continuación, haga clic en una región de red de la lista \#que desee enrutar a la región de red 2.

7.  Haga clic en **región \#de red 2**y, a continuación, haga clic en una región de red de la lista \#que desee enrutar a la región de red 1.

8.  Haga clic en **Agregar** junto al campo **Vínculos de región de red** y luego agregue un vínculo de región de red que se usará en la ruta entre regiones de red.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red, debido a que no hay un vínculo de región de red directo entre ellas.

    
    </div>

9.  Haga clic en **Confirmar**.

10. Para finalizar la creación de rutas entre regiones de red de la topología, repita los pasos del 4 al 9 con la configuración para otras rutas entre regiones de red.

</div>

</div>

<span> </span>

</div>

</div>

</div>

