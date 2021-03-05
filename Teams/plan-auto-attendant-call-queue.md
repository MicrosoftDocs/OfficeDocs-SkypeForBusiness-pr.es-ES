---
title: Planear los operadores automáticos y las colas de llamadas de Teams
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
description: Obtenga información sobre operadores automáticos y colas de llamadas y cómo usarlos para ayudar a los autores de llamadas a desplazarse por un sistema de menús para llegar a personas o departamentos de su organización.
ms.openlocfilehash: 2944f7b4add49b136d56620f41a2a1afb1a30a92
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460730"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planear los operadores automáticos y las colas de llamadas de Teams

Los operadores automáticos le permiten configurar opciones de menú para enrutar llamadas en función de la entrada de la persona que llama. Opciones de menú, como "Ventas, presione 1.  Para servicios presione 2", para un operador automático, permita que una organización proporcione una serie de opciones que guían a los autores de llamadas a su destino rápidamente, sin depender de un operador humano para controlar las llamadas entrantes.

Las colas de llamadas son áreas de espera para las personas que llaman. Para situaciones en las que los autores de llamadas necesitan contactar con alguien con una especialidad específica (como ventas o servicio) en lugar de una persona específica, puede usar las colas de llamadas para conectar a los autores de llamadas con el grupo de agentes que pueden ayudarles. Las llamadas se ponen en espera hasta que un agente asignado a la cola esté disponible para realizar la llamada.

Usados juntos, los operadores automáticos y las colas de llamadas pueden enrutar fácilmente a los autores de llamadas a la persona o el departamento adecuados de su organización.

## <a name="auto-attendants"></a>Operadores automáticos

El objetivo principal de un operador automático es dirigir a un autor de la llamada a una persona o departamento adecuado en función de la entrada del autor de la llamada a las opciones de menú proporcionadas. Las personas que llaman pueden dirigirse a personas específicas de su organización, a las colas de llamadas en las que esperan para hablar con el siguiente agente disponible o al correo de voz. Se pueden especificar diferentes opciones de enrutamiento de llamadas para horas laborables, fuera del horario laboral y días festivos.

Los mensajes de menú se pueden crear mediante texto a voz (mensajes generados por el sistema) o cargando un archivo de audio grabado. El reconocimiento de voz acepta comandos de voz para la navegación manos libres, pero las personas que llaman también pueden usar el teclado del teléfono para navegar por los menús.

Cada operador automático tiene un idioma y una zona horaria específicos. Si hace negocios en varios idiomas o en varias partes del mundo, puede crear tantos operadores automáticos diferentes como necesite para dar cabida a sus autores de llamadas.

Para cada operador automático, puede configurar un operador. Aunque puede configurar las llamadas de operadores para que vayan a una variedad de destinos, la característica de operador está diseñada para permitir que los autores de llamadas hablen con una persona específica de su organización que pueda ayudarle.

Los operadores automáticos se pueden configurar para permitir que los autores de llamadas busquen en el directorio de su organización, ya sea por nombre o por número de extensión. Dentro de un operador automático, puede especificar quién está disponible para la búsqueda de directorios eligiendo grupos de usuarios para incluir o excluir. (Esto se conoce como ámbito *de marcado*).)

Las personas que llaman pueden llegó a un operador automático ya sea por número de teléfono directo, si está configurado, o bien al ser redirigidos desde otro operador automático o una cola de llamadas.

## <a name="call-queues"></a>Colas de llamadas

Una cola de llamadas es similar a una sala de espera de un edificio físico. Las personas que llaman esperan en espera mientras las llamadas se enruta a los agentes de la cola. Las colas de llamadas se usan habitualmente para las funciones de ventas y servicios. Sin embargo, las colas de llamadas se pueden usar para cualquier situación en la que el número de llamadas supere su capacidad interna, como un recepcionista en una instalación ocupada.

Las colas de llamadas permiten el enrutamiento específico de llamadas en casos en los que el número total de autores de llamadas en la cola o el tiempo de espera supera los límites especificados. Las llamadas se pueden enrutar a personas específicas, correo de voz, otras colas de llamadas o operadores automáticos.

