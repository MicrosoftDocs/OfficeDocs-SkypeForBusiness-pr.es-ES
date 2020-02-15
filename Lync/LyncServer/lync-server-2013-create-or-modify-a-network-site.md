---
title: 'Lync Server 2013: crear o modificar un sitio de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce676c4e86d6bceae81d60897846e3005780eb58
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Crear o modificar un sitio de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Las implementaciones de control de admisión de llamadas (CAC), de E9-1-1 y de desvío de medios se basan en la configuración de los *sitios de red* que hay definidos y que siempre están asociados a una región de red. Un sitio de red representa la ubicación de una sucursal, un conjunto de edificios o un campus. Los sitios de red son colecciones de subred con un ancho de banda similar.

Use los siguientes procedimientos para crear o modificar sitios de red. Por ejemplo, si ya ha creado sitios de red en relación con una característica de voz, no será necesario crear sitios de red nuevos, ya que las otras características de voz harán uso de esos mismos sitios de red. Con todo, puede que sea necesario modificar una definición de sitio de red existente para aplicar una configuración específica de una característica. Así, si ha creado un sitio de red para E9-1-1, deberá modificar el sitio de red durante la implementación de un control de admisión de llamadas con objeto de aplicar un perfil de directiva de ancho de banda.

<div>


> [!NOTE]  
> Si los hay, encontrará ejemplos y requisitos específicos de los sitios de red pertenecientes a una característica de voz avanzada en la documentación de implementación de cada característica: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurar sitios de red para CAC en Lync Server 2013</A></P></LI></UL>



</div>

Para obtener información detallada sobre cómo trabajar con sitios de red, vea la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Crear un sitio de red

Cree una región de red que sirva para el control de admisión de llamadas, E9-1-1 o el desvío de medios.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>Para crear un sitio de red mediante el Shell de administración

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkSite para crear sitios de red:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Por ejemplo:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    En este ejemplo, ha creado un sitio de red denominado “Chicago” que se encuentra en la región de red “NorthAmerica”.
    
    <div>
    

    > [!NOTE]  
    > Esta región de red ya debe existir para que este comando se ejecute correctamente.

    
    </div>

3.  Para terminar de crear sitios de red en su topología, repita el paso 2 con la configuración pertinente del resto de sitios.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Para crear un sitio de red mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Sitio**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nuevo sitio**, haga clic en **Nombre** y, a continuación, escriba un nombre para el sitio de red.

6.  Haga clic en **Región** y, a continuación, en una región de la lista.

7.  Si lo desea, también puede hacer clic en **Directiva de ancho de banda** y hacer clic en una directiva de ancho de banda de la lista.
    
    <div>
    

    > [!NOTE]  
    > Las directivas de ancho de banda solo son necesarias cuando se implementa el control de admisión de llamadas en el sitio.

    
    </div>

8.  Si lo desea, también puede hacer clic en **Directiva de ubicación** y hacer clic en una directiva de ubicación de la lista.
    
    <div>
    

    > [!NOTE]  
    > Las directivas de ubicación solo son necesarias cuando se implementa E9-1-1 en el sitio.

    
    </div>

9.  Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.

10. Haga clic en **Confirmar**.

11. Para terminar de crear sitios de red en su topología, repita los pasos 4 a 10 con la configuración pertinente del resto de sitios.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Modificar un sitio de red

Modifique una región de red que sirva para el control de admisión de llamadas, E9-1-1 o el desvío de medios.

<div>

## <a name="to-modify-a-network-site"></a>Para modificar un sitio de red

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsNetworkSite para modificar sitios de red:
    
        Set-CsNetworkSite -Identity <string>
    
    Por ejemplo:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    En este ejemplo, el sitio denominado “Albuquerque” se traslada a la región de red “NorthAmerica”. Para modificar la configuración de sitio de red a fin de implementar el control de admisión de llamadas, E9-1-1 o el desvío de medios, cambie la configuración del sitio de red ejecutando el cmdlet Set-CsNetworkSite con los parámetros BWPolicyProfileID o LocationPolicy respectivamente.
    
    <div>
    

    > [!NOTE]  
    > En el caso del desvío de medios, existe un parámetro BypassID, si bien se recomienda encarecidamente no invalidar automáticamente los identificadores de desvío generados. No es necesario especificar más parámetros para configurar un sitio de red para el desvío de medios.

    
    </div>

3.  Para terminar de modificar sitios de red en su topología, repita el paso 2 con la configuración pertinente del resto de sitios.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Para modificar un sitio de red mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Sitio**.

4.  En la tabla, haga clic en el sitio de red que desee modificar.

5.  Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.

6.  En la página **Modificar sitio**, cambie los valores de la configuración del sitio de red según proceda.

7.  Haga clic en **Confirmar**.

8.  Para terminar de modificar sitios de red, repita los pasos 4 a 7 con la configuración pertinente del resto de sitios.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

