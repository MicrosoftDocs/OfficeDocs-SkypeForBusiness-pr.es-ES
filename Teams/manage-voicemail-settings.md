---
title: Administrar la configuración de Correo de voz en la nube
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
description: Administrar la configuración del correo de voz de los usuarios.
ms.openlocfilehash: 80dad0b2088518c9d6f08ee005eba25cc1e10e2b
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494863"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>Administrar la configuración de Correo de voz en la nube para los usuarios

La configuración del correo de voz le permite configurar el correo de voz para usuarios individuales.

Antes de configurar las opciones del correo de voz de los usuarios, lea [Configurar Correo de voz en la nube](set-up-phone-system-voicemail.md). Para obtener información sobre cómo establecer directivas para grupos de usuarios, vea [Administrar directivas de correo de voz](manage-voicemail-policies.md).

La configuración predeterminada para Correo de voz en la nube es la siguiente:

- El correo de voz está habilitado.
- El idioma del mensaje se establece en el idioma preferido del usuario.
- El saludo de fuera de la oficina está deshabilitado.
- El saludo de fuera de la oficina, cuando se configuran las respuestas automáticas en Outlook, está deshabilitado.
- El saludo de fuera de la oficina, cuando el calendario de Outlook muestra Fuera de la oficina, está deshabilitado.
- Se deshabilita el uso compartido de los datos del correo de voz y la transcripción con el servicio para la formación y mejora de la precisión.
- La regla de respuesta de llamadas se establece en Correo de voz normal.
- No se establece la sobrescritura del mensaje de saludo predeterminado.
- No se establece la sobrescritura predeterminada del mensaje de saludo de Fuera de la oficina.
- El objetivo de transferencia no está establecido.


Para administrar Correo de voz en la nube características para los usuarios, puede usar el Centro de administración de Teams o PowerShell. Tenga en cuenta que los usuarios finales también pueden configurar estas opciones en el cliente de Teams yendo a **Configuración -> Llamadas -> Configurar correo de voz.**

## <a name="use-teams-admin-center"></a>Usar el Centro de administración de Teams

En el Centro de administración de Teams:

1.  En el panel de navegación izquierdo, vaya a **Usuarios > Administrar usuarios** y seleccione el usuario.

2.  En la página de detalles del usuario, vaya a la pestaña **Correo de voz** .

3.  Cambia la configuración.

4.  Seleccione **Guardar**.


## <a name="use-powershell"></a>Usar PowerShell

También puede usar PowerShell para administrar la configuración del correo de voz de la siguiente manera:

- Para administrar Correo de voz en la nube configuración para usuarios individuales, use el cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). 

- Para ver la configuración, use el cmdlet [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) .

- Puede deshabilitar Correo de voz en la nube para un usuario mediante el cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) y establecer el parámetro VoicemailEnabled en $false. 

## <a name="voicemail-settings"></a>Configuración del correo de voz

- **Correo de voz habilitado**: esta configuración controla si Correo de voz en la nube está habilitado para el usuario. Si la configuración es falsa, Correo de voz en la nube servicio no estará disponible para el usuario y no registrará un correo de voz del usuario.

- **Idioma del mensaje**: esta configuración especifica el idioma usado para las indicaciones de la Correo de voz en la nube. Para obtener más información, vea [Cambiar el idioma predeterminado para saludos y correos electrónicos](change-the-default-language-for-greetings-and-emails.md).

- **Configuración del saludo**: Correo de voz en la nube puede reproducir un saludo específico para cuando el usuario está en la oficina y para cuando el usuario está fuera de la oficina. El usuario puede grabar ambos saludos o usar un saludo de texto a voz.

  - **Sobrescribir mensaje de saludo predeterminado** : especifica el saludo de texto a voz que se reproducirá en caso de que el usuario no haya grabado un saludo.

  - **Saludo habilitado** : especifica si el saludo de fuera de la oficina se reproduce en el escenario de depósito del correo de voz, independientemente de la configuración de Outlook.

  - **Saludo de Oof Seguir respuestas automáticas habilitadas** : especifica si se debe reproducir el saludo de fuera de la oficina en el escenario de depósito del correo de voz cuando el usuario establece respuestas automáticas en Outlook.

  - **Oof Greeting Follow Calendar Enabled** : especifica si se debe reproducir el saludo de fuera de la oficina en el escenario de depósito del correo de voz cuando el usuario se establece fuera de la oficina en el calendario.

  - **Sobrescribir símbolo del sistema operativo predeterminado** : especifica el saludo de texto a voz que se reproducirá en caso de que el usuario esté fuera de la oficina y no haya grabado un saludo de fuera de la oficina.

- **Regla de respuesta de llamadas** : esta configuración especifica la regla de respuesta de llamadas. La regla puede ser:
  - El servicio rechazará la llamada sin mensaje.
  - Solo se reproduce el saludo correspondiente (normal o fuera de la oficina).
  - Se reproduce el saludo relevante (normal o fuera de la oficina) y el autor de la llamada se transfiere al usuario o número de teléfono especificado.
  -  Se reproduce el saludo relevante (normal o fuera de la oficina) y el autor de la llamada puede dejar un correo de voz.
  - Se reproduce el saludo relevante (normal o fuera de la oficina), el autor de la llamada puede dejar un correo de voz y puede presionar 0 para transferirlo al usuario o número de teléfono especificado.

- **Compartir datos para mejoras del servicio** : especifica si los datos del correo de voz y la transcripción se comparten con el servicio para la formación y la mejora de la precisión. Si se establece en false, los datos del correo de voz no se compartirán, independientemente de la elección del usuario.

- **Transferencia de llamada** : especifica el usuario o número de teléfono al que se transfiere el autor de la llamada.