Al igual que los operadores automáticos, las colas de llamadas tienen una configuración de idioma. Puede usar distintas colas de llamadas si hace negocios en varios idiomas. Los agentes pueden ser miembros de más de una cola si son multilingües.

Para cada cola de llamadas, puede especificar si los agentes de la cola pueden optar por no realizar llamadas y si las llamadas se deben enrutar a ellos en función de su indicación de presencia en Teams.

Puede asignar un número de teléfono a una cola de llamadas, pero las colas de llamadas no proporcionan enrutamiento de llamadas independiente para las horas y días festivos. A menos que la cola de llamadas tenga personal las 24 horas del día, se recomienda asignar el número de teléfono a un operador automático que redirige a la cola de llamadas durante el horario laboral.

## <a name="prerequisites"></a>Requisitos previos

Para configurar operadores automáticos y colas de llamadas, necesita los siguientes recursos:

- Una cuenta de recursos para cada operador automático y cada cola de llamadas
- Un sistema telefónico gratuito: licencia de usuario virtual para cada cuenta de recursos
- Al menos un número [de servicio de Microsoft,](getting-service-phone-numbers.md)un número de enrutamiento directo o un número híbrido para cada cuenta de recurso que desea que se pueda marcar directamente
 - El número de servicio puede ser un número gratuito o de pago

Los agentes que reciban llamadas de las colas de llamadas deben estar Telefonía IP empresarial habilitados para usuarios en línea o locales. Además, si las colas de llamadas usan números de enrutamiento directo, los agentes que necesitan realizar conferencias o transferir llamadas también requieren:

- Una directiva de enrutamiento de voz en línea asignada si la cola de llamadas usa el modo de transferencia
- Una licencia de audioconferencia o una directiva de enrutamiento de voz en línea asignada si la cola de llamadas usa el modo de conferencia

Si los agentes usan la aplicación Microsoft Teams para llamadas en cola de llamadas, deben estar en modo TeamsOnly.

Al transferir llamadas a un número de teléfono externo, la cuenta de recursos que realiza la transferencia (es decir, la asociada con el operador automático o la cola de llamadas) debe tener una licencia de usuario virtual de Microsoft 365 Phone System y una de las siguientes asignadas:

- Una [licencia del plan de llamadas](calling-plans-for-office-365.md)
- Una [directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md)

> [!NOTE]
> Los números de servicio de enrutamiento directo para operadores automáticos y colas de llamadas solo son compatibles con los usuarios de Microsoft Teams y los agentes de llamadas.<br>
> Las transferencias entre los troncos del plan de llamadas y los troncos de enrutamiento directo no son compatibles.<br>
> En un escenario híbrido, la cuenta de recursos debe crearse localmente. Para obtener más información, vea Planear colas [de llamadas en la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-queue)

## <a name="business-decisions"></a>Decisiones empresariales

Antes de configurar los operadores automáticos y las colas de llamadas, hay algunas decisiones que debe tomar sobre cómo usar estas características en su empresa. Estas decisiones determinarán la configuración que elija al configurar los operadores automáticos y las colas de llamadas.

Documente sus respuestas a estas preguntas y proporcione la información al administrador que haga la configuración.

- ¿Qué idiomas necesita? ¿Dónde se necesitan estos idiomas: qué departamento o grupo?
- ¿Desea permitir entradas de voz de autores de llamadas o solo entradas de marcado?
- ¿Necesita un enrutamiento de llamadas independiente para días no festivos? ¿Cuáles son las horas y días festivos?
- ¿Desea permitir que los agentes de una cola de llamadas no puedan realizar llamadas?
- ¿Desea que los agentes de las colas de llamadas o el operador tengan un identificador de llamada específico si marcan hacia fuera?
- ¿Desea habilitar el estacionamiento de [llamadas y](call-park-and-retrieve.md) la recuperación en su organización para ayudar a realizar entregas de llamadas entre personas o departamentos?
- Para las indicaciones de voz, ¿desea grabar la suya propia o usar la voz generada por el sistema? (La voz generada por el sistema es fácil de actualizar).

