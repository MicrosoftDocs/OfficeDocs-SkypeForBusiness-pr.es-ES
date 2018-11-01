---
title: "Lync Server 2013 : Nlles fonctionnalités du serveur de conversation permanente"
TOCTitle: Nuevas características del servidor de chat persistente
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48276586
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nuevas características del servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Con Lync Server 2013, Servidor de chat persistente podrá participar en conversaciones, con varios participantes y sobre un tema en particular, que persisten a lo largo del tiempo. Servidor de chat persistente puede ayudar a una organización a realizar las actividades siguientes:

  - Mejorar la comunicación entre equipos geográficamente dispersos y multifuncionales.

  - Ampliar el uso de la información y la participación.

  - Mejorar la comunicación con la organización extendida.

  - Reducir la sobrecarga de información.

  - Mejorar el uso de la información.

  - Aumentar la divulgación de la información y los conocimientos más relevantes.

Servidor de chat persistente de Lync Server 2013 no está disponible en Microsoft Office 365. Actualmente, solo está disponible para clientes locales de Lync 2013.

En Lync 2013, Chat persistente, la funcionalidad de Lync 2013 está integrada en el cliente. Así, los usuarios tienen acceso a mensajería instantánea y presencia, audio y vídeo, conferencias y Chat persistente, todo en el cliente Lync 2013. Para más información sobre el cliente Lync 2013, vea <http://go.microsoft.com/fwlink/p/?linkid=270877>.

En este tema se describen los cambios en las características entre la versión nueva de Lync Server 2013, Servidor de chat persistente y la versión anterior ( Microsoft Lync Server 2010, chat en grupo), entre los que se incluyen los siguientes:

  - Facilitar la experiencia administrativa en Panel de control de Lync Server y eliminar Herramienta de administración de chat en grupo.

  - Integrar los parámetros de configuración de Servidor de chat persistente en el Generador de topologías con la eliminación de Herramienta de configuración de chat en grupo.

  - Facilitar la migración y actualización de versiones anteriores de Servidor de chat persistente.

  - Proporcionar alta disponibilidad y soluciones de recuperación ante desastres.

