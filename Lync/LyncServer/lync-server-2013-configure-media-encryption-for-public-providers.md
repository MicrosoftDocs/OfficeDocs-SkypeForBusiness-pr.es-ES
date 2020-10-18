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
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="11523-103">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11523-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11523-104">_**Última modificación del tema:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="11523-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="11523-105">Si va a implementar la Federación de audio y vídeo (A/V) con Windows Live Messenger, hay dos parámetros que debe modificar: el nivel de cifrado de Lync Server y la Directiva EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="11523-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="11523-106">De forma predeterminada, el nivel de cifrado está configurado en Requerido.</span><span class="sxs-lookup"><span data-stu-id="11523-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="11523-107">Debe cambiar esta opción a Compatible.</span><span class="sxs-lookup"><span data-stu-id="11523-107">You must change this setting to Supported.</span></span> <span data-ttu-id="11523-108">Si la directiva EnablePublicCloudAccess está definida en falso, debe definirse en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="11523-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="11523-109">Puede hacerlo desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11523-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="11523-110">Configurar la federación para Windows Live</span><span class="sxs-lookup"><span data-stu-id="11523-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="11523-111">Inicie el shell de administración de Lync Server en el servidor front-end: haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="11523-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="11523-112">Desde el símbolo del sistema, escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="11523-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="11523-113">Este es un paso necesario porque Windows Live Messenger no admite el cifrado de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="11523-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="11523-114">El comando configura su directiva global en una configuración de cifrado compatible en lugar de requerir el cifrado de los datos de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="11523-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="11523-115">Los clientes que admiten el cifrado seguirán usando el cifrado, como Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="11523-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

