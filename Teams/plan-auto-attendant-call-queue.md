---
title: Planear los operadores automáticos de Teams y las colas de llamadas
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
description: Obtenga más información sobre los operadores automáticos y las colas de llamadas, y sobre cómo usarlos para que las personas que llaman puedan moverse por un sistema de menús para llegar a personas o departamentos de su organización.
ms.openlocfilehash: ece138b3e3513273b57d980442f46f683aaddda4
ms.sourcegitcommit: 5a013b4c0a8d23d33ab9e9147991f2b3b7247693
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "48748902"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planear los operadores automáticos de Teams y las colas de llamadas

Los operadores automáticos permiten configurar opciones de menú para enrutar llamadas según la entrada de la persona que llama. Opciones de menú ("para ventas, presione 1.  Para los servicios Pulse 2 ") para un operador automático que permita a una organización ofrecer una serie de opciones que guíen a los autores de las llamadas a su destino rápidamente, sin depender de que un operador humano controle las llamadas entrantes.


Las colas de llamadas son áreas de espera para las personas que llaman. Para las situaciones en las que las personas que llaman deben comunicarse con una especialidad en particular, como las ventas o el servicio, en lugar de una persona específica, puede usar colas de llamadas para conectar a los autores de las llamadas con el grupo de agentes que pueden ayudarle. Las personas que llaman se ponen en espera hasta que un agente asignado a la cola esté disponible para realizar su llamada.

Si se usan conjuntamente, los operadores automáticos y las colas de llamadas pueden enrutar fácilmente a las personas que llaman a la persona o al departamento correspondiente de su organización.

## <a name="auto-attendants"></a>Operadores automáticos

El propósito principal de un operador automático es dirigir a una persona que llama a una persona o departamento adecuado en función de la entrada de la llamada a las opciones de menú proporcionadas. Las personas que llaman pueden dirigirse a personas específicas de su organización, a colas de llamadas, donde esperan para comunicarse con el siguiente agente disponible o al buzón de voz. Se pueden especificar diferentes opciones de enrutamiento de llamadas para el horario laboral, las horas de inactividad y los días festivos.

Las indicaciones de menú se pueden crear con texto a voz (mensajes generados por el sistema) o mediante la carga de un archivo de audio grabado. El reconocimiento de voz acepta comandos de voz gratis, pero las personas que llaman también pueden usar el teclado del teléfono para navegar por los menús.

Cada operador automático tiene un idioma y una zona horaria específicos. Si haces negocios en varios idiomas o en varias partes del mundo, puedes crear tantos operadores automáticos diferentes como necesites para acomodar a las personas que llaman.

Para cada operador automático, puede configurar un operador. Aunque puede configurar las llamadas de operador para ir a una variedad de destinos, la característica de operador está diseñada para permitir a los autores de llamadas hablar con una persona específica de su organización que pueda ayudarle.

Los operadores automáticos pueden configurarse para permitir que las personas que llaman puedan buscar en el directorio de su organización, ya sea por nombre o por número de extensión. Dentro de un operador automático, puede especificar las personas que están disponibles para la búsqueda en el directorio seleccionando grupos de usuarios para incluir o excluir. (Esto se conoce como *ámbito de marcado*).

Las personas que llaman pueden comunicarse con un operador automático mediante un número de teléfono directo, si está configurado, o mediante su redireccionamiento desde otro operador automático o una cola de llamadas.

## <a name="call-queues"></a>Colas de llamadas

Una cola de llamadas es análoga a una sala de espera en un edificio físico. Las personas que llaman esperan en espera mientras las llamadas se enrutan a los agentes de la cola a medida que estén disponibles. Las colas de llamadas suelen usarse para las ventas y las funciones de servicio, pero se pueden usar en cualquier situación en la que el número de llamadas supere su capacidad interna, como una recepcionista en un centro de ocupado.

Las colas de llamadas permiten el enrutamiento específico de llamadas en aquellos casos en los que el número total de llamadas de la cola o el tiempo de espera supera los límites especificados. Las llamadas se pueden enrutar a personas específicas, buzón de voz, otras colas de llamadas o operadores automáticos.