Para más información sobre la versión más reciente de Servidor de chat persistente, consulte lo siguiente:

  - La Ayuda de Chat persistente en <http://go.microsoft.com/fwlink/p/?linkid=270945>, que ofrece una lista detallada de las características de Chat persistente, cómo funcionan y cómo deben usarse mientras se ejecuta Servidor de chat persistente.

  - [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planeación, [Implementar el servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) en la documentación de implementación, [Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) en la documentación de migración y [Administrar el servidor de chat persistente de Lync Server 2013](managing-lync-server-2013-persistent-chat-server.md) en la documentación de operaciones. Todos estos recursos ofrecen instrucciones para configurar Servidor de chat persistente.

  - El archivo Documentation.msi de Servidor de chat persistente (archivo de Windows Installer) permite a los usuarios obtener acceso a documentación exhaustiva sin conexión sobre Servidor de chat persistente.

## Principales cambios en la topología clave del Servidor de chat persistente

Entre los cambios de alto nivel para Servidor de chat persistente se incluyen los siguientes:

Servidor de chat persistente es ahora un rol de servidor. En Microsoft Lync Server 2010, Servidor de chat en grupo era una aplicación de confianza de terceros para Microsoft Lync Server 2010. Chat persistente se puede agregar a la topología de Lync Server 2013 con Generador de topologías. En Lync Server 2013, la funcionalidad de Servidor de chat persistente se implementa con tres nuevos roles de servidor:

  - **PersistentChatService :** rol front-end de Chat persistente. En las implementaciones de Standard Edition, el rol de servicio de Servidor de chat persistente se coloca en el servidor Standard Edition que implementa el programa previo, como cualquier otro rol de Lync Server. En las implementaciones de Enterprise Edition, el programa previo implementa el rol de servicio de Chat persistente en los equipos autónomos, como cualquier otro rol de Lync Server.

  - **PersistentChatStore :** servidor back-end que se corresponde con la base de datos de contenido de Chat persistente donde se almacena todo el contenido de los chats.

  - **PersistentChatComplianceStore :** servidor back-end que se corresponde con la base de datos de cumplimiento de Chat persistente donde se almacenan todos los eventos de cumplimiento.

Estos roles de Servidor de chat persistente son opcionales y solo los instalan los clientes que desean tener acceso a la funcionalidad completa de Servidor de chat persistente. El rol **PersistentChatComplianceStore** solo es necesario si opta por implementar el cumplimiento de Chat persistente.

El rol **PersistentChatService** ejecuta dos servicios:

  - Servicio de Chat persistente

  - Servicio de cumplimiento de Chat persistente

Si se ejecutan estos servicios en cada Servidor de chat persistente, se proporciona una alta disponibilidad para estos servicios en un Grupo de servidores de chat persistente multiservidor.

Además, para disfrutar de compatibilidad con la carga y descarga de archivos en los salones de Chat persistente, Servidor de chat persistente incluye un servicio web. Antes, este servicio se colocaba en Servidor de chat persistente, Servidor front-end y requería que la instalación previa de Servicios de Internet Information Server (IIS). En Servidor de chat persistente de Lync Server 2013, el servicio web de carga y descarga de archivos se coloca en el Servidor front-end de Lync Server 2013. Como efecto colateral, Servicios de Internet Information Server (IIS) deja de ser un requisito previo para Servidor de chat persistente. El servicio web de carga y descarga de archivos se identifica como **PersistentChat** en el administrador de Servicios de Internet Information Server (IIS).

> [!IMPORTANT]  
> Para ejecutar el rol <strong>PersistentChatService</strong> en el mismo servidor que Servidor front-end de Lync Server 2013, Servidor front-end debe ser Servidor front-end de Standard Edition. El rol <strong>PersistentChatService</strong> no se puede ejecutar independientemente de Servidor front-end de Lync Server 2013. Solo puede instalarse en el contexto de una implementación de Lync Server 2013.



En Servidor de chat persistente, se ha eliminado el servicio de búsqueda. En Lync Server 2010, chat en grupo, el servicio de búsqueda se ejecutaba en cada Servidor de chat en grupoServidor front-end y realizaba el enrutamiento a uno de los servidores de canal. Lync Server 2013 se basa en enrutamiento mediante objetos contacto, donde cada Grupo de servidores de chat persistente está representado por un objeto contacto que usa Servidores front-end de Lync Server para identificar y redirigir las solicitudes al Grupo de servidores de chat persistente adecuado, y a uno de los equipos donde se ejecuta Servidor de chat persistente en el grupo.

En Lync Server 2013, hay cambios en el servicio de cumplimiento:

  - En Lync Server 2010, el servicio de cumplimiento se ejecutaba de manera independiente (no instalado) y tan solo en un servidor. El servicio de cumplimiento ahora se ejecuta en todos los Servidores front-end de Servidor de chat persistente, junto con el servicio de Chat persistente y, por lo tanto, proporciona una alta disponibilidad en un Grupo de servidores de chat persistente multiservidor. Solo se puede configurar un adaptador de cumplimiento para extraer los datos de la base de datos de cumplimiento en uno de los sistemas restantes (archivo XML, archivos hospedados en Exchange, etc.). Servidor de chat persistente incluye un adaptador de XML.

  - La cola de Message Queue Server (también conocida como MSMQ) que comparten el servicio de Chat persistente y el servicio de cumplimiento en cada Servidor front-end de Servidor de chat persistente, es ahora una cola privada que se comparte únicamente entre los dos servicios. Todos los servicios de cumplimiento escriben en la misma base de datos del servidor back-end de cumplimiento. Asimismo, todos leen en esa base de datos para enviar los datos a su instancia del adaptador. El servidor back-end de cumplimiento se representa como un nuevo rol de servidor back-end.
    
    > [!IMPORTANT]  
    > Como en versiones anteriores, todos los datos de cumplimiento se procesan una sola vez. Los datos pueden procesarse desde cualquiera de las instancias de adaptador al que llama el servicio de cumplimiento que se ejecuta en los distintos equipos con Servidor de chat persistente de Lync Server 2013. En Servidor de chat persistente, cualquiera de las instancias del adaptador podría procesar los datos.
    
    

    > [!NOTE]
    > Para más información sobre la instalación de Message Queue Server, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013</A> en la documentación de implementación.



En Lync Server 2013, hay mejoras relacionadas con la alta disponibilidad y la recuperación ante desastres:

  - Mejoras de alta disponibilidad: con la creación de reflejos de SQL Server se proporciona una disponibilidad elevada de las bases de datos de contenido de Servidor de chat persistente y de cumplimiento de Chat persistente, en un centro de datos (en el sitio).

  - Mejoras de recuperación ante desastres: Servidor de chat persistente admite una arquitectura de grupo extendida que permite extender un único Grupo de servidores de chat persistente en dos sitios (es decir, un único grupo lógico, con servidores en el grupo ubicado físicamente entre dos sitios). El envío de registros de SQL Server se usa para la recuperación ante desastres en todos los sitios.

Para más información sobre la elevada disponibilidad y la recuperación ante desastres, consulte [Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación de implementación.

## Cambios clave de administración para Servidor de chat persistente

Lync Server 2013 facilita la administración de Servidor de chat persistente, con:

  - Una administración unificada. Lync Server 2013 facilita la administración de Servidor de chat persistente con herramientas con las que ya están familiarizados los administradores de Lync. Servidor de chat persistente incluye una experiencia de interfaz de usuario administrativa integrada con Panel de control de Lync Server y soluciona problemas de rendimiento con las versiones anteriores de la interfaz de usuario de Servidor de chat en grupo. Además, Servidor de chat persistente incluye una colección de cmdlets de Windows PowerShell para administrar las categorías de Servidor de chat persistente, salones de Servidor de chat persistente (incluidas la eliminación de salones y la purga del contenido obsoleto) y complementos.

  - Un modelo de administración simplificado. Lync Server 2013 ha cambiado y simplificado el modelo de Servidor de chat persistente al modificar los requisitos clave del cliente siguientes:
    
      - Ha quitado las jerarquías anidadas complejas de ámbitos y categorías.
    
      - Ofrece soporte para definir listas de negación y listas de permisos (ámbitos) para los clientes actuales de MindAlign que planean migrar a Servidor de chat persistente.

## ¿Qué diferencias hay con los roles de usuario de las versiones anteriores de Servidor de chat en grupo?

Lync Server 2010, chat en grupo disponía de roles de administrador de usuarios, salones de chat y Lync Server, que podía administrar complementos. Servidor de chat persistente simplemente proporciona un rol de administrador de Chat persistente (que es similar a otros roles de control de acceso basado en roles de Lync Server, o RBAC). Cualquier miembro del rol RBAC puede administrar salones de chat, complementos y categorías (y por lo tanto, puede conceder acceso de usuario a esas categorías), así como la configuración de Grupo de servidores de chat persistente.

## ¿Qué diferencias hay con las categorías de los salones chat de versiones anteriores de Servidor de chat en grupo?

Las categorías de los salones de chat ya no pueden anidarse y la categoría raíz no puede modificarse. AllowedMembers/DeniedMembers integra lo que solía ser un ámbito en las versiones heredadas de Servidor de chat en grupo (salvo que no admitía la especificación de una lista de rechazados). Los ámbitos no pueden sobrescribirse porque no hay categorías anidadas. Un administrador de Chat persistente en Lync Server 2013 tiene la capacidad de crear y administrar categorías de salones de chat. Como parte de la creación y administración de las categorías de salones de chat, el administrador de Chat persistente puede configurar entidades de seguridad (usuarios/contenedores/grupos de Active Directory) con acceso para ser miembros o creadores de salones de chat en una categoría determinada. Un administrador de Chat persistente también puede agregar DeniedMembers a una categoría, que se definen como exclusiones explícitas para la lista de permitidos. DeniedMembers anula lo establecido en AllowedMembers.

## ¿Qué diferencias hay con las propiedades de los salones de chat de las versiones anteriores de Servidor de chat en grupo?

Existe un nuevo concepto de salón de chat abierto en Servidor de chat persistente de Lync Server 2013. Todos los miembros con permiso pueden unirse al salón de chat sin pertenencia exclusiva.

Se han eliminado las propiedades de salón de chat siguientes que se encontraban en las versiones anteriores de Servidor de chat persistente:

  - Tema: un salón ahora solo tiene una descripción.

  - Crear nueva lista de miembros: en Servidor de chat persistente, todos los salones de chat se inician sin ningún miembro (y pueden maximizarse a una pertenencia equivalente a los miembros con permisos).

  - Carga de archivos: era un valor definido en cada salón de chat para controlar si se permitía la carga y descarga de archivos. Ahora se define en el nivel de categoría y se aplica a todos los salones de esa categoría.

  - Historial de chat: era un valor definido en cada salón de chat para controlar si se habilitaba el historial de chat, pero ahora se define solo en el nivel de categoría y se aplica a todos los salones de esa categoría.

  - Invitaciones: un salón siempre hereda el valor de invitaciones de la categoría, o puede desactivarse en el salón. Un salón no puede activar las invitaciones si la categoría tiene las invitaciones desactivadas.

## ¿Qué diferencias hay con las directivas de las versiones anteriores de Servidor de chat en grupo?

Servidor de chat persistente tiene una nueva directiva de Lync habilitada con Chat persistente, por usuario, grupo, sitio o para la configuración global. En el cliente Lync 2013, el entorno de Chat persistente está disponible solo para los usuarios que se encuentran habilitados con la directiva para Chat persistente (ya sea directamente o a través del grupo, el sitio o la configuración global).

Las versiones anteriores de Servidor de chat en grupo no disponían de directivas integradas en las directivas de Lync Server. Por usuario y por categoría o salón, con la característica **Puede cargar archivos** por usuario se podía convertir al usuario en un usuario administrador, un administrador de un salón de chat o configurar la capacidad del usuario de cargar archivos. La característica de **Carga de archivos** de Servidor de chat persistente solo funciona por categoría.

## Registro

El registro en Servidor de chat persistente y System Center Operations Manager se integra en el registro de seguimiento de Lync Server 2013.

## Vea también

#### Otros recursos

[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)

