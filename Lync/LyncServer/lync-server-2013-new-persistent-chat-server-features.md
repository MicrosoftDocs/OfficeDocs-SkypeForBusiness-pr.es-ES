---
title: 'Lync Server 2013: nuevas características del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c5ad73d11ae629ec0848539b2f4bac2bc81a43e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Nuevas características del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Lync Server 2013, el servidor de chat persistente permite participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo. El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:

  - Mejorar la comunicación entre equipos geográficamente dispersos y multifuncionales

  - Ampliar el uso de la información y la participación

  - Mejorar la comunicación con la organización extendida

  - Reducir la sobrecarga de la información

  - Mejorar el uso de la información

  - Aumentar la divulgación de información y conocimientos importantes

Lync Server 2013, el servidor de chat persistente no está disponible en Microsoft Office 365. En este momento, solo está disponible para clientes locales de Lync 2013.

En Lync 2013, la funcionalidad de chat persistente se integra en el cliente de Lync 2013. Como resultado, los usuarios tienen acceso a la mensajería instantánea, presencia, audio, vídeo, conferencias y chat persistente en el cliente de Lync 2013. Para obtener más información sobre el cliente de Lync 2013 <https://go.microsoft.com/fwlink/p/?linkid=270877>, consulte.

En este tema se describen los cambios de características entre la nueva versión de Lync Server 2013, el servidor de chat persistente y la versión anterior (Microsoft Lync Server 2010, Group chat), entre los que se incluyen:

  - Proporcionar una experiencia administrativa en el panel de control de Lync Server y eliminar la herramienta de administración de chat en grupo

  - Integre la configuración del servidor de chat persistente en el generador de topologías mediante la eliminación de la herramienta de configuración de chat en grupo

  - Facilitar la migración y la actualización de versiones anteriores del servidor de chat persistente

  - Proporcionar soluciones de alta disponibilidad y recuperación ante desastres

