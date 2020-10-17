---
title: 'Lync Server 2013: configuración del almacenamiento para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab7e22d4ff0e34d903fa0306d971705c5455b2f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521787"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configurar el almacenamiento para el archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-17_

El almacenamiento de archivado para Lync Server 2013 incluye lo siguiente:

  - **Almacenamiento**     de datos El almacenamiento de datos es necesario para almacenar el contenido de mensajería instantánea.

  - **Almacenamiento**     de archivos El almacenamiento de archivos es necesario para almacenar el almacenamiento de datos de contenido y de conferencia (reunión).

<div>

## <a name="setting-up-data-storage"></a>Configuración de almacenamiento de datos

Los requisitos para configurar el almacenamiento de datos para el archivado en Lync Server 2013 dependen de cómo desea almacenar los datos de archivado:

  - Integre el archivado de Lync Server 2013 con su implementación de Exchange para almacenar datos de archivado con el almacenamiento de Exchange.

  - Configurar servidores de base de datos de SQL Server independientes para almacenar los datos de archivado.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configuración de almacenamiento de Exchange para datos de archivado

La configuración de Exchange para el almacenamiento de datos de archivado requiere que la implementación de Exchange ejecute Exchange 2013. Además, los buzones de correo de los usuarios deben estar hospedados en el servidor de Exchange 2013 y sus buzones se deben poner en espera de In-Place. Para obtener más información acerca de la configuración de Exchange 2013, consulte la documentación del producto de Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configuración de servidores de bases de datos de SQL Server para el almacenamiento de datos de archivado

El archivado en Lync Server 2013 requiere que el software de base de datos de SQL Server almacene los datos archivados, a menos que integre la implementación de con Exchange.

Para las bases de datos de archivado de SQL Server, debe instalar SQL Server en el equipo que va a hospedar la base de datos de archivado. Puede usar la misma instancia de SQL que usa para la base de datos de back-end de un grupo de servidores front-end. Para un mejor rendimiento, debe implementar la base de datos de archivado en un equipo que sea independiente del Almacén de administración central. Para obtener más información sobre los componentes de combinar Lync Server 2013, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.

Cada servidor de bases de datos debe ejecutar una versión compatible de SQL Server. Para obtener más información sobre las versiones compatibles, consulte [Technical Requirements for archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) en la documentación referente a la planeación.

Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. Para obtener más información acerca de SQL Server, vea SQL Server TechCenter en [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

<div>


> [!NOTE]  
> Asegúrese de que el tipo de inicio del servicio Agente SQL Server es automático y de que el servicio Agente SQL Server se está ejecutando para la instancia de SQL que contiene la base de datos de archivado, de modo que el trabajo de mantenimiento de SQL Server de archivado predeterminado se pueda ejecutar según el control del servicio del Agente SQL Server.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configuración de almacenamiento de archivos

El archivado usa el recurso compartido de archivos 2013 de Lync Server que especificó al configurar el grupo de servidores front-end o el servidor Standard Edition. No se puede cambiar el recurso compartido de archivos usado para el archivado. Para obtener más información sobre los sistemas de almacenamiento de archivos compatibles, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación sobre compatibilidad.

</div>

</div>

<span> </span>

</div>

</div>

</div>

