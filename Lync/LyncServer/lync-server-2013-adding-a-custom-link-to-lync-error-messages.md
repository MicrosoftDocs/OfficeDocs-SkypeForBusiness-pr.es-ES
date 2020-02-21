---
title: 'Lync Server 2013: adición de un vínculo personalizado a los mensajes de error de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa65580cd9138b58792d4a0f0621bfe6f5f10c9c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="7a62d-102">Adición de un vínculo personalizado a los mensajes de error de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a62d-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a62d-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7a62d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7a62d-104">Personalice los mensajes de error de Lync 2013 agregando un vínculo a su propia información de solución de problemas o asistencia técnica.</span><span class="sxs-lookup"><span data-stu-id="7a62d-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="7a62d-105">Para ello, use los cmdlets del shell de administración de Lync Server **New-CSClientPolicy** o **set-CSClientPolicy** con el parámetro CustomLinkInErrorMessages.</span><span class="sxs-lookup"><span data-stu-id="7a62d-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="7a62d-106">El texto del vínculo personalizado es "haga clic aquí para ver los temas de soporte de su administrador" y no se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="7a62d-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="7a62d-107">Por ejemplo, el siguiente comando hace que el vínculo personalizado aparezca en el área de notas al pie de cada mensaje de error de Lync 2013 y establece el destino de vínculo enhttp://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="7a62d-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="7a62d-108">Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a62d-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="7a62d-109">Para obtener más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a62d-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

