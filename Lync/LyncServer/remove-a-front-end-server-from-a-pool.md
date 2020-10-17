---
title: Quitar un servidor front-end de un grupo de servidores
description: Quitar un servidor front-end de un grupo de servidores.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551306"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Quitar un servidor front-end de un grupo de servidores

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

El servidor front-end de Microsoft Lync Server 2010 Enterprise Edition no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si hay un solo equipo en el grupo.

Este tema le guiará por el proceso de eliminación de un servidor front-end individual de un grupo de servidores front-end existente. Si el servidor front-end es el último servidor del grupo o si va a quitar completamente el grupo de servidores, consulte [quitar un grupo de servidores front-end o un servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end. Al quitar el grupo de servidores, se quitan todos los servidores front-end.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Para quitar un servidor front-end de un grupo

1.  Abra el servidor front-end de Lync Server 2013 y abra el generador de topologías.

2.  Navegue hasta el nodo 2010 de Lync Server.

3.  Expanda grupos de servidores Front **-End Enterprise Edition**, expanda el grupo de servidores front-end con el servidor front-end que desea quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

