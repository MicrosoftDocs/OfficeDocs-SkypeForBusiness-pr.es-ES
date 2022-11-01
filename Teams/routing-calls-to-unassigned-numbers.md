---
title: Enrutamiento de llamadas a números no asignados
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre cómo enrutar llamadas a números no asignados de su organización.
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795522"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Enrutamiento de llamadas a números no asignados

Como administrador, puede enrutar las llamadas a números no asignados de su organización. Por ejemplo, es posible que desee redirigir las llamadas a números no asignados de la siguiente manera: 

- Enrutar todas las llamadas a un número sin asignar determinado a un anuncio personalizado.

- Enrutar todas las llamadas a un número determinado sin asignar al panel de control principal.

Puede redirigir las llamadas a números no asignados a un usuario, a una cuenta de recurso asociada a un operador automático o a una cola de llamadas, o a un servicio de anuncios que reproducirá un archivo de audio personalizado al autor de la llamada.

Puede configurar el enrutamiento de números no asignados mediante el Centro de administración de Teams o PowerShell.

## <a name="use-teams-admin-center"></a>Usar el Centro de administración de Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Números de teléfono** **de voz** > .

2. En la pestaña **Reglas de enrutamiento** , haga clic en **Agregar**.

3. Asigne un nombre a la regla, una descripción y especifique el orden de evaluación de la regla.

4. Decida qué tipo de regla desea agregar. Puede seleccionar las reglas en las que el tipo de patrón de número de teléfono está preconfigurado y completar el patrón y la opción de enrutamiento. También puede seleccionar la configuración avanzada, donde puede especificar directamente la expresión regular para el patrón de número de teléfono y la opción de enrutamiento.

5. Seleccione **Guardar**.

También puede crear una regla de enrutamiento directamente para un número de teléfono sin asignar.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Números de teléfono** **de voz** > .

2. En la pestaña **Números** , seleccione un número de teléfono sin asignar y haga clic en **Ruta** en la parte superior de la vista.

4. Asigne un nombre a la regla, una descripción y especifique el orden de evaluación de la regla.

4. Seleccione la opción de enrutamiento.

5. Seleccione **Guardar**.

Puede probar las reglas de enrutamiento con la característica Número de prueba.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Números de teléfono** **de voz** > .

2. En la pestaña **Reglas de enrutamiento** , haga clic en **Número de prueba**.

3. Escriba un número de teléfono directamente o haga clic en **Seleccionar un número** y seleccione uno de los números de teléfono no asignados en la lista desplegable.

4. Seleccione **Probar**.


## <a name="use-powershell"></a>Usar PowerShell

Para redirigir las llamadas a un número no asignado, use el cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponible en el módulo PowerShell 2.5.1 de Teams o posterior.

Debe especificar el número o rango de números que se llama y el enrutamiento asociado para las llamadas a estos números. Por ejemplo, el comando siguiente especifica que todas las llamadas al número +1 (555) 222-3333 se redirigirán a la cuenta de recursos aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

En el ejemplo siguiente se especifica que todas las llamadas al intervalo de números +1 (555) 333-0000 a +1 (555) 333-9999 se redirigirán al servicio de anuncios, que reproducirá el archivo de audio MainAnnouncement.wav al autor de la llamada.

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Notas

- Si se enruta a un anuncio, el archivo de audio se reproducirá una vez al autor de la llamada.

- Para redirigir las llamadas a los números de suscriptor no asignados de Microsoft Calling Plan, su inquilino debe tener [créditos de comunicaciones](what-are-communications-credits.md) disponibles.

- Para redirigir las llamadas a números de servicio del plan de llamadas de Microsoft no asignados, su inquilino debe tener al menos una licencia **de cuenta de recurso de Teléfono Microsoft Teams**.

- Los formatos compatibles con archivos de audio personalizados son WAV (PCM lineal sin comprimir con profundidad de 8/16/32 bits en mono o estéreo), WMA (solo mono) y MP3. El contenido del archivo de audio no puede tener más de 5 MB.

> [!NOTE]
> Usted es responsable de borrar y proteger de forma independiente todos los derechos y permisos necesarios para usar cualquier archivo de música o audio con su servicio de Microsoft Teams. Esto puede incluir la propiedad intelectual y otros derechos en cualquier música, efectos de sonido, audio, marcas, nombres y otro contenido del archivo de audio de todos los titulares de derechos pertinentes. Los titulares pueden incluir artistas, actores, artistas intérpretes o ejecutantes, músicos, compositores, sellos discográficos, editores musicales, sindicatos, sindicatos, sociedades de derechos, organizaciones de gestión colectiva y cualquier otra parte que posea, controle o licencia los derechos de autor de la música, efectos sonoros, audio y otros derechos de propiedad intelectual.

- Tanto las llamadas entrantes a Microsoft Teams como las llamadas salientes de Microsoft Teams tendrán el número llamado marcado en el intervalo de números no asignados.

- Si un patrón o rango especificado contiene números de teléfono asignados a una cuenta de usuario o recurso en el inquilino, las llamadas a estos números de teléfono se redirigirán al destino adecuado y no se redirigirán al tratamiento de números no asignados especificado. No hay otras comprobaciones de los números del rango. Si el intervalo contiene un número de teléfono externo válido, las llamadas salientes de Microsoft Teams a ese número de teléfono se enrutarán según el tratamiento.


## <a name="related-topics"></a>Temas relacionados

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
