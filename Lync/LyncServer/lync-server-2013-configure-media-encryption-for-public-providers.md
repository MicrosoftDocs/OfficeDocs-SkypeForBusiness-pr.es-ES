---
title: 'Lync Server 2013: Configurar el cifrado de medios para proveedores públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 270035730b8268c56b1730d8c212e90c8a9f1a30
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="b3cc2-102">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3cc2-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3cc2-103">_**Última modificación del tema:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="b3cc2-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="b3cc2-104">Si está implementando la Federación de audio y vídeo (A/V) con Windows Live Messenger, hay dos parámetros que debe modificar: el nivel de cifrado de Lync Server y la Directiva EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="b3cc2-105">De forma predeterminada, el nivel de cifrado se establece en requerido.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="b3cc2-106">Debe cambiar esta configuración a compatible.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-106">You must change this setting to Supported.</span></span> <span data-ttu-id="b3cc2-107">Si la Directiva EnablePublicCloudAccess se establece en false, debe establecerse en **true**.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="b3cc2-108">Puede hacerlo desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="b3cc2-109">Configurar la Federación para Windows Live</span><span class="sxs-lookup"><span data-stu-id="b3cc2-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="b3cc2-110">Inicie el shell de administración de Lync Server en el servidor front-end: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b3cc2-111">En el símbolo del sistema, escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="b3cc2-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b3cc2-112">Este es un paso obligatorio porque Windows Live Messenger no admite el cifrado de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="b3cc2-113">El comando establece la directiva global en una configuración de cifrado compatible en lugar de requerir el cifrado de los datos de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="b3cc2-114">Los clientes que admiten el cifrado seguirán usando el cifrado, como Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b3cc2-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

