---
title: Plan para operadores automáticos y colas de llamadas de Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Obtenga información sobre los operadores automáticos y las colas de llamadas, así como sobre cómo usarlos para ayudar a los autores de llamadas a desplazarse por un sistema de menús para llegar a los usuarios o departamentos de su organización.
ms.openlocfilehash: 65dac48267379d17b76443e42eb70e2e866f6e8f
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125672"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Plan para operadores automáticos y colas de llamadas de Teams

Los operadores automáticos le permiten configurar opciones de menú para enrutar llamadas en función de la entrada del autor de la llamada. Opciones de menú, como "Ventas, pulse 1.  Para Los Servicios presionan 2", para un operador automático, permite a una organización proporcionar una serie de opciones que guían a los autores de llamadas a su destino rápidamente, sin depender de un operador humano para controlar las llamadas entrantes.

Las colas de llamadas son áreas de espera para los autores de llamadas. Para situaciones en las que los autores de llamadas necesiten comunicarse con alguien con una especial especial, como ventas o servicio, en lugar de con una persona determinada, puede usar colas de llamadas para conectar a los autores de llamadas con el grupo de agentes que pueden ayudarlos. Las personas que llaman están en espera hasta que un agente asignado a la cola esté disponible para realizar su llamada.

Cuando se usan de forma conjunta, los operadores automáticos y las colas de llamadas pueden dirigir fácilmente a los autores de llamadas a la persona o el departamento correspondiente de su organización.

## <a name="auto-attendants"></a>Operadores automáticos

La finalidad principal de un operador automático es dirigir al autor de la llamada a una persona o departamento adecuado en función de la información que el autor de la llamada aporte a las opciones de menú proporcionadas. Los autores de llamadas pueden dirigirse a personas específicas de su organización, a colas de llamadas donde esperan para hablar con el siguiente agente disponible o al correo de voz. Se pueden especificar diferentes opciones de enrutamiento de llamadas para el horario laboral, fuera del horario laboral y los días festivos.

Las solicitudes de menú se pueden crear usando texto a voz (mensajes generados por el sistema) o cargando un archivo de audio grabado. El reconocimiento de voz acepta comandos de voz para la navegación manos libres, pero las personas que llaman también pueden usar el teclado del teléfono para navegar por los menús.

Cada operador automático tiene un idioma y una zona horaria específicos. Si hace negocios en varios idiomas o en varias partes del mundo, puede crear tantos operadores automáticos como necesite para dar cabida a sus autores de llamadas.

Puede configurar un operador para cada operador automático. Aunque puede configurar llamadas de operadores para ir a una variedad de destinos, la característica de operador está diseñada para permitir que los autores de llamadas hablen con una persona específica de su organización que pueda ayudarlo.

Los operadores automáticos se pueden configurar para permitir que los autores de llamadas busquen en el directorio de su organización, ya sea por nombre o por número de extensión. Dentro de un operador automático, puede especificar quién está disponible para la búsqueda en el directorio eligiendo grupos de usuarios que se incluirán o excluyan. (Esto se conoce como ámbito *de marcado).*

Los autores de llamadas pueden comunicarse con un operador automático ya sea por número de teléfono directo (si está configurado) o bien por medio de la redirigiendo desde otro operador automático o una cola de llamadas.

## <a name="call-queues"></a>Colas de llamadas

Una cola de llamadas es analógica a una sala de espera de un edificio físico. Las personas que llaman esperan en espera mientras las llamadas se enrutadas a los agentes de la cola. Las colas de llamadas se usan con frecuencia para las funciones de ventas y servicios. Sin embargo, las colas de llamadas se pueden usar para cualquier situación en la que el número de llamadas supere su capacidad interna, como un recepcionista en una instalación ocupada.

Las colas de llamadas permiten el enrutamiento específico de llamadas en los casos en que el número total de llamadas en la cola o el tiempo de espera superen los límites que especifique. Las llamadas se pueden enrutar a personas específicas, correo de voz, otras colas de llamadas o operadores automáticos.

