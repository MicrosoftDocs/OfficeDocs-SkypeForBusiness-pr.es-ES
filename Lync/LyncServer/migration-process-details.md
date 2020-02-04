---
title: Proceso de migración - Detalles
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Proceso de migración - Detalles

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Use los siguientes requisitos previos y pasos detallados para migrar Lync Server 2010, chat grupal o chat grupal de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.

<div>

## <a name="prerequisites-for-migration"></a>Requisitos previos para la migración

Asegúrese de que ha cumplido los siguientes requisitos previos antes de migrar Lync Server 2010, chat grupal o chat grupal de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.

1.  Implemente un mínimo de un grupo de 2013 de Lync Server. Si tiene varios grupos de servidores de Lync Server 2013, decida qué grupo de servidores de Lync Server 2013 será el grupo principal para el nuevo grupo de servidores de chat persistente de Lync Server 2013.

2.  Instale Lync Server 2013, grupo de servidores de chat persistente. Estará vacío (no hay categorías, salones ni complementos). Antes de migrar las categorías, salas o complementos heredados, puede crear salas, categorías o complementos en su Lync Server 2013, implementación persistente del servidor de chat.
    
    <div>
    

    > [!IMPORTANT]  
    > Tenga en cuenta que estos elementos recién creados pueden entrar en conflicto con los elementos heredados que migra. Evitar conflictos de nombres; de lo contrario, se sobrescribirán cuando se migren los datos heredados.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Preparar los datos de origen para la migración

Realice los siguientes pasos para preparar correctamente los datos de origen para la migración.

1.  Haga una copia de seguridad de las bases de datos de origen para Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chat grupal. Para obtener detalles sobre cómo realizar copias de seguridad de SQL Server, consulte "Introducción a la <http://go.microsoft.com/fwlink/p/?linkid=254851>copia de seguridad (SQL Server)" en.
    
    <div>
    

    > [!IMPORTANT]  
    > Los servicios de dominio de Active Directory deben ser iguales. Como condición para la migración, no se puede migrar a un grupo en una implementación diferente (en concreto, en un bosque de Active Directory diferente).

    
    </div>

2.  Inspeccione su Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chats grupales chat y configuración de categoría. Los cambios en las categorías, salas o complementos de la implementación heredada existente serán realizados por la herramienta de administración de chats grupales.
    
    <div>
    

    > [!TIP]  
    > Cualquier cambio en las categorías, salas o complementos de su Lync Server 2013, el panel de control de Lync Server o los cmdlets de Windows PowerShell realizan la implementación del servidor de chat persistente.

    
    </div>
    
    Siga estos pasos para preparar el sistema heredado para la migración.
    
    1.  El servidor de chat persistente admite un único nivel de categorías, a diferencia de un conjunto jerárquico de categorías. Después de la migración, las subcategorías van precedidas de nombres de categorías primarias completas. Es posible que desee simplificar y acoplar la estructura de categorías existente para que la estructura resultante cumpla sus requisitos.
    
    2.  Verifica los **administradores** en la categoría raíz. Si hay algún administrador en este nivel, estos usuarios se agregarán como **administradores a todas las salas después de** la migración. Si esto no es un requisito para su organización, debe quitar estos administradores de la categoría raíz.
    
    3.  Verifique la longitud de los nombres de las salas. Después de la migración, debido a las estructuras de categoría simplificadas, si los salones existen en una categoría secundaria, están prefijados con nombres completos de categorías primarias. El límite de nombres es de 256 caracteres, incluidos los nombres de categorías principales. Debe verificar la longitud de los nombres de las salas y, posiblemente, acortar la longitud si son demasiado largas.
    
    4.  En Lync Server 2013, si la configuración de **invitaciones** de categoría se establece en verdadero, puede elegir verdadero o falso para las invitaciones a salas de esta categoría. Sin embargo, si la configuración de invitaciones de categorías está establecida en falso, las salas de esta categoría tienen desactivadas las invitaciones. Antes de la migración, debe restablecer la configuración de la invitación en la versión del servidor de chat del grupo de Lync Server heredado, si quiere que los salones existan en una categoría específica. De lo contrario, durante la migración, Lync Server 2013 muestra advertencias y establece salas en el valor predeterminado de falso.
    
    5.  Si ha usado archivos en salones de chat, debe XCOPY manualmente en el nuevo almacén de archivos de chat persistente después de la migración. Las herramientas no hacen esto.
    
    6.  Si tiene usuarios federados y salas con usuarios federados, tenga en cuenta que el servidor de chat persistente no admite Federación. Se migrarán las salas con usuarios federados; sin embargo, los usuarios ellos mismos no podrán acceder al contenido porque no se admite el acceso federado.
    
    7.  Identifique los salones que no desea migrar y márquelos como deshabilitados.
    
    8.  Identifique la fecha más allá de la cual desea migrar el contenido del salón de chat. Por ejemplo, es posible que no desee migrar mensajes anteriores al 1 de enero de 2010, ya que estos mensajes pueden estar obsoletos o no son relevantes para la migración.

</div>

<div>

## <a name="performing-the-migration"></a>Realizar la migración

