---
title: 'Lync Server 2013: Agregar un vínculo personalizado a los mensajes de error de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Agregar un vínculo personalizado a los mensajes de error de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Personalice los mensajes de error de Lync 2013 agregando un vínculo a su información de ayuda o de asistencia. Para ello, use los cmdlets del shell de administración de Lync Server **New-ClientPolicy** o **set-ClientPolicy** con el parámetro CustomLinkInErrorMessages. El texto del vínculo personalizado es "haga clic aquí para ver los temas de ayuda de su administrador" y no se puede personalizar.

Por ejemplo, el siguiente comando hace que el vínculo personalizado aparezca en el área de notas al pie de cada mensaje de error de Lync 2013 y establece el destino del vínculo enhttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Use **Grant-ClientPolicy** para asignar esta nueva Directiva a los usuarios. Para obtener más información, vea **New-ClientPolicy** y **Grant-ClientPolicy** en la documentación del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

