---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Los teléfonos de área común son teléfonos IP que suelen residir en un área de trabajo compartida o en un área común, como un vestíbulo, una cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de UC de Lync Server. Después de migrar una implementación de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Usar el shell de administración de Lync Server primero se recuperarán todos los objetos de contacto asociados a los teléfonos de área común de Lync Server 2010 y, a continuación, se moverán esos objetos al grupo de Lync Server 2013.

**Migrar teléfonos de área común**

1.  En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.

2.  En la línea de comandos, escriba lo siguiente:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Para comprobar que todos los objetos de contacto se han movido al grupo de 2013 de Lync Server, escriba lo siguiente en el shell de administración de Lync Server:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Compruebe que todos los objetos de contacto estén ahora asociados con el grupo de servidores de Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

