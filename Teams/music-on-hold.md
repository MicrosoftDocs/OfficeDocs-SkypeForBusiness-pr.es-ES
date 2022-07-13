---
title: Música en espera
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: Aprende a administrar la función Música en espera de Sistema telefónico.
ms.openlocfilehash: 9d8fa247ffdc982c5d41777c68f6b620a92644e3
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773759"
---
# <a name="music-on-hold"></a>Música en espera

Cuando un usuario de Microsoft Teams pone una llamada entrante en espera, el autor de la llamada puede escuchar la música seleccionada.

La música que se reproduce es la música predeterminada proporcionada por Microsoft o la música personalizada que cargues y configures. Como administrador de inquilinos, puede configurar si Música en espera está disponible creando una directiva de llamadas de Teams y asignando la directiva al usuario de Teams.

La música predeterminada que se proporciona en los escenarios de llamadas de Microsoft Teams está libre de las regalías que su organización debe pagar.

Ten en cuenta que los autores de llamadas también pueden escuchar Música en espera en otros escenarios; por ejemplo, cuando llama a una cola de llamadas en la nube o cuando un usuario de Microsoft Teams estaciona su llamada. Estas situaciones no están cubiertas ni controladas por las características mencionadas en este artículo.

## <a name="configure-music-on-hold"></a>Configurar música en espera

Para configurar Música en espera:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Directivas de llamadas de voz >**.

2. En la pestaña **Administrar directivas** , seleccione una de las directivas existentes o cree una nueva.

3. En el campo **Música en espera para autores de llamadas RTC** , seleccione **Habilitado** en el menú desplegable.

También puede configurar Música en espera mediante el módulo de PowerShell de Teams. En TeamsCallingPolicy, cambie el parámetro MusicOnHoldEnabledType a Enabled y, a continuación, conceda esa instancia de directiva a uno o más usuarios.

Si un usuario de Teams tiene una directiva de llamadas de Teams con la opción Música en espera establecida en Deshabilitada, no se reproducirá música cuando el usuario de Teams pone la llamada en espera.

## <a name="configure-custom-music"></a>Configurar música personalizada

Además de reproducir música predeterminada para los autores de llamadas, puede cargar un archivo de audio personalizado con música u otro contenido de audio y configurar ese archivo de audio para que se reproduzca al autor de la llamada.
Por ejemplo, un departamento u organización podría querer reproducir un anuncio personalizado o música personalizada cuando se ponen en espera las llamadas RTC externas.

La configuración se realiza mediante directivas de retención de llamadas.

> [!NOTE]
> Usted es responsable de borrar y proteger de forma independiente todos los derechos y permisos necesarios para usar cualquier archivo de música o audio con su servicio de Microsoft Teams. Esto puede incluir la propiedad intelectual y otros derechos en cualquier música, efectos de sonido, audio, marcas, nombres y otro contenido del archivo de audio de todos los titulares de derechos pertinentes. Los titulares pueden incluir artistas, actores, artistas intérpretes o ejecutantes, músicos, compositores, sellos discográficos, editores musicales, sindicatos, sindicatos, sociedades de derechos, organizaciones de gestión colectiva y cualquier otra parte que posea, controle o licencia los derechos de autor de la música, efectos sonoros, audio y otros derechos de propiedad intelectual.

### <a name="use-the-teams-admin-center"></a>Usar el Centro de administración de Teams
Puede usar el Centro de administración de Teams para configurar música personalizada en espera para los usuarios creando o editando directivas de suspensión de llamadas.

Para configurar una nueva directiva de retención de llamadas:

1. En el Centro de administración de Teams, vaya a **Directivas** de **retención de llamadas de** voz > .

2. Seleccione la pestaña **Agregar** .

3. Asigne un nombre y una descripción a la directiva.

4. Selecciona **Cargar archivo** para cargar el archivo de audio de música personalizado.

5. Seleccione **Aplicar**.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>Asignar una directiva de retención de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>Usar PowerShell
Para configurar música en espera personalizada, use los cmdlets de PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile en el módulo de PowerShell 3.0.0 o posterior de Teams.

Para ver los formatos de audio admitidos y el tamaño máximo de archivo, consulte [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Asegúrese de que el usuario de Teams tiene Música en espera para los autores de llamadas RTC establecido en Habilitado en la directiva de llamadas de Teams. 

2. Cargue el archivo de audio personalizado.

3. Cree una directiva de suspensión de llamadas de Teams que haga referencia al archivo de audio personalizado y asígnelo al usuario de Teams.

### <a name="upload-the-custom-audio-file"></a>Cargar el archivo de audio personalizado

La configuración de Música en espera personalizada comienza con la carga del archivo de audio. Para este propósito, se usa el cmdlet de PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

A continuación se muestra un ejemplo de carga de un archivo de audio MP3 con Windows PowerShell 5.1. Para ver otros ejemplos, consulte [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Hacer referencia al archivo de audio en una directiva de retención de llamadas de Teams

Después de cargar el archivo de audio, debe hacer referencia al archivo en una directiva de suspensión de llamadas de Teams con el Identificador del archivo al crear o establecer una directiva de retención de llamadas de Teams. Por ejemplo:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Después de crear la nueva directiva de suspensión de llamadas de Teams, puede concederla a los usuarios mediante Grant-CsTeamsCallHoldPolicy como se indica a continuación:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Para obtener información sobre los archivos de audio cargados, use el cmdlet de Get-CsOnlineAudioFile.

Para quitar un archivo de audio cargado, use el cmdlet Remove-CsOnlineAudioFile. Antes de quitar un archivo de audio, compruebe que no está usando ese archivo de audio en un TeamsCallHoldPolicy.

Para exportar un archivo de audio cargado, use el cmdlet de Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilidad de características

En la tabla siguiente se indican las características en las que los clientes y dispositivos admiten Música en espera y Música personalizada en espera. Microsoft sigue agregando soporte técnico para las características, por lo que debe volver a comprobar con frecuencia si hay disponibilidad adicional.

| Característica | Escritorio <br> Windows/Mac OS | Explorador | Móvil <br> iOS | Móvil <br> Android | Teams Phone |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Espera en llamada RTC 1:1 | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera |
| Espera en llamada de Teams 1:1 | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera |
| Espera en transferencia consultiva en llamada RTC 1:1 |-Música en espera<br>-Música personalizada en espera || -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera |
| Retener la transferencia consultiva en la llamada de Teams 1:1 |-Música en espera<br>-Música personalizada en espera || -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera | -Música en espera<br>-Música personalizada en espera |

## <a name="restrictions"></a>Restricciones

- Música en espera solo está disponible en instancias comerciales y en la nube GCC.

- Música en espera solo está disponible cuando el usuario está en el modo TeamsOnly.

- Si el usuario llamado de Teams está habilitado para Location-Based Enrutamiento, no se podrá reproducir música en espera para el autor de la llamada.

- Música personalizada en espera no está disponible para los usuarios configurados para la apariencia de línea compartida (delegación) y cuando se usa el parque de llamadas. Se reproducirá la música en espera estándar.

- En algunos casos, una llamada de omisión multimedia de enrutamiento directo se convertirá en omisión no multimedia para reproducir música en espera y la llamada permanecerá como omisión no multimedia hasta que finalice la llamada.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
