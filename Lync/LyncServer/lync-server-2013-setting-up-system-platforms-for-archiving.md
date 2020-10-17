---
title: 'Lync Server 2013: configurar plataformas del sistema para archivado'
description: 'Lync Server 2013: configurar plataformas del sistema para el archivado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554186"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configurar plataformas del sistema para el archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Antes de iniciar la implementación de archivado, debe instalar el sistema operativo requerido y cualquier otro software necesario como requisito previo en el hardware que cumpla los requisitos del sistema:

  - Plataforma Lync Server **2013**     Las implementaciones de Lync Server 2013 no tienen servidores de archivado. En su lugar, agentes de colección de datos unificada se ejecutan en servidores front-end y servidores de Standard Edition para capturar datos de archivado, de modo que ninguna plataforma independiente del sistema sea necesaria para hospedar el archivado.

  - Plataforma de almacenamiento de **datos**     En Lync Server 2013, puede almacenar datos mediante uno de los siguientes elementos:
    
      - Integración de Microsoft **Exchange**     Si desea almacenar los datos de archivado de Lync Server 2013 mediante la implementación de Exchange 2013, en lugar de configurar una base de datos independiente para el almacenamiento de los datos de archivado o además de la configuración de una base de datos independiente, la implementación de Exchange debe ejecutar Exchange 2013. Para obtener información detallada sobre cómo configurar las plataformas del sistema para Exchange 2013, consulte la documentación del producto de Exchange.
    
      - **SQL Server**     Si desea usar una base de datos de SQL Server independiente para el almacenamiento de datos de archivado, en lugar de usar o además del uso de la integración de Microsoft Exchange, debe configurar la plataforma del sistema para la base de datos antes de la implementación del archivado. Los requisitos específicos de la plataforma del sistema dependen de si usa Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para la base de datos de archivado. Para obtener información detallada sobre cómo configurar las plataformas del sistema para estas bases de datos, consulte la documentación del producto Microsoft SQL Server 2008 R2 y Microsoft SQL Server 2012.

  - Plataforma de servidor de **archivos**     Lync Server 2013 almacena los archivos de archivado de Lync Server en la misma ubicación que se especifica para el almacenamiento de archivos al configurar los servidores front-end o los servidores Standard Edition. No puede especificar una ubicación independiente para el almacenamiento de archivos de archivado, por lo que no es necesaria ninguna plataforma del sistema independiente para el almacenamiento de archivos de archivado. Si usa la integración de Microsoft Exchange, Exchange 2013 los archivos de las comunicaciones de Lync archivadas se almacenan en los servidores de Exchange 2013 para los usuarios alojados en esos servidores de Exchange.

</div>

<span> </span>

</div>

</div>

</div>

