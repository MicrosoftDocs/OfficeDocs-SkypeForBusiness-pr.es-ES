---
title: Planear reuniones grandes en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumen: lea este tema para obtener información sobre los procedimientos recomendados para implementar y administrar reuniones grandes en Skype Empresarial Server.'
ms.openlocfilehash: 97d2f501c4ebf203e03b2229af4469c89d827f4ef9e74de6360982c782ba83e0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331142"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planear reuniones grandes en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre los procedimientos recomendados para implementar y administrar reuniones grandes en Skype Empresarial Server.
  
El tamaño de las reuniones que Skype Empresarial Server puede admitir depende de si las conferencias se hospedan en un grupo compartido o dedicado: desde 250 participantes en un grupo compartido hasta 1000 participantes en un grupo dedicado. 
  
> [!NOTE]
> Este tema se centra en los procedimientos recomendados para reuniones grandes admitidas por Skype Empresarial Server. Si su organización requiere capacidades de reunión más grandes, debe considerar la posibilidad de implementar un entorno híbrido que aproveche la difusión de reuniones de Skype, un nuevo servicio en línea que forma parte de Microsoft 365 y Office 365. 

> [!NOTE]
> Skype Difusión de reuniones permite a los usuarios hospedar y difundir reuniones a grandes audiencias en línea de hasta 10 000 participantes. El uso de Skype de reunión requiere que Skype Empresarial Server esté configurado en una configuración híbrida con una organización Microsoft 365 o Office 365 de producción. Todos los usuarios deben tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que pueda aprovechar la difusión de reunión de Skype, vea ¿Qué es una difusión de reunión de [Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) y Configure [your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md). 
  
Las reuniones grandes suelen tener las siguientes características:
  
- El formato de la reunión es una presentación de uno a varios.
    
- Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.
    
- El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.
    
- Se necesita audio y también se puede usar vídeo.
    
- Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con antelación.
    
- El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y el salón de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.
    
Cuando un usuario programa una reunión, Skype Empresarial Server crea un registro en la base de datos de conferencias, que almacena datos de conferencia, pero no reserva recursos de hardware para la reunión programada con antelación. En su lugar, Skype Empresarial Server tiene lógica de equilibrio de carga integrada para asignar dinámicamente recursos de conferencia en servidores front-end de forma que distribuya las cargas por igual en todos los servidores front-end del grupo. Esto aprovisiona y usa recursos de hardware de forma eficaz, pero es importante que planee adecuadamente admitir reuniones muy grandes. 
  
Por ejemplo, cuando un grupo Skype Empresarial Server se ejecuta cerca de su capacidad superior, cada servidor front-end puede hospedar aproximadamente 125 reuniones de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión para 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.
  
Admitir reuniones grandes de hasta 1000 participantes requiere abordar los problemas relacionados con el modelo de hardware compartido y el modelo sin reserva. En general, debe planear un grupo dedicado y seguir los procedimientos recomendados como se describe en las secciones siguientes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planear un grupo dedicado

Si su organización requiere reuniones con más de 250 participantes, debe planear un grupo dedicado para admitir la carga. 
  
Para tener suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end de hospedaje no deben hospedar ninguna otra mensajería instantánea (MI) y cargas de trabajo de presencia o Telefonía IP empresarial cliente. Los servidores tampoco deben hospedar otras reuniones, independientemente del tamaño de las demás reuniones. Para hospedar reuniones de hasta 1000 usuarios, debe configurar un grupo de servidores independiente Skype Empresarial Server dedicado a hospedar reuniones grandes.
  
Un grupo de Skype Empresarial Server dedicado a hospedar reuniones grandes debe hospedar una y solo una reunión de hasta 1000 usuarios al mismo tiempo, por lo que las horas de reunión deben reservarse por adelantado mediante un proceso de programación fuera de banda para garantizar la compatibilidad dedicada de los servidores front-end. Para admitir más de una reunión grande al mismo tiempo, debe configurar varios grupos de reuniones grandes dedicados.
  
