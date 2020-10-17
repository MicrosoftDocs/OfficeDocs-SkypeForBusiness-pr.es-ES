---
title: 'Lync Server 2013: adición de un vínculo personalizado a los mensajes de error de Lync'
description: 'Lync Server 2013: adición de un vínculo personalizado a los mensajes de error de Lync.'
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
ms.openlocfilehash: a5d333b6f27e10e5092de23fcdf1d37fd75e75a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560036"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="6d0c2-103">Adición de un vínculo personalizado a los mensajes de error de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d0c2-103">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d0c2-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6d0c2-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6d0c2-105">Personalice los mensajes de error de Lync 2013 agregando un vínculo a su propia información de solución de problemas o asistencia técnica.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-105">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="6d0c2-106">Para ello, use los cmdlets del shell de administración de Lync Server **New-CSClientPolicy** o **set-CSClientPolicy**   con el parámetro CustomLinkInErrorMessages.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-106">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="6d0c2-107">El texto del vínculo personalizado es "haga clic aquí para ver los temas de soporte de su administrador" y no se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-107">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="6d0c2-108">Por ejemplo, el siguiente comando hace que el vínculo personalizado aparezca en el área de notas al pie de cada mensaje de error de Lync 2013 y establece el destino de vínculo en http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="6d0c2-108">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="6d0c2-109">Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-109">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="6d0c2-110">Para obtener más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-110">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

