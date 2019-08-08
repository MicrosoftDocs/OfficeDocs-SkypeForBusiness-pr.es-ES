---
title: Preguntas más frecuentes sobre las directivas de retención de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Preguntas más frecuentes sobre las directivas de retención en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 955006d952454e31698156fa89e2a2047cff823b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243558"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Preguntas más frecuentes sobre las directivas de retención de Microsoft Teams

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>¿Qué tipos de directivas puedo configurar en las directivas de retención y cómo funcionan?

En el centro de cumplimiento de seguridad &, al configurar una directiva de retención para Teams o para cualquier otra carga de trabajo, puede configurar dos tipos principales de directivas: 
- Preservación: estas directivas garantizan que los datos se conservan durante un período de tiempo determinado, independientemente de lo que suceda en las herramientas para el usuario final. Garantizan que los datos se conservan por razones de cumplimiento y que están disponibles en eDiscovery hasta que vence este tiempo. Una vez transcurrido el tiempo, la Directiva puede indicar si no hace nada o elimina los datos. En Teams, si crea una directiva de conservación por 7 años, incluso si los usuarios finales eliminan sus mensajes de Teams, estos mensajes se conservarán para la exhibición de mensajes en tiempo de conservación por 7 años.
- Eliminación: estas directivas garantizan que los datos no sean responsabilidad de su organización. Después de la duración especificada, los datos se eliminan de todo el almacenamiento relevante en Teams. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>¿Se puede incluir Teams en las directivas de toda la organización? 

No, no en este momento. Debe crear directivas específicas para los chats de los equipos y los mensajes de canal con la fila de ubicación de equipos o estos cmdlets de Teams: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Estos cmdlets también tienen las versiones get y set.

### <a name="are-these-retention-policies-retroactive"></a>¿Están las directivas de retención retroactivas? 

Sí, están. Si crea una directiva de retención para eliminar los datos anteriores a 60 días, se eliminarán los datos de Teams creados hace más de 60 días. 

### <a name="what-is-the-default-retention-policy"></a>¿Qué es la Directiva de retención predeterminada? 

De forma predeterminada, los datos de chat, canal y archivos de Teams se conservan para siempre. Un usuario puede eliminar algo pero, en ausencia de directivas de retención, los datos de Teams siempre se archivan en buzones de Exchange Online (usuario y grupo) y permanecen allí para eDiscovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>¿Puedo apuntar a conjuntos de usuarios o equipos en una directiva? 

Sí, puedes hacerlo. En el Asistente para la creación de directivas, en el paso ubicaciones, puede incluir o excluir equipos (**mensajes de canal de equipos**) o usuarios (chat de**equipos**) y crear directivas dirigidas para su organización. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>¿Cuál es la principal diferencia entre usar la fila Ubicación del buzón de grupo y la fila ubicaciones de los mensajes de canal en las directivas de retención? 

Si usa las filas buzón de grupo y ubicación del buzón de usuario de Exchange Online, los datos de Teams se eliminarán de los buzones especificados. Sin embargo, esto solo quita los datos del buzón. No elimina otros datos de los equipos, como el servicio de chats. Le recomendamos que use las directivas de retención de Teams para administrar correctamente todos los datos de Teams. Una directiva de retención de Teams quita los datos de Teams de todas las ubicaciones de almacenamiento: buzones, servicio de chat y clientes de Teams. 

Nota: el inicio de la característica directivas de retención para Teams garantiza que solo las directivas de Teams eliminen los elementos de equipo almacenados en ubicaciones de buzones de Exchange (usuario o grupo). La configuración de otras directivas de los buzones no puede afectar a los elementos de Teams. Esto fue cierto en el pasado, pero se ha corregido con el lanzamiento de la característica de directivas de retención. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>¿Qué pasa con Skype empresarial online y Teams Interop chats, ¿se ven afectados por las políticas de retención?

Sí, los chats interoperativos de Skype empresarial online y Teams funcionan de la misma manera. Una vez que la conversación de Skype empresarial online llega a Teams, se convierte en un mensaje en un chat de equipos y se incorpora al buzón de correo correspondiente. Por lo tanto, el mismo flujo funciona: las directivas de eliminación de equipos eliminarán estos mensajes de la conversación de Teams. Sin embargo, si el historial de conversaciones está activado para Skype empresarial online y desde el lado del cliente de Skype empresarial online se guardan en un buzón de correo, esta información de chat no se administra mediante una directiva de retención de Teams.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>¿Puedo hacerlo a través de los cmdlets del centro de cumplimiento & seguridad? ¿Qué debo usar? 

Realmente. Puede crear directivas de retención de Teams mediante los cmdlets de [PowerShell del centro de cumplimiento de seguridad &]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Recuerde que no son cmdlets de Exchange Online. Estos son los cmdlets que hemos creado para Teams. Siguen la nomenclatura y el estilo existentes desde los cmdlets de retención disponibles hoy día en el centro de cumplimiento de seguridad &.

|Políticas|Filete|
|---|---|
|[Nuevo: TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nuevo: TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Si hay varias directivas de retención para Teams con duraciones diversas, ¿cuál es el WINS?

Seguimos los [principios de las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)y le recomendamos que también lo haga. La respuesta breve es: 
-   Preservar siempre gana la eliminación
-   El período de preservación más largo siempre gana
-   La inclusión explícita prevalece sobre la inclusión implícita en términos de ubicaciones
-   Gana el período de eliminación más corto
