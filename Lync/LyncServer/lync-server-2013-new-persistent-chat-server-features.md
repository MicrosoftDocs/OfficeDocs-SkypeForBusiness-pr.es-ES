---
title: 'Lync Server 2013: Nuevas características del servidor de chat persistente'
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
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Nuevas características del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Lync Server 2013, el servidor de chat persistente le permite participar en conversaciones con varias partes y basadas en temas que se conservan a lo largo del tiempo. El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:

  - Mejorar la comunicación entre equipos geográficamente dispersos y con varias funciones

  - Ampliar el conocimiento y la participación de la información

  - Mejorar la comunicación con su organización extendida

  - Reducir sobrecarga de información

  - Mejorar el conocimiento de la información

  - Aumentar la dispersión de información y conocimientos importantes

Lync Server 2013, el servidor de chat persistente no está disponible en Microsoft Office 365. En este momento, solo está disponible para los clientes locales de Lync 2013.

En Lync 2013, la funcionalidad de chat persistente se integra en el cliente de Lync 2013. Como resultado, los usuarios tienen acceso a mensajería instantánea/presencia, audio, vídeo, conferencias y chat persistente en el cliente de Lync 2013. Para obtener más información sobre el cliente de Lync 2013 <http://go.microsoft.com/fwlink/p/?linkid=270877>, consulte.

En este tema se describen los cambios de características entre la nueva versión de Lync Server 2013, el servidor de chat persistente y la versión anterior (Microsoft Lync Server 2010, chat grupal), entre los que se incluyen:

  - Proporcionar una experiencia administrativa en el panel de control de Lync Server y eliminar la herramienta de administración de chats grupales

  - Integre la configuración del servidor de chat persistente en el generador de topología eliminando la herramienta de configuración de chats grupales.

  - Facilitar la migración y la actualización de versiones anteriores del servidor de chat persistente

  - Proporcionar soluciones de alta disponibilidad y recuperación ante desastres

