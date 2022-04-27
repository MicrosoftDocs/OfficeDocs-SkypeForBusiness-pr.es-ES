---
title: Planear Teams operadores automáticos y colas de llamadas
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Obtenga información sobre operadores automáticos y colas de llamadas y cómo usarlos para ayudar a los autores de llamadas a desplazarse por un sistema de menús para ponerse en contacto con personas o departamentos de su organización.
ms.openlocfilehash: 76755e722abdcde6673baac42681697165921aca
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059281"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planear Teams operadores automáticos y colas de llamadas

Los operadores automáticos le permiten configurar opciones de menú para enrutar llamadas en función de la entrada del autor de la llamada. Opciones de menú, como "Para Ventas, presione 1.  Para Servicios, presione 2", para un operador automático, permita que una organización proporcione una serie de opciones que guían a los autores de llamadas a su destino rápidamente, sin necesidad de que un operador humano controle las llamadas entrantes.

Las colas de llamadas son áreas de espera para los autores de llamadas. En situaciones en las que los autores de llamadas necesitan ponerse en contacto con alguien con una especialidad en particular , como ventas o servicio, en lugar de con una persona específica, puede usar colas de llamadas para conectar a los autores de llamadas con el grupo de agentes que pueden ayudarle. Los autores de llamadas se ponen en espera hasta que un agente asignado a la cola esté disponible para realizar su llamada.

Si se usan de forma conjunta, los operadores automáticos y las colas de llamadas pueden redirigir fácilmente los autores de llamadas a la persona o el departamento adecuados de su organización.

## <a name="auto-attendants"></a>Operadores automáticos

El propósito principal de un operador automático es dirigir el autor de la llamada a una persona o departamento adecuados en función de la entrada del autor de la llamada a las opciones de menú proporcionadas. Los autores de llamadas se pueden dirigir a personas específicas de su organización, a colas de llamadas donde esperan para hablar con el siguiente agente disponible o al correo de voz. Se pueden especificar diferentes opciones de enrutamiento de llamadas para el horario laboral, las horas de descanso y los días festivos.

Las indicaciones de menú se pueden crear mediante texto a voz (mensajes generados por el sistema) o mediante la carga de un archivo de audio grabado. El reconocimiento de voz acepta comandos de voz para la navegación con manos libres, pero las personas que llaman también pueden usar el teclado del teléfono para navegar por los menús.

Cada operador automático tiene un idioma y una zona horaria específicos. Si hace negocios en varios idiomas o en varias partes del mundo, puede crear tantos operadores automáticos como necesite para dar cabida a sus autores de llamadas.

Para cada operador automático, puede configurar un operador. Aunque puede configurar las llamadas del operador para que vayan a varios destinos, la característica del operador está diseñada para permitir que los autores de llamadas hablen con una persona específica de su organización que pueda ayudarle.

Los operadores automáticos pueden configurarse para permitir que los autores de llamadas realicen búsquedas en el directorio de su organización, ya sea por nombre o por número de extensión. Dentro de un operador automático, puede especificar quién está disponible para la búsqueda en el directorio eligiendo grupos de usuarios para incluir o excluir. (Esto se conoce como *ámbito de marcado*).

Los autores de llamadas pueden ponerse en contacto con un operador automático, ya sea por número de teléfono directo, si están configurados, o por ser redirigidos desde otro operador automático o una cola de llamadas.

## <a name="call-queues"></a>Colas de llamadas

Una cola de llamadas es análoga a una sala de espera en un edificio físico. Los autores de llamadas esperan en espera mientras las llamadas se redirigen a los agentes de la cola. Las colas de llamadas se usan normalmente para las funciones de ventas y servicio. Sin embargo, las colas de llamadas se pueden utilizar para cualquier situación en la que el número de llamadas supere su capacidad interna, como una recepcionista en una instalación ocupada.

Las colas de llamadas permiten un enrutamiento específico de llamadas en los casos en los que el número total de autores de llamadas en la cola o el tiempo de espera supera los límites que especifique. Las llamadas se pueden enrutar a personas específicas, correo de voz, otras colas de llamadas o operadores automáticos.

