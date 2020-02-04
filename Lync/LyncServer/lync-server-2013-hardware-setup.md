---
title: 'Lync Server 2013: Configuración del hardware'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Configuración del hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La configuración del hardware y de otros componentes necesarios en la infraestructura que necesita para implementar su topología requiere que, antes de publicar su topología en el generador de topología, haga lo siguiente:

  - Instale el hardware de cada componente en el diseño de topología que haya creado y guardado con el generador de topología, incluidos los equipos requeridos (servidores que ejecutan Lync Server 2013, servidores de base de datos, servidores de Internet Information Services (IIS) y servidores proxy inversos, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento (como servidores de archivos). Confirme que ha seguido las recomendaciones para el número y la velocidad de los adaptadores de red. Si va a usar equilibradores de carga de hardware, asegúrese de que tiene la información adecuada del proveedor para configurarla para su uso con Lync Server 2013. Si va a usar un servidor de archivos u otro servidor para albergar el recurso compartido de archivos requerido por Lync Server, asegúrese de que el servidor está disponible y listo para configurar el recurso compartido de archivos. Para obtener más información sobre cómo definir una topología que especifique los componentes necesarios para su implementación, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para obtener más información sobre los requisitos de hardware para servidores, consulte [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación de soporte técnico.

  - Asegúrese de que la infraestructura de red cumpla con los requisitos. Para obtener más información, consulte [requisitos de infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación de planeación.

  - Configurar los servicios de dominio de Active Directory. La configuración de AD DS incluye la preparación de AD DS y la definición de todos los componentes que desea implementar en AD DS. Para obtener detalles sobre la preparación de AD DS, consulte [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación de implementación.

  - Configure los permisos necesarios para crear el recurso compartido de archivos. Los permisos de uso compartido de archivos por Lync Server 2013 se configuran automáticamente mediante el generador de topología al publicar su topología. Sin embargo, la cuenta de usuario usada para publicar la topología debe tener control total (lectura/escritura/modificar) en el recurso compartido de archivos para que el generador de topología configure los permisos necesarios. Para asegurarse de que el recurso compartido de archivos se puede administrar correctamente durante el proceso de publicación del generador de topologías, el usuario o el grupo de dominio al que pertenece el usuario debe ser miembro del grupo de administradores locales en el equipo en el que se encuentra el recurso compartido de archivos. En un escenario de dominios múltiples, un usuario o un grupo de dominio debe ser miembro del grupo de administradores locales en el equipo del dominio B donde estará el recurso compartido de archivos.
    
    Para obtener más información sobre cómo actualizar con recursos compartidos de archivos en un sistema de archivos distribuido (DFS), vea [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > El recurso compartido de archivos de Lync Server 2013, Enterprise Edition no se puede encontrar en el servidor front-end.

    
    </div>

  - Instale y configure el equilibrador de carga de hardware para servicios Web. Con el equilibrio de carga del sistema de nombres de dominio (DNS) implementado, aún necesita usar equilibradores de carga de hardware para estos grupos, pero solo para el tráfico HTTP/HTTPS. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80. Aunque siga necesitando equilibradores de carga de hardware para estos grupos, la configuración y la administración serán principalmente para el tráfico HTTP/HTTPS, al que los administradores de los equilibradores de carga de hardware están acostumbrados.

Después de completar todas las tareas de preparación según se describe en este tema, pero antes de publicar la topología, también tendrá que:

  - [Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configurar SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar los registros DNS para un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

