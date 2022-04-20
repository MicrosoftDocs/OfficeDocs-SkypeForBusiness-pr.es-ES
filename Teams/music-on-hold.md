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
description: Obtenga información sobre cómo administrar la característica Música en espera en Sistema telefónico.
ms.openlocfilehash: 3e3e9c12eb459fdf52506be4577dfea88943ffa7
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922661"
---
# <a name="music-on-hold"></a>Música en espera

Cuando un usuario Microsoft Teams pone una llamada entrante en espera, el autor de la llamada puede escuchar la música seleccionada.

La música que se reproduce es la música predeterminada proporcionada por Microsoft o la música personalizada que cargues y configures. Como administrador de inquilinos, puede configurar si Música en espera está disponible creando una directiva de llamadas de Teams y asignando la directiva al usuario de Teams.

La música predeterminada suministrada en Microsoft Teams escenarios de llamadas está libre de las regalías que su organización debe pagar.

Tenga en cuenta que los autores de llamadas también pueden escuchar Música en espera en otros escenarios; por ejemplo, cuando llaman a una cola de llamadas en la nube o cuando un usuario de Microsoft Teams estaciona su llamada. Estas situaciones no están cubiertas ni controladas por las características mencionadas en este artículo.

## <a name="configure-music-on-hold"></a>Configurar Música en espera

Para configurar Música en espera:

1.  En el panel de navegación izquierdo del centro de administración de Teams, vaya a **Directivas de llamadas de voz >**.

2.  En la pestaña **Administrar directivas** , seleccione una de las directivas existentes o cree una nueva.

3.  En el campo **Música en espera para autores de llamadas RTC**, seleccione **Habilitado** en el menú desplegable.

También puede configurar Música en espera mediante el módulo Teams PowerShell. En TeamsCallingPolicy, cambie el parámetro MusicOnHoldEnabledType a Enabled y, a continuación, conceda esa instancia de directiva a uno o más usuarios.

Si un usuario Teams tiene una directiva de llamada Teams con Música en espera establecido en Deshabilitado, no se reproducirá música cuando el usuario de Teams pone la llamada en espera.

## <a name="configure-custom-music"></a>Configurar música personalizada

Además de reproducir música predeterminada para los autores de llamadas, puede cargar un archivo de audio personalizado con música u otro contenido de audio y configurar ese archivo de audio para que se reproduzca al autor de la llamada.
Por ejemplo, un departamento u organización podría querer reproducir un anuncio personalizado o música personalizada cuando se ponen en espera las llamadas RTC externas.  

> [!NOTE]
> Usted es responsable de borrar y proteger de forma independiente todos los derechos y permisos necesarios para usar cualquier archivo de música o audio con su servicio de Microsoft Teams. Esto puede incluir la propiedad intelectual y otros derechos en cualquier música, efectos de sonido, audio, marcas, nombres y otro contenido del archivo de audio de todos los titulares de derechos pertinentes. Los titulares pueden incluir artistas, actores, artistas intérpretes o ejecutantes, músicos, compositores, sellos discográficos, editores musicales, sindicatos, sindicatos, sociedades de derechos, organizaciones de gestión colectiva y cualquier otra parte que posea, controle o licencia los derechos de autor de la música, efectos sonoros, audio y otros derechos de propiedad intelectual.

Para configurar Música personalizadas en espera, use los cmdlets de PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile en Teams módulo de PowerShell 3.0.0 o posterior.

Para ver los formatos de audio admitidos y el tamaño máximo de archivo, consulte [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)


1. Asegúrese de que el usuario de Teams tiene Música en espera para los autores de llamadas RTC establecido en Habilitado en la directiva de llamadas Teams. 

2. Upload el archivo de audio personalizado.

3. Cree una Teams directiva de suspensión de llamadas que haga referencia al archivo de audio personalizado y asígnelo al usuario de Teams.

### <a name="upload-the-custom-audio-file"></a>Upload el archivo de audio personalizado

La configuración de Música personalizadas en espera comienza con la carga del archivo de audio. Para este propósito, se usa el cmdlet de PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

A continuación se muestra un ejemplo de carga de un archivo de audio MP3 con la interfaz de PowerShell:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Hacer referencia al archivo de audio en una Teams directiva de retención de llamadas

Después de cargar el archivo de audio, debe hacer referencia al archivo en una Teams directiva de suspensión de llamadas con el Identificador del archivo al crear o establecer una Teams directiva de retención de llamadas. Por ejemplo:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Después de crear la nueva Teams directiva de suspensión de llamadas, puede concederla a los usuarios mediante Grant-CsTeamsCallHoldPolicy como se indica a continuación:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Para obtener información sobre los archivos de audio cargados, use el cmdlet de Get-CsOnlineAudioFile.

Para quitar un archivo de audio cargado, use el cmdlet Remove-CsOnlineAudioFile. Antes de quitar un archivo de audio, compruebe que no está usando ese archivo de audio en un TeamsCallHoldPolicy.

Para exportar un archivo de audio cargado, use el cmdlet de Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilidad de características

La tabla siguiente indica qué características admiten los clientes y dispositivos Música en espera y Música personalizadas en espera. Microsoft sigue agregando soporte técnico para las características, por lo que debe volver a comprobar con frecuencia si hay disponibilidad adicional.


| Característica | Escritorio <br> Windows/Mac OS | Explorador | Móvil <br> iOS | Móvil <br> Android | Teams Teléfono |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Espera en llamada RTC 1:1 | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera |
| Espera 1:1 Teams llamada | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera |
| Espera en transferencia consultiva en llamada RTC 1:1 |-Música en espera<br>-Música personalizado en espera || -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera |
| Espera en transferencia consultiva el 1:1 Teams llamada |-Música en espera<br>-Música personalizado en espera || -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera | -Música en espera<br>-Música personalizado en espera |

## <a name="restrictions"></a>Restricciones

- Música en espera solo está disponible en instancias comerciales y GCC en la nube.

- Música en espera solo está disponible cuando el usuario está en modo TeamsOnly.

- Si el usuario llamado Teams está habilitado para Location-Based enrutamiento, no se puede reproducir Música en espera al autor de la llamada.

- La Música personalizada en espera no está disponible para los usuarios configurados para la apariencia de línea compartida (delegación) y cuando se usa el parque de llamadas. Se reproducirá el Música estándar en espera.

- En algunos casos, una llamada de omisión multimedia de enrutamiento directo se convertirá en omisión no multimedia para reproducir Música en espera y la llamada permanecerá como omisión no multimedia hasta que finalice la llamada.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)
