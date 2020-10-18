---
title: 'Lync Server 2013: preparar la infraestructura y los sistemas'
description: 'Lync Server 2013: preparar la infraestructura y los sistemas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfabdda9d117af1534578c8543f9ce72808d5a53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579996"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Preparación de la infraestructura y los sistemas para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La implementación de Lync Server 2013 requiere el uso del generador de topologías para definir y publicar el diseño de la topología. Para identificar los componentes necesarios para la topología, use el generador de topologías para crear y guardar el diseño de la topología. Antes de publicar la topología en el generador de topologías, haga lo siguiente:

  - Adquirir e instalar el hardware para cada componente en el diseño de la topología que creó y guardó mediante el generador de topologías, incluidos todos los equipos necesarios (servidores que ejecutan Lync Server 2013, servidores de bases de datos, servidores que ejecutan Internet Information Services (IIS) y servidores de proxy inverso, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos Para obtener información detallada sobre cómo definir una topología que especifique los componentes necesarios para la implementación, consulte [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obtener más información sobre los requisitos de hardware para los servidores, consulte [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.

  - Asegúrese de que la infraestructura de red cumple los requisitos. Para obtener más información, consulte [requisitos de la infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación referente a la planeación.

  - Configurar los servicios de dominio de Active Directory. Para publicar y habilitar la topología, necesita los servidores internos que se van a representar mediante cuentas de equipo en AD DS. Esto se consigue uniendo los equipos a AD DS. Para obtener información detallada sobre la preparación de AD DS, consulte [preparación de los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Cree un recurso compartido de archivos. Los servidores Standard Edition pueden hospedar el recurso compartido de archivos para el archivo requerido, mientras que en una implementación empresarial no se puede hospedar el recurso compartido de archivos en el servidor front-end. Los permisos y pertenencias a grupos necesarios para implementar y establecer la lista de control de acceso (ACL) en la carpeta y el recurso compartido deben configurarse correctamente para que el generador de topología finalice correctamente. Debe asegurarse de que la persona que ejecuta Topology Builder tiene los siguientes permisos y pertenencias a grupos:
    
      - Miembro de administradores locales
    
      - Miembro de usuarios de dominio
    
      - Control total sobre el recurso compartido y la carpeta del almacén de archivos

  - Para Enterprise Edition, instale y Configure SQL Server. Para que el programa de instalación de SQL Server funcione correctamente, el servidor basado en SQL Server debe estar en línea y la persona que publica la topología debe ser un administrador local en SQL Server y debe ser miembro del grupo sysadmin de SQL Server en la instancia de SQL Server.

Una vez completadas todas las tareas de preparación descritas en este tema, pero antes de publicar la topología, también debe realizar el resto de tareas de preparación, incluida la instalación de los sistemas operativos Windows y otro software necesario como requisito previo, la instalación de IIS y la configuración de DNS. Para obtener más información sobre estas tareas, vea [requisitos del sistema para servidores que ejecutan Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)y [preparar la infraestructura y los sistemas para Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Asimismo, debe familiarizarse con los clientes y los requisitos de los clientes. Para obtener más información, consulte [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de hardware para Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuración de software de Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparación de los servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configuración de SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar registros DNS en Lync Server 2013 para un grupo de servidores front-end o un servidor Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Instalación de las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

