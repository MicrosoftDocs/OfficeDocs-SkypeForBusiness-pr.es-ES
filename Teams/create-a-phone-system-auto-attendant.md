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
ms.openlocfilehash: 3a501ee9cdea0cf04466be1cbbd9c8f4407a9842
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711924"
---
# <a name="set-up-an-auto-attendant"></a>Configurar un operador automático

Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el departamento adecuado, la cola de llamadas, una persona o un operador. Puede crear operadores automáticos para su organización con el centro Microsoft Teams de administración o con PowerShell.

> [!TIP]
> Este artículo es para organizaciones grandes. Si su organización es una pequeña empresa, lea [Configurar un operador automático : tutorial de pequeña empresa](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) en su lugar.

Asegúrese de que ha leído Planear Teams operadores [automáticos](plan-auto-attendant-call-queue.md) y colas de llamadas y ha seguido los pasos de [](plan-auto-attendant-call-queue.md#getting-started) introducción antes de seguir los procedimientos de este artículo.

Los operadores automáticos pueden dirigir las llamadas, según la entrada de los autores de llamadas, a uno de los siguientes destinos: <a name="call-routing-options" ></a>

- **Operador** : el operador definido para el operador automático. Definir un operador es opcional. El operador se puede definir como cualquiera de los otros destinos de esta lista.
- **Persona de la organización** : una persona de su organización que puede recibir llamadas de voz. Esta persona puede ser un usuario en línea o un usuario hospedado localmente mediante Skype Empresarial Server.
- **Aplicación de voz** : otro operador automático o una cola de llamadas. (Elija la cuenta de recursos asociada con el operador automático o la cola de llamadas al elegir este destino).
- **Correo** de voz: el buzón de voz asociado a Microsoft 365 grupo que especifique. Puede elegir si desea transcripciones de correo de voz y "Deje un mensaje después del tono". símbolo del sistema.
- **Número de teléfono externo** : cualquier número de teléfono. (Vea [detalles técnicos de transferencia externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Anuncio (archivo de audio):** reproducir un archivo de audio. Un mensaje de anuncio grabado que carga que se guarda como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede ser superior a 5 MB. El sistema reproduce el anuncio y, a continuación, vuelve al menú operador automático.
- **Anuncio (con tipo):** escriba un mensaje. Texto que desea que lea el sistema. Puede escribir hasta 1000 caracteres. El sistema reproduce el anuncio y, a continuación, vuelve al menú operador automático.

Se le pedirá que elija una de estas opciones en varias fases mientras configura un operador automático.

Para configurar un operador automático, en el centro de administración de Teams, expanda **Voz, seleccione** **Operadores automáticos** y, a continuación, **seleccione Agregar**.

## <a name="video-demonstration"></a>Demostración de vídeo

En este vídeo se muestra un ejemplo básico de cómo crear un operador automático en Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>Información general

![Captura de pantalla de la configuración del operador automático para el nombre, el operador, la zona horaria, el idioma y las entradas de voz.](media/auto-attendant-general-info-page-new.png)

1. Escriba un nombre para el operador automático en el cuadro de la parte superior.

2. Para designar un operador, especifique el destino de las llamadas al operador. Esta designación es opcional (pero recomendada). Establezca la **opción Operador** para permitir a los autores de llamadas salir de los menús y hablar con una persona designada.

3. Especifique la zona horaria para este operador automático. La zona horaria se usa para calcular el horario laboral si crea [un flujo de llamadas independiente para horas posteriores](#call-flow-for-after-hours).

4. Especifique un [idioma compatible](create-a-phone-system-auto-attendant-languages.md) para este operador automático. Este es el idioma que se usará para las solicitudes de voz generadas por el sistema.

5. Elija si desea habilitar las entradas de voz. Cuando se habilita, el nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la opción de menú denominada "Ventas".

   > [!NOTE]
   > Si elige un idioma en el paso 4 que no admite entradas de voz, esta opción se deshabilitará.

6. Seleccione **Siguiente**.

## <a name="call-flow"></a>Flujo de llamadas

![Captura de pantalla de la configuración del mensaje de felicitación.](media/auto-attendant-call-flow-greeting-message.png)

Elija si desea reproducir un saludo cuando el operador automático responda a una llamada.

Si selecciona **Reproducir un archivo de audio**, puede usar el botón **Upload** archivo para cargar un mensaje de saludo grabado guardado como audio en . WAV, .MP3 o . Formato WMA. La grabación no puede ser superior a 5 MB.

Si selecciona **Escribir un mensaje de** saludo, el sistema leerá el texto que escriba (hasta 1000 caracteres) cuando el operador automático responda a una llamada.

![Captura de pantalla de la configuración de enrutamiento de llamadas.](media/auto-attendant-call-flow-route-call-message.png)

Elija cómo desea enrutar la llamada.

Si **selecciona Desconectar,** el operador automático colgará la llamada.

Si selecciona **Redirigir llamada**, puede elegir uno de los destinos de enrutamiento de llamadas.

Si selecciona Opciones **de menú** Reproducir, puede elegir Reproducir un archivo de **audio** o Escribir en un mensaje de saludo y, **a** continuación, elegir entre opciones de menú y búsqueda de directorios.

### <a name="menu-options"></a>Opciones de menú

![Captura de pantalla de las opciones de la tecla de marcado.](media/auto-attendant-call-flow-menu-options-complete.png)

Para las opciones de marcado, asigne las teclas 0-9 del teclado del teléfono a uno de los destinos de enrutamiento de llamadas. (Las teclas \* (asterisco) y \# (libra) están reservados por el sistema y no se pueden reasignar. Al presionar cualquiera de estas teclas, se repetirá el menú actual).

> [!NOTE]
> La tecla # solo hace una copia de seguridad del operador automático más reciente. Una vez que se haya cruzado el límite a un nuevo operador automático, la tecla # no podrá llevarte al anterior.

Las asignaciones de claves no tienen que ser continuas. Es posible crear un menú con las teclas 0, 1 y 3 asignadas a opciones, mientras que la tecla número 2 no se usa.

Se recomienda asignar la clave cero al operador si ha configurado una. Si el operador no está establecido en ninguna tecla, el comando de voz "Operador" también está deshabilitado.

Para cada opción de menú, especifique la siguiente configuración:

- **Tecla de marcado** : la tecla del teclado del teléfono para acceder a esta opción. Si hay entradas de voz disponibles, los autores de llamadas también pueden decir este número para acceder a la opción.

- **Comando de voz** : define el comando de voz que un autor de la llamada puede dar para obtener acceso a esta opción, si las entradas de voz están habilitadas. Puede contener varias palabras como "Servicio al cliente" o "Operaciones y motivos". Por ejemplo, el autor de la llamada puede presionar 2, decir "dos" o decir "Ventas" para seleccionar la opción asignada a las dos teclas. Este texto también se representa de texto a voz para el mensaje de confirmación del servicio, que puede ser algo así como "Transferir la llamada a las ventas".

- **Redirigir a** : el destino de enrutamiento de llamadas que se usa cuando los autores de llamadas eligen esta opción. Si va a redirigir a un operador automático o a una cola de llamadas, elija la cuenta de recursos asociada.

### <a name="directory-search"></a>Búsqueda de directorios

Si asigna teclas de marcado a destinos, le recomendamos que elija **Ninguna para** búsqueda **de directorio**. Si un autor de la llamada intenta marcar un nombre o una extensión con claves asignadas a destinos específicos, es posible que se enruten inesperadamente a un destino antes de que terminen de escribir el nombre o la extensión. Le recomendamos que cree un operador automático independiente para la búsqueda de directorios y que tenga el vínculo del operador automático principal con una tecla de marcado.

Si no ha asignado las teclas de marcado, elija una opción para la búsqueda **de directorios**.

**Marcar por nombre** : si habilita esta opción, los autores de llamadas pueden decir el nombre del usuario o escribirlo en el teclado del teléfono. Cualquier usuario en línea o cualquier usuario hospedado local que use Skype Empresarial Server, es un usuario apto y se puede encontrar con Marcado por nombre. (Puede establecer quién es y quién no se incluye en el directorio en la [página Ámbito de](#dial-scope) marcado).

**Marcar por extensión** : si habilita esta opción, los autores de llamadas pueden conectarse con los usuarios de su organización marcando su extensión de teléfono. Cualquier usuario en línea o cualquier usuario hospedado local que use Skype Empresarial Server, es un usuario apto y se puede encontrar **con Marcar por extensión**. (Puede establecer quién es y quién no se incluye en el directorio en la [página Ámbito de](#dial-scope) marcado).

Los usuarios que desee que estén disponibles para Marcar por extensión deben tener una extensión especificada como parte de uno de los siguientes atributos de teléfono definidos en Active Directory (y sincronizados a través de Azure AD Conectar) o Azure Active Directory. (Vea [Agregar usuarios individualmente o en masa](/microsoft-365/admin/add-users/add-users) para obtener más información).

- OfficePhone/TelephoneNumber (AD y Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD y Azure AD)
- OtherTelephone (AD)

El formato necesario para introducir la extensión en el campo de número de teléfono de usuario puede ser uno de los siguientes formatos:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- Ejemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Ejemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Ejemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Puede establecer la extensión en [el Centro de administración de Microsoft 365 o](https://admin.microsoft.com/) en el [centro Azure Active Directory administración](https://aad.portal.azure.com). Los operadores automáticos y las colas de llamadas pueden tardar hasta 12 horas en estar disponibles para los cambios.

> [!NOTE]
> Si desea usar las características Marcar por  nombre y Marcar por  extensión, puede asignar una clave de marcado en el operador automático principal para llegar a un operador automático habilitado para Marcar **por nombre**. Dentro de ese operador automático, puede asignar la tecla 1 (que no tiene letras asociadas) para que llegue al operador automático Marcar **por extensión.**

Consulte Referencia [de marcado y voz](dial-voice-reference.md) para obtener más información.

Una vez que haya seleccionado una **opción de búsqueda de** directorio, seleccione **Siguiente**.

## <a name="call-flow-for-after-hours"></a>Flujo de llamadas para horas  pasadas

![Captura de pantalla de la configuración de días y horas adicionales.](media/auto-attendant-business-hours.png)

El horario laboral se puede establecer para cada operador automático. Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada. El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral. Puede establecer diferentes opciones de administración de llamadas entrantes y saludos para las horas adicionales.

Según cómo haya configurado los operadores automáticos y las colas de llamadas, es posible que solo tenga que especificar el enrutamiento de llamadas adicionales para los operadores automáticos con números de teléfono directos.

Si quiere un enrutamiento de llamadas independiente para las personas que llaman fuera del horario laboral, especifique su horario laboral para cada día. Seleccione **Agregar nueva hora para** especificar varios conjuntos de horas para un día determinado, por ejemplo, para especificar un descanso para comer.

Una vez que haya especificado el horario laboral, elija las opciones de enrutamiento de llamadas para horas adicionales. Las mismas opciones están disponibles que para el enrutamiento de llamadas en horario laboral que especificó anteriormente.

Seleccione **Siguiente** cuando haya terminado.

## <a name="call-flows-during-holidays"></a>Flujos de llamadas durante los días festivos

![Captura de pantalla de la configuración de saludo navideña y navideña.](media/auto-attendant-holiday-greeting.png)

El operador automático puede tener un flujo de llamadas para cada [vacaciones que haya configurado](set-up-holidays-in-teams.md). Puede agregar un máximo de 20 días festivos programados a cada operador automático.

1. En la página Configuración de la llamada navideña, seleccione **Agregar**.

2. Escriba un nombre para esta configuración navideña.

3. En la **lista desplegable** Vacaciones, elija los días festivos que quiera usar.

4. Elija el tipo de saludo que desea usar.

    ![Captura de pantalla de la configuración de acción de llamada navideña.](media/auto-attendant-holiday-actions.png)

5. Elija si desea desconectar **o** **redirigir la** llamada.

6. Si elige redirigir, elija el destino de enrutamiento de llamadas para la llamada.

7. Seleccione **Guardar**.

![Captura de pantalla de la configuración de vacaciones con días festivos en la lista.](media/auto-attendant-holiday-call-settings.png)

Repita el procedimiento según sea necesario para cada vacaciones adicionales.

Cuando haya agregado todos los días festivos, seleccione **Siguiente**.

## <a name="dial-scope"></a>Ámbito de marcado

![Captura de pantalla del ámbito de marcado incluir y excluir opciones.](media/auto-attendant-dial-scope.png)

El *ámbito de marcado* define qué usuarios están disponibles en el directorio cuando un autor de la llamada usa marcado por nombre o marcado por extensión. El valor predeterminado de **Todos los usuarios en** línea incluye todos los usuarios de su organización que son usuarios en línea o hospedados localmente mediante Skype Empresarial Server.

Puede incluir o excluir usuarios específicos seleccionando Grupo de usuarios personalizados  en Incluir  o Excluir y eligiendo uno o varios grupos de Microsoft 365, listas de distribución o grupos de seguridad. Por ejemplo, es posible que desee excluir ejecutivos de su organización del directorio de marcado. (Si un usuario está en ambas listas, se excluirá del directorio).

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio.

Cuando haya terminado de configurar el ámbito de marcado, seleccione **Siguiente**.

## <a name="resource-accounts"></a>Cuentas de recursos

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán al menos una cuenta de recursos que tenga un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada una con un número de servicio independiente.

![Captura de pantalla del panel agregar cuentas de la cuenta de recursos.](media/auto-attendant-add-resource-account.png)

Para agregar una cuenta de recurso, seleccione **Agregar cuenta** y busque la cuenta que desea agregar. Seleccione **Agregar** y, a continuación, **seleccione Agregar**.

![Captura de pantalla de la lista de cuentas de recursos que muestra la cuenta de recursos con el número de servicio asignado.](media/auto-attendant-resource-account-assigned.png)

Cuando haya terminado de agregar cuentas de recursos, seleccione **Enviar** para completar la configuración de operador automático.

Vea [Administrar Teams de recursos para](manage-resource-accounts.md) obtener más información.

## <a name="external-phone-number-transfers---technical-details"></a>Transferencias de números de teléfono externos: detalles técnicos

Consulte Los [requisitos previos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que los operadores automáticos transfieran llamadas externamente.  Además:

- Para una cuenta de recurso con una licencia de [plan](calling-plans-for-office-365.md) de llamadas o un número de operador [Conectar](operator-connect-plan.md), el número de teléfono de transferencia externa debe especificarse en formato E.164 (+[código de país][código de área][número de teléfono]).

- Para una cuenta de recursos con una directiva de enrutamiento de voz de Microsoft Teams Teléfono Licencia y Enrutamiento directo en línea, el formato de número de teléfono de transferencia externa depende de la configuración del Controlador de borde de sesión [(SBC](direct-routing-connect-the-sbc.md)).

El número de teléfono saliente que se muestra se determina de la siguiente manera:

  - Para el plan de llamadas y el operador Conectar, se muestra el número de teléfono del autor de la llamada original.
  - Para los números de enrutamiento directo, el número enviado se basa en la configuración P-Asserted-Identity (PAI) en el SBC, como se muestra a continuación:
    - Si se establece en Deshabilitado, se muestra el número de teléfono del autor de la llamada original. Esta es la configuración predeterminada y recomendada.
    - Si se establece en Habilitado, se muestra el número de teléfono de la cuenta de recurso.

En un Skype Empresarial híbrido, para transferir una llamada de operador automático a la RTC, cree un nuevo usuario local con el reenvío de llamadas establecido en el número RTC. El usuario debe estar habilitado para Telefonía IP empresarial y tener asignada una directiva de voz. Para obtener más información, vea [Transferencia automática de llamadas a RTC](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

## <a name="auto-attendant-cmdlets"></a>Cmdlets para operadores automáticos

Windows PowerShell permite crear y administrar operadores automáticos a través de la línea de comandos de forma por lotes o mediante programación.

Los siguientes cmdlets le permiten administrar operadores automáticos:

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

Los siguientes cmdlets adicionales también son necesarios para administrar los usuarios, cuentas de recursos, licencias de Microsoft Teams Teléfono, números de teléfono, archivos de audio e idioma compatible que se usarán con las colas de llamadas:

Usuarios/Teams

- Usuarios
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)

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
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

Archivos de audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Idiomas de soporte técnico y zonas horarias

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

Para obtener una guía paso a paso para crear operadores automáticos con PowerShell, vea Crear [operadores automáticos con cmdlets de PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="auto-attendant-diagnostic-tool"></a>Operador automático de diagnóstico

Si es administrador, puede usar la siguiente herramienta de diagnóstico para validar que un operador automático puede recibir llamadas:

1. Seleccione **Ejecutar pruebas** a continuación, lo cual rellenará el diagnóstico en el Centro de administración de Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Ejecutar pruebas: Teams Operador automático](https://aka.ms/TeamsAADiag)

2. En el panel Ejecutar diagnóstico, escriba la cuenta de recursos en el campo Nombre de usuario o **Correo** electrónico y, a continuación, seleccione **Ejecutar pruebas**.

3. Las pruebas identificarán las configuraciones de cuenta de inquilino, directiva o recurso que impiden que el operador automático pueda recibir llamadas y proporcionará pasos para solucionar los problemas identificados.

## <a name="related-topics"></a>Temas relacionados

[Esto es lo que obtienes con Teams Teléfono](./here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio](./getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
