---
title: 'Lync Server 2013: habilitar o deshabilitar la integración con el almacenamiento de Exchange'
description: 'Lync Server 2013: habilitar o deshabilitar la integración con el almacenamiento de Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42d140bd99bdc4aa86bea2f6ad310c4e06f06faf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546546"
---
# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>Habilitación o deshabilitación de la integración de Lync Server 2013 con almacenamiento de Exchange

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

En el panel de control de Lync Server 2013, se usan configuraciones de archivado para habilitar y deshabilitar la integración con el almacenamiento de Exchange. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.

Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>Para habilitar o deshabilitar la integración con el almacenamiento de Microsoft Exchange

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.

4.  Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
      - Para habilitar la integración con el almacenamiento de Exchange 2013, active la casilla de verificación **integración de Microsoft Exchange** .
    
      - Para deshabilitar la integración con el almacenamiento de Exchange 2013, desactive la casilla de verificación **integración de Microsoft Exchange** .

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

