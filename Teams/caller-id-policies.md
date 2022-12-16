---
title: Administrar directivas del id. de llamada en Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Aprenda a usar y administrar directivas de identificador de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada de los usuarios de Teams de su organización.
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414708"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas del id. de llamada en Microsoft Teams

De forma predeterminada, cuando un usuario de Teams realiza una llamada a un teléfono RTC, el número de teléfono del usuario de Teams está visible. Del mismo modo, cuando un autor de llamada RTC realiza una llamada a un usuario de Teams, el número de teléfono del autor de la llamada RTC está visible.

Como administrador, puede usar directivas de identificador de llamada para cambiar o bloquear el identificador de llamada (también conocido como identificador de línea de llamada). Puede usar directivas de identificador de llamadas para mostrar un número de teléfono alternativo para los usuarios de Teams de su organización, bloquear el número de teléfono saliente, bloquear un número entrante para que no se muestre o establecer el nombre de la entidad de llamada (CNAM). Por ejemplo, cuando un usuario realiza una llamada, puede cambiar el identificador de llamada para mostrar el número de teléfono principal y el nombre de la empresa de su organización en lugar del número de teléfono del usuario.

Para administrar las directivas de identificador de llamadas, vaya a Directivas de **identificador de llamadas** de **voz** >  en el centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificador de llamada personalizada

1. En el panel de navegación izquierdo del Microsoft centro de administración de Teams, vaya a Directivas de **identificador de llamadas** de **voz** > .
2. Haga clic en **Agregar**. <br>
![Captura de pantalla de la nueva página de directiva de identificador de llamada en el centro de administración.](media/caller-id-policies-add-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. Desde aquí, elija la configuración que desee:

    - **Bloquear el identificador de llamada entrante**: active esta opción para impedir que se muestre el identificador de llamada de las llamadas entrantes.
    - **Invalidar la directiva de identificador de llamada**: active esta opción para permitir que los usuarios invalide la configuración de la directiva relativa a mostrar su número a las calles o no. Esto significa que los usuarios pueden elegir si mostrar su identificador de llamada. Para obtener más información, vea [Control por parte del usuario final del identificador de llamadas saliente](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).
    - **Reemplace el identificador de llamada por**: Establezca el identificador de llamada que se mostrará a los usuarios seleccionando una de las siguientes opciones:

        - **Número del usuario**: muestra el número del usuario. 
        - **Número de servicio**: permite establecer un número de teléfono de servicio para que se muestre como identificador de llamada.
        - **Anónimo**: muestra el identificador de llamada como anónimo.

    - **Reemplace el identificador de llamada por este número de servicio**: elija un número de servicio para reemplazar el identificador de llamada de los usuarios. Esta opción está disponible si seleccionó **Número de servicio** en **Reemplazar el identificador de llamada por**.

5. Haga clic en **Guardar**.

## <a name="edit-a-caller-id-policy"></a>Editar una directiva de identificador de llamada

Puede editar la directiva global o cualquier directiva personalizada que cree. 

1. En el panel de navegación izquierdo del Microsoft centro de administración de Teams, vaya a Directivas de **identificador de llamadas** de **voz** > .
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificador de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
