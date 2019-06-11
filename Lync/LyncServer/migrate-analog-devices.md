---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Lync Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Lync Server. Después de migrar de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Lync Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos de Lync Server 2010 y, a continuación, mueva esos objetos al grupo de servidores de Lync Server 2013.

<div>

## <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  En la línea de comandos, escriba:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Compruebe que todos los objetos de contacto se han movido al grupo de 2013 de Lync Server. En la línea de comandos, escriba:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Compruebe que todos los objetos de contacto están asociados con el grupo de servidores de Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