Al igual que los operadores automáticos, las colas de llamadas tienen una configuración de idioma. Puede usar diferentes colas de llamadas si realiza negocios en varios idiomas. Los agentes pueden ser miembros de más de una cola si son multilingües.

Para cada cola de llamadas, puede especificar si los agentes de la cola pueden optar por no tomar llamadas y si las llamadas se deben dirigir en función de su indicación de presencia en Teams.

Puede asignar un número de teléfono a una cola de llamadas, pero las colas de llamadas no proporcionan un enrutamiento de llamadas por separado por horas y vacaciones. A menos que su cola de llamadas tenga personal 24/7, le recomendamos asignar el número de teléfono a un operador automático que redirige a la cola de llamadas durante el horario comercial.

## <a name="prerequisites"></a>Requisitos previos

Para configurar los operadores automáticos y las colas de llamadas, necesita lo siguiente:

- Una cuenta de recursos para cada operador automático y cola de llamadas
- Un sistema telefónico gratis: licencia de usuario virtual para cada cuenta de recursos
- Un número de servicio para cada operador automático o cola de llamadas que desee que se marquen directamente
- Plan de llamadas para cada persona que recibirá llamadas en la cola de llamadas

> [!NOTE]
> Los números del servicio de enrutamiento directo para las colas de llamadas y los usuarios de Microsoft Teams solo son compatibles con los usuarios de Microsoft Teams y los agentes de llamadas.

## <a name="business-decisions"></a>Decisiones empresariales

Antes de configurar los operadores automáticos y las colas de llamadas, hay algunas decisiones que debe tomar acerca de cómo usar estas características en su empresa. Estas decisiones determinarán la configuración que elige al configurar los operadores automáticos y las colas de llamadas.

Documente sus respuestas a estas preguntas y proporcione la información que el administrador realice en la configuración.

- ¿Qué idiomas necesita? ¿Dónde se necesitan estos idiomas: ¿qué departamento o grupo?
- ¿Deseas permitir las entradas de voz de las personas que llaman o solo las entradas de marcado?
- ¿Necesitas un enrutamiento de llamadas por separado por horas de inactividad o días festivos? ¿Cuáles son las horas y las vacaciones?
- ¿Deseas permitir que los agentes de una cola de llamadas puedan optar por recibir llamadas?
- ¿Desea que los agentes de las colas de llamadas o el operador tengan un identificador de llamada específico si llaman? 
- ¿Desea habilitar el [aparcamiento de llamadas y la recuperación](call-park-and-retrieve.md) de su organización para ayudarle a llamar a entregas entre personas o departamentos?
- Para las solicitudes de voz, ¿desea grabar la suya propia o usar la voz generada por el sistema? (La actualización de la voz generada por el sistema es muy sencilla).

## <a name="technical-decisions"></a>Decisiones técnicas

Al usar los operadores automáticos y las colas de llamadas para conectar a los autores de las llamadas a las personas de su organización, hay que tomar decisiones técnicas antes de iniciar la configuración.

Los agentes se pueden agregar a las colas de llamadas de las siguientes maneras:

- Usuarios individuales
- Listas de distribución
- Grupos de seguridad, incluidos los grupos de seguridad habilitados para correo
- Grupos o equipos de Microsoft 365

Puede usar una combinación de estas opciones para cada cola, si es necesario. Los grupos que tienen una dirección de correo electrónico se pueden usar para el buzón de voz. El uso de Teams ofrece varias ventajas, entre las que se incluyen el almacenamiento de archivos compartidos y el chat entre agentes, un buzón común donde se pueden recibir los mensajes de voz y una plataforma ampliable que puede incluir la integración con las aplicaciones de línea de negocio o Power apps.

Le recomendamos que elija una estrategia para agregar agentes de llamadas a las colas antes de comenzar la configuración.