Para obtener más información acerca de los requisitos de hardware y software, y planear una topología que admita reuniones grandes, vea [Requisitos](hardware-and-software-requirements.md) de hardware y software para conferencias en Skype Empresarial Server y Planear la topología de conferencia para [Skype Empresarial Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementar procedimientos recomendados para reuniones grandes

Después de configurar un grupo dedicado para reuniones grandes, puede tomar medidas para garantizar que las reuniones grandes hospedadas en el grupo proporcionen la mejor experiencia de usuario. En las secciones siguientes se proporcionan directrices para administrar reuniones grandes:
  
- Crear organizadores de reuniones dedicados
    
- Crear moderadores dedicados
    
- Mantener un calendario independiente de reuniones grandes
    
- Implementar un proceso de programación de reuniones grandes
    
- Especificar los detalles de programación adecuados
    
- Crear una directiva de conferencia para reuniones grandes
    
### <a name="create-dedicated-meeting-organizers"></a>Crear organizadores de reuniones dedicados

Para minimizar el tráfico de comunicaciones en tiempo real en el grupo de reuniones grandes, Microsoft no recomienda hospedar usuarios que inician sesión con regularidad con clientes de Skype Empresarial y participan en mensajería instantánea (MI), presencia, conferencias y sesiones de voz. En su lugar, realice una de las siguientes acciones:
  
- Crear una o más cuentas de usuario dedicadas solo para programar reuniones grandes
    
- Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool
    
### <a name="create-dedicated-moderators"></a>Crear moderadores dedicados

Con varios cientos o miles de usuarios en una reunión, es una buena práctica que una persona dedicada modere la sesión en línea de una reunión grande. Esta persona dedicada puede ser un delegado del organizador de la reunión o un miembro del personal de soporte técnico de reuniones grandes de la organización. Es importante que, en el momento de programar la reunión, agregue como moderador al encargado dedicado a moderar la reunión, aunque puede promocionar a un asistente a la reunión en línea al rol de moderador mientras la reunión se está celebrando.
  
El moderador de la reunión puede usar todas las funcionalidades de moderador de Skype Empresarial clientes para administrar la reunión grande. Estas funcionalidades incluyen:
  
- Supervisar la sala de espera y admitir o rechazar usuarios en la sala de espera
    
- Quitar a los usuarios de la reunión que no deberían estar en la reunión
    
- Cambio de tipos de acceso a reuniones
    
- Cambio de roles de participante
    
- Invitar a participantes adicionales durante la reunión mediante la funcionalidad de arrastrar y colocar, llamar por teléfono o correo electrónico
    
- Silenciar y desmutar la audiencia o usuarios individuales
    
- Administración del contenido de la reunión, incluida la carga de contenido, la eliminación de contenido y el cambio de contenido activo

    
### <a name="maintain-a-separate-calendar"></a>Mantener un calendario independiente

Para cada grupo de reuniones grandes, debe mantener un calendario independiente de reuniones grandes programadas en ese grupo. Por ejemplo, puede hospedar una sola cuenta de usuario en el grupo de reuniones grandes y usar Outlook con Exchange y complemento de reunión en línea para Skype Empresarial mantener un calendario independiente. Si usa varias cuentas de usuario para habilitar personal de ayuda para crear grandes reuniones, puede configurar un calendario independiente que agrupe todas las reuniones grandes creadas por los miembros del personal de ayuda. 
  
Mantener un calendario de reuniones independiente ayuda a evitar conflictos y garantizar que solo una reunión grande está activa en un determinado momento.
  
### <a name="implement-a-scheduling-process"></a>Implementar un proceso de programación

Dado que solo se admite una reunión grande a la vez en el grupo de reuniones grande dedicado, debe implementar un gran proceso de programación de reuniones para facilitar la configuración de reuniones grandes y ayudar a evitar conflictos. Esta funcionalidad no se proporciona directamente por parte de Skype Empresarial Server o Skype Empresarial cliente. Una forma de implementar este proceso es usar el sistema de vales del equipo de soporte técnico de la organización, si está disponible.
  
La programación de una reunión grande implica completar los pasos siguientes:
  
- El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.
    
- El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.
    
- Si se aprueba la solicitud, el personal de programación (con credenciales en el grupo dedicado) usa el complemento de reunión en línea para Skype Empresarial con Outlook para configurar una reunión en el grupo de reuniones grandes dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.
    
- El organizador o delegado de la reunión Outlook para programar la próxima reunión, agregando la dirección URL para unirse a la reunión a la invitación a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar los detalles de programación adecuados

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. 
  
Para garantizar la mejor experiencia del usuario, es importante programar la reunión grande con los niveles de acceso adecuados y la configuración de la reunión adecuada para las necesidades del organizador de la reunión. Tenga en cuenta las siguientes opciones de programación configuradas Skype Empresarial opciones de reunión:
  
- Use un nuevo espacio de reunión para cada reunión grande en lugar de volver a usar el espacio de reunión dedicado. 
    
- Especifique el nivel de acceso de reunión de la siguiente manera:
    
  - Si al menos un invitado es externo a la organización, establezca el tipo de acceso a la reunión en **Cualquiera (sin restricciones).** Esto le habilita para evitar tener que administrar una sala de espera potencialmente grande cuando la reunión está en curso.
    
  - Si la reunión es solo interna, establezca el tipo de acceso de reunión en **Cualquiera de mi organización**.
    
    > [!NOTE]
    > Evite establecer el tipo de acceso de reunión en **Personas de mi compañía a quien invito** porque cuando usa esta configuración, los organizadores deben agregar todas las direcciones de correo electrónico de usuario a la lista de invitados y no puede invitar a un grupo de distribución. Evite establecer el tipo de acceso de reunión en **Solo yo, el organizador de la reunión** porque esta configuración requiere que todos los participantes de las reuniones, incluidos los moderadores, deben colocarse en la sala de espera en el tiempo de ejecución de la reunión. La persona responsable de la ejecución de la reunión grande debe supervisar entonces constantemente la lista de la sala de espera y admitir a nuevos usuarios que estén en la sala de espera.
  
- Permita a los usuarios que marquen desde teléfonos que entren en la reunión automáticamente activando la configuración para que los **autores de llamada entren directamente**.
    
- Invitar de manera explícita a los siguientes usuarios:
    
  - Delegado y organizador de reunión (solicitante)
    
  - La lista de moderadores proporcionada por un solicitante de reunión
    
    > [!NOTE]
    > Si el tipo de acceso de reunión se establece en **Las personas que yo elija**, tiene que agregar de manera explícita a cada participante de una reunión grande como invitado de la reunión. 
  
- Administrar de manera explícita moderadores, en lugar de establecer la opción de moderador a uno de los valores de promoción automática. Asegúrese de agregar los siguientes usuarios como moderadores:
    
  - Delegado y organizador de reunión (solicitante)
    
  - La lista de moderadores proporcionada por solicitantes de grandes reuniones
    
    Al administrar explícitamente los presentadores, puede limitar los presentadores a un número lo suficientemente pequeño como para que sea posible tener una reunión de gran tamaño eficaz. Si la mayoría de los participantes de la reunión tienen el rol de asistente, ayuda a reducir la oportunidad de que las personas tomen de manera accidental el control de la presentación, la eliminación de una presentación de PowerPoint, poner/quitar el silencio de los moderadores, y otras interrupciones de la reunión. 
    
- Active la configuración de **silenciar a todos los asistentes** para asegurarse de que solo los moderadores pueden difundir audio a la reunión.
    
- Compruebe la configuración bloquear el vídeo de los **asistentes** para asegurarse de que solo los presentadores pueden difundir vídeo en la reunión.
    
### <a name="create-a-conferencing-policy"></a>Crear una directiva de conferencia

Cree una nueva directiva de conferencia específicamente para reuniones grandes y, a continuación, asigne la directiva de conferencia a los usuarios que se encuentran en el grupo de reuniones grandes dedicado. Configure la directiva de conferencias mediante las siguientes opciones:
  
- Establezca la **opción MaxMeetingSize** en 1000. (El valor predeterminado es 250).
    
- Establezca la opción **AllowLargeMeetings** en **True**. 
    
- Establezca la opción **EnableAppDesktopSharing** en **None**.
    
- Establezca la opción **AllowUserToScheduleMeetingsWithAppSharing** en **False**.
    
- Establezca la opción **AllowSharedNotes** en **False**.
    
- Establezca la opción **AllowAnnotations** en **False**.
    
- Establezca la opción **DisablePowerPointAnnotations** en **True**.
    
- Establezca la opción **AllowMultiview** en **False**.
    
- Establezca la opción **EnableMultiviewJoin** en **False**.
    
> [!NOTE]
> La compatibilidad con reuniones grandes en Skype Empresarial Server requiere que la configuración **AllowLargeMeetings** se establezca en true. Cuando esta configuración se establece en true, la experiencia Skype Empresarial se optimizará para reuniones de gran tamaño cuando los usuarios se unan a la reunión. Específicamente, en una reunión grande, Skype Empresarial no mostrará la inicial o la actualización de la lista completa de participantes de la reunión, lo que es un cuello de botella de rendimiento tanto para el cliente como para Skype Empresarial Server. En su Skype Empresarial solo se mostrará información sobre el usuario y la lista de presentadores de la reunión. Skype Empresarial mostrará el número total de participantes disponibles en las reuniones grandes.

La **configuración allowLargeMeetings $true** hace lo siguiente:

- Oculta la lista de asistentes. 

- Deshabilita los errores en la ventana MI.

- Deshabilita el vídeo de varias partes.

- Deshabilita la capacidad de promover un asistente a moderador. Debe planear con antelación y declarar todos los presentadores antes de la reunión.

- Deshabilita la capacidad de desenmuerar asistentes individuales.

- Deshabilita la capacidad de aplicar la característica Bloquear foco de vídeo a los asistentes.

- El marcado RTC en los usuarios no podrá deshacerse con 6 porque falta asistencia virtual personal responsable de los comandos DTMF en reuniones grandes activas.

- Si el moderador/organizador programa una reunión en la que todos deben silenciarse primero ("Silenciar todo"), los usuarios RTC se silenciarán durante toda la llamada y no podrán desenmutecerse.

Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funcionalidades de conferencia que no se necesitan en reuniones grandes.
  
Además, debe configurar el grupo de reuniones grandes dedicado para que cada usuario de Skype Empresarial Server que se encuentra en el grupo de servidores y responsable de administrar la programación de reuniones tenga los permisos adecuados. Para ello, siga estos pasos:
  
- Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no deben ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores deben designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.
    
- Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento de reunión en línea para Skype Empresarial siempre programa conferencias con la conferencia asignada por el organizador, lo que significa que las reuniones programadas tienen la misma dirección URL de unión y la misma información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Sin embargo, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.
    
- Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no está activada a menos que se necesite. Esta configuración afecta al tipo de acceso de reunión predeterminado programado por el complemento de reunión en línea para Skype Empresarial cuando no se usa una conferencia asignada. La opción adecuada para esta configuración depende de las necesidades de la organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.
    
Para obtener más información acerca de la creación de una directiva de conferencia, vea [Manage conferencing policies in Skype Empresarial Server](../../manage/conferencing/conferencing-policies.md).
  

