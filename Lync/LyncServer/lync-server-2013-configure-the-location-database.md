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
ms.openlocfilehash: 9495bc0c52e8e9af4af0daa3d29304d5b25d4b7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520267"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a>Configurar la base de datos de ubicaciones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones. Si no configura ninguna base de datos de ubicaciones, y **Ubicación obligatoria** se ha establecido como **Sí** o **Declinación de responsabilidades** en la directiva de ubicación, se le pedirá al usuario que introduzca manualmente una ubicación.

Para configurar la base de datos de ubicaciones, deberá realizar las siguientes tareas:

1.  Llene la base de datos con una búsqueda de elementos de red a las ubicaciones. Si usa una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), deberá incluir el ELIN en el \<CompanyName\> campo.

2.  Validar las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.

3.  Publicar la base de datos actualizada.

<div>


> [!NOTE]  
> También puede optar por definir una base de datos secundaria de origen de ubicaciones, para usarla en lugar de la base de datos de ubicaciones. Para obtener más información, consulte <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurar un servicio de información de ubicaciones secundarias en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Rellenar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Validar direcciones en Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Publicar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

