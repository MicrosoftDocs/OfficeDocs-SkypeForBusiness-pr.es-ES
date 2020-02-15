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
ms.openlocfilehash: 3c9f15b72f105edf291007569999c549b8b2c841
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Adición de un vínculo personalizado a los mensajes de error de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Personalice los mensajes de error de Lync 2013 agregando un vínculo a su propia información de solución de problemas o asistencia técnica. Para ello, use los cmdlets del shell de administración de Lync Server **New-CSClientPolicy** o **set-CSClientPolicy** con el parámetro CustomLinkInErrorMessages. El texto del vínculo personalizado es "haga clic aquí para ver los temas de soporte de su administrador" y no se puede personalizar.

Por ejemplo, el siguiente comando hace que el vínculo personalizado aparezca en el área de notas al pie de cada mensaje de error de Lync 2013 y establece el destino de vínculo enhttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios. Para obtener más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

