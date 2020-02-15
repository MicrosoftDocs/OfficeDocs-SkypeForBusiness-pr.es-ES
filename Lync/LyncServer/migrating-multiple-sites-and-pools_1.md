---
title: Migrar varios sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97bd53e884d4b66b8197ef2672d6ffdca39d4cea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrar varios sitios y grupos de servidores

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-26_

Lync Server 2013 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos de servidores de Office Communications Server 2007 R2 a Lync Server 2013 requiere las siguientes consideraciones:

1.  Después de implementar un grupo piloto de Lync Server 2013, debe definir un subconjunto de usuarios piloto que se trasladarán al grupo de Lync Server 2013 y una metodología para validar la funcionalidad de los usuarios.

2.  Después de implementar un servidor perimetral en el grupo piloto, debe validar que los usuarios externos pueden comunicarse con el grupo de servidores de Lync 2013.

3.  Después de realizar la transición de las rutas federadas de los servidores perimetrales de Office Communications Server 2007 R2 a los servidores perimetrales de Lync Server 2013 piloto, debe validar que los usuarios federados puedan comunicarse con el grupo de Lync Server 2013.

4.  Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo de servidores de Office Communications Server 2007 R2 está vacío.

5.  Después de comprobar que el grupo de servidores de Office Communications Server 2007 R2 está vacío, puede desactivar el grupo.
    
    Para obtener más información sobre cómo desactivar el grupo y los servidores heredados de Office Communications Server 2007 R2, consulte [Phase 10: decommission Legacy site](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

