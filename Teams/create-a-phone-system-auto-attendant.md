---
title: Configurar un operador automático para Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: Aprenda a configurar y probar los operadores automáticos para Microsoft Teams.
ms.openlocfilehash: 00cf80578564db122d4eaf206456b465a21668af
ms.sourcegitcommit: 950c04ce49064209ee04880e7c7473a4f931df50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "48999222"
---
# <a name="set-up-an-auto-attendant"></a>Configurar un operador automático

Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el Departamento adecuado, la cola de llamadas, la persona o un operador. Puede crear operadores automáticos para su organización con el centro de administración de Microsoft Teams o con PowerShell. 

Asegúrese de que tiene el [plan de lectura de los operadores automáticos de Teams y las colas de llamadas](plan-auto-attendant-call-queue.md) y siga los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de este artículo.

Los operadores automáticos pueden dirigir llamadas en función de la entrada de los autores de llamadas a uno de los siguientes destinos: <a name="call-routing-options" ></a>

- **Persona de la organización** : una persona de su organización que puede recibir llamadas de voz. Puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server.
- **Aplicación de voz** : otro operador automático o una cola de llamadas. (Elija la cuenta de recursos asociada al operador automático o a la cola de llamadas al elegir este destino).
- **Número de teléfono externo** , cualquier número de teléfono. (Consulta los [detalles técnicos de la transferencia externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- Buzón de **voz: el buzón de voz** asociado a un grupo de Microsoft 365 que especifique.
- **Operador** : el operador definido para el operador automático. Definir un operador es opcional. El operador se puede definir como cualquiera de los otros destinos de esta lista.

Cuando configure un operador automático, se le pedirá que elija una de estas opciones.

Para configurar un operador automático, en el centro de administración de Teams, expanda **voz** , haga clic en **operadores automáticos** y, a continuación, haga clic en **Agregar**.

## <a name="general-info"></a>Información general

![Captura de pantalla de configuración de operador automático para nombre, operador, zona horaria, idioma y entradas de voz](media/auto-attendant-general-info-page-new.png)

1. Escriba un nombre para el operador automático en el cuadro de la parte superior.

2. Si desea designar un operador, especifique el destino de las llamadas al operador. Esto es opcional (pero se recomienda). Puede configurar la opción de **operador** para permitir que los autores de llamadas interrumpan los menús y hablen con una persona designada.

3. Especifique la zona horaria de este operador automático. La zona horaria se usa para calcular el horario laboral si se [crea un flujo de llamada independiente para después del horario laboral](#call-flow-for-after-hours).

4. Especifique un idioma para este operador automático. Este es el idioma que se usará para los avisos de voz generados por el sistema.

5. Elija si desea habilitar las entradas de voz. Cuando está habilitado, el nombre de todas las opciones de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, las personas que llamen pueden decir "una" para seleccionar la opción de menú asignada a la clave 1, o pueden decir "ventas" para seleccionar la opción de menú denominada "ventas".

6. Haga clic en **Siguiente**.

## <a name="call-flow"></a>Flujo de llamadas

![Captura de pantalla de la configuración de mensaje de saludo](media/auto-attendant-call-flow-greeting-message.png)

Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.

Si selecciona **reproducir un archivo de audio** , puede usar el botón **Cargar archivo** para cargar un mensaje de saludo grabado guardado como audio en. WAV,. MP3 o. Formato WMA. La grabación no puede tener más de 5 MB.

Si selecciona **escribir un mensaje de saludo** , el sistema leerá el texto con el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.

![Captura de pantalla de configuración de enrutamiento de llamadas](media/auto-attendant-call-flow-route-call-message.png)

Elige cómo quieres enrutar la llamada.

Si seleccionas **desconectar** , el operador automático colgará la llamada.

Si selecciona **redirigir llamada** , puede elegir uno de los destinos de enrutamiento de llamadas.

Si selecciona **reproducir opciones de menú** , puede elegir **reproducir un archivo de audio** o **escribir un mensaje de bienvenida** y, a continuación, elegir entre las opciones de menú y la búsqueda de directorio.

### <a name="menu-options"></a>Opciones de menú

![Captura de pantalla de las opciones de teclas de marcado](media/auto-attendant-call-flow-menu-options-complete.png)

Para las opciones de marcado, puede asignar las teclas de 0-9 en el teclado del teléfono a uno de los destinos de enrutamiento de llamadas. (Las teclas \* (Repetir) y \# (atrás) están reservados para el sistema y no se pueden reasignar.)

Las asignaciones de teclas no tienen que ser continuas. Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a las opciones, mientras que la tecla 2 no se usa.

Se recomienda asignar la clave 0 al operador si se ha configurado una. Si el operador no se establece en ninguna tecla, el comando de voz "operador" también está deshabilitado. 

Para cada opción de menú, especifique lo siguiente:

- **Tecla de marcado** : la tecla del teclado del teléfono para acceder a esta opción. Si hay entradas de voz disponibles, las personas que llaman también pueden decir este número para tener acceso a la opción.

- **Comando voz** : define el comando de voz que la persona que llama puede conceder para obtener acceso a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras como "servicio al cliente" o "operaciones y motivos". Por ejemplo, la persona que llama puede presionar 2, decir "dos" o decir "ventas" para seleccionar la opción asignada a la tecla 2. Este texto se representa también por texto a voz para la pregunta de confirmación del servicio, que puede ser como "transfiriendo la llamada a ventas".

- Redirigir al destino de enrutamiento de llamada **que se** usa cuando la persona que llama elige esta opción. Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada a él.

### <a name="directory-search"></a>Búsqueda en el directorio

Si asigna teclas de marcado a destinos, le recomendamos que elija **ninguno** para la búsqueda en el **directorio**. Si una persona que llama intenta marcar un nombre o una extensión con las teclas que se asignan a destinos específicos, es posible que se dirijan de forma inesperada a un destino antes de que terminen de introducir el nombre o la extensión. Le recomendamos que cree un operador automático independiente para la búsqueda en el directorio y que le vincule su operador automático principal a través de una tecla de marcado.

Si no ha asignado las teclas de marcado, elija una opción para la búsqueda en el **directorio**.

**Marcado por nombre** : Si habilita esta opción, las personas que llamen pueden decir el nombre del usuario o escribirla en el teclado del teléfono. Cualquier usuario en línea con una licencia de sistema telefónico o cualquier usuario local que use Skype empresarial Server es un usuario elegible y puede encontrarse con el marcado por nombre. (Puede establecer quién está y no incluido en el directorio de la página de [ámbito de marcado](#dial-scope) ).

**Marcado por extensión** : Si habilita esta opción, las personas que llamen podrán conectarse con los usuarios de su organización marcando su extensión de teléfono. Cualquier usuario en línea con una licencia de sistema telefónico o cualquier usuario local que use Skype empresarial Server es un usuario elegible y puede encontrarse con la **función de marcado por extensión**. (Puede establecer quién está y no incluido en el directorio de la página de [ámbito de marcado](#dial-scope) ).

Los usuarios que desea que estén disponibles para marcar por extensión necesitan tener una extensión especificada como parte de uno de los siguientes atributos de teléfono definidos en Active Directory o Azure Active Directory (para obtener más información, consulte [Agregar usuarios individualmente o de forma masiva](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) .)

- OfficePhone
- Teléfono particular
- Móvil/teléfono móvil
- TelephoneNumber/PhoneNumber
- OtherTelephone

El formato requerido para introducir la extensión en el campo número de teléfono del usuario es *+ \<phone number> ext \<extension> =* o *+ \<phone number> x \<extension>*.

Puede establecer la extensión en el [centro de administración de Microsoft 365](https://admin.microsoft.com/) o en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com). Pueden pasar hasta 12 horas antes de que los cambios estén disponibles para los operadores automáticos y las colas de llamadas.

> [!NOTE]
> Si desea usar el **marcado por nombre** y las características de **marcado por extensión** , puede asignar una tecla de marcado en su operador automático principal para comunicarse con un operador automático habilitado para **el marcado por nombre**. Dentro de ese operador automático, puedes asignar la tecla 1 (que no tiene ninguna letra asociada) para alcanzar el **marcado por** el operador automático de extensión.

Una vez que haya seleccionado una opción de **búsqueda de directorio** , haga clic en **siguiente**.

## <a name="call-flow-for-after-hours"></a>Flujo de llamadas para después del horario

![Captura de pantalla de la configuración de día y hora de horas postales](media/auto-attendant-business-hours.png)

Puede establecer el horario comercial para cada operador automático. Si no se han establecido las horas de trabajo, todos los días y todas las horas del día se consideran horario comercial porque una programación de 24/7 está establecida de forma predeterminada. El horario comercial se puede establecer con interrupciones en el tiempo durante el día, y todas las horas que no se configuran como horas laborales se consideran horas laborales. Puede establecer distintas opciones de tratamiento de llamadas entrantes y saludos para después de las horas de trabajo.

En función de cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas después de las horas para los operadores automáticos con números de teléfono directos.

Si desea un enrutamiento de llamadas por separado para llamadas de fuera de horario laboral, especifique el horario laboral para cada día. Haga clic en **Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una pausa para comer.

Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para después de horas. Las mismas opciones están disponibles para el enrutamiento de llamadas de horario laboral que especificó más arriba.

Cuando haya terminado, haga clic en **siguiente** .

## <a name="call-flows-during-holidays"></a>Flujos de llamadas durante los días festivos

![Captura de pantalla de la configuración de felicitación por vacaciones y vacaciones](media/auto-attendant-holiday-greeting.png)

El operador automático puede tener un flujo de llamadas por cada [festividad que hayas configurado](set-up-holidays-in-teams.md). Puede agregar un máximo de 20 días festivos programados a cada operador automático.

1. En la página de configuración de llamadas, haga clic en **Agregar**.

2. Escriba un nombre para esta configuración de días festivos.

3. En la lista desplegable **vacaciones** , elija el día no laborable que desea usar.

4. Elija el tipo de saludo que desea usar.

    ![Captura de pantalla de la configuración de acciones de llamadas navideñas](media/auto-attendant-holiday-actions.png)

5. Elige si deseas **desconectar** o **desviar** la llamada.

6. Si eliges redirigir, elige el destino de enrutamiento de llamadas para la llamada.

7. Haga clic en **Guardar**.

![Captura de pantalla de la configuración de días festivos con días festivos](media/auto-attendant-holiday-call-settings.png)

Repita el procedimiento según sea necesario para cada festividad adicional.

Cuando haya agregado todos los días no laborables, haga clic en **siguiente**.

## <a name="dial-scope"></a>Ámbito de marcado

![Captura de pantalla del ámbito de marcado opciones para incluir y excluir](media/auto-attendant-dial-scope.png)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando una persona que llama usa el método de marcado por nombre o la extensión de marcado. El valor predeterminado de **todos los usuarios en línea** incluye todos los usuarios de su organización que son usuarios en línea con una licencia de sistema de teléfono o que se han hospedado de forma local con Skype empresarial Server.

Puede incluir o excluir determinados usuarios seleccionando **grupo de usuarios personalizado** en **incluir** o **excluir** y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado. (Si un usuario está en ambas listas, se excluirá del directorio).

> [!NOTE]
> Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio.

Cuando haya terminado de establecer el ámbito de marcado, haga clic en **siguiente**.

## <a name="resource-accounts"></a>Cuentas de recursos

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos con un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada uno con un número de servicio diferente.

![Captura de pantalla de la cuenta de recursos panel agregar cuentas](media/auto-attendant-add-resource-account.png)

Para agregar una cuenta de recursos, haga clic en **Agregar cuenta** y busque la cuenta que desea agregar. Haga clic en **Agregar** y, a continuación, en **Agregar**.

![Captura de pantalla de la lista de cuentas de recursos que muestra una cuenta de recursos con un número de servicio asignado](media/auto-attendant-resource-account-assigned.png)

Cuando haya terminado de agregar cuentas de servicio, haga clic en **Enviar**. Esto completa la configuración del operador automático.

## <a name="external-phone-number-transfers---technical-details"></a>Transferencias de números de teléfono externos: detalles técnicos

Consulte los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas de forma externa.  Además:

- Para una cuenta de recursos con un número de [plan de llamadas](calling-plans-for-office-365.md) , el número de teléfono de transferencia externa debe introducirse en el formato E. 164 (+ [código de país] [código de área] [número de teléfono]).

- Para una cuenta de recursos con un número de enrutamiento directo, el formato del número de teléfono de la transferencia externa depende de la configuración del [controlador de borde de sesión (SBC)](direct-routing-connect-the-sbc.md) .

El número de teléfono saliente que se muestra se determina de la siguiente manera:

  - Para los números de planes de llamadas, se muestra el número de teléfono de la persona que llama original.
  - Para los números de enrutamiento directos, el número enviado se basa en la configuración P-asserted-Identity (PAI) en SBC, de la siguiente manera:
    - Si se establece en deshabilitado, se muestra el número de teléfono de la persona que llama original. Esta es la configuración predeterminada y recomendada.
    - Si se establece en habilitado, se muestra el número de teléfono de la cuenta del recurso.

En un entorno híbrido de Skype empresarial, para transferir una llamada de operador automático a la RTC, cree un nuevo usuario local con el desvío de llamadas establecido en el número de la RTC. El usuario debe estar habilitado para telefonía IP empresarial y tiene asignada una directiva de voz. Para obtener más información, consulte [transferencia automática de llamadas de operador a RTC](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="create-an-auto-attendant-with-powershell"></a>Crear un operador automático con PowerShell

También puede usar PowerShell para crear y configurar operadores automáticos. Estos son los cmdlets que necesita para administrar un operador automático:

- [Nuevo: CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [Nuevo: CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [Nuevo: CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [Nuevo: CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Exportar-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [Nuevo: CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Importar-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [Nuevo: CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa) 

[Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
