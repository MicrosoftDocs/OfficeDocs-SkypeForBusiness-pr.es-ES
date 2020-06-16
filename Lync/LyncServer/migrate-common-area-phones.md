---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138068c73264ded3483d8d9f0902d403833a306d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas de Lync Server. Después de migrar una implementación de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Mediante el shell de administración de Lync Server, primero se recuperarán todos los objetos de contacto asociados con los teléfonos de área común de Lync Server 2010 y, a continuación, se mueven dichos objetos al grupo de servidores de Lync Server 2013.

**Migrar teléfonos de área común**

1.  En el servidor front-end de Lync Server 2013, abra Shell de administración de Lync Server.

2.  En la línea de comandos, escriba lo siguiente:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Para comprobar que todos los objetos de contacto se han movido al grupo de servidores de Lync Server 2013, desde el shell de administración de Lync Server, escriba lo siguiente:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Compruebe que todos los objetos de contacto están ahora asociados con el grupo de servidores de Lync 2013.

</div>

<span> </span>

</div>

</div>

</div>

