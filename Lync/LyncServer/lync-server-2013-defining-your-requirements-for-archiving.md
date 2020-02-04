---
title: 'Lync Server 2013: Definir los requisitos para archivado'
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
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definir los requisitos para archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Si su organización debe seguir las normas de cumplimiento, puede implementar el archivado para habilitar el soporte de archivo para Lync Server 2013, mensajería instantánea (mi) y conferencias (reuniones). Para obtener más información sobre el tipo de contenido que se puede archivar, vea [información general sobre el archivado en Lync Server 2013](lync-server-2013-overview-of-archiving.md) en la documentación de planeación.

Para implementar el archivado, primero debe decidir cómo cumplir los requisitos de archivo de su organización. Esto requiere determinar lo siguiente:

  - **Cuándo implementar el archivado**. Puede implementar el archivado como parte de la implementación inicial de Lync Server 2013, o bien puede agregarlo a una implementación existente. Para implementar el archivado, use el generador de topologías para agregarlo a su topología y, a continuación, publique la topología.

  - **Si archivar las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización, o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    <div>
    

    > [!NOTE]  
    > Si usa la integración de Microsoft Exchange para almacenar datos archivados, la configuración de Exchange controla si se archivan las comunicaciones de Lync. Si su implementación incluye varios bosques, debe sincronizar la configuración entre Lync Server y Exchange. El control de archivado para comunicaciones internas o externas solo está disponible para la Directiva de Lync. Para el archivado integrado de Exchange, ambos se archivarán o no se archivarán.

    
    </div>

  - **Por qué habilitar el archivado**. Puede habilitar y deshabilitar el archivado para toda la implementación en un nivel global, y puede habilitar y deshabilitar el archivado para determinados sitios y usuarios. En cada uno de estos niveles, especifica si desea habilitar el archivado de sesiones de mensajería instantánea (de punto a punto), conferencias (reuniones, que son sesiones de varias personas) o ambas. De forma predeterminada, el archivado está deshabilitado.

  - **Cómo se archiva el archivo fundamental para los usuarios de su organización**. Si el archivado es de misión crítica en su organización, puede especificar que Lync Server 2013 se ejecute en modo crítico, lo que bloquea las sesiones de mensajería instantánea y de conferencia si se produce un error de archivado. Por ejemplo:
    
      - Si el servicio de archivado no puede enviar temporalmente un mensaje a la cola de la base de datos o insertar un mensaje en la base de datos), la funcionalidad de mensajería instantánea y de conferencia está bloqueada en la implementación hasta que se restaura la compatibilidad de archivado.
    
      - Si un usuario de conferencia carga un archivo, pero el archivo no se puede copiar en el almacén de archivos de archivado, la funcionalidad de conferencia se bloquea en la implementación hasta que se resuelva el problema, pero la funcionalidad de mensajería instantánea no se bloquea.
    
    Puede configurar esta opción en el nivel de nivel global, de sitio y de grupo. De forma predeterminada, el modo crítico no está habilitado.

  - **Si desea usar la integración de Microsoft Exchange**. Esta opción integra el almacenamiento de archivado en el almacenamiento de Exchange 2013, de modo que los datos archivados de Lync Server y los datos archivados de Exchange 2013 se almacenen conjuntamente en Exchange. Puede usar la integración de Microsoft Exchange para el almacenamiento de datos de archivado para los usuarios que estén alojados en Exchange 2013, si sus buzones se han colocado en conservación local. Si no tiene una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync que no está alojado en Exchange 2013, puede implementar bases de datos de archivado independientes con SQL Server para almacenar los datos archivados de las comunicaciones de Lync. Puede configurar la opción de integración de Microsoft Exchange en el nivel global, en el nivel de sitio y en el nivel de grupo. De forma predeterminada, la integración de Microsoft Exchange no está habilitada.

  - **Cómo se administran los datos archivados**. La base de datos de archivado no está diseñada para la retención a largo plazo y Lync Server 2013 no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que es necesario mover los datos a otro almacenamiento. Lync Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados y que crea transcripciones que permiten búsquedas de los datos archivados. Para la directiva global y para cada sitio y Directiva de usuario que cree, puede habilitar la purga de datos y especificar una de las siguientes opciones:
    
      - Purgue los datos de archivado exportados y los datos de archivado almacenados después de un número específico de días. El número mínimo de días que puede especificar es un día. El número máximo de días que puede especificar es de 2562 días.
    
      - Purgar solo los datos exportados de archivado. Esta opción purga todos los registros que se han exportado y marcado como seguros para eliminarlos con la herramienta de exportación de sesión.
    
    Puede configurar esta opción en el nivel de nivel global, de sitio y de grupo. De forma predeterminada, la purga no está habilitada.

