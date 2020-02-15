---
title: 'Lync Server 2013: configuración del ancho de banda de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f1eb39099f51da36b62360282bc89c06ab94817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configuración del ancho de banda de vídeo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Lync Server 2013 incluye varias configuraciones para administrar el vídeo para llamadas de dos participantes y conferencias con varios participantes. Al implementar Lync Server 2013, debe evaluar si la configuración predeterminada es adecuada para su organización y modificarla según sea necesario.

Los parámetros descritos en esta sección se aplican a las llamadas entre dos entidades y a las conferencia entre varias entidades. Vea o modifique estos parámetros con uno de los cmdlets siguientes:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Compruebe los siguientes parámetros en la directiva de conferencias:

  - **VideoBitRateKb**   esta configuración especifica la velocidad de bits de vídeo máxima en kilobits por segundo (kbps) que se usa para el vídeo enviado por un usuario. El valor predeterminado es 50.000 kbps. Los valores válidos son 0 a 50.000.
    
    Este parámetro se aplica por separado al vídeo principal y al vídeo panorámico.
    
    Ejemplo: Si especifica 2000 Kbps, Lync Server puede enviar 2000 Kbps para la secuencia de vídeo principal y 2000 Kbps para la secuencia de vídeo panorámico.
    
    <div>
    

    > [!NOTE]  
    > El ancho de banda de red de vídeo máximo para un punto de conexión 2013 de Lync es de 8000 Kbps para el vídeo principal y 2500 Kbps para vídeo panorámico. Estos valores máximos solo se alcanzan si se reciben o envían varios vídeos. Para obtener más información, consulte la sección "uso de la red de tráfico de medios" en <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013</A>. Esta sección muestra el ancho de banda máximo y típico para secuencias de vídeo en todas las resoluciones compatibles.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   esta configuración, que es nueva en Lync Server 2013, especifica la velocidad de bits máxima permitida (en kilobits por segundo) para todas las secuencias de vídeo recibidas por un cliente. Es decir, especifica el total combinado de todas las secuencias de vídeo, excepto las secuencias de vídeo panorámico, que puede recibir un cliente. Por ejemplo, si especifica 1.500 kbps, un cliente puede recibir hasta 1.500 kbps de vídeo, que puede componerse de varias secuencias de vídeo o una secuencia de vídeo única. Esta configuración solo se aplica a clientes de Lync Server 2013.
    
    El valor predeterminado para **TotalReceiveVideoBitRateKb** es 50.000 kbps. Si el parámetro **EnableMultiviewJoin** para Vista Galería se establece en True, **TotalReceiveVideoBitRateKb** no debe establecer por debajo de 420 kbps. Si el parámetro **EnableMultiviewJoin** para Vista Galería se establece en False, **TotalReceiveVideoBitRateKb** no debe establecerse por debajo de 100 kbps. Si **EnableMultiviewJoin** se establece en True y establece el valor por debajo de 420 kbps, los valores serán el valor del umbral de forma predeterminada. Este umbral ayuda a evitar errores accidentales que podrían resultar en una experiencia de usuario deficiente.
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre la configuración de <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">configuración de la vista de galería en Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   este parámetro ya no se usa en clientes de Lync Server 2013 en conferencias de Lync Server 2013. Las conferencias de Lync Server 2013 usan los controles de velocidad de bits descritos anteriormente en esta sección. Esta configuración se sigue usando para clientes heredados que se unan a una conferencia de Lync Server 2013. Este parámetro determina la resolución máxima permitida para los clientes heredados en conferencias organizadas por usuarios hospedados en Lync Server 2013. Es decir, los clientes heredados se tratan de la misma forma que en versiones anteriores de Lync Server u Office Communications Server.

Además de los parámetros de la directiva de conferencias que se aplican a los usuarios, evalúe los parámetros de configuración de los medios. Vea o modifique estos parámetros con uno de los cmdlets siguientes:

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Compruebe la siguiente configuración:

  - **MaxVideoRateAllowed**   esta configuración por grupo especifica la velocidad máxima a la que se transferirán las señales de vídeo en los extremos de cliente. Solo se aplica a las versiones anteriores de clientes de Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Los clientes de Lync Server 2013 ignoran esta configuración y usan el valor TotalReceiveVideoBitRateKb en la Directiva de conferencia en su lugar.

    
    </div>
    
    El valor predeterminado es HD720P. Los valores válidos son HD720p15M, VGA600K y CIF250K.
    
    Por ejemplo: si especifica 1.500 kbps, todos los clientes heredados del grupo pueden recibir hasta 1.500 kbps de vídeo en conferencias entre dos o entre varias entidades.

Los siguientes procedimientos son ejemplos del uso del shell de administración de Lync Server para modificar la configuración que se describe en esta sección.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Para modificar la directiva de conferencias para la configuración de vídeo

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para cambiar la directiva de conferencia:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Para modificar la configuración de medios para los clientes heredados

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para cambiar la configuración de medios:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