Para obtener más información acerca de la versión más reciente del servidor de chat persistente, consulte lo siguiente:

  - La ayuda de chat persistente <https://go.microsoft.com/fwlink/p/?linkid=270945> , en la que se proporciona una lista detallada de características de chat persistente, cómo funcionan y cómo usarlas mientras se ejecuta el servidor de chat persistente.

  - La [planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación, [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) en la documentación sobre implementación, [migración de Lync Server 2010, chat en grupo u Office Communications Server 2007 R2 group chat a Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) en la documentación de migración y [Administración de Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md) en la documentación de operaciones, todo lo que proporciona instrucciones para configurar Servidor de chat persistente.

  - El archivo. msi de documentación del servidor de chat persistente (archivo de Windows Installer) permite a los usuarios acceder a documentación sin conexión completa sobre el servidor de chat persistente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Cambios en la topología de clave para el servidor de chat persistente

Entre los siguientes cambios de alto nivel para el servidor de chat persistente se incluyen:

El servidor de chat persistente ahora es un rol de servidor. En Microsoft Lync Server 2010, el servidor de chat en grupo era una aplicación de confianza de terceros para Microsoft Lync Server 2010. Chat persistente puede agregarse a la topología de Lync Server 2013 mediante el generador de topologías. En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:

  - **PersistentChatService:** Este es el rol front-end de chat persistente. En las implementaciones de Standard Edition, el rol de servicio del servidor de chat persistente se combina en el servidor Standard Edition implementado por el arranque, como cualquier otra función de Lync Server. En las implementaciones de Enterprise Edition, la función del servicio de chat persistente se implementa en equipos independientes por arranque, como cualquier otra función de Lync Server.

  - **PersistentChatStore:** Servidor back-end que corresponde a la base de datos de contenido de chat persistente, donde se almacena todo el contenido de chat.

  - **PersistentChatComplianceStore:** Rol de servidor back-end que corresponde a la base de datos de cumplimiento de chat persistente, donde se almacenan todos los eventos de cumplimiento.

Estos roles de servidor de chat persistente son opcionales, y solo los clientes que desean una funcionalidad completa del servidor de chat persistente pueden instalarlos. El rol **PersistentChatComplianceStore** solo es necesario si elige implementar el cumplimiento de chat persistente.

El rol **PersistentChatService** ejecuta dos servicios:

  - Servicio de chat persistente

  - Servicio de cumplimiento de chat persistente

El hecho de que estos servicios se ejecuten en cada servidor de chat persistente proporciona alta disponibilidad para estos servicios en un grupo de servidores de chat persistente multiservidor.

Además, para admitir la carga y descarga de archivos en salones de chat persistente, el servidor de chat persistente incluye un servicio Web. Anteriormente, este servicio se incluyó en el servidor de chat persistente, en el servidor front-end y en Internet Information Services (IIS) necesario para instalarse como un requisito previo. En el servidor de chat persistente de Lync Server 2013, el servicio Web de carga/descarga de archivos se combina con el servidor front-end de Lync Server 2013. Como efecto secundario, Internet Information Services (IIS) ya no es un requisito previo para el servidor de chat persistente. El servicio Web de carga/descarga de archivos se identifica como **PersistentChat** en el administrador de Internet Information Services (IIS).

<div>


> [!IMPORTANT]  
> El rol <STRONG>PersistentChatService</STRONG> se puede ejecutar en el mismo servidor que un servidor Front&nbsp;-end de Lync Server 2013 solo si el servidor front-end&nbsp;es un servidor front-end Standard Edition. El rol <STRONG>PersistentChatService</STRONG> no se puede ejecutar de forma independiente de&nbsp;un servidor front-end 2013 de Lync Server. Solo se puede instalar en el contexto de una implementación de Lync Server 2013.



</div>

En el servidor de chat persistente, se ha eliminado el servicio de búsqueda. En Lync Server 2010, chat en grupo, el servicio de búsqueda se ejecutó en cada servidor front-end del servidor de chat de grupo y realizó el enrutamiento a uno de los servidores de canal. Lync Server 2013 se basa en el enrutamiento mediante objetos de contacto, donde cada grupo de servidores de chat persistente se representa mediante un objeto de contacto que los servidores front-end de Lync Server usan para identificar y enrutar las solicitudes a un grupo de servidores de chat persistente adecuado, y para uno de los equipos que ejecutan el servidor de chat persistente en el grupo.

En Lync Server 2013, hay modificaciones del servicio de cumplimiento:

  - En Lync Server 2010, el servicio de cumplimiento se ejecutó de forma independiente (no combinada) y solo en un único servidor. El servicio de cumplimiento ahora se ejecuta en todos los servidores front-end del servidor de chat persistente, junto con el servicio de chat persistente y, por lo tanto, proporciona alta disponibilidad en un grupo de servidores de chat persistente multiservidor. Se puede configurar un adaptador de cumplimiento único para extraer datos de la base de datos de cumplimiento y en uno de los otros sistemas (archivo XML, archivos hospedados por Exchange, etc.). El servidor de chat persistente incluye un adaptador XML.

  - La cola de Message Queue Server (también conocido como MSMQ) que comparte el servicio de chat persistente y el servicio de cumplimiento en cada servidor front-end del servidor de chat persistente es ahora una cola privada compartida solo por los dos servicios. Todos los servicios de cumplimiento escriben en la misma base de datos back-end de cumplimiento. También se han leído de esa base de datos, con el fin de enviar los datos a su instancia del adaptador. El servidor back-end de cumplimiento se representa como un nuevo rol de servidor back-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Como en versiones anteriores, todos los datos de cumplimiento se procesan una sola vez. Los datos se pueden procesar mediante cualquiera de las instancias de adaptador invocadas por el servicio de cumplimiento que se ejecuta en los diversos equipos del servidor de chat persistente de Lync Server 2013. En el servidor de chat persistente, una de las instancias de adaptador podría procesar los datos.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obtener información sobre la instalación de Message Queue Server, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">instalar sistemas operativos y requisitos previos de software en servidores para Lync Server 2013</A> en la documentación sobre implementación.

    
    </div>

En Lync Server 2013, hay mejoras en la alta disponibilidad y la recuperación ante desastres:

  - Mejoras de alta disponibilidad: el reflejo de SQL Server se usa para proporcionar alta disponibilidad para la base de datos de contenido del servidor de chat persistente y la base de datos de cumplimiento de chat persistente dentro de un centro de datos (en el sitio).

  - Mejoras en la recuperación ante desastres: el servidor de chat persistente admite una arquitectura de grupo extendida que permite estirar un único grupo de servidores de chat persistente en dos sitios (es decir, un único grupo lógico en la topología, con los servidores del grupo físicamente) se encuentra en dos sitios). El trasvase de registros de SQL Server se usa para la recuperación ante desastres entre sitios.

