---
title: 'Lync Server 2013: Preparación de la infraestructura y los sistemas'
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
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Preparación de la infraestructura y los sistemas para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La implementación de Lync Server 2013 requiere el uso de Topology Builder para definir y publicar el diseño de la topología. Para identificar los componentes necesarios para su topología, use el generador de topología para crear y guardar un diseño de topología. Antes de publicar su topología en el generador de topología, puede hacer lo siguiente:

  - Adquiera e instale el hardware de cada componente en el diseño de topología que ha creado y guardado mediante el generador de topología, incluidos todos los equipos necesarios (servidores que ejecutan Lync Server 2013, servidores de bases de datos, servidores que ejecutan servicios de Internet Information Server (). IIS), así como servidores proxy inversos, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento (como servidores de archivos). Para obtener más información sobre cómo definir una topología que especifique los componentes necesarios para su implementación, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obtener más información sobre los requisitos de hardware para servidores, consulte [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación de soporte técnico.

  - Asegúrese de que la infraestructura de red cumpla con los requisitos. Para obtener más información, consulte [requisitos de infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación de planeación.

  - Configurar los servicios de dominio de Active Directory. Para publicar y habilitar la topología, necesita que los servidores internos estén representados por cuentas de equipos en AD DS. Esto se logra al unir los equipos a AD DS. Para obtener detalles sobre la preparación de AD DS, consulte [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Crear un recurso compartido de archivos. Los servidores Standard Edition pueden hospedar el recurso compartido de archivos para el archivo requerido, mientras que en una implementación empresarial el recurso compartido de archivos no se puede hospedar en el servidor front-end. Los permisos y pertenencias a grupos necesarios para implementar y establecer la lista de control de acceso (ACL) en la carpeta y el recurso compartido deben establecerse correctamente para que el generador de topología se complete correctamente. Debe asegurarse de que la persona que ejecuta el generador de topología tenga los siguientes permisos y pertenencias a grupos:
    
      - Miembro de administradores locales
    
      - Miembro de usuarios del dominio
    
      - Control total sobre el recurso compartido y la carpeta del almacén de archivos

  - Para Enterprise Edition, instale y Configure SQL Server. Para que el programa de instalación de SQL Server funcione correctamente, el servidor basado en SQL Server debe estar en línea y la persona que publica la topología es un administrador local en SQL Server y debe ser miembro del grupo de administradores de SQL Server en la instancia de SQL Server.

Después de completar todas las tareas de preparación según se describe en este tema, pero antes de publicar la topología, también tendrá que realizar otras tareas de preparación, como instalar los sistemas operativos de Windows y otro software necesario, configurar IIS y configuración de DNS. Para obtener más información sobre estas tareas, consulte [requisitos del sistema para servidores que ejecutan Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)y [preparar la infraestructura y los sistemas para Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Además, debe familiarizarse con los requisitos de clientes y clientes. Para obtener más información, consulte [implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración del hardware en Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuración del software para Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configurar SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar los registros DNS para un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