## <a name="technical-decisions"></a>Decisiones técnicas

Al usar operadores automáticos y colas de llamadas para conectar llamadas a personas de su organización, hay algunas decisiones técnicas que debe tomar antes de iniciar la configuración.

Los agentes se pueden agregar a las colas de llamadas de las siguientes maneras:

- Usuarios individuales
- Listas de distribución
- Grupos de seguridad, incluidos los grupos de seguridad habilitados para correo
- Grupos o equipos de Microsoft 365

Puede usar una combinación de estas opciones para cada cola si es necesario. Los grupos que tienen una dirección de correo electrónico se pueden usar para el correo de voz. El uso de Teams ofrece una serie de ventajas, como el almacenamiento de archivos compartidos y el chat entre agentes, un buzón común donde se pueden recibir correos de voz y una plataforma extensible que puede incluir la integración con su línea de aplicaciones empresariales o Power Apps.

Se recomienda elegir una estrategia para agregar agentes de llamadas a las colas antes de iniciar la configuración.

Si tiene un operador automático y una infraestructura de cola de llamadas existentes y está migrando a Teams, necesitará un plan para transferir los números de teléfono existentes a los nuevos operadores automáticos y las colas de llamadas. Es posible que tenga que crear una orden [de portabilidad](phone-number-calling-plans/port-order-overview.md) para mover los números de otros proveedores. Le recomendamos que adquiera temporalmente uno o varios números de teléfono nuevos y que pruebe los flujos de la cola de llamadas y el operador automático antes de cambiarlos por los números que tiene actualmente en servicio.

*El modo de* conferencia es una opción en las colas de llamadas que reduce significativamente la cantidad de tiempo que se tarda en conectar las llamadas VOIP de Teams y las llamadas RTC a un agente. Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:

- Última versión del cliente de escritorio de Microsoft Teams, la aplicación de Android o la aplicación de iOS
  - Versión de teléfono 1449/1.0.94.2020051601 o posterior de Microsoft Teams
  
Establezca las cuentas de Teams de los agentes en el modo solo para equipos. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.

Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

## <a name="plan-your-call-routing-flow"></a>Planear el flujo de enrutamiento de llamadas

Como parte del proceso de planificación, le recomendamos que trabaje el enrutamiento de llamadas para su organización en un diagrama. El diagrama ayuda a determinar el enrutamiento más eficaz para las personas que llaman a su organización. También puede usar el diagrama para determinar los operadores automáticos y las colas de llamadas que necesita crear, junto con requisitos relacionados como números de servicio, licencias y cuentas de recursos.

Veamos cómo los operadores automáticos y las colas de llamadas enruta las llamadas.

Los operadores automáticos enrutar todas las llamadas de una de las siguientes maneras:

- **Redirigir inmediatamente:** las llamadas se pueden redirigir a uno de los destinos de enrutamiento de llamadas (se muestra a continuación) inmediatamente después de responder o después de un saludo inicial.
- **Redirigir según las opciones de** marcado: se puede dirigir a los autores de llamadas para que elijan entre las opciones asignadas a los números de su teclado telefónico, 0-9. A cada tecla de marcado se le puede asignar un destino de enrutamiento de llamadas.
- **Marcar a** las personas por nombre o extensión: se puede dirigir a los autores de llamadas para que marquen el número de extensión de la persona a la que están intentando contactar en el directorio de su organización, o bien deletrear el nombre de la persona.
- **Desconectar:** un operador automático puede colgar la llamada.

> [!NOTE]
> Un solo operador automático solo puede admitir un único método de "marcado por".  Para permitir que los autores de llamadas marquen por nombre y por número, deberá crear un operador automático que tenga una opción para marcar por nombre y la otra para marcar por extensión.  Cada una de estas opciones se dirigirá a operadores automáticos separados configurados para estos escenarios de "marcado por".