Al igual que los operadores automáticos, las colas de llamadas tienen una configuración de idioma. Puede usar distintas colas de llamadas si hace negocios en varios idiomas. Los agentes pueden ser miembros de más de una cola si son multilingües.

Para cada cola de llamadas, puede especificar si los agentes de la cola pueden optar por no recibir llamadas y si las llamadas deben redirigirse a ellos en función de su indicación de presencia en Teams.

Puede asignar un número de teléfono a una cola de llamadas, pero las colas de llamadas no proporcionan un enrutamiento de llamadas independiente para los períodos no laborables y festivos. A menos que la cola de llamadas esté atendida las 24 horas del día, se recomienda asignar el número de teléfono a un operador automático que redirija a la cola de llamadas durante el horario laboral.

## <a name="prerequisites"></a>Requisitos previos

Para configurar operadores automáticos y colas de llamadas, necesita los siguientes recursos:

- Una cuenta de recursos para cada operador automático y cada cola de llamadas
- Un sistema de Teléfono Microsoft gratuito: licencia de usuario virtual para cada cuenta de recursos
- Al menos un [número de servicio de Microsoft](getting-service-phone-numbers.md), Conexión con operador número, número de enrutamiento directo o un número híbrido para cada cuenta de recursos a la que desea que se pueda marcar directamente
 - El número de servicio puede ser un número de pago o gratuito

> [!NOTE]
> Las cuentas de recursos están deshabilitadas para iniciar sesión y deben permanecer así. El chat y la presencia no son compatibles con estas cuentas.

Los agentes que reciben llamadas de las colas de llamadas deben estar Telefonía IP empresarial habilitados para los usuarios en línea o locales. Además, si las colas de llamadas usan números de enrutamiento directo, los agentes que necesitan realizar conferencias o transferir llamadas también requieren:

- Una directiva de enrutamiento de voz en línea asignada si la cola de llamadas usa el modo de transferencia
- Una licencia de Audioconferencia o una directiva de enrutamiento de voz en línea asignada si la cola de llamadas usa el modo de conferencia

Si los agentes usan la aplicación Microsoft Teams para las llamadas de la cola de llamadas, deben estar en el modo TeamsOnly.

Al usar una cuenta de recursos para fines de id. de línea de llamadas en colas de llamadas o cuando un operador automático o una cola de llamadas transfiere llamadas a un número de teléfono externo, la cuenta del recurso debe tener una licencia de usuario virtual Sistema telefónico y una de las siguientes asignadas:

- Una licencia [del plan de llamadas](calling-plans-for-office-365.md) y un número de teléfono asignados
- Un número de teléfono [Conexión con operador](operator-connect-plan.md) asignado
- Una [directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md) (la asignación de números de teléfono es opcional al usar enrutamiento directo)

