---
title: Enmascarar los números de teléfono en las reuniones de Microsoft Teams
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo enmascarar números de teléfono en las reuniones de Microsoft Teams
ms.openlocfilehash: cad28ad446c39a45b865fd24767347fdf11bb9c8
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801771"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Enmascarar los números de teléfono en las reuniones de Microsoft Teams

Para mayor privacidad, los números de teléfono de los participantes que llaman a una reunión de Teams mediante audioconferencia se muestran por completo a los participantes internos. Los números se ocultan de los participantes externos a su organización. Esta configuración es la predeterminada para todas las organizaciones. El número enmascarado se muestra como se muestra en la siguiente imagen:

![un ejemplo de un número de teléfono enmascarado.](media/hiddenPhoneNum.png)

Para casos de uso específicos del sector, los administradores tienen la capacidad de elegir cómo aparecen los números de teléfono de los participantes de las audioconferencias en las reuniones organizadas en su inquilino. Los administradores pueden elegir entre tres opciones:

- Los números de teléfono solo se ocultan de los participantes externos. Los participantes que pertenecen al inquilino del organizador de la reunión seguirán viendo el número de teléfono completo.
- Los números de teléfono están enmascarados de todos los participantes de la reunión excepto del organizador.
- Los números de teléfono están desenmascarados, lo que los hace visibles para todos los participantes de la reunión.

Esta configuración se aplica a todas las superficies de la reunión donde se exponen los números de teléfono.

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>Usar el Centro de administración de Teams para configurar el enmascaramiento de números de teléfono

Para cambiar la configuración de enmascaramiento de la red telefónica conmutada (RTC) en el Centro de administración de Teams, inicie sesión en el Centro de administración de Teams como administrador, seleccione **Puentes de conferencia** **de** >  reuniones en el panel de navegación izquierdo y, después, seleccione **Configuración del puente**. **Mostrar identificadores de llamada enmascarados** es una lista desplegable en la parte inferior del panel de configuración del puente y le permitirá elegir lo siguiente:

- Para participantes externos a la organización
- Para todos los participantes de la reunión
- Deshabilitado

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usar Microsoft PowerShell para establecer el enmascaramiento de números de teléfono

Para cambiar la configuración de enmascaramiento de RTC en PowerShell, establezca el **`MaskPstnNumbersType`** parámetro del cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en una de las opciones disponibles.

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
