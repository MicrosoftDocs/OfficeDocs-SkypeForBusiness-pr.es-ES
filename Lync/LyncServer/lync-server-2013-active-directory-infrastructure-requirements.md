---
title: 'Lync Server 2013: requisitos de infraestructura de Active Directory'
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
ms.openlocfilehash: 46435a3683465c1e31406e46181df8ffa069615e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529617"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestructura de Active Directory para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Antes de iniciar el proceso de preparación de los servicios de dominio de Active Directory para Lync Server 2013, asegúrese de que la infraestructura de Active Directory cumple los siguientes requisitos previos:

  - Todos los controladores de dominio (que incluyen todos los servidores de catálogo global) del bosque en el que se implementa Lync Server ejecutan uno de los siguientes sistemas operativos:
    
      - Sistema operativo Windows Server 2012 R2
    
      - Sistema operativo Windows Server 2012
    
      - Sistema operativo Windows Server 2008 R2
    
      - Sistema operativo Windows Server 2008
    
      - Windows Server 2008 Enterprise 32 bits
    
      - Las versiones de 32 y 64 bits del sistema operativo Windows Server 2003 R2
    
      - versiones de 32 bits o de 64 bits del sistema operativo Windows Server 2003

  - Todos los dominios en los que se implementa Lync Server se elevan a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.

  - El bosque en el que se implementa Lync Server se eleva a un nivel funcional del bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.
    
    <div>
    

    > [!NOTE]  
    > Para cambiar el nivel funcional del bosque o del dominio, vea "elevar los niveles funcionales de dominio y bosque" en la biblioteca de TechNet en <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> .

    
    </div>

  - Se implementa un catálogo global en cada dominio en el que se implementan equipos o usuarios de Lync Server.

Lync Server 2013 admite los grupos universales de los sistemas operativos Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad con grupos universales, combinada con la delegación de administrador, simplifica la administración de una implementación de Lync Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.

</div>

<span> </span>

</div>

</div>

</div>

