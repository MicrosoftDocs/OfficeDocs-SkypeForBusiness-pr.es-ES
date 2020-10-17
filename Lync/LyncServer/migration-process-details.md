---
title: 'Proceso de migración: detalles'
description: 'Proceso de migración: detalles.'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569586"
---
# <a name="migration-process---details"></a>Proceso de migración: detalles

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Use los siguientes requisitos previos y pasos detallados para migrar el chat en grupo de Lync Server 2010, de grupo o de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.

<div>

## <a name="prerequisites-for-migration"></a>Requisitos previos de migración

Asegúrese de que ha cumplido los siguientes requisitos previos antes de migrar el chat en grupo de Lync Server 2010, Group chat o Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.

1.  Implemente al menos un grupo de servidores de Lync Server 2013. Si tiene varios grupos de servidores de Lync Server 2013, decida qué grupo de servidores de Lync Server 2013 será el grupo principal del nuevo grupo de servidores de chat persistente de Lync Server 2013.

2.  Instale el servidor Lync Server 2013, el grupo de servidores de chat persistente. Estará vacío (sin categorías, salones ni complementos). Antes de migrar las categorías, los salones o los complementos heredados, puede crear salas, categorías o complementos en su implementación de Lync Server 2013, el servidor de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Tenga presente que estos nuevos elementos pueden entrar en conflicto con los elementos heredados que migre. Evite los conflictos de nombres, de lo contrario se sobrescribirán cuando se migren los datos heredados.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Preparar los datos de origen para la migración

Haga lo siguiente para preparar correctamente los datos de origen para la migración.

1.  Realice una copia de seguridad de las bases de datos de origen para Lync Server 2010, grupo de chat o para el chat en grupo de Office Communications Server 2007 R2. Para obtener más información sobre cómo realizar copias de seguridad de SQL Server, vea "Introducción a la copia de seguridad (SQL Server)" en <https://go.microsoft.com/fwlink/p/?linkid=254851> .
    
    <div>
    

    > [!IMPORTANT]  
    > Los servicios de dominio de Active Directory deben ser los mismos. Como condición para la migración, no puede migrar a un grupo de servidores en una implementación diferente (en concreto, en otro bosque de Active Directory).

    
    </div>

2.  Inspeccione la configuración de categoría y los salones de chat de chat en grupo de Lync Server 2010, chat de grupo o de Office Communications Server 2007 R2. Los cambios en las categorías, los salones o los complementos en la implementación heredada existente se realizarán mediante la herramienta de administración de chat en grupo.
    
    <div>
    

    > [!TIP]  
    > Los cambios en las categorías, los salones o los complementos de su Lync Server 2013, la implementación del servidor de chat persistente se realizan con los cmdlets del panel de control de Lync Server o de Windows PowerShell.

    
    </div>
    
    Siga estos pasos para preparar el sistema heredado para la migración.
    
    1.  El servidor de chat persistente admite un solo nivel de categorías, a diferencia de un conjunto de categorías jerárquico en profundidad. Tras la migración, se agrega a las subcategorías el prefijo con los nombres completos de categoría principal. Puede simplificar la estructura de categorías actual conforme a sus necesidades.
    
    2.  Compruebe los **administradores** de la categoría raíz. Si existe algún administrador en este nivel, estos usuarios se agregarán como **administradores para todos los salones** tras la migración. Si su organización no requiere esto, tiene que eliminar estos administradores de la categoría raíz.
    
    3.  Compruebe la longitud de los nombres de los salones. Tras la migración, debido a que se han simplificado las estructuras de las categorías, si hay salones por debajo de una categoría secundaria, se les agregarán como prefijos los nombres completos de las categorías principales. El límite de los nombres es de 256 caracteres, incluidos los nombres de las categorías principales. Debe comprobar la longitud de los nombres de los salones y posiblemente abreviarlos, si son demasiado largos.
    
    4.  En Lync Server 2013, si la configuración de **invitaciones** de categoría se establece en true, puede elegir true o false para invitaciones a salas de esa categoría. No obstante, si se configuran las invitaciones con el valor false, los salones de esta categoría tienen las invitaciones desactivadas. Antes de la migración, debe restablecer la configuración de la invitación en la versión heredada del servidor de chat en grupo de Lync Server, si desea que existan salas o salas en una categoría específica. De lo contrario, durante la migración, Lync Server 2013 muestra advertencias y establece salas en el valor predeterminado de false.
    
    5.  Si usó archivos en salones de chat, debe usar los archivos de forma manual en el nuevo almacén de archivos de chat persistente después de la migración. Las herramientas no lo hacen.
    
    6.  Si tenía usuarios federados y salones con usuarios federados, tenga en cuenta que el servidor de chat persistente no admite la Federación. Los salones con usuarios federados se migrarán, pero los propios usuarios no tendrán acceso al contenido porque no se admite el acceso federado.
    
    7.  Identifique los salones que no desea migrar y márquelos como deshabilitados.
    
    8.  Identifique la fecha a partir de la cual desea migrar el contenido de los salones de chat. Por ejemplo, quizás no desee migrar los mensajes anteriores al 1 de enero de 2010, porque ya son obsoletos o no son importantes para migrarlos.

</div>

