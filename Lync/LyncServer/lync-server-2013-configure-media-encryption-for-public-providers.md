---
title: 'Lync Server 2013: configurar el cifrado de medios para proveedores públicos'
description: 'Lync Server 2013: configurar el cifrado de medios para proveedores públicos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577626"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurar el cifrado de medios para proveedores públicos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-12_

Si va a implementar la Federación de audio y vídeo (A/V) con Windows Live Messenger, hay dos parámetros que debe modificar: el nivel de cifrado de Lync Server y la Directiva EnablePublicCloudAccess. De forma predeterminada, el nivel de cifrado está configurado en Requerido. Debe cambiar esta opción a Compatible. Si la directiva EnablePublicCloudAccess está definida en falso, debe definirse en **Verdadero**. Puede hacerlo desde el shell de administración de Lync Server.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurar la federación para Windows Live

1.  Inicie el shell de administración de Lync Server en el servidor front-end: haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Shell de administración de Lync Server**.

2.  Desde el símbolo del sistema, escriba los siguientes comandos:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Este es un paso necesario porque Windows Live Messenger no admite el cifrado de audio/vídeo. El comando configura su directiva global en una configuración de cifrado compatible en lugar de requerir el cifrado de los datos de audio y vídeo. Los clientes que admiten el cifrado seguirán usando el cifrado, como Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

