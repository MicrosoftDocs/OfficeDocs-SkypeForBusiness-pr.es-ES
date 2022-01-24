---
title: Crear una cola de llamadas en Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Obtenga información sobre cómo configurar colas de llamadas para grandes organizaciones en Microsoft Teams, que proporciona un mensaje de saludo, música en espera, redirección de llamadas y otras características.
ms.openlocfilehash: 6323a73c0b400b7b8d44a49e1bad2dad9c7f38c7
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180923"
---
# <a name="create-a-call-queue"></a>Crear una cola de llamada

Las colas de llamadas proporcionan un método para enrutamiento de autores de llamadas a personas de la organización que pueden ayudarle con un problema o pregunta en particular. Las llamadas se distribuyen de una en una a las personas que están en la cola (que se denominan *agentes*). 

> [!TIP]
> Este artículo es para organizaciones grandes. Si su organización es una pequeña empresa, lea Crear una cola [de llamadas: tutorial de pequeña empresa](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) en su lugar.

Las colas de llamadas proporcionan:

- Un mensaje de saludo.

- Música que se reproduce mientras los usuarios se mantienen a la espera.

- Enrutamiento de llamadas *Primera en llegar, primera en salir* (FIFO),en la orden para los agentes.

- Opciones de gestión del desbordamiento de la cola y del tiempo de espera.

