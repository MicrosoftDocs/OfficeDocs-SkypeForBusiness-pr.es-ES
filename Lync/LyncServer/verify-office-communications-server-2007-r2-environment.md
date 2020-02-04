---
title: Comprobar el entorno de Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb67868c9f7eddfe2b11b4238c5fdd1bd14d8e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Comprobar el entorno de Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Antes de implementar Lync Server 2013 en un estado de coexistencia con Office Communications Server 2007 R2, debe comprobar que los servicios de Office Communications Server 2007 R2 están configurados e iniciados.

**Comprobar que el grupo se ha iniciado con la herramienta administrativa de Office Communications Server 2007 R2**

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda el nodo **bosque** , expanda el nodo **servidores Standard Edition** o grupos de servidores **Enterprise** y, a continuación, expanda el nombre del servidor o grupo de servidores.

3.  Asegúrese de que los servicios se están ejecutando en el servidor Standard Edition o en el grupo de servidores Enterprise.
    
    ![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")

**Revisar los usuarios configurados para Office Communications Server 2007 R2**

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda el nodo **bosque** , expanda el nodo **servidores Standard Edition** o grupos de servidores **Enterprise** y, a continuación, expanda el nombre del servidor o grupo de servidores.

3.  Haga clic en **usuarios**.

4.  Compruebe la lista de usuarios de Office Communications Server 2007 R2.
    
    ![Lista de usuarios de la herramienta de administración de OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Lista de usuarios de la herramienta de administración de OCS")

**Comprobar la configuración heredada del socio XMPP federado**

1.  Desde el servidor XMPP heredado, vaya al subprograma\\servicios de herramientas administrativas.

2.  Compruebe que se ha iniciado el servicio de puerta de enlace XMPP de Office Communications Server.
    
    ![Servicio de puerta de enlace XMPP de Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