Realice los siguientes pasos para migrar el servidor de chat de grupo heredado.

1.  Apague Lync Server 2010, chat grupal, chat grupal de Office Communications Server 2007 R2 o Lync Server 2013, servicios de servidor de chat persistentes. Todos los servicios deben detenerse, así que planifique hacerlo en un momento en el que haya suficiente tiempo de inactividad. Como se ha descrito anteriormente, asegúrese de realizar una copia de seguridad de la base de datos de chat de grupo actual.

2.  Ejecute el cmdlet **Export-CsPersistentChatData** de Windows PowerShell como miembro del rol de RBAC de administrador de chat persistente (CsPersistentChatAdministrator). Para obtener más información sobre los cmdlets de exportación/importación, consulte [solución de problemas de configuración del servidor de chat persistente con cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Inspeccione el contenido exportado.

3.  Antes de estar listo para importar, apague Lync Server 2013, servicios de servidor de chat persistentes. Todos los servicios deben detenerse, por lo que debe planificar hacerlo en un momento en que haya suficiente tiempo de inactividad.

4.  Realice una copia de seguridad de la base de datos de chat persistente si ha creado categorías, salas o complementos en la implementación de Lync Server 2013 antes de la migración. El proceso de exportación e importación podrá fusionar los datos heredados en la implementación de Lync Server 2013, pero tendrá que realizar una copia de seguridad de la base de datos en caso de que se sobrescriba el contenido por error (por ejemplo, si aún existen conflictos de nombres).

5.  Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell (herramienta de importación) con un comando **Whatif** para rellenar el servidor back-end del grupo de servidores de chat persistente con datos migrados. Algunas conversiones se realizan en el proceso para acomodar el modelo de administración simplificado. Corrija los errores o advertencias que aparezcan.

6.  Ejecute el cmdlet **Import-CsPersistentChatData** del servidor de chat persistente como miembro del rol de RBAC de administrador de chat persistente (CsPersistentChatAdministrator). Para obtener más información sobre los cmdlets de exportación/importación, consulte [solución de problemas de configuración del servidor de chat persistente con cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Debe Autocompletar todos los archivos cargados (toda la carpeta) en el nuevo Lync Server 2013, almacén de archivos de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (cliente) no admite la carga ni la visualización de archivos en salones de chat. Aún puede usar el cliente heredado para publicar y ver archivos en el salón.

    
    </div>

8.  Porte el URI del servidor de búsqueda de chat de Lync Server 2010, chat de grupo u Office Communications Server 2007 R2 a Lync Server 2013, objeto de contacto del servidor de chat persistente. Los pasos siguientes son necesarios si el chat grupal de Lync 2010 o los clientes de chat grupal de Office Communicator 2007 R2 necesitan conectarse a la última versión de Lync 2013, chat persistente (cliente) después de la migración sin cambios en la configuración del cliente:
    
      - Elimine la\<cuenta\>de usuario del servidor de búsqueda ocschat@ domainname. com. Esto se usaba para apuntar al servicio de búsqueda en Lync Server 2010, conversación grupal. Puede desinstalar el grupo y quitar las entradas de confianza más adelante.
    
      - Cree un extremo heredado (objeto de contacto del servidor de chat persistente) ejecutando el cmdlet de Windows PowerShell, **New-CsPersistentChatEndpoint**, con el URI de SIP idéntico para que el cliente heredado funcione de forma eficaz cuando se reinicie el servicio.
    
    El proceso de migración obligatoria ha finalizado en este momento. Los chats grupales de Lync 2010 o de Office Communicator 2007 R2 (clientes) se pueden conectar al nuevo grupo de servidores de chat persistente ahora, de forma transparente.
    
    Siga estos pasos adicionales de retiro para Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chat grupal.

9.  Inicie los servicios del servidor de chat persistentes activando todos los equipos del nuevo grupo de servidores de chat persistente.

10. Use el panel de control de Lync Server y los cmdlets de Windows PowerShell para comprobar que los datos se han migrado correctamente.

11. Desinstale chat grupal de Lync 2010 u conversación grupal de Office Communicator 2007 R2 de los equipos del grupo de servidores de chats grupales.

12. Elimine la aplicación de confianza y el grupo de aplicaciones de confianza con cmdlets de Windows PowerShell. Esto elimina estos elementos del almacén de administración central y las entradas de servicios de confianza asociados (EET) de Active Directory. Como alternativa, este paso funciona con el generador de topología (los grupos y las aplicaciones de confianza también tienen un nodo dedicado).

13. Ahora puede empezar a habilitar la funcionalidad del servidor de chat persistente a través de los nuevos clientes. Para obtener más información sobre cómo habilitar el servidor de chat persistente, consulte [implementar un servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 admite varios grupos de servidores de chat persistentes. Sin embargo, admitimos migrar un chat grupal de Lync 2010 o un grupo de&nbsp;chats grupales de Office Communications Server 2007 R2 a un solo Lync Server 2013, grupo de servidores de chat persistente. Puede agregar nuevos grupos de servidores de chat persistentes en su implementación para satisfacer las necesidades de reglamentación (por ejemplo, mantener los datos dentro de una ubicación geográfica determinada).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