Cuando un operador automático o una cola de llamadas redirigen las llamadas, puede elegir entre los siguientes destinos de enrutamiento de llamadas:

- **Persona de la organización:** una persona de su organización que puede recibir llamadas de voz. Puede ser un usuario en línea o un usuario hospedado localmente con Skype Empresarial Server.
- **Aplicación de voz:** otro operador automático o una cola de llamadas. Elija la cuenta de recursos asociada al destino.
- **Número de teléfono externo:** cualquier número de teléfono. (Vea [detalles técnicos de transferencia externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Correo de** voz: el buzón de voz asociado a un grupo de Microsoft 365 que especifique.
- **Operador** (solo operador automático): el operador definido para el operador automático. Definir un operador es opcional. Un operador puede ser cualquiera de los otros destinos de esta lista.

Los operadores automáticos ofrecen opciones de enrutamiento de llamadas independientes para las llamadas recibidas fuera del horario laboral y en días festivos. El enrutamiento de llamadas después del horario laboral permite todas las opciones enumeradas anteriormente, mientras que el enrutamiento de llamadas navideñas solo permite redirigir o desconectar una llamada, pero no opciones de clave de marcado.

Las colas de llamadas ponen al autor de la llamada en espera hasta que un agente asignado a la cola esté disponible para realizar la llamada. Hay dos situaciones en las que un autor de la llamada podría salir de la cola:

- **Desbordamiento de** llamadas: si el número de llamadas en la cola supera el límite establecido, los nuevos autores de llamadas se redirigirán fuera de la cola.
- **Tiempo de espera de** llamada: si un autor de la llamada ha estado en la cola más tiempo que la configuración de tiempo de espera configurada, se redirige fuera de la cola.

Las llamadas redirigidos fuera de una cola se pueden enviar a cualquiera de los destinos de enrutamiento de llamadas enumerados anteriormente, excepto para un operador. (Las colas de llamadas no tienen operadores, pero puede redirigir a los autores de llamadas al mismo destino que un operador que haya configurado para un operador automático).

En el ejemplo siguiente se muestra un ejemplo de enrutamiento de llamadas con operadores automáticos y colas de llamadas.

![Diagrama de enrutamiento de llamadas con operadores automáticos y colas de llamadas](media/attendant-and-queue-call-routing.png)

En el ejemplo anterior:

- La tecla cero (0) redirige a los autores de llamadas a un operador. El operador de ese operador automático se ha configurado como **una persona de la organización.**
- La clave de una (1) redirige a los autores de llamadas a la cola de llamadas de ventas. Esta cola de llamadas está conectada a un equipo que contiene el equipo de ventas asignado a la cola.
- La tecla dos (2) redirige a los autores de llamadas a la cola de llamadas de soporte técnico. Esta cola de llamadas está conectada a un equipo que contiene el equipo de soporte técnico asignado al equipo.
- La cola de llamadas de soporte técnico tiene un número de teléfono directo a través de un operador automático que interviene. Tener un operador automático responde la línea de soporte técnico permite el enrutamiento de llamadas navideñas y de horas no trabajada.
- La clave de tres (3) redirige a los usuarios a otro operador automático para el directorio de la empresa. El operador automático del directorio de la empresa permite a los autores de llamadas llamar a personas de la organización marcando su nombre o extensión.

Le recomendamos que cree uno o varios diagramas similares al anterior para asignar el enrutamiento de llamadas. Asegúrese de incluir lo siguiente en el diagrama o en la documentación que lo acompaña:

- ¿Qué operadores automáticos tendrán acceso directo a través de números de teléfono?
- ¿Cuáles son los requisitos de enrutamiento fuera de horarios y vacaciones para cada operador automático?
- La pertenencia a cada cola de llamadas. (Puede agregar usuarios individualmente o asignar la cola a diferentes tipos de grupos. Asignar una cola a un equipo proporciona la experiencia más versátil).

Estos son algunos procedimientos recomendados de enrutamiento de llamadas:

- Mire el sistema de llamadas existente y analice los tipos y la frecuencia de las llamadas entrantes. Use esta información para ayudar a informar a su operador automático y a la estructura de la cola de llamadas.
- Coloque las opciones más comunes lo antes posible en el menú para enrutar las llamadas lo antes posible.
- Evite conectar números de servicio directamente a las colas de llamadas a menos que las colas estén disponibles las 24 horas del día, los 7 días de la noche. Las colas de llamadas no permiten el tratamiento de llamadas por separado durante horas o días festivos. Si desea tener una cola con un número directo, asigne el número a un operador automático que redirige automáticamente a la cola durante el horario laboral.
- Si recibe numerosas llamadas solicitando información básica sobre su empresa, como el horario laboral, la ubicación o la dirección del sitio web, considere la posibilidad de crear un operador automático para responder a estas preguntas con mensajes grabados.
- Mantenga la lista de elementos de menú en cinco o menos. Los autores de llamadas pueden tener problemas para recordar más de cinco opciones. Use operadores automáticos anidados si se necesitan más opciones para enrutar correctamente una llamada.
- Describa el servicio en primer lugar, seguido de la opción de presionar (por ejemplo: Para ventas presione 1) en lugar de al revés (por ejemplo. Presione 1 para Ventas).
- Terminología de usuario que los autores de llamadas comprenderán en lugar de lo que puede usar internamente.
- Evite actualizaciones frecuentes para el enrutamiento de llamadas. Si cambia las opciones de menú de un operador automático en el futuro, resálalo en las indicaciones de voz durante los primeros 30 días.

## <a name="getting-started"></a>Introducción

Una vez que haya completado las tareas de planificación de este artículo, siga estos pasos para configurar los operadores automáticos y las colas de llamadas:

1. Obtenga los números de servicio que necesita para los operadores automáticos y las colas de llamadas a las que desea que se pueda acceder mediante el marcado directo desde fuera de su organización. Esto puede incluir [la transferencia de números de otro proveedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la solicitud de nuevos números de [servicio.](getting-service-phone-numbers.md)

2. Obtener un [sistema telefónico: licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) para cada cuenta de recursos que tiene previsto crear. Estas licencias son gratuitas, por lo que le recomendamos obtener algunas adicionales en caso de que decida realizar cambios en sus cuentas de recursos en el futuro.

3. [Cree una cuenta de recursos](manage-resource-accounts.md) para cada operador automático y la cola de llamadas que desee crear. Asigne a cada cuenta una licencia de Usuario virtual y, opcionalmente, un número de servicio.

4. [Cree los días festivos](set-up-holidays-in-teams.md) para los que desea tener enrutamiento de llamadas independiente en los operadores automáticos.

5. Opcionalmente, [configure el estacionamiento de llamadas](call-park-and-retrieve.md) y la recuperación si desea usar esta característica para ayudar con las transferencias de llamadas.

6. Cree los grupos que desee usar para contener los agentes de llamadas para las colas de llamadas.

7. Si tiene previsto permitir el marcado por extensión, asegúrese de que ha agregado el número de extensión de los usuarios a su perfil de Azure Active Directory.

Una vez que haya completado los pasos anteriores, estará listo para crear los operadores automáticos y las colas de llamadas. Como los operadores automáticos y las colas de llamadas pueden redirigir las llamadas entre sí, consulte el diagrama de flujo de trabajo que ha creado para determinar qué operador automático o cola de llamadas se deben crear primero. En el ejemplo del diagrama anterior, crearía las colas de llamadas de soporte técnico y ventas antes de crear el operador automático principal de Contoso, ya que el operador automático principal debe dirigir a los autores de llamadas a las colas de llamadas de soporte técnico y ventas.

Vea los artículos siguientes para obtener información sobre cómo crear operadores automáticos y colas de llamadas:

- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Temas relacionados

[Planear el enrutamiento directo](direct-routing-plan.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Crear una cola de llamadas: tutorial para pequeñas empresas](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurar un operador automático : tutorial de pequeña empresa](business-voice/create-a-phone-system-auto-attendant-smb.md)