Si tiene una infraestructura de cola de llamadas y un operador automático existentes y va a migrar a Teams, necesitará un plan para transferir los números de teléfono existentes a los nuevos operadores automáticos y colas de llamadas. Es posible que tenga que crear una [solicitud de portabilidad](phone-number-calling-plans/port-order-overview.md) para mover los números de otros proveedores. Le recomendamos que adquiera temporalmente uno o varios números de teléfono nuevos y pruebe el operador automático y los flujos de cola de llamadas antes de cambiarlos por los números que tiene en servicio.

El *modo de conferencia* es una opción de las colas de llamadas que reduce significativamente la cantidad de tiempo que se tarda en conectar las llamadas VoIP de Teams y las llamadas RTC a un agente. Para que el modo de conferencia funcione, los agentes de la cola de llamadas deben usar uno de los siguientes clientes:

  - La versión más reciente del cliente de escritorio de Microsoft Teams, la aplicación Android o la aplicación iOS
  - Microsoft Teams Phone versión 1449/1.0.94.2020051601 o posterior
  
Las cuentas de los agentes de Teams deben establecerse en el modo de solo equipos. Los agentes que no cumplan con los requisitos no se incluyen en la lista de enrutamiento de llamadas.

Recomendamos habilitar el modo de conferencia para las colas de llamadas si todos los agentes usan clientes compatibles.

> [!NOTE]
> El modo de conferencia no admite el uso ocupado en ocupado. Es posible que los agentes de las llamadas a colas que no sean de llamadas sigan apareciendo con una llamada en la cola de llamadas si el enrutamiento basado en presencia no está habilitado.

## <a name="plan-your-call-routing-flow"></a>Planear el flujo de enrutamiento de llamadas

Como parte del proceso de planeación, le recomendamos que destaque el enrutamiento de llamadas de su organización en un diagrama. Esto le ayudará a determinar el enrutamiento más eficaz para las personas que llaman a su organización. También puede usar el diagrama para determinar los operadores automáticos y las colas de llamadas que necesita crear, junto con los requisitos relacionados, como números de servicio, licencias y cuentas de recursos.

Echemos un vistazo a cómo los operadores automáticos y las colas de llamadas enrutan las llamadas.

Los operadores automáticos enrutan todas las llamadas de una de las siguientes maneras:

- El **redireccionamiento de llamadas inmediatas** puede redirigirse a uno de los destinos de enrutamiento de llamadas (enumerados a continuación) inmediatamente después de contestar o después de un saludo inicial.
- **Redireccionamiento basado en las opciones de marcado: las** personas que llaman pueden dirigirse para elegir entre las opciones que se asignan a los números en el teclado del teléfono, 0-9. A cada tecla de marcado se le puede asignar un destino de enrutamiento de llamadas.
- Las personas que llaman **por nombre o extensión** pueden dirigirse a las personas que llaman para marcar el número de extensión de la persona a la que están tratando en el directorio de su organización, o bien pueden escribir el nombre de la persona.
- **Desconectar** : un operador automático puede colgar la llamada.

> [!NOTE]
> Un solo operador automático solo puede admitir un único método de "marcado por".  Para permitir que las personas que llaman llamen por nombre y número, tendrá que crear un operador automático que tenga una opción de marcado por nombre y otra para marcar por extensión.  Cada una de estas opciones se redirigirá a attenants automático configurado para estos escenarios de "marcado por". 

Cuando las llamadas son redirigidas por un operador automático o una cola de llamadas, puede elegir entre los siguientes destinos de enrutamiento de llamadas:

