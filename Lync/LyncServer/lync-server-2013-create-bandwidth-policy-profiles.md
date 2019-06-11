---
title: 'Lync Server 2013: crear perfiles de directiva de ancho de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9464e83370690e018374c4ffb60e0b61c30fe300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Crear perfiles de directiva de ancho de banda en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Las *directivas de ancho de banda* definen limitaciones en el uso de ancho de banda para las modalidades de audio y vídeo en tiempo real. Las directivas de ancho de banda se aplican a los *perfiles de directiva de ancho de banda*, que pueden aplicarse a varios sitios de red para el control de admisión de llamadas.

Para obtener instrucciones sobre qué límites de ancho de banda debe establecer en su implementación CAC, consulte [definir los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) en la documentación de planeación.

Para obtener más información sobre cómo trabajar con directivas de ancho de banda y perfiles de Directiva, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Las directivas de ejemplo creadas en el procedimiento siguiente definen límites para el tráfico de audio global, sesiones de audio individuales, el tráfico de vídeo global y sesiones de vídeo individuales. Por ejemplo, el perfil\_de directiva de ancho de banda del vínculo de 5 MB establece los siguientes límites:

  - Límite de audio: 2.000 kbps

  - Límite de sesión de audio: 200 kbps

  - Límite de vídeo: 1.400 kbps

  - Límite de sesión de vídeo: 700 kbps

<div class=" ">


> [!NOTE]  
> El valor de Límite de sesión de audio es 40 kbps. El valor de Límite de sesión de vídeo es 100 kbps.



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>Para crear perfiles de directiva de ancho de banda mediante el shell de administración

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para cada perfil de directiva de ancho de banda que quiera crear, ejecute el cmdlet New-CsNetworkBandwidthPolicyProfile. Por ejemplo, ejecute lo siguiente:
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>Para crear perfiles de directiva de ancho de banda mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Perfil de directiva**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nuevo perfil de directiva**, haga clic en **Nombre** y escriba un nombre para el perfil de directiva de ancho de banda.

6.  Haga clic en **Límite de audio** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de audio combinadas.

7.  Haga clic en **Límite de sesión de audio** y escriba el número máximo de kbps que se deben permitir para cada sesión de audio.

8.  Haga clic en **Límite de vídeo** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de vídeo combinadas.

9.  Haga clic en **Límite de sesión de vídeo** y escriba el número máximo de kbps que se deben permitir para cada sesión de vídeo.

10. Si lo desea, haga clic en **Descripción** y escriba información adicional para describir este perfil de directiva de ancho de banda.

11. Haga clic en **Confirmar**.

12. Para terminar de crear perfiles de directiva de ancho de banda para su topología, repita los pasos del 4 al 11 con la configuración para otros perfiles de directiva de ancho de banda.

</div>

</div>

<span> </span>

</div>

</div>

</div>