Para obtener más información sobre la versión más reciente del servidor de chat persistente, consulte lo siguiente:

  - La ayuda de chat persistente <http://go.microsoft.com/fwlink/p/?linkid=270945> , en la que se proporciona una lista detallada de las características de los chats persistentes, cómo funcionan y cómo usarlos mientras se ejecuta el servidor de chat persistente.

  - El [plan de servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planeación, [implementar un servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) en la documentación de implementación, [migración desde Lync Server 2010, chat grupal o grupo de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) en la documentación de la migración y [Administración de Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md) en la documentación de las operaciones, todas las cuales proporcionan instrucciones para configurar Servidor de chat persistente.

  - El archivo. msi de la documentación del servidor de chat persistente (archivo de Windows Installer) permite a los usuarios acceder a documentación sin conexión completa sobre el servidor de chat persistente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Cambios de topología de clave para el servidor de chat persistente

Los siguientes cambios de alto nivel para el servidor de chat persistente incluyen:

El servidor de chat persistente es ahora un rol de servidor. En Microsoft Lync Server 2010, el servidor de chats grupales era una aplicación de confianza de terceros para Microsoft Lync Server 2010. El chat persistente se puede Agregar a la topología de Lync Server 2013 con el generador de topologías. En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:

  - **PersistentChatService:** Este es el rol front end para chat persistente. En las implementaciones de Standard Edition, el rol de servicio del servidor de chat persistente se inserta en el servidor Standard Edition implementado por el arranque, como cualquier otra función de Lync Server. En las implementaciones de Enterprise Edition, el rol de servicio de chat persistente se implementa en equipos independientes por programa previo, como cualquier otra función de Lync Server.

  - **PersistentChatStore:** Servidor back-end que corresponde a la base de datos de contenido de chat persistente, donde se almacena todo el contenido de la conversación.

  - **PersistentChatComplianceStore:** Función back-end del servidor que corresponde a la base de datos de cumplimiento de chat persistente, en la que se almacenan todos los eventos de cumplimiento.

Estos roles de servidor de chat persistente son opcionales, y solo los clientes que deseen una completa funcionalidad del servidor de chat persistente. El rol de **PersistentChatComplianceStore** es necesario solo si elige implementar el cumplimiento de las conversaciones de forma persistente.

El rol **PersistentChatService** ejecuta dos servicios:

  - Servicio de chat persistente

  - Servicio de cumplimiento de chat persistente

El hecho de que estos servicios se ejecuten en cada servidor de chat persistente proporciona alta disponibilidad para estos servicios en un grupo de servidores de chat persistente multiservidor.

Además, para admitir la carga y descarga de archivos en salones de chat persistentes, el servidor de chat persistente incluye un servicio Web. Anteriormente, este servicio se colocaba en el servidor de chat persistente, el servidor front-end y los servicios de información de Internet (IIS) necesarios para instalarse como requisito previo. En Lync Server 2013 el servidor de chat persistente, el servicio Web de carga/descarga de archivos se encuentra en el servidor front-end de Lync Server 2013. Como efecto secundario, servicios de información de Internet (IIS) ya no es un requisito previo para el servidor de chat persistente. El servicio Web de carga/descarga de archivos se identifica como **PersistentChat** en el administrador de Internet Information Services (IIS).

<div>


> [!IMPORTANT]  
> El rol <STRONG>PersistentChatService</STRONG> se puede ejecutar en el mismo servidor que un servidor Front&nbsp;-end de Lync Server 2013 solo si ese servidor front-end&nbsp;es un servidor de front-end Standard Edition. El rol <STRONG>PersistentChatService</STRONG> no puede ejecutarse de forma independiente en&nbsp;un servidor front-end 2013 de Lync Server. Solo se puede instalar en el contexto de una implementación de Lync Server 2013.



</div>

En el servidor de chat persistente, se eliminó el servicio de búsqueda. En Lync Server 2010, chat grupal, el servicio de búsqueda se ejecutó en cada servidor de usuario de chat de grupo y realizó el enrutamiento a uno de los servidores de canal. Lync Server 2013 se basa en el enrutamiento mediante objetos de contacto, donde cada grupo de servidores de chat persistente se representa mediante un objeto de contacto que los servidores front-end de Lync Server usan para identificar y enrutar solicitudes a un grupo de servidores de chat persistente adecuado, y para uno de los equipos que ejecutan el servidor de chat persistente en el grupo.

En Lync Server 2013, hay modificaciones en el servicio de cumplimiento:

  - En Lync Server 2010, el servicio de cumplimiento se ejecutó de forma independiente (no está) y solo en un único servidor. El servicio de cumplimiento ahora se ejecuta en todos los servidores de aplicaciones para el usuario de chat persistente, junto con el servicio de chat persistente y, por lo tanto, proporciona alta disponibilidad en un grupo de servidores de chat persistente multiservidor. Se puede configurar un único adaptador de cumplimiento para extraer datos de la base de datos de cumplimiento y a uno de los otros sistemas (archivo XML, archivos hospedados por Exchange, etc.). El servidor de chat persistente incluye un adaptador XML.

  - La cola de Message Queue Server (también conocido como MSMQ) compartida por el servicio de chat persistente y el servicio de cumplimiento en cada servidor de cliente de chat persistente es ahora una cola privada compartida solo por los dos servicios. Todos los servicios de cumplimiento escriben en la misma base de datos back end de cumplimiento. También leen esa base de datos, con el fin de enviar los datos a su instancia del adaptador. El servidor back-end de cumplimiento se representa como un nuevo rol de servidor de back end.
    
    <div>
    

    > [!IMPORTANT]  
    > Al igual que en versiones anteriores, todos los datos de cumplimiento solo se procesan una vez. Cualquiera de las instancias de adaptador invocadas por el servicio de cumplimiento que se ejecuta en los diversos Lync Server 2013, los equipos servidores de chat persistentes pueden procesar los datos. En el servidor de chat persistente, cualquiera de las instancias de adaptador podría procesar los datos.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obtener información acerca de la instalación de Message Queue Server, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">instalar sistemas operativos y el software necesario en servidores para Lync Server 2013</A> en la documentación de implementación.

    
    </div>

En Lync Server 2013, hay mejoras en la alta disponibilidad y la recuperación ante desastres:

  - Mejoras de alta disponibilidad: el reflejo de SQL Server se usa para proporcionar alta disponibilidad para la base de datos de contenido del servidor de chat persistente y la base de datos de cumplimiento persistente de la conversación en un centro de datos (en el sitio).

  - Mejoras en la recuperación de desastres: el servidor de chat persistente admite una arquitectura de agrupación extendida que permite estirar un único grupo de servidores de chat persistente en dos sitios (es decir, un único grupo lógico en la topología, con servidores en el grupo físicamente). se encuentra en los dos sitios). El trasvase de registros de SQL Server se usa para la recuperación de desastres entre sitios.