Asegúrese de que ha leído Planear Teams operadores [automáticos](plan-auto-attendant-call-queue.md) y [](plan-auto-attendant-call-queue.md#getting-started) colas de llamadas y ha seguido los pasos de introducción antes de seguir los procedimientos de este artículo.

## <a name="video-demonstration"></a>Demostración de vídeo

Este vídeo muestra un ejemplo básico de cómo crear una cola de llamadas en Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>Crear la cola de llamadas

Para configurar una cola de llamadas, en el centro de administración de Teams, expanda **Voz**, haga clic en **Llamar** y, después, haga clic en **Agregar**.

Escriba un nombre descriptivo para la cola.

## <a name="resource-accounts"></a>Cuentas de recursos

![Captura de pantalla de la configuración de la cuenta de recursos.](media/call-queue-name-language.png)

Haga clic en **Agregar cuentas**, busque la cuenta de recursos que desea usar con esta cola de llamadas, haga clic en **Agregar** y, después, haga clic en **Agregar**. (Los agentes verán el nombre de la cuenta de recurso cuando reciban una llamada entrante).

Para obtener más información, vea [Administrar Teams cuentas de recursos](manage-resource-accounts.md).

### <a name="assign-calling-id"></a>Asignar id. de llamada

![Captura de pantalla de la configuración de id. de llamada.](media/call-queue-assign-calling-id.png)

Si tiene previsto usar un canal Teams para los agentes de llamada, puede asignar un número de identificación de llamada saliente para los agentes especificando una o más cuentas de recursos con un número de teléfono.

Haga **clic en** Agregar , busque las cuentas de recursos a las que desea permitir que los agentes llamen con fines de identificación al realizar llamadas salientes, haga clic en Agregar y, a continuación, haga clic en **Agregar.** 

Si no usa un canal Teams para controlar la pertenencia al agente, considere la posibilidad de establecer directamente el identificador de llamada de los miembros de la cola de llamadas en el número de servicio de la cola de llamadas o en el operador automático adecuado. Para obtener más información, vea [Administrar directivas de identificador de llamadas en Microsoft Teams](caller-id-policies.md).

> [!NOTE]
> La cuenta de recurso usada para los fines de id. de llamada debe tener una Microsoft Teams Sistema telefónico de usuario virtual y una de las siguientes asignadas:
>
> - Una licencia del plan de llamadas y un número de teléfono asignado
> - Un operador Conectar número de teléfono asignado
> - Una directiva de enrutamiento de voz en línea (la asignación de número de teléfono es opcional al usar enrutamiento directo)


## <a name="language"></a>Idioma

![Captura de pantalla de la configuración de idioma.](media/call-queue-language.png)

Elija un [idioma compatible.](create-a-phone-system-call-queue-languages.md) Este idioma se usará para los mensajes de voz generados por el sistema y la transcripción de correo de voz (si las habilita).

## <a name="greetings-and-music-on-hold-in-queue"></a>Saludos y música en espera en cola

![Captura de pantalla de saludos y música en espera en la configuración de cola.](media/call-queue-greetings-music.png)

Especifique si quiere reproducir un saludo a los autores de llamadas cuando lleguen a la cola. Debe cargar un archivo MP3, WAV o WMA que contenga el saludo que desea reproducir. La grabación cargada no puede ser superior a 5 MB.

Los equipos proporcionan música predeterminada a los autores de llamadas mientras están en espera en una cola. La música predeterminada que se proporciona en las colas de llamadas de Teams no tiene que pagar ningún pago de la organización. Si desea reproducir un archivo de audio específico, elija **Reproducir un archivo de audio en** y cargar un archivo MP3, WAV o WMA.

> [!NOTE]
> Usted es responsable de borrar y asegurar de forma independiente todos los derechos y permisos necesarios para usar cualquier archivo de música o audio con su servicio de Microsoft Teams, que puede incluir propiedad intelectual y otros derechos sobre cualquier música, efectos de sonido, audio, marcas, nombres y otro contenido en el archivo de audio de todos los titulares de derechos pertinentes, que pueden incluir artistas, actores,  intérpretes, músicos, compositores, compositores, discográficas, editores de música, uniones, cofradías, asociaciones de derechos, organizaciones de administración colectiva y cualquier otra parte que posee, controla o licencia los derechos de copyright de música, efectos de sonido, audio y otros derechos de propiedad intelectual.

## <a name="call-agents"></a>Llamar a agentes

Revise los [requisitos previos para agregar agentes a una cola de llamadas.](plan-auto-attendant-call-queue.md#prerequisites)

![Captura de pantalla de la configuración de usuarios y grupos para las colas de llamadas.](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams canal

Puede agregar hasta 200 agentes a través de un Teams. Debe ser miembro del equipo, creador o propietario del canal para agregar un canal a la cola.

Si desea usar un [canal Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)para administrar la  cola, seleccione la opción Elegir un equipo y haga clic **en Agregar un canal.** Busque el equipo que desea usar, selecciónelo y haga clic en **Agregar**. Seleccione el canal que desea usar (solo se admiten los canales estándar) y haga clic en **Aplicar.** 

Los clientes siguientes son compatibles al usar un canal Teams para las colas de llamadas: 

  - Microsoft Teams Windows cliente
  - Cliente de Microsoft Teams para Mac

> [!NOTE]
> Si usa esta opción, la cola de llamadas puede tardar hasta 24 horas en estar completamente operativa.

##### <a name="users-and-groups"></a>Usuarios y grupos

Puede agregar hasta 20 agentes individualmente y hasta 200 agentes a través de grupos.

Si desea agregar usuarios o grupos individuales a la cola, seleccione la **opción Elegir usuarios y** grupos. 

Para agregar un usuario a la cola, haga clic en **Agregar usuarios**, busque el usuario, haga clic en **Agregar** y, después, haga clic en **Agregar**.

Para agregar un grupo a la cola, haga clic en **Agregar grupos**, busque el grupo, haga clic en **Agregar** y, después, haga clic en **Agregar**. Puede usar listas de distribución, grupos de seguridad, grupos de seguridad, grupos de Microsoft 365 o equipos de Microsoft Teams.

> [!NOTE]
> Los nuevos usuarios agregados a un grupo pueden tardar hasta ocho horas en llegar a su primera llamada.

## <a name="call-routing"></a>Enrutamiento de llamada

![Captura de pantalla de la configuración del modo de conferencia y del método de enrutamiento.](media/call-queue-conference-mode-routing-method.png)

**El modo de conferencia** reduce de forma significativa la cantidad de tiempo que tarda un autor de llamada en estar conectado con un agente, después de que el agente acepte la llamada. Para que el modo de conferencia funcione, los agentes en la cola de llamadas deben usar uno de los siguientes clientes:

  - Última versión del cliente de escritorio de Microsoft Teams, la aplicación de Android o la aplicación de iOS
  - Microsoft Teams Teléfono versión 1449/1.0.94.2020051601 o posterior
  
Las cuentas Teams agentes deben establecerse en Teams modo de solo lectura. Los agentes que no cumplan los requisitos no se incluyen en la lista de enrutamiento de llamadas. Se recomienda habilitar el modo de conferencia para las colas de llamadas si los agentes usan clientes compatibles.

> [!NOTE]
> El modo de conferencia no es compatible si las llamadas telefónicas se enruta a la cola desde una puerta de enlace de enrutamiento directo habilitada para enrutamiento basado en ubicación.

> [!TIP]
> Establecer **el modo de conferencia** en **On** es la configuración recomendada.

**El método de enrutamiento** determina el orden en que los agentes reciben llamadas de la cola. Elija una de estas opciones:

- **El enrutamiento de operador** hace una llamada a todos los agentes en la cola al mismo tiempo. El primer agente de llamada que tome la llamada la recibe.

- **El enrutamiento de serie** a todos los agentes de llamada uno por uno en el orden especificado en la **Llamar a** lista. Si un agente desestima o no contesta una llamada, se realizará una llamada al siguiente agente y se intentará con todos los agentes hasta que la llamada sea contestada o se agote el tiempo de espera.

- **Distribución equilibrada** equilibra el enrutamiento de llamadas entrantes para que cada agente de llamadas reciba el mismo número de llamadas de la cola. Esto puede ser deseable en un entorno de ventas de entrada para asegurar la misma oportunidad entre todos los agentes de llamada.

- **Inactividad mayor** dirige cada llamada al agente que ha estado inactivo por más tiempo. Un agente se considera inactivo si su estado de presencia es Disponible. Los agentes cuyo estado de presencia no esté disponible no podrán recibir llamadas hasta que cambien su presencia a Disponible. 

> [!TIP]
> Establecer **El método de enrutamiento** en **Redondear** o Más **tiempo** inactivo es la configuración recomendada.

> [!NOTE]
> Si [la grabación de cumplimiento](teams-recording-policy.md) está habilitada en los agentes, no se admite la combinación del modo **de** conferencia y **el** enrutamiento del operador. Si necesita usar el modo **conferencia,** seleccione Enrutamiento **en serie,** Cíclico **redondo** o **Inactivo más** largo como método **de enrutamiento.** Si necesita usar el enrutamiento **del operador,** establezca **el modo de conferencia** en **Desactivado.**
> 
> Al usar **el** modo inactivo más largo, es posible que haya ocasiones en las que un agente reciba una llamada de la cola poco después de que no esté disponible o si hay un breve retraso en recibir una llamada de la cola después de estar disponible.

![Captura de pantalla del enrutamiento, la opción de no participar y la configuración de la hora de alerta.](media/call-queue-presence-agents-time.png)

**La red de enrutamiento basada en** usa el estado de disponibilidad de los agentes de llamada para determinar si un agente debe incluirse en la lista de enrutamiento de llamadas para el método de enrutamiento seleccionado. Los agentes de llamadas cuyo estado de disponibilidad está establecido en **Disponible** se incluyen en la lista de enrutamiento de llamadas y pueden recibir llamadas. Los agentes cuyo estado de disponibilidad se establezca en cualquier otro estado se excluyen de la lista de enrutamiento de llamadas y no recibirán llamadas hasta que el estado de disponibilidad vuelva a cambiar a **Disponible**. 

Puede habilitar el enrutamiento de llamadas basado en presencia con cualquiera de los métodos de enrutamiento.

Si un agente opta por no recibir llamadas, no se incluirán en la lista de enrutamiento de llamadas independientemente de cómo esté configurado su estado de disponibilidad. 

> [!NOTE]
> Cuando **el** modo inactivo más largo está seleccionado como método de enrutamiento, el enrutamiento basado  en presencia se requiere y se habilita automáticamente aunque el botón de alternancia de enrutamiento basado en presencia estará desactivado y atenuado.
>
> Si el enrutamiento basado en presencia no está habilitado y hay varias llamadas en la cola, el sistema presentará estas llamadas simultáneamente a los agentes, independientemente de su estado de presencia. Esto provocará varias notificaciones de llamada a los agentes, especialmente si algunos agentes no responden a la llamada inicial que se les ha presentado.
> 
> Los agentes que usan el cliente de Skype Empresarial no se incluyen en la lista de enrutamiento de llamadas cuando está habilitado el enrutamiento basado en presencia. Si tiene agentes que usan Skype Empresarial, no habilite el enrutamiento de llamadas basado en presencia.

> [!TIP]
> Establecer **el enrutamiento basado en presencia** en **On** es la configuración recomendada.

**Tiempo de alerta de agente** especifica qué tanto tiempo sonará el teléfono de un agente antes de que la cola redirija la llamada al siguiente agente.

> [!TIP]
> Establecer **la hora de alerta del agente** en **20 segundos** es la configuración recomendada.

## <a name="call-overflow-handling"></a>Gestión de desbordamiento de llamadas

![Captura de pantalla de la configuración de desbordamiento de llamadas.](media/call-queue-overflow-handling.png)

**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede elegir un valor entre 0 y 200. Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.

Puede elegir desconectar la llamada o redirigirla a cualquiera de los destinos de enrutamiento de llamadas. Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola. Para las transferencias externas, vea [Requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) y las transferencias de números de teléfono [externos: detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para el formato de números.

> [!NOTE]
> Si el número máximo de llamadas se establece en 0, no se reproducirá el mensaje de saludo.

## <a name="call-timeout-handling"></a>Gestión de la caducidad de la llamada

![Captura de pantalla de la configuración de tiempo de espera de la llamada.](media/call-queue-timeout-handling.png)

**Tiempo de espera de la llamada: tiempo máximo** especifica el tiempo máximo en que una llamada puede estar en espera en la cola antes de que se redirija o se desconecta. Puede establecer un intervalo de entre 0 y 45 minutos.

Puede elegir desconectar la llamada o redirigirla a uno de los destinos de enrutamiento de llamadas. Por ejemplo, puede que el autor de llamada deje un correo de voz para los agentes en la cola. Para las transferencias externas, consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) [las transferencias de números de teléfono externos (los detalles técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) el formato de los números).

Cuando haya seleccionado las opciones del tiempo de espera de la llamada, haga clic **Guardar**.

## <a name="summary-of-recommended-call-queue-settings"></a>Resumen de la configuración recomendada de la cola de llamadas

Se recomienda la siguiente configuración:

- **Modo de conferencia** en **On**
- **Método de enrutamiento** a **distribución equilibrada** o **inactividad mayor**
- **Enrutamiento basado en presencia** a **Activado**
- **Hora de alerta de agente:** a **20 segundos**

## <a name="supported-clients"></a>Clientes compatibles

Los siguientes clientes son compatibles con agentes de llamada en una cola de llamadas:

  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
  - Todos los modelos de teléfonos IP compatibles con Microsoft Teams. Consulte [Obtener teléfonos con Skype Empresarial Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Cliente de Skype for Business para Mac (versión 16.8.196 y posteriores)
  - Cliente de Skype para Business para Android (versión 6.16.0.9 y posteriores)
  - Cliente de Skype for Business para iPhone (versión 6.16.0 y posteriores)
  - Cliente de Skype for Business para iPad (versión 6.16.0 y posteriores)
  - Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
  - Cliente de Microsoft Teams para Mac
  - Microsoft Teams infraestructura [de escritorio virtualizada](/microsoftteams/teams-for-vdi) (Windows escritorio virtual, Citrix y VMware)
  - Aplicación Microsoft Teams para iPhone
  - Aplicación Microsoft Teams para Android

    > [!NOTE]
    > Las colas de llamadas a las que se les asigna un número de enrutamiento directo no admiten clientes de Skype Empresarial, clientes Lync o teléfonos IP de Skype Empresarial como agentes. El Teams solo es compatible con un modo [de coexistencia de Teams solo](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="call-queue-cmdlets"></a>Cmdlets de colas de llamadas

Windows PowerShell permite crear y administrar colas de llamadas a través de la línea de comandos de forma por lotes o mediante programación.

Los siguientes cmdlets le permiten administrar una cola de llamadas:

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

Los siguientes cmdlets adicionales también son necesarios para administrar los usuarios, cuentas de recursos, licencias de Microsoft Teams Teléfono, números de teléfono, archivos de audio e idioma compatible que se usarán con las colas de llamadas:

Usuarios/Teams

- Usuarios
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)
- - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

Cuentas de recursos:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

Licencias Teams Teléfono virtuales:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

Teléfono asignación de números:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

Archivos de audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Listas de idioma de soporte técnico

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

Para obtener una guía paso a paso para crear colas de llamadas con PowerShell, vea Crear colas de llamadas [con cmdlets de PowerShell](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="call-queue-diagnostic-tool"></a>Herramienta de diagnóstico de cola de llamadas

Si es administrador, puede usar la siguiente herramienta de diagnóstico para validar que una cola de llamadas puede recibir llamadas:

1. Seleccione **Ejecutar pruebas** a continuación. Esto rellenará el diagnóstico en el Centro de administración de Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Ejecutar pruebas: Teams cola de llamadas](https://aka.ms/TeamsCallQueueDiag)

2. En el panel Ejecutar diagnóstico, escriba la cuenta de recursos en el campo Nombre de usuario o **Correo** electrónico y, a continuación, **seleccione Ejecutar pruebas.**

3. Las pruebas devolverán los mejores pasos siguientes para abordar cualquier configuración de cuenta de inquilino, directiva y recurso para validar que la cola de llamadas pueda recibir llamadas.

## <a name="related-topics"></a>Temas relacionados

[Esto es lo que obtienes con Microsoft Teams Teléfono](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
