---
title: Planear reuniones grandes en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumen: Lea este tema para obtener información sobre los procedimientos recomendados para implementar y administrar grandes reuniones en Skype empresarial Server.'
ms.openlocfilehash: 0ed044a811d4a482690be13c8626f93089aa24a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277324"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planear reuniones grandes en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre los procedimientos recomendados para implementar y administrar grandes reuniones en Skype empresarial Server.
  
El tamaño de las reuniones que puede admitir Skype empresarial Server depende de si las conferencias se hospedan en un grupo compartido o dedicado: desde 250 participantes en un grupo compartido hasta 1000 participantes en un grupo dedicado. 
  
> [!NOTE]
> Este tema se centra en los procedimientos recomendados para las reuniones grandes compatibles con Skype empresarial Server. Si su organización requiere capacidades de reunión mayores, considere la posibilidad de implementar un entorno híbrido que aproveche las ventajas de la difusión de reunión de Skype, un nuevo servicio en línea que forma parte de Office 365. 

> [!NOTE]
> La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes públicos en línea de hasta 10.000 participantes. El uso de la difusión de reunión de Skype requiere que Skype Empresarial Server ya esté configurado en una configuración híbrida con un inquilino de producción de Office 365. Todos los usuarios necesitan tener un inquilino en línea establecido como requisito previo. Si le interesa implementar una solución híbrida que pueda aprovechar la difusión de reunión de Skype, vea [¿Qué es una difusión de reunión de Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) y [configurar la implementación local para la difusión de reunión de Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Las reuniones grandes normalmente tienen las siguientes características:
  
- El formato de la reunión es una presentación de uno a varios.
    
- Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.
    
- El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.
    
- Se necesita audio y también se puede usar vídeo.
    
- Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con suficiente antelación.
    
- El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y la sala de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.
    
Cuando un usuario programa una reunión, Skype empresarial Server crea un registro en la base de datos de conferencia, que almacena los datos de conferencia, pero no reserva de antemano ningún recurso de hardware para la reunión programada. En su lugar, Skype empresarial Server tiene una lógica de equilibrio de carga integrada para asignar dinámicamente los recursos de conferencia en los servidores de aplicaciones para el usuario de modo que se distribuyan uniformemente en todos los servidores front-end del grupo. Esto suministra y usa los recursos de hardware de forma eficaz, pero es importante que planee adecuadamente para admitir reuniones muy grandes. 
  
Por ejemplo, cuando un grupo de servidores de Skype empresarial se ejecuta cerca de su capacidad máxima, cada servidor front-end podría hospedar aproximadamente 125 reuniones de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión de 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.
  
La compatibilidad con grandes reuniones de hasta 1000 participantes requiere abordar problemas relacionados con el modelo de hardware compartido y el modelo sin reservas. En general, debe planear un grupo dedicado y seguir los procedimientos recomendados, como se describe en las secciones siguientes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planificar un grupo dedicado

Si su organización requiere reuniones con más de 250 participantes, necesita planificar un grupo dedicado para admitir la carga. 
  
Para tener suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end que hacen de host no tienen que hospedar ninguna otra carga de trabajo de mensajería instantánea (MI), de presencia o de telefonía IP empresarial. Los servidores tampoco tienen que hospedar otras reuniones, independientemente de su tamaño. Para hospedar reuniones de hasta 1000 usuarios, debe configurar un grupo de servidores de Skype empresarial independiente dedicado a hospedar reuniones grandes.
  
Un grupo de servidores de Skype empresarial dedicado a hospedar reuniones grandes debe hospedar una y solo una reunión de hasta 1000 usuarios al mismo tiempo, de modo que es necesario reservar de antemano las horas de reunión a través de un proceso de programación fuera de banda para garantizar la compatibilidad exclusiva de la Servidores front-end. Para admitir más de una gran reunión al mismo tiempo, tendría que configurar varios grupos de grandes reuniones dedicados.
  
Para obtener más información sobre los requisitos de hardware y software, y para planear una topología que admita reuniones grandes, consulte [requisitos de hardware y software para conferencias en Skype empresarial Server](hardware-and-software-requirements.md) y [planear la topología de conferencias para Skype empresarial Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Aplicar procedimientos recomendados para reuniones grandes

Después de configurar un grupo de servidores dedicado para reuniones de gran tamaño, puede realizar ciertos pasos para garantizar que las reuniones grandes hospedadas en el grupo proporcionen la mejor experiencia de usuario posible. Las siguientes secciones proporcionan instrucciones para administrar reuniones grandes:
  
- Crear organizadores de reuniones dedicados
    
- Crear moderadores dedicados
    
- Mantener un calendario de grandes reuniones independiente
    
- Implementar un proceso de programación de reuniones grandes
    
- Especificar detalles de programación correspondientes
    
- Crear una directiva de conferencia para reuniones grandes
    
### <a name="create-dedicated-meeting-organizers"></a>Crear organizadores de reuniones dedicados

Para minimizar el tráfico de comunicaciones en tiempo real en el grupo de reuniones de gran tamaño, Microsoft no recomienda el alojamiento de usuarios que inicien sesión regularmente con clientes de Skype empresarial y participen en sesiones de mensajería instantánea (mi), presencia, Conferencia y voz. En cambio, realice alguna de las siguientes opciones:
  
- Crear una o más cuentas de usuarios dedicados solo para programar grandes reuniones
    
- Hospedar las cuentas de usuario del personal responsable de programar grandes reuniones en un grupo de servidores de grandes reuniones
    
### <a name="create-dedicated-moderators"></a>Crear moderadores dedicados

En las reuniones que tengan cientos o miles de usuarios, recomendamos dedicar a una persona a moderar la sesión en línea. Esta persona dedicada puede ser un delegado del organizador de la reunión o un miembro del personal de soporte técnico de las grandes reuniones de la organización. Es importante que, en el momento de programar la reunión, agregue como moderador al encargado dedicado a moderar la reunión, aunque puede promocionar a un asistente a la reunión en línea al rol de moderador mientras la reunión se está celebrando.
  
El moderador de la reunión puede usar todas las funciones del moderador de los clientes de Skype empresarial para administrar la reunión de gran tamaño. Estas funciones incluyen:
  
- Supervisión de la sala de espera y admisión o rechazo de los usuarios en la sala
    
- Eliminación de los usuarios de la reunión que no tendrían que estar en ella
    
- Cambio de los tipos de acceso a la reunión
    
- Cambio de los roles de los participantes
    
- Invitar a participantes adicionales durante la reunión con la funcionalidad de arrastrar y colocar, el marcado telefónico o el correo electrónico
    
- Desactivación o activación del audio del público o de usuarios individuales
    
- Administración del contenido de la reunión, como la carga o eliminación de contenido o el cambio del contenido activo

    
### <a name="maintain-a-separate-calendar"></a>Mantener un calendario independiente

Para cada grupo de reunión grande, necesita mantener un calendario independiente de grandes reuniones programadas en ese grupo. Por ejemplo, puede alojar una sola cuenta de usuario en el grupo de reuniones de gran tamaño y usar Outlook con Exchange y el complemento de reunión en línea para Skype empresarial para mantener un calendario independiente. Si usa varias cuentas de usuario para habilitar personal de soporte para crear grandes reuniones, puede configurar un calendario independiente que agrupe todas las reuniones grandes creadas por los miembros del personal de soporte. 
  
Mantener un calendario de reuniones independiente ayuda a evitar conflictos y garantizar que solo una reunión grande está activa en un determinado momento.
  
### <a name="implement-a-scheduling-process"></a>Implementar un proceso de programación

Puesto que solo se admite una reunión de gran tamaño a la vez en el grupo dedicado de reuniones grandes, debe implementar un proceso de programación de reuniones de gran tamaño para facilitar la configuración de reuniones de gran tamaño y ayudar a evitar conflictos. Dicha capacidad no es proporcionada directamente por Skype empresarial Server ni por clientes de Skype empresarial. Una forma de implementar este proceso es usar el sistema de vales del equipo de soporte técnico de su organización, si está disponible.
  
Programar una reunión grande implica completar los siguientes pasos:
  
- El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.
    
- El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.
    
- Si se aprueba la solicitud, el personal de programación (que usa las credenciales en el grupo dedicado) usa el complemento de reuniones en línea para Skype empresarial con Outlook para configurar una reunión en el gran grupo de reuniones dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.
    
- El organizador de la reunión o el delegado usará Outlook para programar la próxima reunión y agregará a la invitación la dirección URL para unirse a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar detalles de programación correspondientes

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de la gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. 
  
Para garantizar la mejor experiencia del usuario, es importante programar la reunión de gran tamaño con los niveles de acceso y la configuración de reunión adecuados para las necesidades del organizador de la reunión. Considere las siguientes opciones de programación configuradas en las opciones de reunión de Skype empresarial:
  
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
    
- Active la configuración de **vídeo bloquear asistentes** para asegurarse de que solo los moderadores puedan difundir vídeo a la reunión.
    
### <a name="create-a-conferencing-policy"></a>Crear una directiva de conferencia

Cree una directiva de conferencias específica para reuniones grandes y, después, asígnela a los usuarios alojados en el grupo de reuniones grandes dedicado. Configure la directiva de conferencias por medio de las siguientes opciones:
  
- Establezca la opción **MaxMeetingSize** en 1000. (El valor predeterminado es 250).
    
- Establezca la opción **AllowLargeMeetings** en **True**. 
    
- Establezca la opción **EnableAppDesktopSharing** en **None**.
    
- Establezca la opción **AllowUserToScheduleMeetingsWithAppSharing** en **False**.
    
- Establezca la opción **AllowSharedNotes** en **False**.
    
- Establezca la opción **AllowAnnotations** en **False**.
    
- Establezca la opción **DisablePowerPointAnnotations** en **True**.
    
- Establezca la opción **AllowMultiview** en **False**.
    
- Establezca la opción **EnableMultiviewJoin** en **False**.
    
> [!NOTE]
> La compatibilidad con las reuniones de gran tamaño en Skype empresarial Server requiere que el valor de **AllowLargeMeetings** se establezca en true. Cuando esta configuración se establece en true, la experiencia de Skype empresarial se optimizará para las reuniones de mayor tamaño cuando los usuarios se unan a la reunión. Específicamente, en una reunión grande, Skype empresarial no mostrará el inicio ni la actualización de la lista completa de participantes de la reunión, lo cual es un cuello de botella de rendimiento tanto para el cliente como para Skype empresarial Server. En su lugar, Skype empresarial solo mostrará información sobre el usuario y la lista de moderadores de la reunión. Skype empresarial aún mostrará la cantidad total de participantes disponibles en las reuniones grandes.

El parámetro-AllowLargeMeetings $true causa lo siguiente: · Oculta la lista de asistentes. · Deshabilita los errores en la ventana de mi.
· Deshabilita el vídeo de varias partes.
· Deshabilita la posibilidad de promocionar un asistente al moderador. Debe planificar por adelantado y declarar a todos los moderadores antes de la reunión.
· Deshabilita la posibilidad de reactivar el audio de los asistentes individuales.
· Deshabilita la posibilidad de aplicar la característica bloquear foco de vídeo a los asistentes.
· Los usuarios con acceso telefónico a través de la red RTC no podrán reactivarse mediante * 6 porque falta la asistencia personal virtual responsable de los comandos DTMF en las reuniones grandes activas.
· Si el moderador o organizador programa una reunión en la que todos se deben silenciar en primer lugar ("silenciar a todos"), los usuarios de la RTC se silenciarán durante la llamada y no podrán reactivarse.

Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funciones de conferencia que no se necesitan en reuniones grandes.
  
Además, debe configurar el grupo de reuniones de gran tamaño dedicado para que todos los usuarios de Skype empresarial Server alojados en el grupo y responsables de administrar la programación de la reunión tengan los permisos adecuados. Para ello, siga estos pasos:
  
- Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no tienen que ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores necesitan designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.
    
- Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento de la reunión en línea para Skype empresarial siempre programa conferencias con la Conferencia asignada al organizador, lo que significa que las reuniones programadas tienen la misma dirección URL de la combinación y la información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Pero, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.
    
- Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no esté activada a menos que se necesite. Esta configuración afecta al tipo de acceso a la reunión predeterminado programado por el complemento de reuniones en línea para Skype empresarial cuando no se usa una conferencia asignada. La opción adecuada para esta configuración depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.
    
Para obtener más información sobre la creación de una directiva de conferencia, consulte [Administrar directivas de conferencia en Skype empresarial Server](../../manage/conferencing/conferencing-policies.md).
  