Para obtener más información acerca de la alta disponibilidad y la recuperación ante desastres, vea [configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación de implementación.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Cambios de administración y administración clave para el servidor de chat persistente

Lync Server 2013 ha facilitado la administración y la administración del servidor de chat persistente proporcionando:

  - Administración unificada y administración. Lync Server 2013 facilita la administración y la administración del servidor de chat persistente mediante el uso de herramientas que ya son familiares para los administradores de Lync. El servidor de chat persistente incluye una experiencia de interfaz de usuario administrativa que está integrada en el panel de control de Lync Server, que soluciona problemas de rendimiento con las versiones anteriores de la interfaz de usuario del servidor de chats grupales. Además, el servidor de chat persistente incluye una colección de cmdlets de Windows PowerShell para administrar y administrar categorías de servidores de chat persistentes, salones de servidores de chat persistentes (incluidos la eliminación de salas y el purgado de contenido obsoleto) y complementos.

  - Modelo de administración simplificado. Lync Server 2013 ha cambiado y simplificado el modelo de servidor de chat persistente al tratar los siguientes requisitos clave del cliente:
    
      - Quite las jerarquías anidadas complejas de ámbitos y categorías.
    
      - Compatibilidad para definir listas de denegación, así como listas (ámbitos) permitidas para los clientes actuales de MindAlign que planean migrar a un servidor de chat persistente.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre los roles de usuario de versiones anteriores del servidor de chat de grupo?

Lync Server 2010, chat grupal tenía un rol de administrador de usuarios, un rol de administrador del salón de chat y un rol de administrador de Lync Server que podría administrar complementos. el servidor de chat persistente simplemente proporciona una función de administrador de chat persistente (que es similar a la de otros Lyncs). Roles de control de acceso basado en roles de servidor (RBAC)). Cualquier persona que sea miembro de este rol RBAC puede administrar salones de chat, complementos y categorías (y, por lo tanto, obtener acceso de usuario para estas categorías) y la configuración del grupo de servidores de chat persistente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las categorías del salón de chat de versiones anteriores del servidor de chat de chat?

Las categorías de salones de chat ya no se pueden anidar y la categoría raíz ya no se puede modificar. AllowedMembers/DeniedMembers comprende lo que un ámbito solía estar en las versiones del servidor de chat de grupo heredado (excepto que no es compatible con la especificación de una lista denegada). Los ámbitos ya no se pueden invalidar porque no hay categorías anidadas. Un administrador de chat persistente de Lync Server 2013 puede crear y administrar categorías de salones de chat. Como parte de la creación y administración de categorías de salones de chat, un administrador de chat persistente puede configurar principales (grupos/contenedores de Active Directory/usuarios) que tengan acceso a miembros o creadores de salones de chat de una determinada categoría. Un administrador de chat persistente también puede Agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas a la lista de permitidos. Los miembros denegados reemplazan a los miembros permitidos.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las propiedades del salón de chat de versiones anteriores del servidor de chat?

Existe un nuevo concepto de salones de chat abiertos en Lync Server 2013, servidor de chat persistente. Todos los miembros permitidos pueden unirse al salón de chat, sin pertenencia exclusiva.

Se han eliminado las siguientes propiedades de salón de chat incluidas en versiones anteriores del servidor de chat persistente:

  - Tema: ahora solo hay una descripción en una sala.

  - Crear nueva lista de miembros: en el servidor de chat persistente, todos los salones de chat comienzan con la pertenencia vacía (y pueden maximizar a una pertenencia igual a los miembros permitidos).

  - Carga de archivos: se usa para establecer una configuración por salón de chat para controlar si se permite la carga y descarga de archivos. Ahora solo se establece el nivel de categoría y se aplica a todas las salas de esa categoría.

  - Historial de conversaciones: se usa para controlar la configuración de un salón de chat si el historial de conversaciones está habilitado, pero ahora solo se establece en el nivel de categoría y se aplica a todos los salones de esa categoría.

  - Invitados: una sala siempre hereda la configuración de invitados de la categoría; también puede desactivarse en la habitación. Una sala no puede activar invitados si la categoría se configuró anteriormente como invitado.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>¿Qué diferencias hay entre las directivas de las versiones anteriores del servidor de chat de grupo?

El servidor de chat persistente tiene habilitada una nueva Directiva de Lync con chat persistente, por usuario/grupo de sitio/sitio/configuración global. En el cliente de Lync 2013, el entorno de chat persistente solo está disponible para los usuarios que están habilitados por una directiva de chat persistente (directamente o a través de la configuración de Pool/sitio/global).

Las versiones anteriores del servidor de chats grupales no tenían directivas integradas en las directivas de Lync Server. En el caso de un usuario o por categoría/sala, mediante la característica **puede cargar archivos** por usuario, puede hacer que el usuario sea un administrador de usuarios, un administrador del salón de chat o configurar la capacidad del usuario para cargar archivos. La característica de **carga de archivos** del servidor de chat persistente es solo por categoría.

</div>

<div>

## <a name="logging"></a>Registro

El registro de servidor de chat persistente y System Center Operations Manager está integrado en el registro de seguimiento de Lync Server 2013.

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

