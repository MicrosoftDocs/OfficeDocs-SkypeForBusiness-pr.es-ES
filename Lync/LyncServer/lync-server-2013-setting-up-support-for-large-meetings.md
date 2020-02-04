---
title: 'Lync Server 2013: configuración de soporte técnico para reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configurar la compatibilidad para reuniones grandes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-12_

La compatibilidad con las reuniones de gran tamaño de hasta 1000 usuarios requiere la creación de una topología adecuada, la satisfacción de los requisitos previos de hardware y software, y la configuración adecuada del entorno.

<div>

## <a name="topology-requirements"></a>Requisitos de topología

Una única reunión grande requiere al menos un servidor front-end y un servidor back-end. Sin embargo, para ofrecer una alta disponibilidad, recomendamos un grupo de servidores front-end con servidores de back-end duplicados.

El usuario que hospede las reuniones grandes debe tener su cuenta de usuario alojada en este grupo. Pero, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Como la configuración de las reuniones grandes se optimiza para el rendimiento, al utilizarla como un usuario normal podría tener problemas como la imposibilidad de promover una sesión P2P a una reunión cuando hay un extremo RTC involucrado.

Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para obtener más información, vea [topologías y componentes para servidores front-end, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Además, si desea proporcionar la opción de recuperación ante desastres y conmutación por error para el grupo que se usa para las reuniones grandes, puede asociarlo a un grupo dedicado con una configuración similar y datos diferentes. Para obtener más información, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuración de grupo de servidores para reuniones grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuración de grupo de servidores para reuniones grandes")

Las siguientes son notas adicionales sobre la topología:

  - Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el servidor de archivado está implementado y habilitado, para el archivado de los archivos. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener más información sobre cómo configurar el recurso compartido de archivos, consulte [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Se necesita un servidor de Office Web Apps para habilitar la funcionalidad de presentación de PowerPoint en reuniones grandes. El servidor de Office Web Apps se puede dedicar al grupo de reuniones de gran tamaño o puede ser el mismo servidor de Office Web Apps usado por otros grupos en el sitio en el que se implementa el grupo dedicado.

  - El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga de contenido de la reunión). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para obtener información detallada, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Si desea usar el servidor de supervisión para el grupo de reuniones de gran tamaño dedicado, le recomendamos que use el servidor de supervisión y su base de datos que se comparten en todos los grupos de servidores front-end de su implementación de Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Los requisitos de hardware de los servidores de un grupo de reuniones grande dedicado son los mismos que los de los otros servidores de Lync Server 2013. Para obtener más información sobre los requisitos de hardware, vea "[plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Los servidores de un grupo de reuniones dedicado de gran tamaño deben cumplir todos los requisitos de software de Lync Server 2013. Para obtener más información sobre los requisitos de software, consulte la siguiente documentación:

  - [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Además, tanto Lync Server 2013 como todos los clientes de Lync Server 2013 deben tener las actualizaciones más recientes.

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuración

Le recomendamos crear una nueva Directiva de conferencia específicamente para reuniones grandes y, a continuación, asignar la Directiva de conferencia a los usuarios alojados en el grupo de reuniones de gran tamaño dedicado. Configure la directiva de conferencias por medio de las siguientes opciones:

  - Establezca la opción **MaxMeetingSize** en **1000**. (El valor predeterminado es **250**).

  - Establezca la opción **AllowLargeMeetings** en **True**.

  - Establezca la opción **EnableAppDesktopSharing** en **None**.

  - Establezca la opción **AllowUserToScheduleMeetingsWithAppSharing** en **False**.

  - Establezca la opción **AllowSharedNotes** en **False**.

  - Establezca la opción **AllowAnnotations** en **False**.

  - Establezca la opción **DisablePowerPointAnnotations** en **True**.

  - Establezca la opción **AllowMultiview** en **False**.

  - Establezca la opción **EnableMultiviewJoin** en **False**.

<div>


> [!NOTE]  
> El soporte técnico para las reuniones de gran tamaño del usuario de 1000 en Lync Server 2013 requiere que el valor <STRONG>AllowLargeMeetings</STRONG> de la Directiva de conferencia para el programador de reuniones se establezca en true. Cuando esta configuración se establece en true, la experiencia de Lync se optimizará para las reuniones extra grandes cuando los usuarios se unan a la reunión. En concreto, en una reunión grande, Lync no mostrará el inicio ni la actualización de la lista completa de participantes de la reunión, que es un cuello de botella de rendimiento para el cliente y Lync Server 2013. En su lugar, Lync solo mostrará información sobre el usuario y la lista de moderadores de la reunión. Lync seguirá correctamente el número total de participantes disponibles en las reuniones grandes.



</div>

Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funciones de conferencia que no se necesitan en reuniones grandes.

Además, debe configurar el grupo de reuniones dedicado de gran tamaño para que todos los usuarios de Lync Server 2013 alojados en el grupo y responsables de administrar la programación de la reunión tengan los permisos apropiados. Para ello, siga estos pasos:

  - Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no tienen que ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores necesitan designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.

  - Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento de reunión en línea para Lync 2013 siempre programa las conferencias con la Conferencia asignada al organizador, lo que significa que las reuniones programadas tienen la misma dirección URL de la combinación y la información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Pero, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.

  - Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no esté activada a menos que se necesite. Esta configuración afecta al tipo de acceso a la reunión predeterminado programado por el complemento de reunión en línea para Lync 2013 cuando no se usa una conferencia asignada. La opción apropiada para esta opción depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.

</div>

</div>

<span> </span>

</div>

</div>

</div>