Al igual que los operadores automáticos, las colas de llamadas tienen una configuración de idioma. Puede usar diferentes colas de llamadas si hace negocios en varios idiomas. Los agentes pueden ser miembros de más de una cola si son multilingües.

Para cada cola de llamadas, puede especificar si los agentes de la cola pueden dejar de realizar llamadas y si las llamadas se deben enrutar a ellos en función de su indicación de presencia en Teams.

Puede asignar un número de teléfono a una cola de llamadas, pero las colas de llamadas no proporcionan enrutamiento de llamadas separado para horas no laborales y días festivos. A menos que la cola de llamadas esté disponible las 24 horas del día, le recomendamos que asigne el número de teléfono a un operador automático que redirija a la cola de llamadas durante el horario laboral.

## <a name="prerequisites"></a>Requisitos previos

Para configurar operadores automáticos y colas de llamadas, necesita los siguientes recursos:

- Una cuenta de recursos para cada operador automático y cada cola de llamadas
- Un sistema telefónico gratuito: licencia de usuario virtual para cada cuenta de recursos
- Al menos un número [de servicio de Microsoft,](getting-service-phone-numbers.md)un número de enrutamiento directo o un número híbrido para cada cuenta de recursos que desee que se pueda marcar directamente
 - El número de servicio puede ser un número gratuito o de pago.

Los agentes que reciban llamadas de las colas de llamadas Telefonía IP empresarial habilitados en línea o en local. Además, si las colas de llamadas usan números de enrutamiento directo, los agentes que necesiten realizar conferencias o transferir llamadas también necesitarán lo siguiente:

- Una directiva de enrutamiento de voz en línea asignada si la cola de llamadas usa el modo de transferencia
- Una licencia de Audioconferencia o una directiva de enrutamiento de voz en línea asignada si la cola de llamadas usa el modo de conferencia

Si los agentes usan la aplicación de Microsoft Teams para llamadas en cola de llamadas, deben estar en modo TeamsOnly.

Al transferir llamadas a un número de teléfono externo, la cuenta de recurso que realiza la transferencia (es decir, la que está asociada al operador automático o a la cola de llamadas) debe tener un número de teléfono y una licencia de usuario virtual de Microsoft 365 Phone System. Además:

- Para una cuenta de recurso con un número de plan de llamadas, asigne una licencia [de plan de](calling-plans-for-office-365.md) llamadas.
- Para una cuenta de recurso con un número de enrutamiento directo, asigne una [directiva de enrutamiento de voz en línea.](manage-voice-routing-policies.md)

> [!NOTE]
> Los números de servicio de enrutamiento directo para el operador automático y las colas de llamadas solo son compatibles con los usuarios de Microsoft Teams y los agentes de llamadas.<br>
> No se admiten las transferencias entre troncos del plan de llamadas y troncos de enrutamiento directo.

## <a name="business-decisions"></a>Decisiones empresariales

Antes de configurar los operadores automáticos y las colas de llamadas, hay algunas decisiones que debe tomar sobre cómo usar estas características en su empresa. Estas decisiones determinarán la configuración que elija al configurar los operadores automáticos y las colas de llamadas.

Documente sus respuestas a estas preguntas y proporcione la información al administrador que está realizando la configuración.

- ¿Qué idiomas necesita? ¿Dónde se necesitan estos idiomas: qué departamento o grupo?
- ¿Desea permitir la entrada de voz de los autores de llamadas o solo las entradas de marcación?
- ¿Necesita enrutamiento de llamadas separado para no laborales o festivos? ¿Cuáles son las horas y los días festivos?
- ¿Quiere permitir que los agentes de una cola de llamadas puedan dejar de recibir llamadas?
- ¿Quiere que los agentes de las colas de llamadas o su operador tengan un identificador de llamada específico si llaman?
- ¿Desea habilitar el [despegar y](call-park-and-retrieve.md) la recuperación de llamadas en su organización para ayudar en los entregas de llamadas entre personas o departamentos?
- Para las indicaciones de voz, ¿desea grabar la suya propia o usar la voz generada por el sistema? (La voz generada por el sistema es fácil de actualizar).

