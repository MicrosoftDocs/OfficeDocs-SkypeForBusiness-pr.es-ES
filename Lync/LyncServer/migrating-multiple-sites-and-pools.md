---
title: Migrar múltiples sitios y grupos de servidores
description: Migrar varios sitios y grupos de servidores.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7efaa6f038286ff9138e631f23da88bb445e20f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543256"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar múltiples sitios y grupos de servidores

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Lync Server 2013 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos de servidores de Lync Server 2010 a Lync Server 2013 requiere las siguientes consideraciones:

1.  Después de implementar un grupo piloto de Lync Server 2013, debe definir un subconjunto de usuarios piloto que se trasladarán al grupo de Lync Server 2013 y una metodología para validar la funcionalidad de los usuarios. Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la Directiva de conferencia del usuario se ha movido a Lync Server 2013.

2.  Después de implementar un servidor perimetral en el grupo piloto, debe validar que los usuarios externos pueden comunicarse con el grupo de servidores de Lync 2013.

3.  Después de realizar la transición de las rutas federadas de los servidores perimetrales de Lync Server 2010 a los servidores perimetrales de Lync Server 2013 piloto, debe validar que los usuarios federados puedan comunicarse con el grupo de Lync Server 2013.

4.  Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo de servidores de Lync Server 2010 está vacío.

5.  Después de comprobar que el grupo de servidores de Lync Server 2010 está vacío, puede desactivar el grupo de servidores.
    
    Para obtener más información sobre cómo desactivar el grupo de servidores de Lync Server 2010 y los servidores heredados, vea [Phase 8: decommission Legacy pools](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

