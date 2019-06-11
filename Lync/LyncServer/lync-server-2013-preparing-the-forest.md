---
title: 'Lync Server 2013: Preparación del bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Preparación del bosque para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La preparación del bosque crea objetos y la configuración global de Active Directory y los grupos universales de Active Directory para el uso de Lync Server 2013, y concede permisos de acceso adecuados en los objetos de Active Directory. Para obtener una descripción de los grupos universales y la configuración global y los objetos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

La preparación del bosque también crea objetos que contienen conjuntos de propiedades y especificadores de presentación que se usan en Lync Server 2013, y los almacena en el contenedor configuración.

<div>


> [!IMPORTANT]  
> Asegúrese de que los cambios en la preparación del esquema se han replicado en todos los controladores de dominio antes de realizar el procedimiento de preparación del bosque. Si la replicación no se completa, se produce un error.



</div>

Si va a realizar una nueva implementación de Lync Server, debe almacenar la configuración global en el contenedor de configuración. Si está actualizando desde una versión anterior y aún así almacena la configuración global en el contenedor del sistema, puede seguir usando el contenedor del sistema.

Para realizar este procedimiento, debe ser miembro del grupo administradores de dominio o administradores de dominio del dominio raíz del bosque.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ejecutar la preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Usar cmdlets para invertir la preparación del bosque para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