## <a name="technical-decisions"></a>Decisiones técnicas

Al usar operadores automáticos y colas de llamadas para conectar autores de llamadas a personas de su organización, hay que tomar algunas decisiones técnicas antes de iniciar la configuración.

Los agentes se pueden agregar a las colas de llamadas de las siguientes maneras:

- Usuarios individuales
- Listas de distribución
- Grupos de seguridad, incluidos los grupos de seguridad habilitados para correo electrónico
- Grupos o Equipos de Microsoft 365

Puede usar una combinación de estas opciones para cada cola, si es necesario. Los grupos que tienen una dirección de correo electrónico se pueden usar para el correo de voz. El uso de Teams ofrece varias ventajas, como el almacenamiento de archivos compartidos y el chat entre agentes, un buzón común donde se pueden recibir correos de voz y una plataforma extensible que puede incluir la integración con su línea de aplicaciones empresariales o Power Apps.

Le recomendamos que elija una estrategia para agregar agentes de llamadas a las colas antes de iniciar la configuración.

Si ya tiene un operador automático y una infraestructura de colas de llamadas y está migrando a Teams, necesitará un plan para transferir los números de teléfono existentes a los nuevos operadores automáticos y colas de llamadas. Es posible que tenga que crear una orden [de portabilidad](phone-number-calling-plans/port-order-overview.md) para mover los números de otros proveedores. Le recomendamos que adquiera temporalmente uno o varios números de teléfono nuevos y que pruebe el operador automático y los flujos de cola de llamadas antes de cambiarlos por los números que tiene actualmente en servicio.

*El modo de* conferencia es una opción en colas de llamadas que reduce significativamente la cantidad de tiempo que se tarda en conectar llamadas VOIP y llamadas RTC de Teams a un agente. Para que el modo de conferencia funcione, los agentes de la cola de llamadas deben usar uno de los siguientes clientes:

- La última versión del cliente de escritorio de Microsoft Teams, la aplicación para Android o la aplicación de iOS
  - Versión 1449/1.0.94.2020051601 o posteriores de Microsoft Teams
  
Establezca las cuentas de Los agentes en el modo solo para equipos. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.

Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

## <a name="plan-your-call-routing-flow"></a>Planear el flujo de enrutamiento de llamadas

Como parte del proceso de planeación, le recomendamos que trabaje en el enrutamiento de llamadas para su organización en un diagrama. El diagrama le ayuda a determinar el enrutamiento más eficaz para las personas que llaman a su organización. También puede usar el diagrama para determinar los operadores automáticos y las colas de llamadas que necesita crear, junto con requisitos relacionados como números de servicio, licencias y cuentas de recursos.

Veamos cómo enrutar las llamadas los operadores automáticos y las colas de llamadas.

Los operadores automáticos enrutar todas las llamadas de una de las siguientes maneras:

- **Redirigir inmediatamente:** las llamadas se pueden redirigir a uno de los destinos de enrutamiento de llamadas (enumerados a continuación) inmediatamente al responder o después de un saludo inicial.
- **Redirigir según las opciones de** marcado: se puede dirigir a los autores de llamadas para que elijan entre las opciones asignadas a los números de su teclado telefónico (0-9). Se puede asignar un destino de enrutamiento de llamadas a cada tecla de marcado.
- **Marque a las** personas por nombre o extensión: se puede dirigir a los autores de llamadas para que marquen el número de extensión de la persona con la que están intentando contactar en el directorio de la organización o bien deletrear el nombre de la persona.
- **Desconectar:** un operador automático puede colgar la llamada.

> [!NOTE]
> Un único operador automático solo admite un método de marcado por.  Para permitir que los autores de llamadas llamen por nombre y por número, deberá crear un operador automático que tenga una opción para marcar por nombre y otra para marcar por extensión.  Cada una de estas opciones se dirigirá a operadores automáticos separados configurados para estos escenarios de "marcado por".

