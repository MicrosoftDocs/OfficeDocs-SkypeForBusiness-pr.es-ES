---
title: Crear una cola de llamada
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Aprenda a configurar el sistema telefónico para las colas de llamadas con Microsoft Teams, que proporciona un mensaje de saludo, mantiene música, redirige las llamadas y otras características.
ms.openlocfilehash: 31826d1090835a073551e3639cb6105feb16d650
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48793527"
---
# <a name="create-a-call-queue"></a>Crear una cola de llamada

Las colas de llamadas proporcionan un método para dirigir a las personas de su organización que pueden ayudarle con un problema o una pregunta en particular. Las llamadas se distribuyen de una en una a las personas de la cola (que se conocen como *agentes* ). 

Las colas de llamadas proporcionan:

- Un mensaje de bienvenida.

- Música mientras las personas esperan en espera en una cola.

- Enrutamiento de llamadas: remisión de pedido-a de *salida* (FIFO).

- Administración de opciones para el desbordamiento de la cola y el tiempo de espera.

Asegúrese de que tiene el [plan de lectura de los operadores automáticos de Teams y las colas de llamadas](plan-auto-attendant-call-queue.md) y siga los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de este artículo.

Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **voz** , haga clic en **colas de llamadas** y, a continuación, haga clic en **Agregar** .

## <a name="resource-account-and-language"></a>Cuenta de recursos e idioma

![](media/call-queue-name-language.png)

1. Escriba un nombre para la cola de llamadas. Los agentes verán este nombre cuando reciban una llamada entrante de la cola.

2. Haga clic en **Agregar cuentas** , busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, a continuación, haga clic en **Agregar** .

3. Elija un idioma. Este idioma se usará para las solicitudes de voz generadas por el sistema y la transcripción del buzón de voz (si las habilita).

## <a name="greetings-and-hold-music"></a>Saludos y la música en espera

Especifique si desea reproducir un saludo para las personas que llaman cuando llegan a la cola. Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir.

Teams proporciona música predeterminada a las personas que llaman mientras están en espera en una cola. Si desea reproducir un archivo de audio específico, elija **reproducir un archivo de audio** y cargar un archivo mp3, WAV o WMA.

> [!NOTE]
> La grabación cargada no puede tener más de 5 MB.
> La música predeterminada que se proporciona en las colas de llamadas de Teams es gratuita para la organización. 

## <a name="call-agents"></a>Agentes de llamadas

Los agentes de llamadas seleccionados deben ser uno de los siguientes: 

- Usuarios en línea con una licencia de sistema telefónico y la telefonía IP empresarial habilitada
- Usuarios en línea con un plan de llamadas
- Usuarios locales de Skype empresarial Server
- Si los agentes usan la aplicación Microsoft Teams para las llamadas de la cola de llamadas, deben estar en modo TeamsOnly.

![](media/call-queue-users-groups.png)

Puede Agregar hasta 20 agentes de forma individual y hasta 200 agentes a través de grupos.

Para agregar un usuario a la cola, haga clic en **Agregar usuarios** , busque el usuario, haga clic en **Agregar** y, a continuación, haga clic en **Agregar** .

Para agregar un grupo a la cola, haga clic en **agregar grupos** , busque el grupo, haga clic en **Agregar** y, a continuación, haga clic en **Agregar** . Puede usar listas de distribución, grupos de seguridad y grupos de Microsoft 365 o de Microsoft Teams.

> [!NOTE]
> Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.

## <a name="call-routing"></a>Enrutamiento de llamada

![](media/call-queue-conference-mode-routing-method.png)

El **modo de conferencia** reduce significativamente la cantidad de tiempo que tarda una persona que se conecte a un agente, después de que el agente acepte la llamada. Para que el modo de conferencia funcione, los agentes de la cola de llamadas deben usar uno de los siguientes clientes:

  - La versión más reciente del cliente de escritorio de Microsoft Teams, la aplicación Android o la aplicación iOS
  - Microsoft Teams Phone versión 1449/1.0.94.2020051601 o posterior
  
Las cuentas de los agentes de Teams deben establecerse en el modo de solo equipos. Los agentes que no cumplan con los requisitos no se incluyen en la lista de enrutamiento de llamadas. Recomendamos habilitar el modo de conferencia para las colas de llamadas si todos los agentes usan clientes compatibles.

> [!NOTE]
> El modo de conferencia no admite el uso ocupado en ocupado. Es posible que los agentes de las llamadas a colas que no sean de llamadas sigan apareciendo con una llamada en la cola de llamadas si el enrutamiento basado en presencia no está habilitado.

El **método de enrutamiento** determina el orden en el que los agentes reciben llamadas de la cola. Elija una de estas opciones:

- El **enrutamiento del operador** llama a todos los agentes de la cola al mismo tiempo. El primer agente de llamadas que atiende la llamada recibe la llamada.

