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
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 5e28aa4774d105b687551601ba89657d91a08170
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356558"
---
# <a name="music-on-hold"></a>Música en espera

Cuando un Microsoft Teams coloca una llamada entrante de la red telefónica conmutada (RTC) en espera, el autor de la llamada RTC puede escuchar la música seleccionada.

La música que se reproduce es la música predeterminada proporcionada por Microsoft o la música personalizada que carga y configura. Como administrador de inquilinos, puede configurar si Música en espera está disponible creando una directiva de llamada de Teams y asignando la directiva al Teams usuario. 

Tenga en cuenta que los autores de llamadas RTC también pueden escuchar Música en espera en otros escenarios; por ejemplo, cuando llaman a una cola de llamadas en la nube o cuando su llamada está estacionada por un Microsoft Teams usuario. Estas situaciones no están cubiertas ni controladas por las características mencionadas en este artículo. 

## <a name="configure-music-on-hold"></a>Configurar Música en espera

Para configurar Música en espera:

1.  En el panel de navegación izquierdo del centro Teams de administración, vaya **a Directivas de llamadas > voz.**

2.  En la **pestaña Administrar directivas,** seleccione una de las directivas existentes o cree una nueva.

3.  En el **Música de llamadas RTC** en espera, seleccione **Habilitado** en el menú desplegable.

También puede configurar Música en espera mediante el módulo Teams PowerShell. En teamsCallingPolicy, cambie el parámetro MusicOnHoldEnabledType a Habilitado y, después, conceda esa instancia de directiva a uno o varios usuarios.

Si un usuario Teams tiene una directiva de llamadas Teams con Música en espera establecida en Deshabilitado, no se reproducirá música cuando el usuario de Teams coloca la llamada en espera.

## <a name="configure-custom-music"></a>Configurar música personalizada

> [!NOTE]
> Esta característica está disponible como versión de vista previa pública.

Además de reproducir música predeterminada para los autores de llamadas RTC, puede cargar un archivo de audio personalizado con música u otro contenido de audio y configurar ese archivo de audio para que se resalte al autor de la llamada RTC.
Por ejemplo, es posible que un departamento u organización quiera reproducir un anuncio personalizado o música personalizada cuando los autores de llamadas RTC externos se pongan en espera.  

> [!NOTE]
> Usted es responsable de borrar y proteger de forma independiente todos los derechos y permisos necesarios para usar cualquier archivo de música o audio con su Microsoft Teams servicio. Esto puede incluir propiedad intelectual y otros derechos en cualquier música, efectos de sonido, audio, marcas, nombres y otros contenidos del archivo de audio de todos los titulares de derechos pertinentes. Los titulares pueden incluir artistas, actores, intérpretes, músicos, compositores, compositores, discográficas, editores de música, uniones, cofradías, asociaciones de derechos, organizaciones de administración colectiva y cualquier otra parte que tenga, controle o licencia los derechos de propiedad intelectual, los efectos sonoros, el audio y otros derechos de propiedad intelectual.

Para configurar las Música personalizadas en espera, use los cmdlets de PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove-CsOnlineAudioFile en Teams módulo de PowerShell 2.5.0 o posterior.


1. Asegúrese de que Teams usuario Música en espera para los autores de llamadas RTC establecidos en Habilitado en la directiva Teams llamadas. 

2. Upload el archivo de audio personalizado.

3. Cree una Teams de espera de llamada que haga referencia al archivo de audio personalizado y asígnelo al Teams usuario.

### <a name="upload-the-custom-audio-file"></a>Upload el archivo de audio personalizado

La configuración de Música en espera comienza con la carga del archivo de audio. Use el cmdlet de PowerShell Import-CsOnlineAudioFile para este fin. A continuación se muestra un ejemplo de carga de un archivo de audio MP3 con la interfaz de PowerShell:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Hacer referencia al archivo de audio en una Teams de retención de llamadas

Después de cargar el archivo de audio, debe hacer referencia al archivo en una directiva de retención de llamadas de Teams mediante el Id. del archivo al crear o establecer una directiva de retención de llamadas Teams llamada. Por ejemplo:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Después de crear la nueva directiva Teams de retención de llamadas, puede concederla a los usuarios Grant-CsTeamsCallHoldPolicy la siguiente manera:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Para obtener información sobre los archivos de audio cargados, use el cmdlet Get-CsOnlineAudioFile carga.

Para quitar un archivo de audio cargado, use el cmdlet Remove-CsOnlineAudioFile carga. Antes de quitar un archivo de audio, compruebe que no está usando ese archivo de audio en teamsCallHoldPolicy.

## <a name="feature-availability"></a>Disponibilidad de características

En la tabla siguiente se indican las características en las que los clientes y dispositivos admiten Música en espera y Música en espera. Microsoft sigue agregando compatibilidad con características, por lo que vuelve a comprobar a menudo si hay disponibilidad adicional.


| Característica | Escritorio <br> Windows/Mac OS | Explorador | Móvil <br> iOS | Móvil <br> Android | Teams Teléfono |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Espera en una llamada RTC 1:1 | -Música en espera<br>-Custom Música en espera | -Música en espera<br>-Custom Música en espera | -Música en espera<br>-Custom Música en espera | Música en espera | Música en espera |
| Espera en la transferencia consultiva en la llamada RTC 1:1 |-Música en espera<br>-Custom Música en espera | | | | |

## <a name="restrictions"></a>Restricciones

- Música en espera solo está disponible en la nube comercial.

- Música en espera solo está disponible cuando el usuario está en modo TeamsOnly.

- Si el usuario Teams está habilitado para Location-Based enrutamiento, Música en espera no se puede reproducir al autor de la llamada.

- No puede exportar el archivo de audio después de cargarlo; solo puede quitarlo.

- Las Música personalizadas en espera no están disponibles para los usuarios configurados para la apariencia de línea compartida (delegación) y cuando se usa el parque de llamadas. Se reproducirá Música estándar en espera.

- En algunos escenarios, una llamada de omisión de medios de enrutamiento directo se convertirá en omisión no multimedia para reproducir Música en espera y la llamada permanecerá como omisión no multimedia hasta que finalice la llamada.


## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a los usuarios](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





