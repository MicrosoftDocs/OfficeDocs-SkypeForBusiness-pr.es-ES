---
title: Quitar un servidor front-end de un grupo de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Quitar un servidor front-end de un grupo de servidores

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

El servidor front-end de Microsoft Lync Server 2010 Enterprise Edition no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un equipo en el grupo.

Este tema le guiará a través del proceso de eliminación de un servidor de front-end individual de un grupo de servidores front-end existente. Si el servidor front-end es el último servidor del grupo o si va a quitar el grupo por completo, consulte [quitar grupo de servidores front-end o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end. Al quitar el grupo, se quita cada uno de los servidores front-end.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Para quitar un servidor front-end de un grupo

1.  Abra el servidor front-end 2013 de Lync Server, abra Topology Builder.

2.  Vaya al nodo de 2010 de Lync Server.

3.  Expanda **agrupaciones front end de Enterprise Edition**, expanda el grupo de aplicaciones para el usuario con el servidor front-end que desee quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

