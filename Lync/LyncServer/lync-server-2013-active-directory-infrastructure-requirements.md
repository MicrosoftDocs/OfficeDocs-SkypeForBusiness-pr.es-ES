---
title: 'Lync Server 2013: Requisitos de infraestructura de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75278700623ae7251fe7cebec36e959a38f325dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestructura de Active Directory para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Antes de empezar el proceso de preparación de los servicios de dominio de Active Directory para Lync Server 2013, asegúrese de que la infraestructura de Active Directory cumple los siguientes requisitos previos:

  - Todos los controladores de dominio (que incluyen todos los servidores de catálogo global) del bosque donde se implementa Lync Server ejecutan uno de los siguientes sistemas operativos:
    
      - Sistema operativo Windows Server 2012 R2
    
      - Sistema operativo Windows Server 2012
    
      - Sistema operativo Windows Server 2008 R2
    
      - Sistema operativo Windows Server 2008
    
      - Windows Server 2008 Enterprise 32 bits
    
      - versiones de 32 o 64 bits del sistema operativo Windows Server 2003 R2
    
      - versiones de 32 o 64 bits del sistema operativo Windows Server 2003

  - Todos los dominios en los que implementa Lync Server se elevan al nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.

  - El bosque en el que implementa Lync Server se eleva al nivel funcional de bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.
    
    <div>
    

    > [!NOTE]  
    > Para cambiar el nivel funcional de bosque o de dominio, consulte "elevar niveles funcionales de dominios y bosques" en la <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>biblioteca de TechNet en.

    
    </div>

  - Un catálogo global se implementa en cada dominio en el que se implementan equipos o usuarios de Lync Server.

Lync Server 2013 admite los grupos universales de los sistemas operativos Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad con los grupos universales, junto con la delegación de administrador, simplifica la administración de una implementación de Lync Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.

</div>

<span> </span>

</div>

</div>

</div>