- El **enrutamiento en serie** llama a todos los agentes de llamadas uno por uno en el orden especificado en la lista agentes de **llamadas** . Si un agente descarta o no atiende una llamada, la llamada sonará al próximo agente y probará con todos los agentes hasta que se seleccione o agote el tiempo de espera.

- Equilibrar la **operación por turnos** el enrutamiento de las llamadas entrantes para que cada agente de llamadas obtenga el mismo número de llamadas de la cola. Esto puede ser conveniente en un entorno de ventas entrante para asegurar la igualdad de oportunidades entre todos los agentes de llamadas.

- El más **largo** enruta las llamadas al agente que ha estado inactiva el tiempo más largo. Un agente se considera inactivo si su estado de presencia está disponible o si su estado de presencia ha estado ausente por menos de 10 minutos. Los agentes cuyo estado de presencia haya estado ausente más de 10 minutos no se consideran inactivos y no podrán recibir llamadas hasta que cambien su presencia a disponible. 

![](media/call-queue-presence-agents-time.png)


El **enrutamiento basado en la presencia** usa el estado de disponibilidad de los agentes de llamadas para determinar si un agente debería estar incluido en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado. Los agentes de llamadas cuyo estado de disponibilidad esté establecido en **disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas. Los agentes cuyo estado de disponibilidad esté establecido en cualquier otro Estado se excluyan de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que su estado de disponibilidad cambie de nuevo a **disponible** . 

Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.

Si un agente opta por recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas, independientemente del valor de su estado de disponibilidad en. 

> [!NOTE]
> Los agentes que usan el cliente de Skype empresarial no se incluyen en la lista de enrutamiento de llamadas cuando el enrutamiento basado en presencia está habilitado. Si tiene agentes que usan Skype empresarial, no habilite el enrutamiento de llamadas basado en presencia.

La hora de la **alerta del agente** especifica cuánto tiempo sonará el teléfono del agente antes de que la cola redirija la llamada al siguiente agente.

Para las colas de alto volumen, recomendamos la configuración siguiente:

- **Modo** de conferencia **automático**
- **Método de enrutamiento** para **enrutamiento de operador**
- **Enrutamiento basado en presencia** en **activado**
- **Hora de la alerta del agente:** **20 segundos**

## <a name="call-overflow-handling"></a>Control de desbordamiento de llamadas

![](media/call-queue-overflow-handling.png)

Número **máximo de llamadas en la cola** especifica el número máximo de llamadas que pueden esperar en la cola en cualquier momento. El valor predeterminado es 50, pero puede estar comprendido entre 0 y 200. Cuando se alcanza este límite, la llamada se maneja de la forma especificada por la configuración **cuando se alcanza el número máximo de llamadas** .

Puede desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas. Por ejemplo, es posible que la persona que llama deje un buzón de voz para los agentes de la cola.

> [!NOTE]
> Si el número máximo de llamadas se establece en 0, el mensaje de bienvenida no se reproducirá.

## <a name="call-timeout-handling"></a>Control de tiempo de espera de llamadas

![](media/call-queue-timeout-handling.png)

Tiempo de espera de la **llamada: tiempo de espera máximo** especifica el tiempo máximo que una llamada puede estar en espera en la cola antes de que se redirija o desconecte. Puede especificar un valor entre 15 y 45 minutos.

Puede desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas. Por ejemplo, es posible que la persona que llama deje un buzón de voz para los agentes de la cola.

Cuando haya seleccionado las opciones de tiempo de espera de la llamada, haga clic en **Guardar** .

## <a name="caller-id-for-outbound-calls"></a>IDENTIFICACIÓN de llamadas para llamadas salientes

Como los agentes de una cola de llamadas pueden marcar para devolver una llamada de cliente, considere la posibilidad de establecer la identificación de llamadas para los miembros de una cola de llamadas en el número de servicio de un operador automático adecuado. Para obtener más información, consulte [Administrar directivas de identificación de llamadas en Microsoft Teams](caller-id-policies.md) .

## <a name="supported-clients"></a>Clientes compatibles

- Los siguientes clientes son compatibles con los agentes de llamadas en una cola de llamadas:

  - Cliente de escritorio de Skype empresarial 2016 (versiones de 32 y 64 bits)
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
  - Todos los modelos de teléfono IP compatibles con Microsoft Teams. Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)
  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)
  - Cliente de Windows de Microsoft Teams (versiones de 32 y 64 bits)
  - Cliente de Microsoft Teams para Mac
  - Aplicación Microsoft Teams para iPhone
  - Aplicación Microsoft Teams para Android

    > [!NOTE]
    > Las colas de llamadas a las que se asigna un número de enrutamiento directo no son compatibles con clientes de Skype empresarial, clientes de Lync o teléfonos IP de Skype empresarial como agentes.

## <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

También puede usar Windows PowerShell para crear y configurar colas de llamadas. Estos son los cmdlets que usas para administrar una cola de llamadas.

- [Nuevo: CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nuevo: CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
