---
title: Enmascarar números de teléfono en Microsoft Teams reuniones
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo enmascarar números de teléfono Microsoft Teams reuniones
ms.openlocfilehash: d34d2f38a3a1fe2219816184a5f127312cd0475e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758272"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Enmascarar números de teléfono en Microsoft Teams reuniones

Para mayor privacidad, los números de teléfono de los participantes que se marcan en una reunión de Teams mediante audioconferencia se muestran por completo a los participantes internos. Los números se enmascaran de los participantes fuera de su organización. Esta configuración es la predeterminada para todas las organizaciones. El número enmascarado se muestra como se muestra en la siguiente imagen:

![un ejemplo de un número de teléfono enmascarado.](media/hiddenPhoneNum.png)

Para casos de uso específicos del sector, los administradores tienen la capacidad de elegir cómo aparecen los números de teléfono de los participantes de las audioconferencias en las reuniones que están organizadas en su inquilino. Los administradores pueden elegir entre tres opciones:

- Teléfono los números se enmascaran solo de los participantes externos. Los participantes que pertenecen al inquilino del organizador de la reunión siguen teniendo el número de teléfono completo.
- Teléfono los números se enmascaran de todos los usuarios de la reunión, excepto el organizador.
- Teléfono números están desenmascarados, lo que los hace visibles para todos los usuarios de la reunión.

Esta configuración se aplica a todas las superficies de la reunión donde se exponen los números de teléfono.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usar Microsoft PowerShell para establecer el enmascaramiento de números de teléfono

Para cambiar la configuración de enmascaramiento de red telefónica conmutada (RTC), establezca el parámetro del **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en una de las opciones disponibles.

Para enmascarar los números de teléfono solo de participantes externos, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Para enmascarar los números de teléfono de todos los participantes de la reunión (excepto el organizador), ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Para deshabilitar el enmascaramiento de números de teléfono, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```