- **Persona de la organización** : una persona de su organización que puede recibir llamadas de voz. Puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server.
- **Aplicación de voz** : otro operador automático o una cola de llamadas. Elija la cuenta de recursos asociada al destino.
- **Número de teléfono externo** , cualquier número de teléfono. (Consulta los [detalles técnicos de la transferencia externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- Buzón de **voz: el buzón de voz** asociado a un grupo de Microsoft 365 que especifique.
- **Operador** (solo operador automático): operador definido para el operador automático. Definir un operador es opcional. Un operador puede ser cualquiera de los otros destinos de esta lista.

Los operadores automáticos ofrecen opciones de enrutamiento de llamadas por separado para las llamadas que se reciben fuera de las horas laborales y de los días festivos. El enrutamiento de llamadas después de las horas permite todas las opciones enumeradas anteriormente, mientras que el enrutamiento de llamadas de días no laborables permite redireccionar o desconectar una llamada, pero no las opciones de teclas de marcado.

Las colas de llamadas ponen la llamada en espera hasta que un agente asignado a la cola esté disponible para realizar su llamada. Hay dos situaciones en las que una persona que llama puede dirigirse fuera de la cola:

- **Desbordamiento** de la llamada: Si el número de llamadas de la cola supera el límite establecido, las nuevas llamadas se redirigirán fuera de la cola.
- **Tiempo de espera** de la llamada: Si una llamada ha permanecido más tiempo que la configuración del tiempo de espera configurado, se redirigen fuera de la cola.

Las llamadas redirigidas fuera de una cola pueden enviarse a cualquiera de los destinos de enrutamiento de llamadas enumerados anteriormente, excepto para un operador. (Las colas de llamadas no tienen operadores, pero puedes redirigir a las personas que llaman al mismo destino como un operador que hayas configurado para un operador automático).

En el ejemplo siguiente se muestra un ejemplo de enrutamiento de llamadas con operadores automáticos y colas de llamadas.

![](media/attendant-and-queue-call-routing.png)

En el ejemplo anterior:
- La tecla cero (0) redirige a las personas que llaman a un operador. El operador de ese operador automático se ha configurado como una **persona de la organización**.
- La tecla One (1) redirige a los autores de las llamadas la cola de llamadas de ventas. Esta cola de llamadas está conectada a un equipo que contiene el equipo de ventas asignado a la cola.
- La tecla dos (2) redirige a las personas que llaman a la cola de llamadas de asistencia. Esta cola de llamadas está conectada a un equipo que contiene el equipo de soporte técnico asignado al equipo.
- La cola de llamadas de asistencia tiene un número de teléfono directo a través de un operador automático intermedio. Tener una respuesta de operador automático la línea de soporte técnico le permite separar las horas y el enrutamiento de llamadas.
- La clave tres (3) redirige a los usuarios a otro operador automático para el directorio de la empresa. El operador automático de directorio de la empresa permite que las personas que llaman llamen a su nombre o extensión.

Le recomendamos que cree uno o varios diagramas similares a los anteriores para realizar el enrutamiento de las llamadas. Asegúrese de incluir lo siguiente en el diagrama o en la documentación adjunta:

- ¿Qué operadores automáticos tendrán acceso directo a través de números de teléfono?
- ¿Cuáles son los requisitos de enrutamiento fuera de horario laboral y vacaciones para cada operador automático?
- La pertenencia a cada cola de llamadas. (Puede Agregar usuarios individualmente o asignar la cola a distintos tipos de grupos. La asignación de una cola a un equipo proporciona la experiencia más versátil.)

Estos son algunos procedimientos recomendados para el enrutamiento de llamadas:

- Mira el sistema de llamadas que ya tengas y analiza los tipos y la frecuencia de las llamadas entrantes. Use esta información para ayudar a informar a su operador automático y a la estructura de la cola de llamadas.
- Coloque las opciones más comunes en el menú para enrutar las llamadas tan rápido como sea posible.
- Evite conectar números de servicio directamente a colas de llamadas a menos que las colas estén disponibles 24/7. Las colas de llamadas no permiten un control de llamadas por separado por horas de inactividad o días no laborables. Si desea tener una cola con un número directo, asigne el número a un operador automático que se redirija automáticamente a la cola durante el horario comercial.
- Si recibe una gran cantidad de llamadas solicitando información básica sobre su empresa, como el horario comercial, la ubicación o la dirección del sitio web, considere la posibilidad de crear un operador automático para responder a estas preguntas con los mensajes grabados.
- Mantenga la lista de elementos de menú a cinco o menos. Las personas que llamen pueden tener problemas para recordar más de cinco opciones. Use operadores automáticos anidados si necesita más opciones para enrutar una llamada correctamente.
- Describa el servicio en primer lugar, seguido de la opción de pulsar (por ejemplo, para la prensa de ventas 1) en lugar de la otra forma de hacerlo (por ejemplo: Pulse 1 para ventas). 
- Terminología de usuario que las personas que llaman entienden, en lugar de lo que usted puede usar internamente.
- Evite realizar actualizaciones frecuentes para llamar al enrutamiento. Si cambias las opciones de menú para un operador automático en el futuro, puedes llamarlo en las solicitudes de voz durante los primeros 30 días.

## <a name="resource-accounts-and-phone-numbers"></a>Cuentas de recursos y números de teléfono

Teams usa *[cuentas de recursos](manage-resource-accounts.md)* para conectar los operadores automáticos y las colas de llamadas entre sí y asignarles números de teléfono si así lo desea.

- Cada cola de llamadas y operador automático requiere al menos una cuenta de recursos.
- Cada cuenta de recursos requiere un sistema telefónico gratis (licencia de usuario virtual).
- De forma opcional, una cuenta de recursos puede tener asignados uno o más números de servicio. (Esta es la forma en que se asignan los números de teléfono a los operadores automáticos y las colas de llamadas).

Puede asignar un número de [servicio de Microsoft](getting-service-phone-numbers.md), un número de enrutamiento directo o un número híbrido a una cuenta de recursos.

Puede usar números de servicio de pago o gratuitos. No puede usar números de teléfono de usuario para los operadores automáticos ni las colas de llamadas.

## <a name="getting-started"></a>Introducción

Una vez que haya completado las tareas de planeación de este artículo, siga estos pasos para configurar los operadores automáticos y las colas de llamadas:

1. Obtenga los números de servicio que necesita para los operadores automáticos y las colas de llamadas a las que desea que tengan acceso telefónico directo desde fuera de su organización. Esto podría incluir la [transferencia de números de otro proveedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la [solicitud de números de servicio nuevos](getting-service-phone-numbers.md).

2. Obtener un [sistema telefónico: licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) para cada cuenta de recursos que tenga previsto crear. Estas licencias son gratuitas, por lo que le sugerimos que haga algunas opciones adicionales en caso de que decida realizar cambios en las cuentas de recursos en el futuro.

3. [Cree una cuenta de recursos](manage-resource-accounts.md) para cada operador automático y cola de llamadas que desee crear. Asigne a cada cuenta un sistema telefónico: licencia de usuario virtual y, opcionalmente, un número de servicio.

4. [Cree los días no laborables](set-up-holidays-in-teams.md) para los que desea tener un enrutamiento de llamadas independiente en los operadores automáticos.

5. De manera opcional, puedes [configurar el aparcamiento y la recuperación de llamadas](call-park-and-retrieve.md) si deseas usar esta característica para facilitar la transferencia de llamadas.

6. Cree los grupos que desee usar para contener los agentes de llamadas de las colas de llamadas.

7. Si tiene previsto permitir el marcado por extensión, asegúrese de haber agregado el número de extensión de los usuarios a su perfil de Azure Active Directory.

Una vez que haya completado los pasos anteriores, estará listo para crear los operadores automáticos y las colas de llamadas. Dado que los operadores automáticos y las colas de llamadas pueden redirigir las llamadas entre sí, consulte el diagrama de flujo de trabajo que ha creado para determinar qué operador automático o cola de llamadas se debe crear primero. En el ejemplo del diagrama anterior, crearía las colas de llamadas de ventas y de soporte técnico antes de crear el operador automático principal de Contoso porque el operador automático principal necesita llamar a las colas de llamadas de ventas y de soporte técnico.

Consulte los artículos siguientes para obtener información sobre cómo crear operadores automáticos y colas de llamadas:

- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Temas relacionados

[Planear el enrutamiento directo](direct-routing-plan.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)