<div>

## <a name="performing-the-migration"></a>Realizar la migración

Realice los siguientes pasos para migrar el servidor de chat de grupo heredado.

1.  Cierre el chat en grupo de Lync Server 2010, chat en grupo, Office Communications Server 2007 R2 o Lync Server 2013, servicios del servidor de chat persistente. Se deben detener todos los servicios, así que planee hacerlo cada vez cuando haya suficiente tiempo de inactividad. Como se ha descrito anteriormente, asegúrese de realizar una copia de seguridad de la base de datos de chat de grupo actual.

2.  Ejecute el cmdlet **Export-CsPersistentChatData** de Windows PowerShell como miembro del rol de RBAC administrador de chat persistente (CsPersistentChatAdministrator). Para obtener más información sobre los cmdlets de importación y exportación, consulte [Troubleshooting persistent chat Server Configuration Using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Examine el contenido exportado.

3.  Antes de que esté listo para importar, cierre Lync Server 2013, servicios del servidor de chat persistente. Es necesario detener todos los servicios, así que planee hacerlo a la vez cuando haya suficiente tiempo de inactividad.

4.  Realice una copia de seguridad de la base de datos de chat persistente si ha creado categorías, salones o complementos en la implementación de Lync Server 2013 antes de la migración. El proceso de exportación e importación podrá combinar los datos heredados en la implementación de Lync Server 2013, pero querrá hacer una copia de seguridad de la base de datos en caso de que el contenido se sobrescriba involuntariamente (por ejemplo, si todavía existen conflictos de nombres).

5.  Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell (herramienta de importación) con un comando **Whatif** para rellenar el servidor back-end del grupo de servidores de chat persistente con datos migrados. En el proceso se producen algunas conversiones para acomodar el modelo de administración simplificado. Corrija los errores o las advertencias que aparezcan.

6.  Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell del servidor de chat persistente como miembro del rol de RBAC administrador de chat persistente (CsPersistentChatAdministrator). Para obtener más información sobre los cmdlets de importación y exportación, consulte [Troubleshooting persistent chat Server Configuration Using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Debe tener XCOPY de todos los archivos cargados (toda la carpeta) al nuevo Lync Server 2013, el almacén de archivos de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (cliente) no admite la carga ni la visualización de archivos en salones de chat. Puede seguir usando el cliente heredado para publicar y ver los archivos en el salón.

    
    </div>

8.  Porte el URI de servidor de búsqueda de chat de grupo de Lync Server 2010, chat de grupo u Office Communications Server 2007 R2 al objeto de contacto del servidor de chat persistente de Lync Server 2013. Los siguientes pasos son necesarios si el cliente de chat en grupo de Lync 2010 o de Office Communicator 2007 R2 tiene que conectarse a la versión más reciente de Lync 2013, chat persistente (cliente) después de la migración sin cambios en la configuración del cliente:
    
      - Elimine la \<domainName\> cuenta de usuario del servidor de búsqueda ocschat@. com. Esto se usaba para apuntar al servicio de búsqueda en Lync Server 2010, Group chat. Puede desinstalar el grupo y eliminar las entradas de confianza posteriormente.
    
      - Cree un extremo heredado (objeto de contacto del servidor de chat persistente) mediante la ejecución del cmdlet de Windows PowerShell, **New-CsPersistentChatEndpoint**, con el mismo URI del SIP para que el cliente heredado funcione correctamente cuando se reinicie el servicio.
    
    El proceso de migración obligatorio se completa en este punto. Lync 2010 Group chat (clientes) o Office Communicator 2007 R2 Group chat (clientes) se pueden conectar ahora al nuevo grupo de servidores de chat persistente, en forma transparente.
    
    Siga estos pasos adicionales de retiro para Lync Server 2010, Group chat u Office Communications Server 2007 R2 Group chat.

9.  Inicie los servicios del servidor de chat persistentes activando todos los equipos del nuevo grupo de servidores de chat persistente.

10. Use el panel de control de Lync Server y los cmdlets de Windows PowerShell para comprobar que los datos se han migrado correctamente.

11. Desinstale Lync 2010 Group chat u Office Communicator 2007 R2 Group chat en los equipos del grupo de servidores de chat en grupo.

12. Elimine la aplicación de confianza y el grupo de aplicaciones de confianza con los cmdlets de Windows PowerShell. Esto elimina estos elementos del almacén de administración central y de las entradas de servicio de confianza asociadas (TSE) de Active Directory. Como alternativa, este paso funciona con el generador de topologías (los grupos y las aplicaciones de confianza también tienen un nodo dedicado).

13. Ahora puede empezar a habilitar la funcionalidad del servidor de chat persistente a través de los nuevos clientes. Para más detalles sobre cómo habilitar el servidor de chat persistente, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 admite varios grupos de servidores de chat persistente. Sin embargo, se admite la migración de un grupo de chat de grupo de Lync 2010 o de Office Communications Server 2007 R2 &nbsp; a un solo grupo de servidores de chat persistente de Lync server 2013. Puede agregar nuevos grupos de servidores de chat persistente en su implementación para cumplir con las necesidades regulatorias (por ejemplo, mantener datos dentro de una ubicación geográfica determinada).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

