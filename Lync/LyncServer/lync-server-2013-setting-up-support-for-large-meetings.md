---
title: 'Lync Server 2013: configuración de la compatibilidad para reuniones grandes'
description: 'Lync Server 2013: configuración de la compatibilidad para reuniones grandes.'
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
ms.openlocfilehash: cb04b4192c6daa9e6ea255b52566dacee1bd2dcd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554216"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configuración de la compatibilidad para reuniones grandes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-12_

Admitir reuniones grandes de hasta 1000 usuarios requiere crear una topología apropiada, cumplir los requisitos previos de hardware y software y configurar el entorno.

<div>

## <a name="topology-requirements"></a>Requisitos de topología

Una única reunión grande requiere al menos un servidor front-end y un servidor back-end. Sin embargo, para proporcionar alta disponibilidad, recomendamos un grupo de servidores front-end con servidores back-end reflejados.

El usuario que hospeda las reuniones grandes debe tener su cuenta de usuario alojada en este grupo. Sin embargo, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Dado que la configuración de reunión grande está optimizada para el rendimiento, su uso como un usuario normal podría tener problemas como la incapacidad de promover una sesión P2P a una reunión cuando se trata de un punto final de RTC.

Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para obtener más información, vea [topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Además, si desea proporcionar una copia de seguridad y conmutación por error de recuperación ante desastres para el grupo que se usa para reuniones grandes, puede emparejarlo con un grupo de servidores dedicado de configuración similar en un centro de datos diferente. Para obtener más información, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuración del grupo de reuniones grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuración del grupo de reuniones grandes")

Las siguientes son notas adicionales sobre la topología:

  - Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el servidor de archivado está implementado y habilitado, para almacenar los archivos de archivado. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener más información sobre cómo configurar el recurso compartido de archivos, consulte [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Se necesita un servidor de Office Web Apps para habilitar la función de presentación de PowerPoint en reuniones grandes. El servidor de Office Web Apps se puede dedicar al grupo de reuniones de gran tamaño o puede ser el mismo servidor de Office Web Apps usado por otros grupos en el sitio en el que se implementa el grupo dedicado.

  - El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga del contenido de la reunión). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para obtener información detallada, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Si desea usar el servidor de supervisión para el grupo de servidores de gran tamaño dedicado, se recomienda usar el servidor de supervisión y su base de datos que se comparten en todos los grupos de servidores front-end de su implementación de Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Los requisitos de hardware para los servidores de un grupo de reuniones grande dedicado son los mismos que los de los demás servidores de Lync Server 2013. Para obtener más información sobre los requisitos de hardware, consulte "[plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Los servidores de un grupo de reuniones grande dedicado deben cumplir todos los requisitos de software de Lync Server 2013. Para obtener más información acerca de los requisitos de software, consulte la documentación siguiente:

  - [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Además, tanto Lync Server 2013 como todos los clientes de Lync Server 2013 deben tener las actualizaciones más recientes.

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuración

Es recomendable crear una nueva directiva de conferencias específica para reuniones grandes y, después, asignarla a los usuarios alojados en el grupo de reuniones grandes dedicado. Configure la directiva de conferencias mediante las siguientes opciones:

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
> El soporte para las reuniones de gran tamaño de 1000 usuarios en Lync Server 2013 requiere que el valor <STRONG>AllowLargeMeetings</STRONG> de la Directiva de conferencia para el programador de reuniones se establezca en true. Cuando esta configuración se establece en true, la experiencia de Lync se optimizará para reuniones extra grandes cuando los usuarios se unan a la reunión. Concretamente, en una reunión grande, Lync no mostrará la inicial ni la actualización de la lista de participantes de la reunión, que es un cuello de botella de rendimiento tanto para el cliente como para Lync Server 2013. En su lugar, Lync solo mostrará información sobre el usuario y la lista de moderadores de la reunión. Lync seguirá mostrando correctamente el número total de participantes disponibles en las reuniones grandes.



</div>

Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funcionalidades de conferencia que no se necesitan en reuniones grandes.

Además, debe configurar el grupo de reuniones de gran tamaño dedicado para que cada usuario de Lync Server 2013 alojado en el grupo de servidores y responsable de administrar la programación de la reunión tenga los permisos adecuados. Para ello, siga estos pasos:

  - Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no deben ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores deben designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.

  - Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento de reunión en línea para Lync 2013 siempre programa conferencias con la Conferencia asignada al organizador, lo que significa que las reuniones programadas tienen la misma dirección URL de combinación y la información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Sin embargo, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.

  - Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no está activada a menos que se necesite. Esta configuración afecta al tipo de acceso a la reunión predeterminado programado por el complemento de reunión en línea para Lync 2013 cuando no se usa una conferencia asignada. La opción apropiada para esta opción depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.

</div>

</div>

<span> </span>

</div>

</div>

</div>

