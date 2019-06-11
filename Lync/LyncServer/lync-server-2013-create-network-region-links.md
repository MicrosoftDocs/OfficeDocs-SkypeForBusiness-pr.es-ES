---
title: 'Lync Server 2013: crear vínculos de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7715aa258c56e98789f12d3c057047d947fd3c51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>Crear vínculos de región de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Las regiones de una red se vinculan mediante conexiones de red WAN físicas. Un *vínculo región de red* crea un vínculo entre dos regiones configuradas para el control de admisión de llamadas (CAC) y establece las limitaciones de ancho de banda en el tráfico de audio y vídeo entre estas regiones.

Para obtener más información sobre cómo trabajar con vínculos de región de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

La topología de ejemplo tiene un vínculo entre las regiones de Norteamérica y APAC, y uno entre las regiones de EMEA y APAC. Cada uno de estos vínculos de región está restringido por el ancho de banda WAN, como se describe en la tabla información de ancho de banda de vínculos de región en el [ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) de la documentación de planeación.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Para crear vínculos de región de red con el shell de administración de Lync Server

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkRegionLink para crear vínculos de región de red y aplicar los correspondientes perfiles de directiva de ancho de banda. Por ejemplo, ejecute lo siguiente:
    
      ```
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Para crear vínculos de región de red con el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Vínculo de región**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nuevo vínculo de región**, haga clic en **Nombre** y asigne un nombre al vínculo de región de red.

6.  Haga clic en **región \#de red 1**y, a continuación, haga clic en la región de red en la lista \#que desea vincular a la región de red 2.

7.  Haga clic en **región \#de red 2**y, a continuación, haga clic en una región de red en la lista \#que desee vincular a la región de red 1.

8.  También puede hacer clic en **Directiva de ancho de banda** y seleccionar el perfil de directiva de ancho de banda que desea aplicar al vínculo de región de red.
    
    <div class=" ">
    

    > [!NOTE]  
    > Aplique una directiva de ancho de banda únicamente si el vínculo de región de red tiene restricciones de ancho de banda y desea usar control de admisión de llamadas para controlar el tráfico de medios en ese vínculo.

    
    </div>

9.  Haga clic en **Confirmar**.

10. Para terminar de crear vínculos de región de red para la topología, repita los pasos del 4 al 9 con parámetros para otras regiones.

</div>

</div>

<span> </span>

</div>

</div>

</div>