Cuando un operador automático o una cola de llamadas redirija las llamadas, puede elegir entre los siguientes destinos de enrutamiento de llamadas:

- **Persona de la organización:** una persona de la organización que puede recibir llamadas de voz. Puede ser un usuario en línea o un usuario alojado en local con Skype Empresarial Server.
- **Aplicación de voz:** otro operador automático o una cola de llamadas. Elija la cuenta de recurso asociada con el destino.
- **Número de teléfono externo:** cualquier número de teléfono. (Consulte [los detalles técnicos de la transferencia externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Correo** de voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.
- **Operador** (solo operador automático): el operador definido para el operador automático. La definición de un operador es opcional. Un operador puede ser cualquiera de los otros destinos de esta lista.

Los operadores automáticos ofrecen opciones de enrutamiento de llamada independientes para las llamadas recibidas fuera del horario laboral y en días festivos. El enrutamiento de llamadas no laborales permite todas las opciones mencionadas anteriormente, mientras que el enrutamiento de llamadas navideñas solo permite redirigir o desconectar una llamada, pero no ofrece opciones de tecla de marcado.

Las colas de llamadas ponen al autor de la llamada en espera hasta que un agente asignado a la cola esté disponible para realizar la llamada. Hay dos situaciones en las que un autor de llamada podría ser dirigido fuera de la cola:

- **Desbordamiento de** llamadas: si el número de llamadas en la cola supera el límite establecido, se redirigirá a los nuevos autores de llamadas fuera de la cola.
- **Tiempo de espera de** la llamada: si un autor de llamada ha estado en la cola más tiempo de espera que la configuración de tiempo de espera configurada, se le redirigirá fuera de la cola.

Las llamadas redirigidos fuera de una cola se pueden enviar a cualquiera de los destinos de enrutamiento de llamadas enumerados anteriormente excepto para un operador. (Las colas de llamadas no tienen operadores, pero puede redirigir a los autores de llamadas al mismo destino que un operador que haya configurado para un operador automático).

El ejemplo siguiente muestra un ejemplo de enrutamiento de llamadas con operadores automáticos y colas de llamadas.

![Diagrama de enrutamiento de llamadas con operadores automáticos y colas de llamadas](media/attendant-and-queue-call-routing.png)

En el ejemplo anterior:

- La tecla cero (0) redirige a los autores de llamadas a un operador. El operador para ese operador automático se ha configurado como **una persona de la organización.**
- La clave uno (1) redirige a los autores de llamadas a la cola de llamadas de ventas. Esta cola de llamadas está conectada a un equipo que contiene el equipo de ventas asignado a la cola.
- La tecla dos (2) redirige a los autores de llamadas a la cola de llamadas de soporte técnico. Esta cola de llamadas está conectada a un equipo que contiene el equipo de soporte técnico asignado al equipo.
- La cola de llamadas de soporte tiene un número de teléfono directo a través de un operador automático local. Hacer que un operador automático responda a la línea de soporte técnico permite el enrutamiento de llamadas de días no laborales y festivos.
- La clave de tres (3) redirige a los usuarios a otro operador automático para el directorio de la empresa. El operador automático del directorio de la empresa permite a los autores de llamadas llamar a personas de la organización marcando su nombre o extensión.

Le recomendamos que cree uno o más diagramas similares al anterior para asignar el enrutamiento de llamadas. Asegúrese de incluir lo siguiente en el diagrama o la documentación correspondiente:

- ¿Qué operadores automáticos tendrán acceso directo a través de números de teléfono?
- ¿Cuáles son los requisitos de enrutamiento para días no laborales y días festivos para cada operador automático?
- La pertenencia de cada cola de llamadas. (Puede agregar usuarios individualmente o asignar la cola a diferentes tipos de grupos. La asignación de una cola a un equipo proporciona la experiencia más versátil).

Estos son algunos procedimientos recomendados de enrutamiento de llamadas:

- Mire su sistema de llamadas existente y analice los tipos y la frecuencia de las llamadas entrantes. Use esta información para ayudar a informar al operador automático y a la estructura de la cola de llamadas.
- Coloque las opciones más comunes más pronto en el menú para enrutar las llamadas lo antes posible.
- Evite conectar números de servicio directamente a las colas de llamadas, a menos que estén disponibles las 24 horas. Las colas de llamadas no permiten administrar llamadas por separado en horas no laborales o días festivos. Si quiere tener una cola con un número directo, asigne el número a un operador automático que redirija automáticamente a la cola durante el horario comercial.
- Si recibe numerosas llamadas que solicitan información básica sobre su empresa, como el horario laboral, la ubicación o la dirección del sitio web, considere la posibilidad de crear un operador automático para responder estas preguntas con los mensajes grabados.
- Mantenga la lista de elementos de menú en cinco o menos. Los autores de llamadas pueden tener problemas para recordar más de cinco opciones. Use operadores automáticos anidados si necesita más opciones para enrutar correctamente una llamada.
- Primero describa el servicio, seguido de la opción de presionar (p. ej.: Para ventas pulse 1) en lugar de al revés (eg. Pulse 1 para Ventas).
- Terminología de usuario que los autores de llamadas comprenderán en lugar de lo que puede usar internamente.
- Evite actualizaciones frecuentes para el enrutamiento de llamadas. Si en el futuro cambia las opciones de menú de un operador automático, puede llamar a esa opción en los avisos de voz de los primeros 30 días.

## <a name="getting-started"></a>Introducción

Una vez que haya completado las tareas de planeación en este artículo, siga estos pasos para configurar los operadores automáticos y las colas de llamadas:

1. Obtenga los números de servicio que necesita para los operadores automáticos y las colas de llamadas a los que desea obtener acceso mediante marcado directo desde fuera de su organización. Esto puede incluir [la transferencia de números de otro proveedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](getting-service-phone-numbers.md)

2. Obtener un [sistema telefónico: licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) para cada cuenta de recurso que planea crear. Estas licencias son gratuitas, por lo que le recomendamos que le sugerirá que realice algunos cambios adicionales en caso de que decida realizar cambios en sus cuentas de recursos en el futuro.

3. [Cree una cuenta de recursos](manage-resource-accounts.md) para cada operador automático y la cola de llamadas que desee crear. Asigne a cada cuenta un sistema telefónico: licencia de usuario virtual y, opcionalmente, un número de servicio.

4. [Cree los días festivos](set-up-holidays-in-teams.md) para los que desea tener enrutamiento de llamadas separado en los operadores automáticos.

5. Opcionalmente, [configure el estacionamiento de llamadas y](call-park-and-retrieve.md) la recuperación si desea usar esta característica para ayudar con las transferencias de llamadas.

6. Cree los grupos que quiera usar para contener los agentes de llamadas para las colas de llamadas.

7. Si planeas permitir el marcado por extensión, asegúrate de haber agregado el número de extensión de los usuarios a su perfil de Azure Active Directory.

Una vez que haya completado los pasos anteriores, estará listo para crear los operadores automáticos y las colas de llamadas. Como los operadores automáticos y las colas de llamadas pueden redirigir las llamadas entre sí, consulte el diagrama de flujo de trabajo que ha creado para determinar qué operador automático o cola de llamadas tienen que crearse primero. En el ejemplo del diagrama anterior, crearía las colas de llamadas de ventas y soporte técnico antes de crear el operador automático principal de Contoso, ya que el operador automático principal necesita dirigir a los autores de llamadas a las colas de llamadas de ventas y soporte técnico.

Consulte los artículos siguientes para obtener información sobre cómo crear operadores automáticos y colas de llamadas:

- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Temas relacionados

[Planear el enrutamiento directo](direct-routing-plan.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Crear una cola de llamadas: tutorial para pequeñas empresas](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurar un operador automático: tutorial para pequeñas empresas](business-voice/create-a-phone-system-auto-attendant-smb.md)
