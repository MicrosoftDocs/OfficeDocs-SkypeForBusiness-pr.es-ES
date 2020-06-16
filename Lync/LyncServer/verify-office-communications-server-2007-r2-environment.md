---
title: Comprobar el entorno de Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a7ba7e51e6dd1f6e42aeddfbbbd4ce7581d3fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Comprobar el entorno de Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Antes de implementar Lync Server 2013 en un estado de coexistencia con Office Communications Server 2007 R2, debe comprobar que los servicios de Office Communications Server 2007 R2 están configurados e iniciados.

**Comprobar que el grupo se ha iniciado mediante la herramienta administrativa de Office Communications Server 2007 R2**

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda el nodo **Bosque**, después, el nodo **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y, por último, expanda el nombre del servidor o grupo.

3.  Compruebe que los servicios se ejecuten en el servidor Standard Edition o en el grupo de servidores Enterprise.
    
    ![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")

**Revise los usuarios configurados para Office Communications Server 2007 R2**

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  Expanda sucesivamente el nodo **Bosque**, **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y después expanda el grupo de servidores o el nombre de servidor.

3.  Haga clic en **Usuarios**.

4.  Compruebe la lista de usuarios de Office Communications Server 2007 R2.
    
    ![Lista de usuarios en la herramienta de administración de OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Lista de usuarios en la herramienta de administración de OCS")

**Compruebe la configuración del socio federado XMPP heredado**

1.  Desde el servidor de XMPP heredado, vaya al \\ subprograma Servicios de herramientas administrativas.

2.  Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.
    
    ![Servicio de puerta de enlace XMPP de Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

