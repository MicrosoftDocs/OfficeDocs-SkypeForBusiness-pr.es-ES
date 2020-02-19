---
title: 'Lync Server 2013: definición de los requisitos para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110423897de0d4d8e280a44cd51c645ab479241a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definición de los requisitos para el archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Si su organización debe seguir las normas de cumplimiento, puede implementar el archivado para habilitar la compatibilidad de archivado para la mensajería instantánea (mi) 2013 y las conferencias (reuniones) de Lync Server. Para obtener más información sobre el tipo de contenido que se puede archivar, consulte [información general sobre el archivado en Lync Server 2013](lync-server-2013-overview-of-archiving.md) en la documentación referente a la planeación.

Para implementar el archivado, debe decidir en primer lugar cómo satisfacer los requisitos de su organización para el archivado. Esto requiere determinar lo siguiente:

  - **Cuándo se debe implementar el archivado**. Puede implementar el archivado como parte de la implementación inicial de Lync Server 2013 o puede agregarlo a una implementación existente. Para implementar el archivado, use el generador de topologías para agregarlo a la topología y, a continuación, publique la topología.

  - **Archivar o no las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    <div>
    

    > [!NOTE]  
    > Si usa la integración de Microsoft Exchange para almacenar datos archivados, la configuración de Exchange controla si se archivan las comunicaciones de Lync. Si la implementación de incluye varios bosques, debe sincronizar la configuración entre Lync Server y Exchange. El control de archivado para las comunicaciones internas o externas solo está disponible para la Directiva de Lync. Para el archivado integrado de Exchange, ambos se archivarán o no se archivarán.

    
    </div>

  - **Por qué habilitar el archivado**. Puede habilitar y deshabilitar el archivado para toda implementación en un nivel global, y también para usuarios y sitios específicos. En cada uno de estos niveles, debe especificar si desea habilitar el archivado de las sesiones de mensajería instantánea (de punto a punto), de las conferencias (reuniones, que son sesiones con varios participantes), o de ambas. De forma predeterminada, el archivado está deshabilitado.

  - **La importancia del archivado para los usuarios de la organización**. Si el archivado es de misión crítica en su organización, puede especificar que Lync Server 2013 se ejecute en modo crítico, que bloquea las sesiones de mensajería instantánea y de conferencia si se produce un error en el archivado. Por ejemplo:
    
      - Si el servicio de archivado está temporalmente no disponible para enviar un mensaje a la cola de la base de datos o para insertar un mensaje en la base de datos, ambas funcionalidades, mensajería instantánea y conferencias, se bloquean en la implementación hasta que se restablece la compatibilidad del archivado.
    
      - Si el usuario de una conferencia carga un archivo pero el archivo no se puede copiar al almacén de archivos de archivado, la funcionalidad de conferencia se bloquea en la implementación hasta que se soluciona el problema, pero la funcionalidad de mensajería instantánea no se bloquea.
    
    Puede configurar esta opción en el nivel global, nivel de sitio y nivel de grupo. De forma predeterminada, el modo crítico no está habilitado.

  - **Si se va a usar la integración de Microsoft Exchange**. Esta opción integra el almacenamiento de archivado con el almacenamiento de Exchange 2013, de modo que los datos archivados de Lync Server y los datos archivados de Exchange 2013 se almacenan juntos en Exchange. Puede usar la integración de Microsoft Exchange para el almacenamiento de datos de archivado para los usuarios hospedados en Exchange 2013, si sus buzones se han colocado en conservación local. Si no dispone de una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync que no esté hospedado en Exchange 2013, puede implementar bases de datos de archivado independientes con SQL Server para almacenar datos archivados de Lync Communications. Puede configurar la opción de integración de Microsoft Exchange en el nivel global, en el nivel de sitio y en el nivel de grupo. De forma predeterminada, la integración de Microsoft Exchange no está habilitada.

  - **Cómo se administrarán los datos archivados**. La base de datos de archivado no está pensada para la retención a largo plazo y Lync Server 2013 no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que es necesario mover los datos a otro almacenamiento. Lync Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados y que crea transcripciones que permiten búsquedas de los datos archivados. Para la directiva global y para cada una de las directivas de usuario y de sitio que cree, puede habilitar la depuración de datos y especificar una de las siguientes opciones:
    
      - Purgar tanto datos de archivado exportados como datos de archivado almacenados tras un número determinado de días. El número mínimo de días que puede especificar es un día. El número máximo de días que puede especificar son 2.562.
    
      - Purgar solo datos archivados exportados. Esta opción purga todos los registros exportados y marcados como seguros para su eliminación con la herramienta de exportación de sesiones.
    
    Puede configurar esta opción en el nivel global, de sitio y de grupo. De forma predeterminada, la purgación no está habilitada.

