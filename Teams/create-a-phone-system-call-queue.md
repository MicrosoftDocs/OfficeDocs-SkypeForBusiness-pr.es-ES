---
title: Crear una cola de llamadas en Microsoft Teams
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
- m365initiative-voice
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
description: Aprenda a configurar Sistema telefónico para colas de llamadas con Microsoft Teams, que proporciona un mensaje de saludo, música en espera, redirección de llamadas y otras características.
ms.openlocfilehash: 0253fb15a8672d83e672e3e3e18f8455d292214c
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145897"
---
# <a name="create-a-call-queue"></a>Crear una cola de llamada

Las colas de llamadas proporcionan un método para enrutar a los autores de llamadas a personas de su organización que pueden ayudarle con un problema o una pregunta en particular. Las llamadas se distribuyen de una en una a las personas de la cola (que se conocen como *agentes).* 

Las colas de llamadas proporcionan:

- Un mensaje de saludo.

- Música mientras los usuarios están en espera en una cola.

- Enrutamiento de llamadas, *en orden de primero en entrada,* orden first out (FIFO), a agentes.

- Opciones de control para el desbordamiento de la cola y el tiempo de espera.

Asegúrese de haber leído plan para operadores [automáticos](plan-auto-attendant-call-queue.md) y [](plan-auto-attendant-call-queue.md#getting-started) colas de llamadas de Teams y de haber seguido los pasos de introducción antes de seguir los procedimientos de este artículo.

Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **Voz,** haga clic en Colas de llamadas **y,** a continuación, haga clic **en Agregar.**

## <a name="resource-account-and-language"></a>Cuenta e idioma del recurso

![Captura de pantalla de la configuración de cuenta de recursos e idioma](media/call-queue-name-language.png)

1. Escriba un nombre para la cola de llamadas. Los agentes verán este nombre cuando reciban una llamada entrante de la cola.

2. Haga **clic en Agregar** cuentas, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en Agregar y, a continuación, haga clic en **Agregar.** 

3. Elige un idioma. Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción del correo de voz (si los habilita).

## <a name="greetings-and-music-on-hold-in-queue"></a>Saludos y música en espera en cola

Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola. Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que quiere reproducir.

Teams proporciona música predeterminada a los autores de llamadas mientras están en espera en una cola. Si desea reproducir un archivo de audio específico, elija Reproducir un archivo de **audio** y cargue un archivo MP3, WAV o WMA.

> [!NOTE]
> La grabación cargada no puede tener un tamaño superior a 5 MB.
> La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar regalías por su organización. 

## <a name="call-agents"></a>Agentes de llamadas

Consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para poder agregar agentes a una cola de llamadas.

![Captura de pantalla de la configuración de usuarios y grupos para colas de llamadas](media/call-queue-users-groups.png)

Puede agregar hasta 20 agentes de forma individual y hasta 200 agentes a través de grupos.

Para agregar un usuario a la cola, haga clic en Agregar **usuarios,** busque el usuario, haga clic en Agregar **y,** a continuación, haga clic **en Agregar.**

Para agregar un grupo a la cola, haga clic en **Agregar grupos,** busque el grupo, haga clic en Agregar **y,** a continuación, haga clic en **Agregar.** Puede usar listas de distribución, grupos de seguridad y grupos de Microsoft 365 o equipos de Microsoft Teams.

> [!NOTE]
> Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.

## <a name="call-routing"></a>Enrutamiento de llamada

![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento](media/call-queue-conference-mode-routing-method.png)

**El modo** de conferencia reduce significativamente la cantidad de tiempo que tarda un autor de llamada en conectarse con un agente, después de que el agente acepte la llamada. Para que el modo de conferencia funcione, los agentes de la cola de llamadas deben usar uno de los siguientes clientes:

  - La última versión del cliente de escritorio de Microsoft Teams, la aplicación para Android o la aplicación de iOS
  - Versión 1449/1.0.94.2020051601 o posteriores de Microsoft Teams
  
Las cuentas de equipos de agentes deben configurarse en modo solo para equipos. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas. Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

**El método de** enrutamiento determina el orden en que los agentes reciben llamadas de la cola. Elija una de estas opciones:

- **El enrutamiento del operador** suena a todos los agentes de la cola al mismo tiempo. El primer agente de llamada que recibe la llamada recibe la llamada.

- **El enrutamiento serial** suena a todos los agentes de llamadas uno por uno en el orden especificado en la **lista de agentes de** llamadas. Si un agente descarta o no acepta una llamada, la llamada llamará al siguiente agente y probará con todos los agentes hasta que se le atende o se atenten.

- **Redondear robin** equilibra el enrutamiento de las llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola. Esto puede ser deseable en un entorno de ventas entrantes para garantizar la misma oportunidad entre todos los agentes de llamadas.

- **La inactividad más** larga enruta cada llamada al agente que haya estado inactivo más tiempo. Un agente se considera inactivo si su estado de presencia está disponible o si su estado de presencia ha estado fuera durante menos de 10 minutos. Los agentes cuyo estado de presencia ha estado fuera durante más de 10 minutos no se consideran inactivos y no podrán recibir llamadas hasta que cambien su presencia a Disponible. 

![Captura de pantalla de la configuración de enrutamiento, de no participar y de hora de alerta](media/call-queue-presence-agents-time.png)


**El enrutamiento basado en presencia usa** el estado de disponibilidad de agentes de llamadas para determinar si un agente debe incluirse en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado. Los agentes de llamadas cuyo estado de disponibilidad se establece en **Disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas. Los agentes cuyo estado de disponibilidad se establece en cualquier otro estado se excluyen de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que el estado de disponibilidad cambie de nuevo a **Disponible.** 

Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.

Si un agente decide no recibir llamadas, no se incluirá en la lista de enrutamiento de llamadas independientemente de cuál sea su estado de disponibilidad. 

> [!NOTE]
> Los agentes que usan el cliente de Skype Empresarial no están incluidos en la lista de enrutamiento de llamadas cuando el enrutamiento basado en presencia está habilitado. Si tiene agentes que usan Skype Empresarial, no habilite el enrutamiento de llamadas basado en presencia.

**La hora de alerta** de agente especifica cuánto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.

Se recomiendan las siguientes opciones:

- **Modo de conferencia** a **Automático**
- **Método de enrutamiento** **a Round robin** o **Longest idle**
- **Enrutamiento basado en presencia** a **On**
- **Hora de alerta de agente:** **20 segundos**

> [!NOTE]
> Si el enrutamiento basado en presencia no está habilitado y hay varias llamadas en la cola, el sistema presentará estas llamadas simultáneamente a los agentes independientemente de su estado de presencia. Esto dará como resultado varias notificaciones de llamada a los agentes, especialmente si algunos agentes no responden a la llamada inicial que se les presenta.

## <a name="call-overflow-handling"></a>Administración de desbordamiento de llamadas

![Captura de pantalla de la configuración de desbordamiento de llamadas](media/call-queue-overflow-handling.png)

**El número máximo de llamadas en** la cola especifica el número máximo de llamadas que pueden esperar en la cola en cualquier momento dado. El valor predeterminado es 50, pero puede variar de 0 a 200. Cuando se alcanza este límite, la llamada se administra según lo especificado por la configuración Cuando se alcanza el número máximo de **llamadas.**

Puede elegir desconectar la llamada o redirigirla a cualquiera de los destinos de enrutamiento de llamadas. Por ejemplo, puede hacer que el autor de la llamada deje un correo de voz para los agentes de la cola. Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las transferencias de números de teléfono externos: [detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para el formato del número.

> [!NOTE]
> Si se establece el número máximo de llamadas en 0, el mensaje de saludo no se reproducirá.

## <a name="call-timeout-handling"></a>Administración del tiempo de espera de llamadas

![Captura de pantalla de la configuración de tiempo de espera de llamada](media/call-queue-timeout-handling.png)

**Tiempo de espera de llamada:** el tiempo máximo de espera especifica el tiempo máximo que una llamada puede estar en espera en la cola antes de que se redirija o se desconecte. Puede especificar un valor entre 0 segundos y 45 minutos.

Puede elegir desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas. Por ejemplo, puede hacer que el autor de la llamada deje un correo de voz para los agentes de la cola. Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las transferencias de números de teléfono [externos: detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para el formato del número.

Cuando haya seleccionado las opciones de tiempo de espera de la llamada, haga clic en **Guardar.**

## <a name="caller-id-for-outbound-calls"></a>Identificación de llamadas para llamadas salientes

Como los agentes de una cola de llamadas pueden llamar para devolver una llamada del cliente, considere la posibilidad de establecer el identificador de llamada de los miembros de una cola de llamadas en el número de servicio de un operador automático adecuado. Vea [Administrar directivas de identificador de llamada en Microsoft Teams](caller-id-policies.md) para obtener más información.

## <a name="supported-clients"></a>Clientes compatibles

Los siguientes clientes son compatibles con agentes de llamadas en una cola de llamadas:

  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
  - Todos los modelos de teléfonos IP compatibles con Microsoft Teams. Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)
  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)
  - Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
  - Cliente de Microsoft Teams para Mac
  - Aplicación Microsoft Teams para iPhone
  - Aplicación Microsoft Teams para Android

    > [!NOTE]
    > Las colas de llamadas que tienen asignado un número de enrutamiento directo no admiten clientes de Skype Empresarial, clientes Lync o teléfonos IP de Skype Empresarial como agentes.

## <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

También puede usar Windows PowerShell para crear y configurar colas de llamadas. Estos son los cmdlets que usa para administrar una cola de llamadas.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