Controle el archivado con los métodos siguientes:

  - **Directivas de archivado**. Use una o más directivas de archivado para habilitar y deshabilitar el archivado de las comunicaciones internas y externas. De forma predeterminada, no se habilita el archivado. Habilite o deshabilite el archivado para comunicaciones internas, comunicaciones externas o ambas en la implementación mediante la directiva global predeterminada. No puede eliminar la directiva global. Puede especificar una o varias directivas de sitio opcionales para habilitar o deshabilitar el archivado de las comunicaciones internas y externas de sitios específicos. También puede especificar una o más directivas de usuario para habilitar o deshabilitar el archivado de usuarios y grupos de usuarios específicos. Las directivas de nivel de usuario invalidan las directivas del sitio. Las directivas de nivel de sitio anulan las directivas de nivel global. Las directivas de nivel de usuario solo se implementan para los usuarios específicos que están configurados para usar la Directiva. Los mensajes instantáneos grupales y las conferencias solo se archivan si una directiva para al menos uno de los participantes está configurada para habilitar el archivado.
    
    <div>
    

    > [!NOTE]  
    > Si usa la integración de Microsoft Exchange, las directivas de Exchange 2013 invalidan las directivas de archivado de Lync Server para todos los usuarios alojados en los servidores de Exchange 2013.

    
    </div>

  - **Configuraciones de archivado**. Use una o más configuraciones de archivado para especificar la mayoría de las opciones de archivado descritas anteriormente en este tema, excepto para habilitar el archivado de comunicaciones internas y externas (configurado mediante directivas de archivado, como se describe en el viñeta anterior). Las configuraciones de archivado incluyen la configuración global predeterminada y las configuraciones de sitios y grupos opcionales. No puede eliminar la configuración global. Las configuraciones de nivel de grupo invalidan las configuraciones de nivel de sitio. Las configuraciones de nivel de sitio invalidan la configuración de nivel global.

Como parte de los análisis de requisitos, debe determinar cómo configurar la directiva global de archivado y la configuración de archivado global. También necesita determinar sus requerimientos para cualquier configuración de archiving de nivel de sitio, configuraciones de archiving de nivel de grupo, políticas de archiving de nivel de sitio y políticas de archiving a nivel de usuario.

Si implementa el archivado para un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos front-end y servidores Standard Edition en su implementación. Debe hacerlo porque los usuarios cuyas comunicaciones deben archivarse pueden ser invitados a una conversación grupal grupal o a reuniones hospedadas en un grupo diferente. Si el archivado no está habilitado en el grupo en el que está hospedada la conversación o la reunión, es posible que no se archiven todos los datos de la Conferencia. El archivado seguirá funcionando para archivar los usuarios habilitados y todos los mensajes INSTANTÁNEos, pero es posible que los eventos y el contenido de las conferencias no se archiven.

<div>


> [!NOTE]  
> Para habilitar la delegación de tareas administrativas a la vez que se mantienen los estándares de seguridad&nbsp;de su organización, Lync Server 2013 usa control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo al asignar a los usuarios roles administrativos predefinidos. Para configurar las directivas de archivado y las configuraciones de archivado de Lync, el usuario debe tener asignado el rol CsArchivingAdministrator (a menos que la configuración se haga directamente en el servidor donde se ha implementado el archivado, en lugar de hacerlo de forma remota desde otro equipo). Para obtener más información sobre RBAC, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación. Para obtener una lista de los derechos de usuario, los permisos y los roles necesarios para la implementación de archivado, vea lista de <A href="lync-server-2013-deployment-checklist-for-archiving.md">comprobación de la implementación para archivar en Lync Server 2013</A>, que está disponible en la documentación de planeación y en la documentación de implementación.<BR>Si utiliza la integración de Microsoft Exchange, la configuración de las directivas de Exchange requiere permisos y derechos de administrador apropiados. Para obtener más información, consulte la documentación de Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

