---
title: Planificar reuniones grandes en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumen: Leer este tema para obtener información acerca de las prácticas recomendadas para implementar y administrar grandes reuniones en Skype para Business Server 2015.'
ms.openlocfilehash: 6a2af2ef9e7698f9141baf78f99b9bc9febfaa67
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-large-meetings-in-skype-for-business-server-2015"></a>Planificar reuniones grandes en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información acerca de las prácticas recomendadas para implementar y administrar grandes reuniones en Skype para Business Server 2015.
  
El tamaño de las reuniones que Skype para Business Server puede admitir depende si conferencia está alojada en un pool compartido o dedicado: en cualquier parte de los 250 participantes en un pool compartido a los participantes en un grupo dedicado de 1000. 
  
> [!NOTE]
> En este tema se centra en procedimientos recomendados para grandes reuniones compatibles con Skype para Business Server. Si su organización necesita mayores capacidades de reunión, considere la posibilidad de implementar un entorno híbrido que saca partido de difundir reunión de Skype, un nuevo servicio en línea que forma parte de Office 365. 

> [!NOTE]
> La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes públicos en línea de hasta 10.000 participantes. El uso de la difusión de reunión de Skype requiere que Skype Empresarial Server ya esté configurado en una configuración híbrida con un inquilino de producción de Office 365. Todos los usuarios necesitan tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que puede aprovechar las ventajas de la difusión de la reunión de Skype, consulte [¿Qué es una reunión de Skype difusión?](https://go.microsoft.com/fwlink/?LinkId=617071) y [configurar su implementación local para difundir reunión de Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Las reuniones grandes normalmente tienen las siguientes características:
  
- El formato de la reunión es una presentación de uno a varios.
    
- Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.
    
- El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.
    
- Se necesita audio y también se puede usar vídeo.
    
- Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con suficiente antelación.
    
- El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y la sala de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.
    
Cuando un usuario programa una reunión, Skype para Business Server crea un registro en la base de datos de la conferencia, que almacena los datos de la conferencia, pero no reserva los recursos de hardware de la reunión programada con anterioridad. En su lugar, Skype para Business Server tiene lógica para asignar dinámicamente recursos de conferencia en los servidores frontales de forma que distribuye las cargas por igual entre todos los servidores frontales en el grupo de equilibrio de carga integrada. Esto suministra y usa los recursos de hardware de forma eficaz, pero es importante que planee adecuadamente para admitir reuniones muy grandes. 
  
Por ejemplo, cuando se ejecuta un Skype para el grupo de servidores de negocios cerca de su capacidad superior, cada servidor Front-End puede alojar aproximadamente 125 reuniones de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión de 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.
  
La compatibilidad con grandes reuniones de hasta 1000 participantes requiere abordar problemas relacionados con el modelo de hardware compartido y el modelo sin reservas. En general, debe prever un grupo dedicado y seguir las prácticas recomendadas como se describe en las secciones siguientes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planificar un grupo dedicado

Si su organización requiere reuniones con más de 250 participantes, necesita planificar un grupo dedicado para admitir la carga. 
  
Para tener suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end que hacen de host no tienen que hospedar ninguna otra carga de trabajo de mensajería instantánea (MI), de presencia o de telefonía IP empresarial. Los servidores tampoco tienen que hospedar otras reuniones, independientemente de su tamaño. Para organizar reuniones de hasta 1000 usuarios, debe configurar un Skype independiente para grupo Business Server dedicado para alojar grandes reuniones.
  
Un Skype para grupo Business Server dedicado para alojar grandes reuniones debe alojar una y sólo una de las reuniones de hasta 1.000 usuarios al mismo tiempo, tan horas de reunión deben ser reservados por adelantado mediante un fuera de banda proceso para garantizar el soporte dedicado de programación desde el Servidores Front-End. Para admitir más de una gran reunión al mismo tiempo, tendría que configurar varios grupos de grandes reuniones dedicados.
  
Para obtener más información acerca de hardware y los requisitos de software y la planificación de una topología que admite grandes reuniones, vea [requisitos de Hardware y software para conferencias en Skype para Business Server 2015](hardware-and-software-requirements.md) y [Planear la topología de las conferencias para Skype para Business Server 2015](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Aplicar procedimientos recomendados para reuniones grandes

Después de configurar un grupo de servidores dedicado para reuniones de gran tamaño, puede realizar ciertos pasos para garantizar que las reuniones grandes hospedadas en el grupo proporcionen la mejor experiencia de usuario posible. Las siguientes secciones proporcionan instrucciones para administrar reuniones grandes:
  
- Crear organizadores de reuniones dedicados
    
- Crear moderadores dedicados
    
- Mantener un calendario de grandes reuniones independiente
    
- Implementar un proceso de programación de reuniones grandes
    
- Especificar detalles de programación correspondientes
    
- Crear una directiva de conferencia para reuniones grandes
    
### <a name="create-dedicated-meeting-organizers"></a>Crear organizadores de reuniones dedicados

Para minimizar el tráfico de comunicaciones en tiempo real en el grupo de grandes reuniones, Microsoft no recomienda albergar usuarios que iniciar sesión con Skype para clientes empresariales con regularidad y participan en la mensajería instantánea (IM), presencia, conferencias y sesiones de voz. En cambio, realice alguna de las siguientes opciones:
  
- Crear una o más cuentas de usuarios dedicados solo para programar grandes reuniones
    
- Hospedar las cuentas de usuario del personal responsable de programar grandes reuniones en un grupo de servidores de grandes reuniones
    
### <a name="create-dedicated-moderators"></a>Crear moderadores dedicados

En las reuniones que tengan cientos o miles de usuarios, recomendamos dedicar a una persona a moderar la sesión en línea. Esta persona dedicada puede ser un delegado del organizador de la reunión o un miembro grande de la reunión de la organización personal de soporte. Es importante que, en el momento de programar la reunión, agregue como moderador al encargado dedicado a moderar la reunión, aunque puede promocionar a un asistente a la reunión en línea al rol de moderador mientras la reunión se está celebrando.
  
El moderador de la reunión puede utilizar todas las funcionalidades de moderador de Skype para clientes de empresa para administrar la reunión grande. Estas funciones incluyen:
  
- Supervisión de la sala de espera y admisión o rechazo de los usuarios en la sala
    
- Eliminación de los usuarios de la reunión que no tendrían que estar en ella
    
- Cambio de los tipos de acceso a la reunión
    
- Cambio de los roles de los participantes
    
- Invitación a participantes adicionales durante la reunión con la función de arrastrar y colocar de Lync, llamadas salientes telefónicas o el correo electrónico
    
- Desactivación o activación del audio del público o de usuarios individuales
    
- Administración del contenido de la reunión, como la carga o eliminación de contenido o el cambio del contenido activo
    
### <a name="maintain-a-separate-calendar"></a>Mantener un calendario independiente

Para cada grupo de reunión grande, necesita mantener un calendario independiente de grandes reuniones programadas en ese grupo. Por ejemplo, puede inicio una única cuenta de usuario en el grupo de grandes reuniones y utilizar Outlook con Exchange y el complemento de reunión en línea de Skype para empresas para mantener un calendario distinto. Si usa varias cuentas de usuario para habilitar personal de soporte para crear grandes reuniones, puede configurar un calendario independiente que agrupe todas las reuniones grandes creadas por los miembros del personal de soporte. 
  
Mantener un calendario de reuniones independiente ayuda a evitar conflictos y garantizar que solo una reunión grande está activa en un determinado momento.
  
### <a name="implement-a-scheduling-process"></a>Implementar un proceso de programación

Como sólo una reunión con muchos asistentes a la vez es compatible con el grupo grande dedicado de la reunión, debe implementar una reunión con muchos asistentes proceso para facilitar la configuración de grandes reuniones y ayudar a evitar conflictos de programación. Estas capacidades no se proporcionan directamente por Skype para Business Server o Skype para clientes empresariales. Una forma de implementar dicho proceso es utilizar el sistema de fichas del equipo de soporte técnico de su organización, si está disponible.
  
Programar una reunión grande implica completar los siguientes pasos:
  
- El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.
    
- El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.
    
- Si se aprueba la solicitud, el personal de programación (utilizando las credenciales en el grupo dedicado) utiliza el complemento reunión en línea de Skype para empresas con Outlook a convocar una reunión, en el grupo de grandes reuniones dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.
    
- El organizador de la reunión o el delegado usará Outlook para programar la próxima reunión y agregará a la invitación la dirección URL para unirse a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar detalles de programación correspondientes

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de la gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. 
  
Para garantizar la mejor experiencia de usuario, es importante programar las reuniones con los niveles de derecho de acceso y opciones de reunión que sean adecuadas a las necesidades del organizador de la reunión. Tenga en cuenta la siguiente programación configuración de Skype para opciones de reunión de negocios:
  
- Use un nuevo espacio de reunión para cada reunión grande en lugar de volver a usar el espacio de reunión dedicado. 
    
- Especifique el nivel de acceso de reunión de la siguiente manera:
    
  - Si al menos un invitado es externo a la organización, establezca el tipo de acceso de reunión en **Cualquiera (sin restricciones)**. Esto le habilita para evitar tener que administrar una sala de espera potencialmente grande cuando la reunión está en curso.
    
  - Si la reunión es solo interna, establezca el tipo de acceso de reunión en **Cualquiera de mi organización**.
    
    > [!NOTE]
    > Evite establecer el tipo de acceso de reunión en **Personas de mi compañía a quien invito** porque cuando usa esta configuración, los organizadores necesitan agregar todas las direcciones de correo electrónico de usuario a la lista de invitados y no puede invitar a un grupo de distribución. Evite establecer el tipo de acceso de reunión en **Solo yo, el organizador de la reunión** porque esta configuración requiere que todos los participantes de la reunión, incluidos los moderadores, tengan que colocarse en la sala de espera en el tiempo de ejecución de la reunión. La persona responsable de la ejecución de la reunión grande necesita supervisar entonces constantemente la lista de la sala de espera y admitir a nuevos usuarios que estén en la sala de espera.
  
- Permita a los usuarios que marquen desde teléfonos para entrar en la reunión automáticamente activando la configuración **Los autores de llamada entran directamente**.
    
- Invitar de manera explícita a los siguientes usuarios:
    
  - Delegado y organizador de reunión (solicitante)
    
  - La lista de moderadores proporcionada por un solicitante de reunión
    
    > [!NOTE]
    > Si el tipo de acceso de reunión se establece en **Las personas que yo elija**, tiene que agregar de manera explícita a cada participante de una reunión grande como invitado de la reunión. 
  
- Administrar de manera explícita moderadores, en lugar de establecer la opción de moderador a uno de los valores de promoción automática. Asegúrese de agregar los siguientes usuarios como moderadores:
    
  - Delegado y organizador de reunión (solicitante)
    
  - La lista de moderadores proporcionada por solicitantes de grandes reuniones
    
    Al administrar de manera explícita moderadores, puede limitar moderadores a una cantidad lo suficientemente pequeña como para hacer posible tener una reunión grande efectiva. Si la mayoría de los participantes de la reunión tienen el rol de asistente, ayuda a reducir la posibilidad de que las personas tomen el control de la presentación, eliminen una presentación de PowerPoint, pongan o quiten el silencio de los moderadores de manera accidental, y otras interrupciones de la reunión. 
    
- Active la configuración **Silenciar a todos los asistentes** para asegurarse de que solo los moderadores pueden difundir audio a la reunión.
    
- Compruebe el **vídeo de los asistentes de bloquear** configuración para asegurarse de que sólo los moderadores pueden difusión de vídeo en la reunión.
    
### <a name="create-a-conferencing-policy"></a>Crear una directiva de conferencia

Cree una directiva de conferencias específica para reuniones grandes y, después, asígnela a los usuarios alojados en el grupo de reuniones grandes dedicado. Configure la directiva de conferencias por medio de las siguientes opciones:
  
- Defina la opción **MaxMeetingSize** en 1000. (El valor predeterminado es 250).
    
- Establezca la opción **AllowLargeMeetings** en **True**. 
    
- Establezca la opción **EnableAppDesktopSharing** en **None**.
    
- Establezca la opción **AllowUserToScheduleMeetingsWithAppSharing** en **False**.
    
- Establezca la opción **AllowSharedNotes** en **False**.
    
- Establezca la opción **AllowAnnotations** en **False**.
    
- Establezca la opción **DisablePowerPointAnnotations** en **True**.
    
- Establezca la opción **AllowMultiview** en **False**.
    
- Establezca la opción **EnableMultiviewJoin** en **False**.
    
> [!NOTE]
> Soporte técnico de grandes reuniones en Skype para Business Server requiere que se establezca el valor de **AllowLargeMeetings** en true. Cuando esta opción está establecida en true, el Skype para experiencia empresarial se optimizará para reuniones extra grandes cuando los usuarios unirse a la reunión. En concreto, en una reunión con muchos asistentes, Skype para empresas no mostrará la inicial o la actualización de la lista de participantes de una reunión completa, que es un cuello de botella de rendimiento para el cliente y Skype para Business Server. En su lugar, Skype para empresas sólo mostrará información acerca del usuario y la lista de los presentadores de la reunión. Skype para empresas seguirá mostrando el número total de participantes disponibles en las grandes reuniones.
  
Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funciones de conferencia que no se necesitan en reuniones grandes.
  
Además, debe configurar el grupo de grandes reuniones dedicado para que cada Skype para usuario Business Server que es responsable de administrar la programación de reuniones y alojados en el grupo tiene los permisos apropiados. Para ello, siga estos pasos:
  
- Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no tienen que ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores necesitan designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.
    
- Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento de reunión en línea para Skype para el negocio siempre programa utilizando el organizador de conferencias asignado conferencia, lo que significa que las reuniones programadas tiene la misma dirección URL de la combinación y la información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Pero, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.
    
- Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no esté activada a menos que se necesite. Esta configuración afecta el valor predeterminado de reuniones programado por el complemento de reunión en línea de Skype para empresas cuando no se utiliza una conferencia asignada el tipo de acceso. La opción adecuada para este parámetro depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.
    
Para obtener más información acerca de cómo crear una directiva de la conferencia, vea [Administrar directivas de conferencia en Skype para Business Server 2015](../../manage/conferencing/conferencing-policies.md).
  

