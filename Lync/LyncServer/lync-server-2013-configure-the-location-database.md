---
title: 'Lync Server 2013: configurar la base de datos de ubicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configure the location database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones. Si no configura una base de datos de ubicación y la **Ubicación requerida** en la Directiva de ubicación está configurada en **sí** o **renuncia**, se le solicitará al usuario que escriba una ubicación manualmente.

Para configurar la base de datos de ubicación, debe realizar las siguientes tareas:

1.  Llene la base de datos con una búsqueda de elementos de red a las ubicaciones. Si usa una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), tendrá que incluir \<la\> Elin en el campo NombreCompañía.

2.  Valide las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.

3.  Publique la base de datos actualizada.

<div>


> [!NOTE]  
> Como alternativa, puede definir una base de datos de origen de ubicación secundaria que se puede usar en una parte de la base de datos de ubicación. Para obtener más información, vea <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurar un servicio de información de ubicación secundaria en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Rellenar la base de datos de ubicación en Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Validar direcciones en Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Publicar la base de datos de ubicación desde Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