Controle el archivado con los métodos siguientes:

  - **Directivas de archivado**. Utilice una o varias directivas de archivado para habilitar y deshabilitar el archivado de comunicaciones internas y externas. De forma predeterminada, está habilitada la opción de no archivado. Habilite o deshabilite el archivado para las comunicaciones internas, las comunicaciones externas o ambas en su implementación usando la directiva global predeterminada. No se puede eliminar la directiva global. Puede especificar una o más directivas de sitio opcionales para habilitar o deshabilitar el archivado para comunicaciones internas y externas para sitios específicos. También puede especificar una o varias directivas de usuario para habilitar o deshabilitar el archivado para usuarios específicos y grupos de usuarios. Las directivas de nivel de usuario invalidan las directivas de sitio. Las directivas de nivel de sitio invalidan las directivas de nivel global. Las directivas de nivel de usuario se implementan solo para los usuarios específicos que están configurados para utilizar la directiva. Las conferencias y los mensajes instantáneos de grupo se archivan solo si se configura una directiva para al menos uno de los participantes para habilitar el archivado.
    
    <div>
    

    > [!NOTE]  
    > Si usa la integración de Microsoft Exchange, las directivas de Exchange 2013 invalidan las directivas de archivado de Lync Server para todos los usuarios hospedados en los servidores de Exchange 2013.

    
    </div>

  - **Configuraciones de archivado**. Puede usar una o varias configuraciones de archivado para especificar la mayoría de las opciones de archivado descritas anteriormente en este tema, excepto para habilitar el archivado de comunicaciones internas y externas (configuradas con las directivas de archivado, tal como se describe en el punto anterior). Las configuraciones de archivado incluyen la configuración global predeterminada y las configuraciones de sitio y de grupo opcionales. No se puede eliminar la configuración global. Las configuraciones de nivel de grupo invalidan las configuraciones de nivel de sitio. Las configuraciones de nivel de sitio invalidan la configuración global.

Como parte del análisis de requisitos, debe determinar cómo establecer la configuración de archivado global y la directiva de archivado global, además de los requisitos para las configuraciones de archivado de nivel de sitio, las configuraciones de archivado de nivel de grupo, las directivas de archivado de nivel de sitio y las directivas de archivado de nivel de usuario.

Si implementa el archivado en un grupo de servidores front-end o en un servidor Standard Edition, deberá habilitarlo para todos los demás grupos de servidores front-end y servidores Standard Edition de su implementación. Esto es necesario porque los usuarios cuyas comunicaciones deben archivarse pueden ser invitados a una conversación de mensajería instantánea en grupo o a reuniones alojadas en un grupo de servidores distinto. Si el archivado no está habilitado en el grupo de servidores en el que se hospeda la conversación o reunión, puede que no se puedan archivar todos los datos de la conferencia. El archivado seguirá funcionando para todos los mensajes instantáneos y los usuarios habilitados, pero puede que no se archiven los eventos y el contenido de conferencia.

<div>


> [!NOTE]  
> Para habilitar la delegación de tareas administrativas a la vez que se mantienen los estándares de seguridad&nbsp;de la organización, Lync Server 2013 usa el control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos. Para configurar las directivas de archivado de Lync y las configuraciones de archivado, se debe asignar al usuario al rol CsArchivingAdministrator (a menos que la configuración se realice directamente en el servidor donde se implementa el archivado, en lugar de hacerlo de forma remota desde otro equipo). Para obtener más información acerca de RBAC, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planeación del control de acceso basado en roles en Lync Server 2013</A> en la documentación referente a la planeación. Para obtener una lista de los derechos de usuario, los permisos y los roles necesarios para la implementación de archivado, consulte <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment Checklist for archiving in Lync Server 2013</A>, que está disponible en la documentación de planeación y en la documentación sobre implementación.<BR>Si usa la integración de Microsoft Exchange, la configuración de las directivas de Exchange requiere permisos y derechos de administrador adecuados. Para obtener más información, consulte la documentación de Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

