---
title: Configurar el soporte para grandes reuniones
TOCTitle: Configurar el soporte para grandes reuniones
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48275980
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el soporte para grandes reuniones

 

_**Última modificación del tema:** 2014-05-12_

Admitir reuniones grandes de hasta 1000 usuarios requiere crear una topología apropiada, cumplir los requisitos previos de hardware y software y configurar el entorno.

## Requisitos de topología

Una sola reunión grande requiere al menos un Servidor front-end y un Servidor back-end. Sin embargo, para proporcionar alta disponibilidad, recomendamos un grupo de dos Servidor front-end con Servidores back-end reflejados.

El usuario que hospeda las reuniones grandes debe tener su cuenta de usuario alojada en este grupo. Sin embargo, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Como la configuración de las reuniones grandes se optimiza para el rendimiento, al utilizarla como un usuario normal podría tener problemas como la imposibilidad de promover una sesión P2P a una reunión cuando hay un extremo PSTN involucrado.

Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para obtener más información, consulte [Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Además, si desea proporcionar la opción de recuperación ante desastres y conmutación por error para el grupo que se usa para las reuniones grandes, puede asociarlo a un grupo dedicado con una configuración similar y datos diferentes. Para obtener información, vea [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuración de grupo de servidores para reuniones grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuración de grupo de servidores para reuniones grandes")

Las siguientes son notas adicionales sobre la topología:

  - Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el Servidor de archivado está implementado y habilitado, para el archivado de los archivos. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener más información sobre cómo configurar el recurso compartido de archivos, consulte [Configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Se requiere un Servidor Office Web Apps para habilitar la funcionalidad de presentación de PowerPoint en reuniones grandes. El Servidor Office Web Apps puede dedicarse al grupo de reuniones grandes o puede ser el mismo Servidor Office Web Apps que otros grupos utilizan en el sitio donde el grupo dedicado está implementado.

  - El equilibrio de carga de los Servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga de contenido de la reunión). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para obtener más información, consulte [Requisitos del equilibrio de carga de Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Si quiere usar el Servidor de supervisión para el grupo de reuniones grandes dedicado, es recomendable usar el Servidor de supervisión y su base de datos que comparten todos los grupos del Servidor front-end en su implementación de Lync Server.

## Requisitos de hardware y software

Los requisitos de hardware de los servidores en un grupo de reuniones grandes dedicado son los mismos que en los demás servidores de Lync Server 2013. Para obtener más información acerca de los requisitos de hardware, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Los servidores de un grupo de reuniones grandes dedicado deben cumplir todos los requisitos de software de Lync Server 2013. Para obtener más información acerca de los requisitos de software, consulte la documentación siguiente:

  - [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Además, tanto Lync Server 2013 como todos los clientes Lync Server 2013 deben tener las actualizaciones más recientes.

## Requisitos de configuración

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


> [!NOTE]
> Para admitir reuniones grandes de 1000 usuarios en Lync Server 2013 es necesario que la opción <STRONG>AllowLargeMeetings</STRONG> de la directiva de conferencias para el programador de reuniones esté establecida en true. Cuando esta opción está establecida en true, la experiencia de Lync se optimizará para reuniones extra grandes cuando los usuarios se unan a dicha reunión. Concretamente, en una reunión grande, Lync no mostrará las iniciales ni actualizará la lista completa de participantes en la reunión, que constituye un cuello de botella tanto para el cliente como para Lync Server 2013. En su lugar, Lync solo mostrará información acerca del usuario y la lista de moderadores de la reunión. Lync seguirá mostrando correctamente el número total de participantes en las reuniones grandes.



Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funcionalidades de conferencia que no se necesitan en reuniones grandes.

Además, debe configurar el grupo de reuniones grandes dedicado para que cada usuario de Lync Server 2013 alojado en el grupo y responsable de administrar el programa de la reunión tenga los permisos apropiados. Para ello, siga estos pasos:

  - Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no deben ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores deben designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.

  - Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta opción controla si el Complemento para conferencia en línea para Lync 2013 programará siempre las conferencias mediante la conferencia asignada del organizador, lo que significa que las reuniones programadas tendrán la misma dirección URL de unión e información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Sin embargo, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.

  - Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no está activada a menos que se necesite. Esta opción afecta al tipo de acceso a la reunión predeterminado programado por el Complemento para conferencia en línea para Lync 2013 cuando no se utiliza una conferencia asignada. La opción apropiada para esta opción depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.

