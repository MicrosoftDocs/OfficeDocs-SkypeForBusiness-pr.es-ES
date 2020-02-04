---
title: 'Lync Server 2013: Configurar el cifrado de medios para proveedores públicos'
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
ms.openlocfilehash: 6d4ab36d19726a6092f978a2ac2a119b248cd0f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurar el cifrado de medios para proveedores públicos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-12_

Si está implementando la Federación de audio y vídeo (A/V) con Windows Live Messenger, hay dos parámetros que debe modificar: el nivel de cifrado de Lync Server y la Directiva EnablePublicCloudAccess. De forma predeterminada, el nivel de cifrado se establece en requerido. Debe cambiar esta configuración a compatible. Si la Directiva EnablePublicCloudAccess se establece en false, debe establecerse en **true**. Puede hacerlo desde el shell de administración de Lync Server.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurar la Federación para Windows Live

1.  Inicie el shell de administración de Lync Server en el servidor front-end: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  En el símbolo del sistema, escriba los siguientes comandos:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Este es un paso obligatorio porque Windows Live Messenger no admite el cifrado de audio y vídeo. El comando establece la directiva global en una configuración de cifrado compatible en lugar de requerir el cifrado de los datos de audio y vídeo. Los clientes que admiten el cifrado seguirán usando el cifrado, como Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

