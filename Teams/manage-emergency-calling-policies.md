---
title: Administrar directivas de llamadas de emergencia en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Aprenda a usar y administrar directivas de llamadas de emergencia en Microsoft Teams para definir lo que ocurre cuando un usuario de Teams de su organización realiza una llamada de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 658e7191a821069d3fa9b13e02cc7cbcdfb29413
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606559"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Administrar directivas de llamadas de emergencia en Microsoft Teams

Si su organización usa los planes de llamadas de Microsoft, Operador Connect, Operador de conexión móvil (versión preliminar pública) o Enrutamiento directo como [opción de conectividad con RTC](pstn-connectivity.md), puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que ocurre cuando un usuario de Teams de su organización realiza una llamada de emergencia.

Puede establecer a quién notificar y cómo se notifica cuando un usuario al que se le asigna la directiva llama a los servicios de emergencia. Por ejemplo, puede configurar la configuración de directivas para notificar automáticamente al departamento de seguridad de su organización y pedirles que escuchen llamadas de emergencia.  

Para administrar las directivas de llamadas de emergencia, vaya a **Directivas** de **emergencia** de voz  >  en el Centro de administración de Microsoft Teams o mediante Windows PowerShell. Las directivas se pueden asignar a usuarios y [sitios de red](cloud-voice-network-settings.md).

Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiarle el nombre ni eliminarla. Para los sitios de red, puede crear y asignar directivas personalizadas.

Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario y si ese usuario se encuentra en ese sitio de red, la directiva que se asigna al sitio de red reemplaza la directiva asignada al usuario.

## <a name="create-a-custom-emergency-calling-policy"></a>Crear una directiva de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de emergencia** de **voz** >  y, a continuación, haga clic en la pestaña **Directivas de llamadas**.

2. Haga clic en **Agregar**.

3. Escriba un nombre y una descripción para la directiva.

4. Establezca el **modo de búsqueda Ubicación externa** en activado para permitir que los usuarios finales configuren su dirección de emergencia cuando trabajan desde una ubicación de red fuera de la red corporativa.

5. Establezca cómo desea notificar a los usuarios de su organización, normalmente el departamento de seguridad, cuando se realiza una llamada de emergencia. Para ello, en **Modo de notificación**, selecciona una de las siguientes opciones:

    - **Enviar solo notificación**: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique.
    - **Conferencia en modo silenciado y no se puede reactivar el audio**: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y podrán escuchar (pero no participar) en la conversación entre el autor de la llamada y el operador PSAP.
    - **Conferencias en silenciadas pero pueden reactivar el audio**: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden reactivar el audio para escuchar y participar en la conversación entre el autor de la llamada y el operador PSAP.

6.  Establezca la **declinación de responsabilidades del servicio de emergencia** para mostrar un banner que recuerde a los usuarios finales que confirmen su ubicación de emergencia.

7.  Si ha seleccionado cualquiera de las **conferencias en modos de notificación silenciados** , en el cuadro **Números para marcar para notificaciones de llamadas de emergencia** , puede introducir un número de teléfono RTC de un usuario o grupo para llamar y unirse a la llamada de emergencia. Por ejemplo, escriba el número del departamento de seguridad de su organización, que recibirá una llamada cuando se realice una llamada de emergencia y podrá escucharla. El teléfono RTC no se puede activar incluso cuando el modo se establece **en Conferencia en silenciado, pero puede reactivar el audio**.

8. Busque y seleccione uno o más usuarios o grupos, como el departamento de seguridad de su organización, para notificar cuando se realiza una llamada de emergencia.  La notificación se puede enviar a direcciones de correo electrónico de usuarios, grupos de distribución y grupos de seguridad. Se puede notificar a un máximo de 50 usuarios.

9. Haga clic en **Aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Editar una directiva de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de emergencia** de **voz** >  y, a continuación, haga clic en la pestaña **Directivas de llamadas**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Asignar una directiva de llamadas de emergencia personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte también [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Asignar una directiva de llamadas de emergencia personalizada a un sitio de red

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede asignar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Topología de red** **de ubicaciones** >  y haga clic en la pestaña **Sitios de red**.
2. Seleccione el sitio haciendo clic a la izquierda del nombre y, a continuación, haga clic en **Editar**.
3. En **Directiva de llamadas de emergencia**, seleccione la directiva y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell
Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.

En el ejemplo siguiente se muestra cómo asignar una directiva denominada Directiva de llamadas de emergencia 1 de Contoso al sitio Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de enrutamiento de llamadas de emergencia en Teams](manage-emergency-call-routing-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
