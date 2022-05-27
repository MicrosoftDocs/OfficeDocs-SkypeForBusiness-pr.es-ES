---
title: Configurar un operador automático para Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: Obtenga información sobre cómo configurar y probar operadores automáticos para grandes organizaciones en Microsoft Teams.
ms.openlocfilehash: 5f4b4f21f2e1cca8c8bbc350541cdd861b1bda3f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674372"
---
# <a name="set-up-an-auto-attendant"></a>Configurar un operador automático

Los operadores automáticos permiten que las personas llamen a su organización y naveguen por un sistema de menús para hablar con el departamento, la cola de llamadas, la persona o un operador adecuados. Puede crear operadores automáticos para su organización con el centro de administración de Microsoft Teams o con PowerShell.

> [!TIP]
> Este artículo está destinado a grandes organizaciones. Si su organización es una pequeña empresa, lea [el tutorial Configurar un operador automático: pequeña empresa](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) en su lugar.

Asegúrese de que ha leído [Planear Teams operadores automáticos y colas de llamadas](plan-auto-attendant-call-queue.md) y ha seguido los [pasos de introducción](plan-auto-attendant-call-queue.md#getting-started) antes de seguir los procedimientos de este artículo.

Los operadores automáticos pueden dirigir llamadas, en función de la entrada de los autores de llamadas, a uno de los siguientes destinos: <a name="call-routing-options" ></a>

- **Operador:** el operador definido para el operador automático. Definir un operador es opcional. El operador puede definirse como cualquiera de los otros destinos de esta lista.
- **Persona de la organización** : una persona de la organización que puede recibir llamadas de voz. Esta persona puede ser un usuario en línea o un usuario hospedado localmente mediante Skype Empresarial Server.
- **Aplicación de voz** : otro operador automático o una cola de llamadas. (Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).
- **Correo de voz**: el buzón de voz asociado a un grupo de Microsoft 365 que especifique. Puede elegir si quiere las transcripciones del correo de voz y "Deje un mensaje después del tono". símbolo del sistema.
- **Número de teléfono externo** : cualquier número de teléfono. (Consulte [los detalles técnicos de las transferencias externas](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Anuncio (archivo de audio):** reproducir un archivo de audio. Un mensaje de anuncio grabado que carga y que se guarda como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede tener más de 5 MB. El sistema reproduce el anuncio y, a continuación, vuelve al menú del operador automático.
- **Anuncio (escrito):** escriba un mensaje. Texto que quiere que lea el sistema. Puede escribir hasta 1000 caracteres. El sistema reproduce el anuncio y, a continuación, vuelve al menú del operador automático.

Se le pedirá que elija una de estas opciones en varias etapas al configurar un operador automático.

Para configurar un operador automático, en el Teams centro de administración, expanda **Voz**, seleccione **Operadores automáticos** y, a continuación, seleccione **Agregar**.

## <a name="video-demonstration"></a>Demostración en vídeo

Este vídeo muestra un ejemplo básico de cómo crear un operador automático en Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>Información general

![Captura de pantalla de la configuración del operador automático para las entradas de nombre, operador, zona horaria, idioma y voz.](media/auto-attendant-general-info-page-new.png)

1. Escriba un nombre para el operador automático en el cuadro de la parte superior.

2. Para designar un operador, especifique el destino de las llamadas al operador. Esta designación es opcional (pero se recomienda). Establezca la opción **Operador** para permitir que los autores de llamadas salgan de los menús y hablen con una persona designada.

3. Especifique la zona horaria de este operador automático. La zona horaria se utiliza para calcular el horario laboral si [crea un flujo de llamada independiente para fuera del horario laboral](#call-flow-for-after-hours).

4. Especifique un [idioma admitido](create-a-phone-system-auto-attendant-languages.md) para este operador automático. Este es el idioma que se usará para los mensajes de voz generados por el sistema.

5. Elija si desea habilitar las entradas de voz. Cuando está habilitada, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".

   > [!NOTE]
   > Si elige un idioma en el paso 4 que no admite entradas de voz, esta opción se deshabilitará.

6. Seleccione **Siguiente**.

## <a name="call-flow"></a>Flujo de llamadas

![Captura de pantalla de la configuración del mensaje de saludo.](media/auto-attendant-call-flow-greeting-message.png)

Elija si quiere reproducir un saludo cuando el operador automático responda a una llamada.

Si selecciona **Reproducir un archivo de audio**, puede usar el botón **Archivo de Upload** para cargar un mensaje de saludo grabado guardado como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede tener más de 5 MB.

Si selecciona **Escribir un mensaje de saludo** , el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.

![Captura de pantalla de la configuración de enrutamiento de llamadas.](media/auto-attendant-call-flow-route-call-message.png)

Elija cómo desea enrutar la llamada.

Si selecciona **Desconectar**, el operador automático colgará la llamada.

Si selecciona **Redirigir llamada**, puede elegir uno de los destinos de enrutamiento de llamadas.

Si selecciona **las opciones del menú Reproducir**, puede elegir **entre Reproducir un archivo de audio** o **Escribir un mensaje de saludo** y, después, elegir entre las opciones de menú y la búsqueda en directorio.

### <a name="menu-options"></a>Opciones de menú

![Captura de pantalla de las opciones de tecla de marcado.](media/auto-attendant-call-flow-menu-options-complete.png)

Para las opciones de marcación, asigne las teclas 0-9 del teclado del teléfono a uno de los destinos de enrutamiento de llamadas. (Las teclas \* (asterisco) y \# (libra) están reservados por el sistema y no se pueden reasignar. Al presionar cualquiera de estas teclas, se repetirá el menú actual).

> [!NOTE]
> La tecla # solo realiza copias de seguridad del operador automático más reciente. Una vez que se cruza el límite con un nuevo operador automático, la tecla # no podrá llevarte al anterior.

Las asignaciones clave no tienen por qué ser continuas. Es posible crear un menú con las teclas 0, 1 y 3 asignadas a opciones, mientras que la tecla número 2 no se usa.

Se recomienda asignar la clave cero al operador si ha configurado una. Si el operador no está establecido en ninguna tecla, el comando de voz "Operador" también está deshabilitado.

Para cada opción de menú, especifique la siguiente configuración:

- **Tecla de marcado** : la tecla del teclado del teléfono para acceder a esta opción. Si hay entradas de voz disponibles, los autores de llamadas también pueden decir este número para acceder a la opción.

- **Comando de voz** : define el comando de voz que puede dar el autor de la llamada para acceder a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras, como "Atención al cliente" o "Operaciones y motivos". Por ejemplo, el autor de la llamada puede presionar 2, decir "dos" o decir "Ventas" para seleccionar la opción asignada a las dos teclas. Este texto también se representa mediante texto a voz para el aviso de confirmación del servicio, que podría ser algo como "Transferir la llamada a ventas".

- **Redirigir a** : el destino de enrutamiento de llamadas que se usa cuando los autores de llamadas eligen esta opción. Si está redirigiendo a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada con él.

### <a name="directory-search"></a>Búsqueda en directorios

Si asigna claves de marcado a destinos, le recomendamos que elija **Ninguno** para **búsqueda en el directorio**. Si el autor de la llamada intenta marcar un nombre o una extensión mediante claves asignadas a destinos específicos, es posible que se rediriban inesperadamente a un destino antes de terminar de escribir el nombre o la extensión. Le recomendamos que cree un operador automático independiente para la búsqueda en directorios y que el operador automático principal le vincule con una clave de marcado.

Si no ha asignado claves de marcado, elija una opción para **Búsqueda en el directorio**.

**Marcar por nombre** : si habilita esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono. Cualquier usuario en línea o cualquier usuario hospedado localmente mediante Skype Empresarial Server, es un usuario apto y puede encontrarse con Marcado por nombre. (Puede establecer quién está y quién no está incluido en el directorio en la página [Ámbito de marcado](#dial-scope) ).

**Marcar por extensión** : si habilita esta opción, los autores de llamadas pueden conectarse con los usuarios de su organización marcando su extensión de teléfono. Cualquier usuario en línea o cualquier usuario hospedado localmente mediante Skype Empresarial Server, es un usuario apto y puede encontrarse con **Marcado por extensión**. (Puede establecer quién está y quién no está incluido en el directorio en la página [Ámbito de marcado](#dial-scope) ).

Los usuarios que quiera que estén disponibles para Marcado por extensión deben tener una extensión especificada como parte de uno de los siguientes atributos del teléfono definidos en Active Directory (y sincronizados a través de azure AD Conectar) o Azure Active Directory. (Vea [Agregar usuarios individualmente o de forma masiva](/microsoft-365/admin/add-users/add-users) para obtener más información).

- OfficePhone/TelephoneNumber (AD y Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD y Azure AD)
- OtherTelephone (AD)

El formato necesario para introducir la extensión en el campo de número de teléfono de usuario puede ser uno de los siguientes formatos:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Ejemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Ejemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- Ejemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Puede establecer la extensión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com/) o en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com). Pueden pasar hasta 12 horas antes de que los cambios estén disponibles para los operadores automáticos y las colas de llamadas.

> [!NOTE]
> Si desea usar las características **Marcado por nombre** y **Marcado por extensión** , puede asignar una tecla de marcado a su operador automático principal para que llegue a un operador automático habilitado para **Marcado por nombre**. Dentro de ese operador automático, puede asignar la tecla 1 (que no tiene letras asociadas con él) para alcanzar el **Dial por operador automático de extensión** .

Consulte [Marcado y referencia de voz](dial-voice-reference.md) para obtener más información.

Una vez que haya seleccionado una opción **de búsqueda en el directorio** , seleccione **Siguiente**.

## <a name="call-flow-for-after-hours"></a>Flujo de llamadas para fuera del horario laboral

![Captura de pantalla de la configuración del día y la hora fuera del horario laboral.](media/auto-attendant-business-hours.png)

El horario laboral se puede establecer para cada operador automático. Si no se establece el horario laboral, todos los días y todas las horas del día se consideran horas laborables porque se establece una programación 24/7 de forma predeterminada. El horario laboral se puede establecer con descansos temporales durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral. Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para fuera del horario laboral.

Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo deba especificar el enrutamiento de llamadas fuera del horario laboral para los operadores automáticos con números de teléfono directos.

Si desea un enrutamiento de llamadas independiente para los autores de llamadas fuera del horario laboral, especifique el horario laboral de cada día. Seleccione **Agregar nueva hora** para especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar una pausa para el almuerzo.

Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para fuera del horario laboral. Están disponibles las mismas opciones que para el enrutamiento de llamadas en horario laboral que ha especificado anteriormente.

Cuando termine, seleccione **Siguiente** .

## <a name="call-flows-during-holidays"></a>Flujos de llamadas durante los días festivos

![Captura de pantalla de la configuración del saludo navideño.](media/auto-attendant-holiday-greeting.png)

El operador automático puede tener un flujo de llamadas para cada [día festivo que haya configurado](set-up-holidays-in-teams.md). Puede agregar un máximo de 20 días festivos programados a cada operador automático.

1. En la página Configuración de llamadas navideñas, seleccione **Agregar**.

2. Escriba un nombre para esta configuración navideña.

3. En la lista desplegable **Días festivos** , elija el día festivo que quiera usar.

4. Elija el tipo de saludo que desea usar.

    ![Captura de pantalla de la configuración de la acción de llamada navideña.](media/auto-attendant-holiday-actions.png)

5. Elige si quieres las **opciones de menú** **Desconectar**, **Redirigir** o Reproducir.

6. Si decide redirigir, elija el destino del enrutamiento de llamadas para la llamada.

7. Si elige reproducir las opciones de menú, configure las [opciones de menú](#menu-options).

8. Seleccione **Guardar**.

![Captura de pantalla de la configuración de días festivos con los días festivos en la lista.](media/auto-attendant-holiday-call-settings.png)

Repita el procedimiento según sea necesario para cada día festivo adicional.

Cuando haya agregado todos los días festivos, seleccione **Siguiente**.

## <a name="dial-scope"></a>Ámbito de marcado

![Captura de pantalla del ámbito de marcado que incluye y excluye opciones.](media/auto-attendant-dial-scope.png)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando el autor de la llamada usa el marcado por nombre o marcado por extensión. El valor predeterminado de **Todos los usuarios en línea** incluye todos los usuarios de la organización que sean usuarios en línea o que se hospeden localmente con Skype Empresarial Server.

Puede incluir o excluir usuarios específicos seleccionando Grupo de **usuarios personalizados** en **Incluir** o **Excluir** y eligiendo uno o más Microsoft 365 grupos, listas de distribución o grupos de seguridad. Por ejemplo, es posible que desee excluir a los ejecutivos de su organización del directorio de marcado. (Si un usuario está en ambas listas, se excluirá del directorio).

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer su nombre en el directorio.

Cuando haya terminado de establecer el ámbito de marcado, seleccione **Siguiente**.

## <a name="resource-accounts"></a>Cuentas de recursos

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recurso que tenga un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.

![Captura de pantalla del panel agregar cuentas de recursos.](media/auto-attendant-add-resource-account.png)

Para agregar una cuenta de recursos, seleccione **Agregar cuenta** y busque la cuenta que desea agregar. Selecciona **Agregar** y, a continuación, **Agregar**.

![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado.](media/auto-attendant-resource-account-assigned.png)

Cuando haya terminado de agregar cuentas de recursos, seleccione **Enviar** para completar la configuración del operador automático.

Vea [Administrar Teams cuentas de recursos](manage-resource-accounts.md) para obtener más información.

## <a name="external-phone-number-transfers---technical-details"></a>Transferencias de números de teléfono externos: detalles técnicos

Consulte los [Requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas externamente.  Además:

- Para una cuenta de recursos con una [licencia de Plan de llamadas](calling-plans-for-office-365.md) o [un número de Conexión con operador](operator-connect-plan.md), el número de teléfono de transferencia externa debe especificarse en formato E.164 (+[código de país][código de área][número de teléfono]).

- Para una cuenta de recursos con una licencia de Teléfono Microsoft Teams y una directiva de enrutamiento de voz en línea de enrutamiento directo, el formato de número de teléfono de transferencia externa depende de la configuración del [controlador de borde de sesión (SBC](direct-routing-connect-the-sbc.md)).

El número de teléfono saliente que se muestra se determina de la siguiente manera:

  - Para los números de Plan de llamadas y Conexión con operador, se muestra el número de teléfono del autor de la llamada original.
  - Para los números de enrutamiento directo, el número enviado se basa en la configuración de P-Asserted-Identity (PAI) en el SBC, como se indica a continuación:
    - Si se establece en Deshabilitado, se muestra el número de teléfono del autor de la llamada original. Esta es la configuración predeterminada y recomendada.
    - Si se establece en Habilitado, se muestra el número de teléfono de la cuenta de recursos.

En un entorno Skype Empresarial híbrido, para transferir una llamada de operador automático a rtc, cree un nuevo usuario local con el desvío de llamadas establecido en el número de RTC. El usuario debe estar habilitado para Telefonía IP empresarial y tener asignada una directiva de voz. Para obtener más información, consulte [Transferencia automática de llamadas de operador a RTC](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

## <a name="auto-attendant-cmdlets"></a>Cmdlets para operadores automáticos

Windows PowerShell le permite crear y administrar operadores automáticos mediante la línea de comandos de forma por lotes o mediante programación.

Los cmdlets siguientes le permiten administrar operadores automáticos:

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

Los siguientes cmdlets adicionales también son necesarios para administrar los usuarios, cuentas de recursos, licencias de Teléfono Microsoft Teams, números de teléfono, archivos de audio e idioma admitido que se usará con las colas de llamadas:

Usuarios/Teams

- Usuarios
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Obtener equipo](/powershell/module/teams/Get-Team)

Cuentas de recursos:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

Licencias de Teams Teléfono virtuales:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

Teléfono asignación numérica:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

Archivos de audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Idiomas compatibles y zonas horarias

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

Para obtener una guía paso a paso para crear operadores automáticos con PowerShell, consulte [Creación de operadores automáticos con cmdlets de PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="auto-attendant-diagnostic-tool"></a>Herramienta de diagnóstico de Operador automático

Si es administrador, puede usar la siguiente herramienta de diagnóstico para validar que un operador automático pueda recibir llamadas:

1. Seleccione **Ejecutar pruebas** a continuación. Esto rellenará el diagnóstico en el Centro de administración de Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Ejecutar pruebas: Teams operador automático](https://aka.ms/TeamsAADiag)

2. En el panel Ejecutar diagnóstico, escriba la Cuenta de recursos en el campo **Nombre de usuario o Correo electrónico** y, después, seleccione **Ejecutar pruebas**.

3. Las pruebas identificarán las configuraciones de cuenta de recursos, directivas o inquilinos que impiden que el operador automático pueda recibir llamadas y proporcionarán pasos para corregir los problemas identificados.

## <a name="related-topics"></a>Temas relacionados

[Esto es lo que obtienes con Teams Teléfono](./here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](./getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
