---
title: 'Lync Server 2013: requisitos técnicos para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Requisitos técnicos para archivar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Entre los requisitos técnicos de Lync Server 2013 se incluyen los siguientes:

  - Requisitos de infraestructura.

  - Requisitos previos de software que deben instalarse para el archivado.

  - Requisitos de almacenamiento de datos para archivar.

  - Las consideraciones y los requisitos de escalado para la implementación de archivado.

  - Consideraciones y requisitos de rendimiento para las bases de datos de archivado.

<div>


> [!NOTE]  
> La información de escalabilidad y rendimiento no está disponible en esta versión 2013 de Lync Server.



</div>

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

Los requisitos de la infraestructura de archivado de Lync Server 2013 son los mismos que para la implementación de Lync Server 2013. Para obtener más información, consulte [determinar los requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación de planeación.

</div>

<div>

## <a name="archiving-prerequisites"></a>Requisitos previos de archivado

Lync Server 2013 optimiza los requisitos previos para el archivado debido a lo siguiente:

  - El servidor de archivado ya no es un rol de servidor. En su lugar, los agentes de recopilación de datos unificados se ejecutan en los servidores front-end de un grupo de servidores y servidores Standard Edition para capturar datos para su archivado, por lo que no se configuran plataformas de sistema independientes para archivar.

  - El archivado usa el almacenamiento de archivos de Lync Server 2013 para almacenar temporalmente los archivos de contenido de la reunión, por lo que no se configura un almacén de archivos independiente para archivado.

  - En Lync Server 2013, no se necesita Message Queue Server.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Requisitos de almacenamiento de datos para archivar

Además, debe configurar la infraestructura para archivar el almacenamiento. Esto incluye una o ambas de las siguientes acciones:

  - **Almacenamiento de Microsoft Exchange**. Meeting content files, such as PowerPoint presentations, are archived as attachments. Si desea usar la integración de Microsoft Exchange para que los datos del archivo de Lync se almacenen con datos de cumplimiento de Exchange, debe usar Exchange 2013 para su implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admita el almacenamiento de los archivos de contenido de la reunión. Si implementa el archivado con la opción de integración de Microsoft Exchange, los datos del archivo de Lync se almacenan con los datos de cumplimiento de Exchange 2013 solo para los usuarios alojados en los servidores de Exchange 2013. Debe implementar Exchange 2013 antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange. Si elige usar el almacenamiento de Exchange 2013, no necesita implementar bases de datos de SQL Server independientes para archivar, a menos que tenga usuarios de Lync que no estén alojados en los servidores de Exchange 2013.

  - **Almacenamiento de base de datos de SQL Server para archivar**. Para admitir usuarios que no están alojados en servidores de Exchange 2013, o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado con una base de datos de SQL Server. Lync Server 2013 admite las siguientes versiones de 64 bits de SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express y Microsoft SQL Server 2012 Express no son compatibles con el archivado. no se admiten las versiones de 32 bits de SQL Server. Para obtener más información sobre restricciones y requisitos de SQL Server, consulte <A href="lync-server-2013-database-software-support.md">compatibilidad de software de base de datos en Lync Server 2013</A> en la documentación de planeación o en la documentación de soporte técnico.

    
    </div>
    
    Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluyendo como parte del procedimiento de instalación. Para obtener más información sobre SQL Server, consulte SQL Server TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

