---
title: 'Lync Server 2013: configuración del ancho de banda de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configuración del ancho de banda de vídeo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Lync Server 2013 incluye varias opciones de configuración para administrar el vídeo para las conferencias de dos participantes y las de varias partes. Al implementar Lync Server 2013, debe evaluar si la configuración predeterminada es adecuada para su organización y modificarla según sea necesario.

Los parámetros descritos en esta sección se aplican tanto a llamadas de terceros como a conferencias de varias partes. Para ver o modificar esta configuración, use uno de los siguientes cmdlets:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Compruebe la configuración siguiente en su Directiva de Conferencia:

  - **VideoBitRateKb**   esta configuración especifica la tasa de bits de vídeo máxima en kilobits por segundo (kbps) usada para el vídeo enviado por un usuario. El valor predeterminado es 50000 kbps. Los valores válidos son de 0 a 50000.
    
    Esta configuración se aplica por separado al vídeo principal y al vídeo panorámico.
    
    Ejemplo: Si especifica 2000 Kbps, Lync Server puede enviar 2000 Kbps para la secuencia de vídeo principal y 2000 Kbps para la secuencia de vídeo panorámica.
    
    <div>
    

    > [!NOTE]  
    > El ancho de banda máximo de la red de vídeo para un extremo de Lync 2013 es de 8000 Kbps para el vídeo principal y 2500 Kbps para el vídeo panorámico. Estos valores máximos solo se alcanzan si se reciben o envían varios vídeos. Para obtener más información, vea la sección "uso de la red de tráfico de multimedia" en <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013</A>. Esta sección muestra el ancho de banda de vídeo máximo y típico de la secuencia de vídeo para todas las resoluciones compatibles.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   esta configuración, que es nueva en Lync Server 2013, especifica la velocidad de bits máxima permitida (en kilobits por segundo) para todas las transmisiones de vídeo recibidas por un cliente. Es decir, especifica el total combinado de todas las transmisiones de vídeo, excepto las secuencias panorámicas de vídeo, que un cliente puede recibir. Por ejemplo, si especifica 1500 kbps, un cliente puede recibir hasta 1500 kbps de video, que puede constar de varias secuencias de vídeo o una única secuencia de vídeo. Esta configuración se aplica solo a los clientes de Lync Server 2013.
    
    El valor predeterminado de **TotalReceiveVideoBitRateKb** es 50000 kbps. Si la configuración de **EnableMultiviewJoin** para la vista de galería se establece en verdadero, **TotalReceiveVideoBitRateKb** no debe ser inferior a 420 kbps. Si la configuración de **EnableMultiviewJoin** para la vista de galería se establece en falso, **TotalReceiveVideoBitRateKb** no debe ser inferior a 100 kbps. Si **EnableMultiviewJoin** se establece en true y establece el valor debajo de 420 Kbps, los valores se establecerán de forma predeterminada en el valor de umbral. Este límite impide la configuración accidental accidental que podría dar lugar a una mala experiencia del usuario.
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre la configuración de <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">configuración de la vista de galería en Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   este parámetro ya no se usa para los clientes de Lync Server 2013 en conferencias de Lync Server 2013. Las conferencias de Lync Server 2013 usan los controles de velocidad de bits descritos anteriormente en esta sección. Esta configuración se sigue usando para clientes heredados que se unan a una conferencia de 2013 de Lync Server. Este parámetro determina la resolución máxima permitida para clientes heredados en conferencias organizadas por usuarios alojados en Lync Server 2013. Es decir, los clientes heredados se tratan de la misma manera que en versiones anteriores de Lync Server u Office Communications Server.

Además de la configuración de directiva de conferencia que se aplica a los usuarios, evalúe la configuración de los medios. Para ver o modificar esta configuración, use uno de los siguientes cmdlets:

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **Nuevo: CsMediaConfiguration**

Compruebe la configuración siguiente:

  - **MaxVideoRateAllowed**   esta configuración por agrupación especifica la tasa máxima a la que se transfieren las señales de video en los puntos de conexión de cliente. Solo se aplica a las versiones anteriores de clientes de Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Los clientes de Lync Server 2013 ignoran esta configuración y usan en su lugar la configuración TotalReceiveVideoBitRateKb en la Directiva de conferencia.

    
    </div>
    
    El valor predeterminado es HD720P. Los valores válidos son HD720p15M, VGA600K y CIF250K.
    
    Ejemplo: Si especifica 1500 kbps, todos los clientes heredados del grupo pueden recibir hasta 1500 kbps de video en conferencias de dos o varias partes.

Los procedimientos siguientes son ejemplos de uso del shell de administración de Lync Server para modificar la configuración que se describe en esta sección.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Para modificar la Directiva de conferencia para la configuración de vídeo

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para editar la Directiva de Conferencia:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Para modificar la configuración de medios de clientes heredados

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para editar la configuración de multimedia:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

