---
title: Planear operadores automáticos y colas de llamadas de Teams
author: DaniEASmith
ms.author: danismith
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
- highpri
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
description: Obtenga información sobre operadores automáticos y colas de llamadas, y cómo usarlos para ayudar a los autores de llamadas a desplazarse por un sistema de menús para ponerse en contacto con personas o departamentos de su organización.
ms.openlocfilehash: acaa4d3e4db56b1b64869f92d27f2dfd73c4afee
ms.sourcegitcommit: 0dfe48fde767d8d9ed7bfc93684af05534acad12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2022
ms.locfileid: "69166736"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planear operadores automáticos y colas de llamadas de Teams

Los operadores automáticos le permiten configurar opciones de menú para enrutar llamadas en función de la entrada del autor de la llamada. Las opciones de menú de un operador automático (como "Para ventas, presione 1)Para Servicios, presione 2", permiten que una organización proporcione una serie de opciones que guían a los autores de llamadas a su destino rápidamente, sin necesidad de que un operador humano controle las llamadas entrantes.

Las colas de llamadas son áreas de espera para los autores de llamadas. Para las situaciones en las que los autores de llamadas necesitan ponerse en contacto con alguien con una especialidad determinada (como ventas o servicio) en lugar de con una persona específica, puede usar colas de llamadas para conectar los autores de llamadas con el grupo de agentes que pueden ayudarle. Los autores de llamadas se ponen en espera hasta que un agente asignado a la cola esté disponible para realizar su llamada.

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

Para cada cola de llamadas, puede especificar si los agentes de la cola pueden optar por no recibir llamadas y si las llamadas se deben enrutar a ellos en función de su indicación de presencia en Teams.

Puede asignar un número de teléfono a una cola de llamadas, pero las colas de llamadas no proporcionan un enrutamiento de llamadas independiente para los períodos no laborables y festivos. A menos que la cola de llamadas esté atendida las 24 horas del día, se recomienda asignar el número de teléfono a un operador automático que redirija a la cola de llamadas durante el horario laboral.

## <a name="prerequisites"></a>Requisitos previos

Para configurar operadores automáticos y colas de llamadas, necesita los siguientes recursos:

- Una [cuenta de recursos](manage-resource-accounts.md) para cada operador automático y cada cola de llamadas.
- Una [licencia gratuita Teléfono Microsoft Teams cuenta de](teams-add-on-licensing/virtual-user.md) recursos para cada cuenta de recursos a la que se podrá marcar directamente desde usuarios de Teams o números de teléfono externos.
- Al menos un [número de servicio de Microsoft](getting-service-phone-numbers.md), [un número De conexión del operador](operator-connect-plan.md), un [número de enrutamiento directo](direct-routing-plan.md) o un número híbrido para cada cuenta de recursos a la que quiera llamar directamente desde números de teléfono externos.
  - El número de servicio puede ser un número de pago o gratuito.

> [!NOTE]
> Las cuentas de recursos están deshabilitadas para iniciar sesión y deben permanecer así. El chat y la presencia no están disponibles para estas cuentas.

Los agentes que reciben llamadas de las colas de llamadas deben estar Telefonía IP empresarial habilitados para los usuarios en línea o locales. Además, si las colas de llamadas usan números de enrutamiento directo, los agentes que necesitan realizar conferencias o transferir llamadas también requieren:

- Una [directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md) asignada si la cola de llamadas usa el modo de transferencia.
- Una [licencia de Audioconferencia](set-up-audio-conferencing-in-teams.md) o [una directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md) asignada si la cola de llamadas usa el modo de conferencia.

Si sus agentes usan la aplicación Microsoft Teams para llamadas de la cola de llamadas, deben estar en el modo TeamsOnly.

Al usar una cuenta de recursos para fines de id. de línea de llamadas en colas de llamadas, la cuenta de recursos debe tener asignada una licencia de cuenta de recursos de Teléfono de Teams y una de las siguientes opciones:

- Una licencia [del plan de llamadas](calling-plans-for-office-365.md) y un número de teléfono asignados.
- Un [número de teléfono Operador Conectar](operator-connect-plan.md) asignado.
- Una [directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md).
  - La asignación de número de teléfono es opcional al usar enrutamiento directo.

Cuando un operador automático o una cola de llamadas transfiere llamadas a un número externo, las cuentas de recursos específicas, como se describe a continuación, deben tener asignada una licencia de cuenta de recursos de Teléfono de Teams y una de las siguientes opciones:

- Una licencia [del plan de llamadas](calling-plans-for-office-365.md) y un número de teléfono asignados.
- Un [número de teléfono Operador Conectar](operator-connect-plan.md) asignado.
- Una [directiva de enrutamiento de voz en línea](manage-voice-routing-policies.md).
  - La asignación de número de teléfono es opcional al usar enrutamiento directo.

Qué cuenta de recursos licenciar:

- Licenciar la cuenta de recursos en el primer operador automático que recibe la llamada cuando ese operador automático se transfiere a otros operadores automáticos o colas de llamadas que transfieren llamadas externamente.
- En todos los demás escenarios de llamadas, licencia la cuenta de recursos del operador automático o de la cola de llamadas que realiza la transferencia externa.

> [!NOTE]
> Si se deshabilita o se quita el plan de llamadas asignado a la cuenta de recursos, se consumirán [créditos de comunicaciones](what-are-communications-credits.md), si están disponibles en el inquilino (sin asignarse a la cuenta de recursos). Si no hay ningún plan de llamadas o créditos de comunicaciones, se producirá un error en la llamada.
>
> Los números de servicio de enrutamiento directo para operadores automáticos y colas de llamadas solo son compatibles con Microsoft los usuarios de Teams y los agentes de llamadas.
> 
> Las transferencias entre los troncos Plan de llamadas, Conexión de operador y Enrutamiento directo no son compatibles.
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
- Para las indicaciones de voz, ¿desea grabar la suya propia o usar la voz generada por el sistema?
  - La voz generada por el sistema es fácil de actualizar.

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

**El modo de conferencia** es una opción en las colas de llamadas que reduce significativamente la cantidad de tiempo que se tarda en conectar llamadas VOIP de Teams y llamadas RTC a un agente. Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:

- La última versión de la Microsoft el cliente de escritorio de Teams, la aplicación de Android o la aplicación de iOS.
- Microsoft versión 1449/1.0.94.2020051601 o posterior.
  
Establezca las cuentas de Teams de los agentes en el modo solo de Teams. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas.

Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

Los planes de **flujo de enrutamiento de llamadas** ayudan a determinar el enrutamiento más eficaz para las personas que llaman a su organización. Para obtener información sobre cómo planear el flujo de enrutamiento de llamadas, consulte [Planear el flujo de enrutamiento de llamadas](plan-your-call-routing-flow.md).

## <a name="getting-started"></a>Introducción

Una vez que haya completado las tareas de planeación de este artículo, siga estos pasos para configurar los operadores automáticos y las colas de llamadas:

1. Obtenga los números de servicio que necesita para los operadores automáticos y las colas de llamadas a los que desea que se pueda obtener acceso mediante marcado directo desde fuera de su organización. Esto puede incluir [transferir números de otro proveedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [solicitar nuevos números de servicio](getting-service-phone-numbers.md).

2. Obtenga una [licencia de cuenta de recursos de Teléfono de Teams](teams-add-on-licensing/virtual-user.md) para cada cuenta de recursos que planee crear. Estas licencias son gratuitas, por lo que le recomendamos que obtenga algunos adicionales por si decide realizar cambios en sus cuentas de recursos en el futuro.

3. [Cree una cuenta de recursos](manage-resource-accounts.md) para cada operador automático y cola de llamadas que desee crear. Asigne una licencia de cuenta de recursos telefónicos de Teams a cada cuenta de recursos a la que se pueda llamar directamente y, opcionalmente, un número de servicio.

4. [Cree los días festivos](set-up-holidays-in-teams.md) para los que desea tener un enrutamiento de llamadas independiente en los operadores automáticos.

5. Opcionalmente, [configure el estacionamiento y la recuperación de llamadas](call-park-and-retrieve.md) si desea usar esta característica para ayudarle con las transferencias de llamadas.

6. Cree los grupos que desee usar para contener los agentes de llamadas de las colas de llamadas.

7. Si tiene previsto permitir el marcado por extensión, asegúrese de que ha agregado el número de extensión de los usuarios a su perfil de Azure Active Directory (Azure AD).

Una vez que haya completado los pasos anteriores, estará listo para crear sus operadores automáticos y colas de llamadas. Como los operadores automáticos y las colas de llamadas pueden redirigir las llamadas entre sí, consulte el diagrama de flujo de trabajo que ha creado para determinar qué operador automático o cola de llamadas se debe crear primero. En el ejemplo del diagrama anterior, crearía las colas de llamadas de ventas y soporte técnico antes de crear el operador automático principal de Contoso, ya que el operador automático principal debe dirigir a los autores de llamadas a las colas de llamadas de ventas y soporte técnico.

Consulte los artículos siguientes para obtener información sobre cómo crear operadores automáticos y colas de llamadas:

- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md)

> [!IMPORTANT]
> El token GUID de Azure AD de un usuario se almacena como parte de la configuración del operador automático o de la cola de llamadas cuando el usuario está configurado como:
>
>  - un operador automático o una cola **de llamadas Usuario autorizado**.
>  - un **operador** automático.
>  - un punto **de transferencia de persona de la organización** .
>  - un miembro individual de una cola de llamadas.
> 
> Las configuraciones del operador automático y la cola de llamadas no se sincronizan con los eventos de ciclo de vida de Azure AD.  Los administradores de Teams deben actualizar manualmente las configuraciones de los operadores automáticos y de las colas de llamadas para quitar estos datos personales cuando un usuario incluido en la configuración deja la organización.
>
> Esto no se aplica a las pertenencias a agentes de cola de llamadas configuradas a través de listas de distribución o canales. Tampoco se aplica a los usuarios a los que se les alcanza mediante la característica **Marcado por nombre** o **Marcado por número** de operadores automáticos.

Si necesita funcionalidades más amplias, como la integración con flujos de trabajo, bots y SMS, considere [la posibilidad de Azure Communication Services](/azure/communication-services/overview).

## <a name="related-topics"></a>Temas relacionados

[Planear el enrutamiento directo](direct-routing-plan.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
