---
title: 'Lync Server 2013: Agregar un vínculo personalizado a los mensajes de error de Lync'
TOCTitle: Agregar un vínculo personalizado a los mensajes de error de Lync
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398979(v=OCS.15)
ms:contentKeyID: 52061777
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar un vínculo personalizado a los mensajes de error de Lync en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-20_

Personalice los mensajes de error de Lync 2013 agregando un vínculo a su propia información de atención al cliente o de solución de problemas. Para ello, use el cmdlet **New-CSClientPolicy** o **Set-CSClientPolicy** del Shell de administración de Lync Server con el parámetro CustomLinkInErrorMessages. El texto del vínculo personalizado es "Haga clic aquí para ver temas de soporte técnico del administrador"; no se puede personalizar.

Por ejemplo, el comando siguiente hace que el vínculo personalizado aparezca en el pie de página de cada mensaje de error de Lync 2013 y establece el destino del vínculo en http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios. Para más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del Shell de administración de Lync Server.

