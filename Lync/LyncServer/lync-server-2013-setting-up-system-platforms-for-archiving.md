---
title: 'Lync Server 2013: configuración de plataformas del sistema para el archivado'
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
ms.openlocfilehash: 13682b7507e133dd49c102bf6c25293ff5da2c08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configurar plataformas del sistema para el archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Antes de iniciar la implementación del archivado, debe instalar el sistema operativo y cualquier otro software necesario en el hardware que cumpla con los requisitos del sistema:

  - **Plataformas 2013 de**   Lync Server las implementaciones de Lync Server 2013 no tienen servidores de archivado. En su lugar, los agentes de recopilación de datos unificados se ejecutan en servidores front-end y servidores Standard Edition para capturar datos para su archivado, por lo que no se necesita ninguna plataforma de sistema independiente para hospedar el archivado.

  - **Plataforma de almacenamiento de datos**   en Lync Server 2013, puede almacenar datos mediante uno de los siguientes procedimientos:
    
      - **Integración de Microsoft Exchange**   si quiere almacenar datos de archivado de Lync Server 2013 mediante la implementación de Exchange 2013, en lugar de configurar una base de datos independiente para el almacenamiento de datos de archivado, su implementación de Exchange debe ejecutar Exchange 2013. Para obtener detalles sobre la configuración de plataformas del sistema para Exchange 2013, consulte la documentación del producto de Exchange.
    
      - **SQL Server**   si desea usar una base de datos de SQL Server independiente para almacenar los datos de archivado, en lugar de o además de usar la integración de Microsoft Exchange, debe configurar la plataforma del sistema para la base de datos antes de implementar el archivado. Los requisitos de la plataforma de sistema específica dependen de si usa Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para la base de datos de archivado. Para obtener detalles sobre la configuración de plataformas del sistema para estas bases de datos, consulte la documentación del producto Microsoft SQL Server 2008 R2 y Microsoft SQL Server 2012.

  - **Plataforma de servidor de archivos**   Lync Server 2013 almacena los archivos de archivado de Lync Server en la misma ubicación que especifique para el almacenamiento de archivos al configurar los servidores front-end o los servidores Standard Edition. No puede especificar una ubicación independiente para archivar el almacenamiento de archivos, por lo que no se requiere ninguna plataforma de sistema independiente para archivar el almacenamiento de archivos. Si usa la integración de Microsoft Exchange, Exchange 2013 los archivos de comunicaciones de Lync archivadas se almacenan en servidores de Exchange 2013 para los usuarios alojados en esos servidores de Exchange.

</div>

<span> </span>

</div>

</div>

</div>