> [!NOTE]
> Si se deshabilita o se quita el plan de llamadas asignado a la cuenta de recursos, se consumirán [créditos de comunicaciones](what-are-communications-credits.md), si están disponibles en el inquilino (sin asignarse a la cuenta de recursos). Si no hay ningún plan de llamadas o créditos de comunicaciones, la llamada no se realizará correctamente.
>
> Los números de servicio de enrutamiento directo para las colas de llamadas y los operadores automáticos solo son compatibles con Microsoft Teams usuarios y agentes de llamadas.
> 
> No se admiten transferencias entre troncos de Plan de llamadas, Conexión con operador y Enrutamiento directo.
> 
> En un escenario híbrido, la cuenta de recursos debe crearse localmente. Para obtener más información, consulte [Planear colas de llamadas en la nube](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Decisiones empresariales

Antes de configurar los operadores automáticos y las colas de llamadas, hay algunas decisiones que debe tomar sobre cómo usar estas características en su empresa. Estas decisiones determinarán la configuración que elija al configurar los operadores automáticos y las colas de llamadas.

Documente sus respuestas a estas preguntas y proporcione la información al administrador que realice la configuración.

- ¿Qué idiomas necesita? ¿Dónde se necesitan estos idiomas: qué departamento o grupo?
- ¿Desea permitir las entradas de voz de los autores de llamadas o solo las entradas de marcación?
- ¿Necesita un enrutamiento de llamadas independiente para las horas de descanso o los días festivos? ¿Cuáles son las horas y los días festivos?
- ¿Desea permitir que los agentes de una cola de llamadas opten por no recibir llamadas?
- ¿Quiere que los agentes de las colas de llamadas o su operador tengan un identificador de llamada específico si llaman?
- ¿Desea habilitar el [estacionamiento y la recuperación de llamadas](call-park-and-retrieve.md) en su organización para ayudar con las entregas de llamadas entre personas o departamentos?
- Para las indicaciones de voz, ¿desea grabar la suya propia o usar la voz generada por el sistema? (La voz generada por el sistema es fácil de actualizar).

## <a name="technical-decisions"></a>Decisiones técnicas

Al usar operadores automáticos y colas de llamadas para conectar autores de llamadas con personas de su organización, hay algunas decisiones técnicas que tomar antes de iniciar la configuración.

Los agentes se pueden agregar a las colas de llamadas de las siguientes maneras:

- Usuarios individuales
- Listas de distribución
- Grupos de seguridad, incluidos los grupos de seguridad habilitados para correo
- Grupos de Microsoft 365 o Teams

Puede usar una combinación de estas opciones para cada cola si es necesario. Los grupos que tienen una dirección de correo electrónico se pueden usar para el correo de voz. El uso de Teams ofrece muchas ventajas, como el almacenamiento de archivos compartidos y el chat entre agentes, un buzón común donde se pueden recibir correos de voz y una plataforma extensible que puede incluir integración con sus aplicaciones de línea de negocio o Power Apps.

Se recomienda elegir una estrategia para agregar agentes de llamadas a las colas antes de iniciar la configuración.

Si tiene un operador automático existente y una infraestructura de cola de llamadas y está migrando a Teams, necesitará un plan para transferir sus números de teléfono existentes a los nuevos operadores automáticos y colas de llamadas. Es posible que deba crear una [solicitud de portabilidad](phone-number-calling-plans/port-order-overview.md) para mover los números de otros proveedores. Le recomendamos que adquiera temporalmente uno o varios números de teléfono nuevos y que pruebe los flujos de su operador automático y cola de llamadas antes de cambiarlos por los números que tiene actualmente en el servicio.

*El modo de conferencia* es una opción en las colas de llamadas que reduce significativamente la cantidad de tiempo que se tarda en conectar Teams llamadas VOIP y llamadas RTC a un agente. Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:

- Última versión del cliente de escritorio de Microsoft Teams, la aplicación de Android o la aplicación de iOS
- Teléfono Microsoft versión del sistema 1449/1.0.94.2020051601 o posterior
  
Establece las cuentas de Teams de los agentes en modo solo Teams. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.

Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

## <a name="plan-your-call-routing-flow"></a>Planear el flujo de enrutamiento de llamadas

Como parte del proceso de planeación, le recomendamos que solucione el enrutamiento de llamadas de su organización en un diagrama. El diagrama ayuda a determinar el enrutamiento más eficaz para las personas que llaman a su organización. También puede usar el diagrama para determinar los operadores automáticos y colas de llamadas que necesita crear, junto con requisitos relacionados como números de servicio, licencias y cuentas de recursos.

Veamos cómo los operadores automáticos y las colas de llamadas enrutan las llamadas.

Los operadores automáticos enrutan todas las llamadas de una de las siguientes maneras:

- **Redirigir inmediatamente** : las llamadas se pueden redirigir a uno de los destinos de enrutamiento de llamadas (enumerados a continuación) inmediatamente después de responder o después de un saludo inicial.
- **Redirigir según las opciones de marcado** : se puede dirigir a los autores de llamadas para que elijan entre las opciones asignadas a los números del teclado del teléfono, 0-9. Se puede asignar a cada tecla de marcado un destino de enrutamiento de llamadas.
- **Marcar a personas por nombre o extensión** : se puede dirigir a los autores de llamadas que marquen el número de extensión de la persona con la que intentan ponerse en contacto en el directorio de su organización o deletreando el nombre de la persona.
- **Desconectar:** un operador automático puede colgar la llamada.

> [!NOTE]
> Un único operador automático solo puede admitir un único método de marcado por.  Para permitir que los autores de llamadas marquen por nombre y por número, deberá crear un operador automático que tenga una opción para marcar por nombre y otro para marcar por extensión.  Cada una de estas opciones redirigirá a operadores automáticos separados configurados para estos escenarios de "marcado por".

Cuando un operador automático o una cola de llamadas redirigen las llamadas, puede elegir entre los siguientes destinos de enrutamiento de llamadas:

- **Persona de la organización** : una persona de la organización que puede recibir llamadas de voz. Puede ser un usuario en línea o un usuario hospedado localmente mediante Skype Empresarial Server.
- **Aplicación de voz** : otro operador automático o una cola de llamadas. Elija la cuenta de recursos asociada con el destino.
- **Número de teléfono externo** : cualquier número de teléfono. (Consulte [los detalles técnicos de las transferencias externas](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Correo de voz**: el buzón de voz asociado a un grupo de Microsoft 365 que especifique. Puede elegir si quiere las transcripciones del correo de voz y "Deje un mensaje después del tono". símbolo del sistema.
- **Operador** (solo operador automático): el operador definido para el operador automático. Definir un operador es opcional. Un operador puede ser cualquiera de los otros destinos de esta lista.

Los operadores automáticos ofrecen opciones de enrutamiento de llamadas independientes para las llamadas recibidas fuera del horario laboral y los días festivos. 

Las colas de llamadas ponen al autor de la llamada en espera hasta que un agente asignado a la cola esté disponible para realizar la llamada. Hay dos situaciones en las que el autor de la llamada podría salir de la cola:

- **Desbordamiento de llamadas** : si el número de llamadas en la cola supera el límite que estableció, los nuevos autores de llamadas se redirigirán fuera de la cola.
- **Tiempo de espera de llamada** : si el autor de la llamada ha estado en la cola más tiempo que el ajuste de tiempo de espera configurado, se redirige fuera de la cola.

Las llamadas redirigidos fuera de una cola se pueden enviar a cualquiera de los destinos de enrutamiento de llamadas enumerados anteriormente, excepto a un operador. (Las colas de llamadas no tienen operadores, pero puede redirigir a los autores de llamadas al mismo destino que un operador que haya configurado para un operador automático).

El ejemplo siguiente muestra un ejemplo de enrutamiento de llamadas con operadores automáticos y colas de llamadas.

![Diagrama de enrutamiento de llamadas con operadores automáticos y colas de llamadas.](media/attendant-and-queue-call-routing.png)

En el ejemplo anterior:

- La tecla cero (0) redirige a los autores de llamadas a un operador. El operador de ese operador automático se ha configurado como **persona de la organización**.
- La clave uno (1) redirige a los autores de llamadas a la cola de llamadas de ventas. Esta cola de llamadas está conectada a un equipo que contiene el equipo de ventas asignado a la cola.
- La tecla dos (2) redirige a los autores de llamadas a la cola de llamadas de soporte técnico. Esta cola de llamadas está conectada a un equipo que contiene el equipo de soporte técnico asignado al equipo.
- La cola de llamadas de soporte técnico tiene un número de teléfono directo a través de un operador automático intermedio. El hecho de que un operador automático responda a la línea de soporte técnico permite el enrutamiento de llamadas por separado y de días festivos.
- La tecla tres (3) redirige a los usuarios a otro operador automático para el directorio de la compañía. El operador automático del directorio de la empresa permite a los autores de llamadas llamar a personas de la organización marcando su nombre o extensión.

Le recomendamos que cree uno o más diagramas similares al anterior para asignar el enrutamiento de llamadas. Asegúrese de incluir lo siguiente en el diagrama o en la documentación correspondiente:

- ¿Qué operadores automáticos tendrán acceso directo a través de números de teléfono?
- ¿Cuáles son los requisitos de enrutamiento de días no horarios y días festivos para cada operador automático?
- La pertenencia a cada cola de llamadas. (Puede agregar usuarios individualmente o asignar la cola a diferentes tipos de grupos. Asignar una cola a un equipo proporciona la experiencia más versátil).

Estos son algunos procedimientos recomendados de enrutamiento de llamadas:

- Examine su sistema de llamadas existente y analice los tipos y la frecuencia de las llamadas entrantes. Use esta información para informar a su operador automático y la estructura de la cola de llamadas.
- Coloque las opciones más comunes más pronto en el menú para enrutar las llamadas lo más rápido posible.
- Evite conectar los números de servicio directamente a las colas de llamadas, a menos que las colas estén disponibles las 24 horas del día, 7 horas. Las colas de llamadas no permiten una administración de llamadas independiente en horarios no laborables ni festivos. Si desea tener una cola con un número directo, asigne el número a un operador automático que redirija automáticamente a la cola durante el horario laboral.
- Si recibe numerosas llamadas que solicitan información básica sobre su empresa, como el horario laboral, la ubicación o la dirección del sitio web, considere la posibilidad de crear un operador automático para responder a estas preguntas con mensajes grabados.
- Mantenga la lista de elementos de menú en cinco o menos. Los autores de llamadas pueden tener problemas para recordar más de cinco opciones. Use operadores automáticos anidados si se necesitan más opciones para redirigir correctamente una llamada.
- Describa primero el servicio, seguido de la opción de presionar (p. ej.: para Ventas presione 1) en lugar de al revés (por ejemplo. Presione 1 para Ventas).
- Terminología de usuario que comprenderán los autores de llamadas en lugar de lo que puede usar internamente.
- Evite las actualizaciones frecuentes para el enrutamiento de llamadas. Si cambia las opciones de menú para un operador automático en el futuro, llámalo en las indicaciones de voz durante los primeros 30 días.

## <a name="getting-started"></a>Introducción

Una vez que haya completado las tareas de planeación de este artículo, siga estos pasos para configurar los operadores automáticos y las colas de llamadas:

1. Obtenga los números de servicio que necesita para los operadores automáticos y las colas de llamadas a los que desea que se pueda obtener acceso mediante marcado directo desde fuera de su organización. Esto puede incluir [transferir números de otro proveedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [solicitar nuevos números de servicio](getting-service-phone-numbers.md).

2. Obtenga una [licencia de Sistema telefónico - Usuario virtual](teams-add-on-licensing/virtual-user.md) para cada cuenta de recursos que planee crear. Estas licencias son gratuitas, por lo que le recomendamos que obtenga algunos adicionales por si decide realizar cambios en sus cuentas de recursos en el futuro.

3. [Cree una cuenta de recursos](manage-resource-accounts.md) para cada operador automático y cola de llamadas que desee crear. Asigne a cada cuenta una Sistema telefónico: licencia de usuario virtual y, opcionalmente, un número de servicio.

4. [Cree los días festivos](set-up-holidays-in-teams.md) para los que desea tener un enrutamiento de llamadas independiente en los operadores automáticos.

5. Opcionalmente, [configure el estacionamiento y la recuperación de llamadas](call-park-and-retrieve.md) si desea usar esta característica para ayudarle con las transferencias de llamadas.

6. Cree los grupos que desee usar para contener los agentes de llamadas de las colas de llamadas.

7. Si planea permitir el marcado por extensión, asegúrese de que ha agregado el número de extensión de los usuarios a su perfil de Azure Active Directory.

Una vez que haya completado los pasos anteriores, estará listo para crear sus operadores automáticos y colas de llamadas. Como los operadores automáticos y las colas de llamadas pueden redirigir las llamadas entre sí, consulte el diagrama de flujo de trabajo que ha creado para determinar qué operador automático o cola de llamadas se debe crear primero. En el ejemplo del diagrama anterior, crearía las colas de llamadas de ventas y soporte técnico antes de crear el operador automático principal de Contoso, ya que el operador automático principal debe dirigir a los autores de llamadas a las colas de llamadas de ventas y soporte técnico.

Consulte los artículos siguientes para obtener información sobre cómo crear operadores automáticos y colas de llamadas:

- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md)

Si necesita funcionalidades más amplias, como la integración con flujos de trabajo, bots y SMS, considere [la posibilidad de Azure Communication Services](/azure/communication-services/overview).

## <a name="related-topics"></a>Temas relacionados

[Planear el enrutamiento directo](direct-routing-plan.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Crear una cola de llamadas: tutorial de pequeña empresa](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurar un operador automático: tutorial de pequeña empresa](business-voice/create-a-phone-system-auto-attendant-smb.md)