Para obtener más información acerca de la alta disponibilidad y la recuperación ante desastres, consulte [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación sobre implementación.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Cambios clave de administración y administración para el servidor de chat persistente

Lync Server 2013 le ha facilitado la administración y la administración del servidor de chat persistente proporcionando:

  - Administración y administración unificadas. Lync Server 2013 facilita la administración y la administración del servidor de chat persistente mediante el uso de herramientas que ya están familiarizadas con los administradores de Lync. El servidor de chat persistente incluye una experiencia de interfaz de usuario administrativa integrada con el panel de control de Lync Server, que soluciona problemas de rendimiento con versiones anteriores de la interfaz de usuario del servidor de chat en grupo. Además, el servidor de chat persistente incluye una colección de cmdlets de Windows PowerShell para administrar y administrar categorías de servidor de chat persistente, salones de servidores de chat persistente (incluidos la eliminación de salones y el purgado de contenido obsoleto) y complementos.

  - Modelo de administración simplificado. Lync Server 2013 ha cambiado y simplificado el modelo de servidor de chat persistente al enfrentar los siguientes requisitos clave del cliente:
    
      - Quite las jerarquías complejas anidadas de ámbitos y categorías.
    
      - Soporte para definir listas de denegación y listas permitidas (ámbitos) para los clientes actuales de MindAlign que tienen previsto migrar a un servidor de chat persistente.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las funciones de usuario de versiones anteriores del servidor de chat en grupo?

Lync Server 2010, Group chat tenía un rol de administrador de usuarios, un rol de administrador de salón de chat y un rol de administrador de Lync Server que podía administrar complementos. el servidor de chat persistente simplemente proporciona un rol de administrador de chat persistente (que es similar a otros Lync Roles de control de acceso basado en roles (RBAC) de servidor. Cualquier persona que sea miembro de este rol RBAC puede administrar salones de chat, complementos y categorías (y, por lo tanto, obtener el acceso de los usuarios a estas categorías) y la configuración del grupo de servidores de chat persistente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las categorías de salones de chat de versiones anteriores del servidor de chat de grupo?

Las categorías de salones de chat ya no se pueden anidar y la categoría raíz ya no se puede modificar. Miembros permitidos/DeniedMembers comprende lo que un ámbito solía estar en las versiones de servidor de chat de grupo heredado (excepto que no admite la especificación de una lista denegada). Los ámbitos ya no se pueden invalidar porque no hay categorías anidadas. Un administrador de chat persistente en Lync Server 2013 puede crear y administrar categorías de salones de chat. Como parte de la creación y la administración de categorías de salones de chat, un administrador de chat persistente puede configurar entidades de identidad (grupos/usuarios de Active Directory) que tienen acceso a miembros o creadores de salones de chat de una categoría determinada. Un administrador de chat persistente también puede Agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas de la lista de permitidos. Los DeniedMembers anulan a los que se encuentran en AllowedMembers.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las propiedades de los salones de chat de versiones anteriores del servidor de chat en grupo?

Existe un nuevo concepto de salones de chat abiertos en Lync Server 2013, el servidor de chat persistente. Todos los miembros permitidos pueden unirse al salón de chat, sin pertenencia exclusiva.

Se han eliminado las siguientes propiedades de salón de chat incluidas en versiones anteriores del servidor de chat persistente:

  - Tema: ahora solo hay una descripción en una sala.

  - Crear nueva lista de miembros: en el servidor de chat persistente, todos los salones de chat comienzan con una pertenencia vacía (y pueden maximizar hasta una pertenencia igual a los miembros permitidos).

  - Carga de archivos: se usa como configuración por salón de chat para controlar si se permite la carga y descarga de archivos. Ahora solo se establece el nivel de categoría y se aplica a todas las salas de esa categoría.

  - Historial de chat: se usa para controlar la configuración de un salón de chat si se habilitó el historial de chats, pero ahora solo se establece en el nivel de categoría y se aplica a todos los salones de esa categoría.

  - Invitados: una sala siempre hereda la configuración de invitaciones para la categoría; o puede desactivarse en la sala. Una sala no puede activar invitaciones si la categoría se estableció previamente como invitaciones.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las directivas de versiones anteriores del servidor de chat en grupo?

El servidor de chat persistente tiene una nueva Directiva de Lync habilitada con chat persistente, por usuario/grupo/sitio/configuración global. En el cliente de Lync 2013, el entorno de chat persistente solo está disponible para los usuarios que están habilitados por la Directiva para chat persistente (ya sea directamente o a través de la configuración de grupo de servidores/sitio/global).

Las versiones anteriores del servidor de chat en grupo no tenían ninguna directiva integrada en las directivas de Lync Server. En el caso de los usuarios y por categoría y por habitación, al usar la característica **Can upload files** per user, puede convertir al usuario en Administrador, administrador de un salón de chat o configurar la capacidad del usuario para cargar archivos. La característica de **carga de archivos** del servidor de chat persistente es solo por categoría.

</div>

<div>

## <a name="logging"></a>Registro

El registro del servidor de chat persistente y System Center Operations Manager se integra en el registro de seguimiento de Lync Server 2013.

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

