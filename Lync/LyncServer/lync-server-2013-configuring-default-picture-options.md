---
title: 'Lync Server 2013: configuración de las opciones predeterminadas de la imagen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e551d069da9a3afb7a884c28096dd97ab3702539
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="81dbf-102">Configuración de las opciones predeterminadas de imagen en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dbf-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81dbf-103">_**Última modificación del tema:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="81dbf-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="81dbf-104">De forma predeterminada, se muestran automáticamente las imágenes de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="81dbf-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="81dbf-105">Si los usuarios desean ocultar sus imágenes, pueden seleccionar la opción **ocultar mi foto** en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="81dbf-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="81dbf-106">Sin embargo, otras aplicaciones de Office omiten esta configuración.</span><span class="sxs-lookup"><span data-stu-id="81dbf-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="81dbf-107">Si la posibilidad de mostrar imágenes incluso cuando el usuario está desactivado es un problema, puede cambiar la configuración de presentación de imágenes de Lync globalmente o de un sitio o servicio para que las imágenes de los usuarios no se muestren de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81dbf-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="81dbf-108">Use el siguiente cmdlet del shell de administración de Lync Server para que no se muestren las imágenes del usuario a menos que seleccionen de forma explícita la opción **Mostrar mi foto** en el cliente:</span><span class="sxs-lookup"><span data-stu-id="81dbf-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="81dbf-109">Para obtener más información sobre este cmdlet, consulte [set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81dbf-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

