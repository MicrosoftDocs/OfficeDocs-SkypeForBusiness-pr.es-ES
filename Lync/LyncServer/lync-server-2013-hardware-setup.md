---
title: 'Lync Server 2013: configuración de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57b06362ad70bedd8edd0baafc3d512cbbf95714
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528347"
---
# <a name="hardware-setup-for-lync-server-2013"></a>Configuración de hardware para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La configuración del hardware y de otros componentes necesarios en la infraestructura necesaria para implementar la topología requiere que, antes de publicar la topología en el generador de topologías, haga lo siguiente:

  - Instale el hardware para cada componente del diseño de la topología que ha creado y guardado mediante el generador de topologías, incluidos todos los equipos necesarios (servidores que ejecutan Lync Server 2013, servidores de bases de datos, servidores que ejecutan Internet Information Services (IIS) y servidores proxy inversos, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento Confirme que ha seguido las recomendaciones sobre el número y la velocidad de los adaptadores de red. Si va a usar equilibradores de carga de hardware, asegúrese de que dispone de la información adecuada del proveedor para configurarlos para su uso con Lync Server 2013. Si va a usar un servidor de archivos u otro servidor para hospedar el recurso compartido de archivos necesario para Lync Server, asegúrese de que el servidor esté disponible y listo para la configuración del recurso compartido de archivos. Para obtener información detallada sobre cómo definir una topología que especifique los componentes necesarios para la implementación, consulte [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obtener más información sobre los requisitos de hardware para los servidores, consulte [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.

  - Asegúrese de que la infraestructura de red cumple los requisitos. Para obtener más información, consulte [requisitos de la infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación referente a la planeación.

  - Configurar los servicios de dominio de Active Directory. La configuración de AD DS incluye la preparación de AD DS y la definición de todos los componentes que desea implementar en AD DS. Para obtener información detallada sobre la preparación de AD DS, consulte preparación de los [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.

  - Configure los permisos necesarios para crear el recurso compartido de archivos. El generador de topologías configura automáticamente los permisos para el uso de recursos compartidos de archivos en Lync Server 2013 al publicar la topología. Sin embargo, la cuenta de usuario usada para publicar la topología debe tener control total (lectura/escritura/modificación) en el recurso compartido de archivos para que el generador de topologías configure los permisos necesarios. Para asegurarse de que el recurso compartido de archivos se puede administrar correctamente durante el proceso de publicación del generador de topologías, el usuario o el grupo de dominio al que pertenece el usuario debe ser miembro del grupo de administradores locales en el equipo en el que se encuentra el recurso compartido de archivos. En un escenario con varios dominios, el usuario o el grupo del dominio A debería convertirse en miembro del grupo de administradores locales en el equipo en el dominio B donde se ubicará el recurso compartido de archivos.
    
    Para obtener más información sobre cómo actualizar con recursos compartidos de archivos en un sistema de archivos distribuido (DFS), consulte [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > El recurso compartido de archivos de Lync Server 2013, Enterprise Edition no se encuentra en el servidor front-end.

    
    </div>

  - Instale y configure el equilibrador de carga de hardware para los servicios Web. Con el equilibrio de carga del Sistema de nombres de dominio (DNS) implementado, aún debe usar equilibradores de carga de hardware para estos grupos de servidores, pero solo para el tráfico de HTTP/HTTPS. El equilibrador de carga de hardware se usa para el tráfico HTTPS procedente de clientes a través de los puertos 443 y 80. Aunque siga siendo necesario usar equilibradores de carga de hardware para estos grupos de servidores, su configuración y administración será sobre todo para el tráfico HTTP/HTTPS, a lo que están acostumbrados los administradores de los equilibradores de carga de hardware.

Cuando haya completado todas las tareas de preparación que se describen en este tema, pero antes de publicar la topología, también es necesario realizar las siguientes tareas:

  - [Instalar los sistemas operativos y el software necesario como requisito previo en los servidores para Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configuración de SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar registros DNS en Lync Server 2013 para un grupo de servidores front-end o un servidor Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

