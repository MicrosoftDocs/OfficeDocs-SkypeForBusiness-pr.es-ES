---
title: Planeación de reuniones grandes en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumen: Lea este tema para obtener información sobre los procedimientos recomendados para implementar y administrar reuniones grandes en Skype empresarial Server.'
ms.openlocfilehash: acb0dd1dbd0efe93b985ed2f9e143ef1538ecb86
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221260"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planeación de reuniones grandes en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre los procedimientos recomendados para implementar y administrar reuniones grandes en Skype empresarial Server.
  
El tamaño de las reuniones que Skype empresarial Server puede admitir depende de si las conferencias se hospedan en un grupo de servidores compartido o dedicado: desde 250 participantes en un grupo compartido hasta 1000 participantes en un grupo dedicado. 
  
> [!NOTE]
> Este tema se centra en los procedimientos recomendados para reuniones grandes compatibles con Skype empresarial Server. Si su organización requiere capacidades de reunión mayores, considere la posibilidad de implementar un entorno híbrido que aproveche la difusión de reunión de Skype, un nuevo servicio en línea que forma parte de Microsoft 365 y Office 365. 

> [!NOTE]
> La difusión de reunión de Skype permite a los usuarios hospedar y difundir reuniones a grandes audiencias en línea de hasta 10.000 participantes. El uso de difusión de reunión de Skype requiere que Skype empresarial Server ya esté configurado en una configuración híbrida con una organización de producción Microsoft 365 u Office 365. Todos los usuarios deben tener un inquilino en línea establecido como requisito previo. Si está interesado en implementar una solución híbrida que puede aprovechar la difusión de reunión de Skype, vea [¿Qué es una difusión de reunión de Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) y [configurar la implementación local para la difusión de reunión de Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Las reuniones grandes suelen tener las siguientes características:
  
- El formato de la reunión es una presentación de uno a varios.
    
- Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.
    
- El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.
    
- Se necesita audio y también se puede usar vídeo.
    
- Una persona dedicada, generalmente sea el organizador de la reunión o un asistente del organizador, configura la reunión con un buen adelanto.
    
- El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y el salón de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.
    
Cuando un usuario programa una reunión, Skype empresarial Server crea un registro en la base de datos de conferencia, que almacena los datos de conferencia, pero no reserva ningún recurso de hardware para la reunión programada antes de tiempo. En su lugar, Skype empresarial Server tiene una lógica de equilibrio de carga integrada para asignar de forma dinámica recursos de conferencia en los servidores front-end de manera que distribuya las cargas equitativamente entre todos los servidores front-end del grupo. Esto aprovisiona y usa recursos de hardware de forma eficaz, pero es importante que planee apropiadamente para admitir reuniones muy grandes. 
  
Por ejemplo, cuando un grupo de Skype empresarial Server se está ejecutando cerca de su capacidad máxima, cada servidor front-end podría hospedar aproximadamente 125 reuniones de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión para 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.
  
La compatibilidad con grandes reuniones de hasta 1000 participantes requiere el tratamiento de los problemas relacionados con el modelo de hardware compartido y con el modelo de no reserva. En general, debe planear un grupo dedicado y seguir los procedimientos recomendados, como se describe en las secciones siguientes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planeación de un grupo dedicado

Si su organización requiere reuniones con más de 250 participantes, debe planear un grupo dedicado para admitir la carga. 
  
Para disponer de suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end de hospedaje no deben hospedar otras cargas de trabajo de mensajería instantánea (mi) y presencia o de telefonía IP empresarial. Los servidores tampoco deben hospedar ninguna otra reunión, independientemente del tamaño del resto de las reuniones. Para hospedar reuniones de hasta 1000 usuarios, debe configurar un grupo de servidores de Skype empresarial independiente dedicado a hospedar reuniones grandes.
  
Un grupo de servidores de Skype empresarial Server dedicado a hospedar reuniones grandes debe hospedar una sola reunión de hasta 1000 usuarios al mismo tiempo, por lo que las horas de reunión deben reservarse por adelantado a través de un proceso de programación fuera de banda para garantizar el soporte dedicado desde los servidores front-end. Para admitir más de una reunión grande al mismo tiempo, debe configurar varios grupos de reuniones de gran tamaño dedicados.
  
Para obtener más información acerca de los requisitos de hardware y software, y la planeación de una topología que admita reuniones grandes, vea [requisitos de hardware y software para conferencias en Skype empresarial Server](hardware-and-software-requirements.md) y [planear la topología de conferencia para Skype empresarial Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementar los procedimientos recomendados para reuniones grandes

Después de configurar un grupo dedicado para reuniones grandes, puede tomar medidas para ayudar a garantizar que las reuniones grandes hospedadas en el grupo ofrezcan la mejor experiencia de usuario. En las siguientes secciones se proporcionan instrucciones para administrar reuniones grandes:
  
- Crear organizadores de reuniones dedicados
    
- Crear moderadores dedicados
    
- Mantener un calendario independiente de reuniones grandes
    
- Implementar un proceso de programación de reuniones grandes
    
- Especificar los detalles de programación adecuados
    
- Crear una directiva de conferencia para reuniones grandes
    
### <a name="create-dedicated-meeting-organizers"></a>Crear organizadores de reuniones dedicados

Para minimizar el tráfico de comunicaciones en tiempo real en el grupo de servidores de gran tamaño, Microsoft no recomienda hospedar usuarios que inicien sesión regularmente con clientes de Skype empresarial y participen en sesiones de mensajería instantánea, presencia, conferencias y voz. En su lugar, realice una de las siguientes acciones:
  
- Crear una o más cuentas de usuario dedicadas solo para programar grandes reuniones
    
- Hospedar las cuentas de usuario del personal responsable de programar grandes reuniones en un grupo de grandes reuniones
    
### <a name="create-dedicated-moderators"></a>Crear moderadores dedicados

Con varios cientos o miles de usuarios en una reunión, se recomienda que una persona dedicada se ponga en moderada la sesión en línea de una reunión grande. Esta persona dedicada puede ser un delegado del organizador de la reunión o de un miembro del personal de soporte técnico de grandes reuniones de la organización. Es importante que, en el momento de programar la reunión, agregue como moderador al encargado dedicado a moderar la reunión, aunque puede promocionar a un asistente a la reunión en línea al rol de moderador mientras la reunión se está celebrando.
  
El moderador de la reunión puede usar todas las funciones del moderador de los clientes de Skype empresarial para administrar la reunión de gran tamaño. Estas funcionalidades incluyen:
  
- Supervisión de la sala de espera y admisión o rechazo de usuarios en la sala de espera
    
- Quitar todos los usuarios de la reunión que no deban estar en la reunión
    
- Cambiar los tipos de acceso a reuniones
    
- Cambio de los roles de los participantes
    
- Invitar a participantes adicionales durante la reunión mediante la funcionalidad de arrastrar y colocar, el marcado telefónico o el correo electrónico
    
- Silenciar y reactivar el audio del público o de usuarios individuales
    
- Administración de contenido de reuniones, incluida la carga de contenido, la eliminación de contenido y el cambio de contenido activo

    
### <a name="maintain-a-separate-calendar"></a>Mantener un calendario independiente

Para cada grupo de reuniones de gran tamaño, debe mantener un calendario independiente de reuniones grandes programadas en ese grupo de servidores. Por ejemplo, puede hospedar una sola cuenta de usuario en el grupo de grandes reuniones y usar Outlook con Exchange y el complemento para reunión en línea de Skype empresarial para mantener un calendario independiente. Si usa varias cuentas de usuario para habilitar personal de ayuda para crear grandes reuniones, puede configurar un calendario independiente que agrupe todas las reuniones grandes creadas por los miembros del personal de ayuda. 
  
Mantener un calendario de reuniones independiente ayuda a evitar conflictos y garantizar que solo una reunión grande está activa en un determinado momento.
  
### <a name="implement-a-scheduling-process"></a>Implementar un proceso de programación

Como solo se admite una reunión grande a la vez en el grupo de reuniones dedicado de gran tamaño, debe implementar un proceso de programación de reuniones grande para facilitar la configuración de reuniones grandes y ayudar a evitar conflictos. Esta capacidad no la proporcionan directamente los clientes de Skype empresarial Server o Skype empresarial. Una forma de implementar un proceso de este tipo es usar el sistema de vales del equipo de soporte técnico de la organización, si está disponible.
  
La programación de una reunión grande implica completar los siguientes pasos:
  
- El organizador de la reunión o el delegado determina la hora, la duración y el tamaño de la próxima reunión, además de presentar una lista de moderadores. Si se anticipa que el tamaño de la reunión va a superar los 250 usuarios o se desea garantizar la mejor experiencia de usuario para una reunión que no supere los 250 usuarios, el organizador o el delegado presentará una solicitud de convocatoria de reunión grande.
    
- El personal de programación comprobará si la fecha y la hora están disponibles. Como solo admitimos una única reunión grande en el grupo de servidores dedicado a la vez, el personal de programación comprobará el calendario de reuniones grandes para determinar si hay otra reunión programada para la fecha y la hora solicitadas. Si la hora solicitada está disponible, el personal aprobará la solicitud de reunión.
    
- Si se aprueba la solicitud, el personal de programación (con credenciales en el grupo dedicado) utiliza el complemento de reunión en línea de Skype empresarial con Outlook para configurar una reunión en el grupo de reuniones de gran tamaño dedicado. Como parte del aviso de aprobación, se proporcionará al solicitante la dirección URL que se usará para unirse a la reunión.
    
- El organizador de la reunión o el delegado usa Outlook para programar la próxima reunión, agregando la dirección URL para unirse a la reunión a la invitación a la reunión. Después, el organizador de la reunión o el delegado especificará los usuarios que desea invitar y les enviará la invitación.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar los detalles de programación adecuados

Tras comprobar para asegurarse de que no hay ninguna otra reunión programada a la hora solicitada, el personal de soporte técnico de gran reunión que administra la solicitud programa la reunión en el grupo de servidores de reuniones grandes. 
  
Para garantizar la mejor experiencia del usuario, es importante programar la reunión grande con los niveles de acceso y las opciones de reunión adecuados para las necesidades del organizador de la reunión. Tenga en cuenta las siguientes opciones de programación configuradas en las opciones de reunión de Skype empresarial:
  
- Use un nuevo espacio de reunión para cada reunión grande en lugar de volver a usar el espacio de reunión dedicado. 
    
- Especifique el nivel de acceso de reunión de la siguiente manera:
    
  - Si al menos un invitado es externo a la organización, establezca el tipo de acceso de reunión en **cualquiera (sin restricciones)**. Esto le habilita para evitar tener que administrar una sala de espera potencialmente grande cuando la reunión está en curso.
    
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
    
    Al administrar de forma explícita los moderadores, puede limitar los moderadores a un número lo suficientemente pequeño para que sea posible tener una reunión grande efectiva. Si la mayoría de los participantes de la reunión tienen el rol de asistente, ayuda a reducir la oportunidad de que las personas tomen de manera accidental el control de la presentación, la eliminación de una presentación de PowerPoint, poner/quitar el silencio de los moderadores, y otras interrupciones de la reunión. 
    
- Active la configuración de **silenciar a todos los asistentes** para asegurarse de que solo los moderadores pueden difundir audio a la reunión.
    
- Active la configuración **bloquear vídeo** de los asistentes para asegurarse de que solo los moderadores pueden difundir vídeo a la reunión.
    
### <a name="create-a-conferencing-policy"></a>Crear una directiva de conferencia

Cree una nueva Directiva de conferencia específica para reuniones grandes y, a continuación, asigne la Directiva de conferencia a los usuarios hospedados en el grupo de reuniones de gran tamaño dedicado. Configure la directiva de conferencias mediante las siguientes opciones:
  
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
> La compatibilidad con reuniones grandes en Skype empresarial Server requiere que el valor de **AllowLargeMeetings** se establezca en true. Cuando esta configuración se establece en true, la experiencia de Skype empresarial se optimizará para reuniones de mayor tamaño cuando los usuarios se unan a la reunión. Concretamente, en una reunión grande, Skype empresarial no mostrará la inicial o actualización de la lista de participantes de la reunión, que es un cuello de botella de rendimiento tanto para el cliente como para Skype empresarial Server. En su lugar, Skype empresarial solo mostrará información sobre el usuario y la lista de moderadores de la reunión. Skype empresarial aún mostrará el número total de participantes disponibles en las reuniones grandes.

El valor de **$true AllowLargeMeetings** provoca lo siguiente:

- Oculta la lista de asistentes. 

- Deshabilita los errores en la ventana de mensajería instantánea.

- Deshabilita el vídeo de varios participantes.

- Deshabilita la capacidad de promover a un asistente a moderador. Debe planear con antelación y declarar todos los moderadores antes de la reunión.

- Deshabilita la capacidad de reactivar el audio de asistentes individuales.

- Deshabilita la capacidad de aplicar la característica bloquear foco de vídeo a los asistentes.

- Los usuarios con marcado RTC no podrán reactivarse por sí mismos usando 6 porque falta asistencia personal virtual responsable de los comandos DTMF en reuniones grandes activas.

- Si el moderador/organizador programa una reunión en la que todos los usuarios deben silenciarse en primer lugar ("silenciar todo"), los usuarios de RTC se silenciarán durante la llamada y no podrán reactivarse.

Excepto en la opción **Tamaño máximo de la reunión**, todas las demás opciones de la directiva de conferencia aquí especificadas son necesarias para deshabilitar las funcionalidades de conferencia que no se necesitan en reuniones grandes.
  
Además, debe configurar el grupo de reuniones de gran tamaño dedicado para que cada usuario de Skype empresarial Server hospedado en el grupo de servidores y responsable de administrar la programación de la reunión tenga los permisos adecuados. Para ello, siga estos pasos:
  
- Establezca la opción **Designar como moderador** en **Ninguno**. Normalmente, uno o varios participantes en una reunión grande son moderadores, por lo que los participantes no deben ser admitidos automáticamente como moderadores en las reuniones grandes. En su lugar, los moderadores deben designarse explícitamente en el momento de programar la reunión o promoverse explícitamente durante la reunión grande.
    
- Asegúrese de que la casilla **Tipo de conferencia asignada de forma predeterminada** no esté activada. Esta configuración controla si el complemento para reunión en línea de Skype empresarial siempre programa conferencias mediante la Conferencia asignada al organizador, lo que significa que las reuniones programadas tienen la misma dirección URL de combinación y la información de audio. En escenarios de colaboración de grupos pequeños, este tipo de conferencia asignada funciona bien porque todos tienen su propia conferencia asignada individual y la dirección URL de unión y la información de audio constantes ayudan a unirse rápidamente a la reunión. Sin embargo, en un escenario de reuniones grandes, el personal de soporte de reuniones grandes programa las reuniones usando un único conjunto de credenciales y después proporciona las direcciones URL de unión y la información de audio a los convocantes de la reunión. En este caso, usar una dirección URL diferente para unirse a cada reunión funciona mejor.
    
- Asegúrese de que la casilla **Admitir usuarios anónimos de forma predeterminada** no está activada a menos que se necesite. Esta configuración afecta al tipo de acceso a la reunión predeterminado programado por el complemento de reunión en línea de Skype empresarial cuando no se usa una conferencia asignada. La opción adecuada para esta configuración depende de las necesidades de su organización. Si la mayoría de las reuniones grandes de su organización son reuniones internas, no active esta opción. Si la mayoría de las reuniones grandes requiere que los usuarios externos puedan unirse, active esta opción.
    
Para obtener más información acerca de la creación de una directiva de conferencia, consulte [Manage Conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

