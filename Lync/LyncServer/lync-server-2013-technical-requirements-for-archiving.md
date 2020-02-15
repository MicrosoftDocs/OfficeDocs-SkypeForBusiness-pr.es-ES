---
title: 'Lync Server 2013: requisitos técnicos para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c388fd04ba7600aa28a142961cd5ac07f63ae7c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Requisitos técnicos para el archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Los requisitos técnicos de Lync Server 2013 incluyen los siguientes:

  - Requisitos de infraestructura.

  - Software como requisito previo que debe estar instalado para el archivado.

  - Requisitos de almacenamiento de datos para el archivado.

  - Requisitos y consideraciones de escalado para su implementación de archivado.

  - Requisitos y consideraciones de rendimiento para sus bases de datos de archivado.

<div>


> [!NOTE]  
> La información de escala y rendimiento no está disponible en esta versión 2013 de Lync Server.



</div>

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

Los requisitos de la infraestructura de archivado de 2013 de Lync Server son los mismos que para la implementación de Lync Server 2013. Para obtener más información, consulte [determining Your Infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="archiving-prerequisites"></a>Requisitos previos de archivado

Lync Server 2013 optimiza los requisitos previos para el archivado debido a lo siguiente:

  - El servidor de archivado ya no es un rol de servidor. En su lugar, los agentes de la colección de datos unificada se ejecutan en los servidores front-end en un grupo de servidores y en servidores Standard Edition para capturar datos de archivado, por lo que no debe configurar plataformas de sistema independientes para el archivado.

  - El archivado usa el almacenamiento de archivos de Lync Server 2013 para el almacenamiento temporal de los archivos de contenido de reuniones, por lo que no se configura un almacén de archivos independiente para el archivado.

  - En Lync Server 2013, no se requiere Message Queue Server.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Requisitos de almacenamiento de datos para el archivado

De manera adicional, debe configurar la infraestructura de almacenamiento de archivado. Esto incluye uno o ambos de estos procedimientos:

  - **Almacenamiento de Microsoft Exchange**. Los archivos de contenido de las reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos. Si desea usar la integración de Microsoft Exchange para que los datos de archivo de Lync se almacenen con datos de cumplimiento de Exchange, debe usar Exchange 2013 para la implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admita el almacenamiento de los archivos de contenido de la reunión. Si implementa el archivado con la opción de integración de Microsoft Exchange, los datos de archivo de Lync se almacenan con los datos de cumplimiento de Exchange 2013 solo para los usuarios hospedados en los servidores de Exchange 2013. Debe implementar Exchange 2013 antes de implementar y habilitar el archivado con la opción de integración de Microsoft Exchange. Si decide usar el almacenamiento de Exchange 2013, no es necesario que implemente bases de datos de SQL Server independientes para el archivado, a menos que tenga usuarios de Lync que no estén hospedados en los servidores de Exchange 2013.

  - **Almacenamiento de base de datos de SQL Server para archivado**. Para admitir usuarios que no están hospedados en servidores de Exchange 2013 o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado con una base de datos de SQL Server. Lync Server 2013 admite las siguientes versiones de 64 bits de SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express y Microsoft SQL Server 2012 Express no son compatibles con el archivado. no se admiten las versiones de 32 bits de SQL Server. Para obtener más información sobre las restricciones y los requisitos adicionales de SQL Server, consulte <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> en la documentación de planeación o en la documentación sobre compatibilidad.

    
    </div>
    
    Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. Para obtener más información acerca de SQL Server, vea SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)TechCenter en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

