---
title: Planeación de reuniones grandes en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumen: Lea este tema para obtener más información sobre los procedimientos recomendados para implementar y administrar reuniones grandes en Skype para Business Server.'
ms.openlocfilehash: 4ef45f5393e389a3c6a1246041d058d1e0b387f1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214375"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planeación de reuniones grandes en Skype para Business Server
 
**Resumen:** Lea este tema para obtener más información sobre los procedimientos recomendados para implementar y administrar reuniones grandes en Skype para Business Server.
  
El tamaño de las reuniones que puede admitir Skype para Business Server depende de si conferencia está hospedada en un grupo de servidores dedicado o compartido: en cualquier parte de los 250 participantes en un grupo compartido a los participantes de 1000 en un grupo dedicado. 
  
> [!NOTE]
> En este tema se centra en procedimientos recomendados para grandes reuniones compatibles con Skype para Business Server. Si la organización requiere más grandes capacidades de reunión, considere la posibilidad de implementar un entorno híbrido que aprovecha las ventajas de la difusión de reunión de Skype, un nuevo servicio en línea que forma parte de Office 365. 

> [!NOTE]
> La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes públicos en línea de hasta 10.000 participantes. El uso de la difusión de reunión de Skype requiere que Skype Empresarial Server ya esté configurado en una configuración híbrida con un inquilino de producción de Office 365. Todos los usuarios necesitan tener un inquilino en línea establecido como requisito previo. Si está interesado en la implementación de una solución híbrida que puede aprovechar las ventajas de Difundir presentación de reunión de Skype, vea [¿Qué es una reunión de Skype difusión?](https://go.microsoft.com/fwlink/?LinkId=617071) y [Configure su implementación local para difundir presentación de reunión de Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Las reuniones grandes normalmente tienen las siguientes características:
  
- El formato de la reunión es una presentación de uno a varios.
    
- Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.
    
- El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.
    
- Se necesita audio y también se puede usar vídeo.
    
- Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con suficiente antelación.
    
- El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y la sala de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.
    
Cuando un usuario programa una reunión, Skype para Business Server crea un registro en la base de datos de conferencia, que almacena datos de conferencia, pero no reserva los recursos de hardware de la reunión programada con anterioridad. En su lugar, Skype para Business Server tiene lógica para asignar dinámicamente los recursos de conferencia en servidores Front-End en un modo en que distribuye las cargas igualmente entre todos los servidores de Front-End del grupo de servidores de equilibrio de carga integrada. Esto suministra y usa los recursos de hardware de forma eficaz, pero es importante que planee adecuadamente para admitir reuniones muy grandes. 
  
Por ejemplo, cuando se ejecuta un Skype para grupo de servidores empresariales cerca de su capacidad superior, cada servidor Front-End podría hospedar aproximadamente 125 reuniones tamaño promedio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión de 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.
  
La compatibilidad con grandes reuniones de hasta 1000 participantes requiere abordar problemas relacionados con el modelo de hardware compartido y el modelo sin reservas. En general, debe planear para un grupo dedicado y seguir las prácticas recomendadas, tal como se describe en las secciones siguientes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planificar un grupo dedicado

Si su organización requiere reuniones con más de 250 participantes, necesita planificar un grupo dedicado para admitir la carga. 
  
Para tener suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end que hacen de host no tienen que hospedar ninguna otra carga de trabajo de mensajería instantánea (MI), de presencia o de telefonía IP empresarial. Los servidores tampoco tienen que hospedar otras reuniones, independientemente de su tamaño. Para hospedar reuniones de hasta 1.000 usuarios, debe configurar un Skype independiente para grupo de servidores de negocio que está dedicado al hospedaje de reuniones grandes.
  
Un Skype para profesionales de servidores que está dedicado al hospedaje de reuniones grandes debe hospedar uno y sólo una de las reuniones de hasta 1.000 usuarios al mismo tiempo, por lo que la reunión veces es necesario reservada con antelación a través de una fuera de banda proceso para asegurar la compatibilidad con dedicado de programación de la Servidores Front-End. Para admitir más de una gran reunión al mismo tiempo, tendría que configurar varios grupos de grandes reuniones dedicados.
  
Para obtener más información acerca de la planeación y los requisitos de software y hardware una topología que admite grandes reuniones, vea [requisitos de Hardware y software para conferencias en Skype para Business Server](hardware-and-software-requirements.md) y [planear su topología de conferencias para Skype para Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Aplicar procedimientos recomendados para reuniones grandes

Después de configurar un grupo de servidores dedicado para reuniones de gran tamaño, puede realizar ciertos pasos para garantizar que las reuniones grandes hospedadas en el grupo proporcionen la mejor experiencia de usuario posible. Las siguientes secciones proporcionan instrucciones para administrar reuniones grandes:
  
- Crear organizadores de reuniones dedicados
    
- Crear moderadores dedicados
    
- Mantener un calendario de grandes reuniones independiente
    
- Implementar un proceso de programación de reuniones grandes
    
- Especificar detalles de programación correspondientes
    
- Crear una directiva de conferencia para reuniones grandes
    
### <a name="create-dedicated-meeting-organizers"></a>Crear organizadores de reuniones dedicados

Para minimizar el tráfico de comunicaciones en tiempo real en el grupo de reuniones grandes, Microsoft recomienda no aloja los usuarios que iniciar sesión mediante Skype para clientes empresariales con regularidad y participan en mensajería instantánea (IM), presencia, conferencias y sesiones de voz. En cambio, realice alguna de las siguientes opciones:
  
- Crear una o más cuentas de usuarios dedicados solo para programar grandes reuniones
    
- Hospedar las cuentas de usuario del personal responsable de programar grandes reuniones en un grupo de servidores de grandes reuniones
    
### <a name="create-dedicated-moderators"></a>Crear moderadores dedicados

En las reuniones que tengan cientos o miles de usuarios, recomendamos dedicar a una persona a moderar la sesión en línea. Esta persona dedicada puede ser un delegado del organizador de la reunión o un miembro del personal de soporte técnico de reuniones grandes de la organización. Es importante que, en el momento de programar la reunión, agregue como moderador al encargado dedicado a moderar la reunión, aunque puede promocionar a un asistente a la reunión en línea al rol de moderador mientras la reunión se está celebrando.
  
El moderador de la reunión puede utilizar todas las funcionalidades de moderador de Skype para clientes empresariales para administrar la reunión de gran tamaño. Estas funciones incluyen:
  
- Supervisión de la sala de espera y admisión o rechazo de los usuarios en la sala
    
- Eliminación de los usuarios de la reunión que no tendrían que estar en ella
    
- Cambio de los tipos de acceso a la reunión
    
- Cambio de los roles de los participantes
    
- Invitar a participantes adicionales durante la reunión mediante arrastrar y colocar funcionalidad, para hacer llamadas de teléfono o correo electrónico
    
- Desactivación o activación del audio del público o de usuarios individuales
    
- Administración del contenido de la reunión, como la carga o eliminación de contenido o el cambio del contenido activo

    
### <a name="maintain-a-separate-calendar"></a>Mantener un calendario independiente

Para cada grupo de reunión grande, necesita mantener un calendario independiente de grandes reuniones programadas en ese grupo. Por ejemplo, puede particular de una única cuenta de usuario en el grupo de reuniones grandes y usar Outlook con Exchange y en el complemento de reunión en línea para Skype para la empresa para mantener un calendario independiente. Si usa varias cuentas de usuario para habilitar personal de soporte para crear grandes reuniones, puede configurar un calendario independiente que agrupe todas las reuniones grandes creadas por los miembros del personal de soporte. 
  
Mantener un calendario de reuniones independiente ayuda a evitar conflictos y garantizar que solo una reunión grande está activa en un determinado momento.
  
### <a name="implement-a-scheduling-process"></a>Implementar un proceso de programación

Debido a que se admite solo una reunión grande en un momento en el grupo de servidores de reunión grande dedicado, debe implementar un proceso para facilitar la configuración de reuniones grandes y ayudar a evitar conflictos de programación de reuniones grandes. No se proporcionan estas capacidades directamente por Skype para Business Server o Skype para clientes empresariales. Una forma de implementar dicho proceso es usar el sistema de fichas del equipo de soporte técnico de su organización, si está disponible.
  
Programar una reunión grande implica completar los siguientes pasos:
  
- El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.
    
- El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.
    
- Si se aprueba la solicitud, el personal de programación (usando las credenciales en el grupo de servidores dedicado) usa Online Meeting Add-in para Skype para la empresa con Outlook para establecer una reunión en el grupo de reuniones grandes dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.
    
- El organizador de la reunión o el delegado usará Outlook para programar la próxima reunión y agregará a la invitación la dirección URL para unirse a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar detalles de programación correspondientes

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de la gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. 
  
Para garantizar la mejor experiencia de usuario, es importante programar la reunión de gran tamaño con la configuración de reunión que es adecuados para las necesidades del organizador de la reunión y los niveles de acceso de derecho. Tenga en cuenta las opciones de programación siguientes configuradas en Skype para opciones de reunión de negocios:
  
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
    
- Compruebe el **vídeo de los asistentes de bloquear** configuración para asegurarse de que sólo los moderadores pueden difundir vídeo a la reunión.
    
### <a name="create-a-conferencing-policy"></a>Crear una directiva de conferencia

Cree una directiva de conferencias específica para reuniones grandes y, después, asígnela a los usuarios alojados en el grupo de reuniones grandes dedicado. Configure la directiva de conferencias por medio de las siguientes opciones:
  
- Establezca la opción **MaxMeetingSize** y 1000. (El valor predeterminado es 250).
    
- Establezca la opción **AllowLargeMeetings** en **True**. 
    
- Establezca la opción **EnableAppDesktopSharing** en **None**.
    
- Establezca la opción **AllowUserToScheduleMeetingsWithAppSharing** en **False**.
    
- Establezca la opción **AllowSharedNotes** en **False**.
    
- Establezca la opción **AllowAnnotations** en **False**.
    
- Establezca la opción **DisablePowerPointAnnotations** en **True**.
    
- Establezca la opción **AllowMultiview** en **False**.
    
- Establezca la opción **EnableMultiviewJoin** en **False**.
    
> [!NOTE]
> Soporte técnico de reuniones grandes en Skype para Business Server requiere que se establezca la opción **AllowLargeMeetings** en true. Cuando esta configuración se establece en true, el Skype para que la experiencia empresarial se optimizará para las reuniones extra grandes cuando los usuarios unirse a la reunión. En concreto, en una reunión grande, Skype para la empresa no mostrará la inicial o la actualización de la lista de participantes de la reunión completa, que es un cuello de botella de rendimiento para el cliente y Skype para Business Server. En su lugar, Skype para la empresa sólo mostrará información sobre el usuario y la lista de moderadores de la reunión. Skype para la empresa seguirá mostrando el número total de participantes disponibles en las reuniones grandes.

La opción - AllowLargeMeetings $true hace lo siguiente: · Oculta la lista de asistentes. · Deshabilita los errores en la ventana de mensajería instantánea.
· Deshabilita el vídeo con varios participantes.
· Deshabilita la posibilidad de promocionar a un asistente a moderador. Debe planear de antemano y declarar todos los moderadores antes de la reunión.
· Deshabilita la capacidad para reactivar el audio de asistentes individuales.
· Deshabilita la capacidad para aplicar la característica Noticias destacadas de vídeo de bloqueo a los asistentes.
· Los usuarios de acceso telefónico RTC no podrá reactivar su uso de audio * 6 porque asistencia Virtual Personal que se encarga de DTMF de comandos en reuniones grandes activas es que faltan.
· Si el organizador de moderador programa una reunión donde todos los usuarios deben estar desactivado en primer lugar ("desactivar todos los"), los usuarios de RTC se silencian a lo largo de la llamada y no podrá reactivar su audio.

Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funciones de conferencia que no se necesitan en reuniones grandes.
  
Además, debe configurar el grupo de reuniones grandes dedicado de modo que cada Skype para usuario Business Server que es responsable de administrar la programación de reuniones y hospedados en el grupo de servidores tiene los permisos adecuados. Para ello, siga estos pasos:
  
- Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no tienen que ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores necesitan designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.
    
- Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento de reunión en línea para Skype para la empresa siempre programa utilizando el organizador de conferencias asignados conferencia, lo que significa que las reuniones programadas tiene la misma dirección URL de combinación y la información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Pero, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.
    
- Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no esté activada a menos que se necesite. Esta configuración afecta el valor predeterminado de la reunión programado por el complemento de reunión en línea para Skype para la empresa cuando no se utiliza una conferencia asignado el tipo de acceso. La opción adecuada para esta configuración depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.
    
Para obtener más información acerca de cómo crear una directiva de conferencia, vea [administrar las directivas de conferencia en Skype para Business Server](../../manage/conferencing/conferencing-policies.md).
  

