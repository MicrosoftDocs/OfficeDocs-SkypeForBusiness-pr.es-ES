---
title: Directivas de retención de Microsoft Teams preguntas más frecuentes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Preguntas más frecuentes acerca de las directivas de retención en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c8ebd3d35c471a529899cd46a364511f7ea267c
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004581"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Directivas de retención de Microsoft Teams preguntas más frecuentes

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>¿Qué tipos de directivas puedo configurar en las directivas de retención y cómo funcionan?

En el centro de cumplimiento y seguridad, cuando se configura una directiva de retención, para los equipos o para cualquier otra carga de trabajo, puede configurar dos tipos principales de directivas: 
- Conservación: Estas directivas Asegúrese de que los datos se conserven durante un período determinado de tiempo, independientemente de lo que sucede en las herramientas de usuario final. Garantizan que los datos se conservan por motivos de cumplimiento de normas y expira disponibles en la exhibición de documentos electrónicos hasta este momento. Después de que expire el tiempo, la directiva puede indicar si no hace nada o eliminar los datos. En los equipos, si crea una directiva de conservación durante siete años, incluso si los usuarios finales eliminar sus mensajes de los equipos, estos mensajes se conservan aún para exhibición de documentos electrónicos durante siete años.
- Eliminación: Estas directivas Asegúrese de que los datos no están un pasivo para la organización. Después de la duración especificada, los datos se eliminan de todo el almacenamiento relevante en los equipos. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>¿Podemos incluir los equipos de directivas en toda la organización? 

No, no actualmente. Debe crear directivas específicas para mensajes de chat y canal de los equipos con la fila de la ubicación de los equipos o los cmdlets de estos equipos: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [TeamsComplianceRetentionRule de nuevo](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Estos cmdlets tienen get y establecer así como las versiones.

### <a name="are-these-retention-policies-retroactive"></a>¿Son retroactivos estas directivas de retención? 

Sí, son. Si crea una directiva de retención para eliminar los datos de más de 60 días, eliminará los datos de los equipos creados hace más de 60 días. 

### <a name="what-is-the-default-retention-policy"></a>¿Qué es la directiva de retención predeterminada? 

De forma predeterminada, se conservan una eternidad chat, canal y datos de los archivos de los equipos. Un usuario puede eliminar algo, pero en ausencia de las directivas de retención, los datos de los equipos, siempre se archivan en buzones de Exchange online (de usuario y de grupo) y permanece en su ubicación de exhibición de documentos electrónicos. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>¿Puedo destinados a conjuntos de usuarios o equipos en una directiva? 

Sí, hacer. En el Asistente para la creación de directivas, en el paso de ubicaciones, puede incluir o excluir (de**los equipos de los mensajes del canal**) a equipos o usuarios (**chat de equipos**) y crear directivas de destino para su organización. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>¿Qué es la principal diferencia entre el uso de la fila de ubicación de buzón de correo de grupo y la fila de ubicación de los mensajes de canal de los equipos en las directivas de retención? 

Si usa el buzón de correo de grupo y las filas de ubicación de buzón de correo de usuario para Exchange Online, se eliminarán los datos de los equipos de los buzones de correo especificados. Sin embargo, esto quita sólo datos desde el buzón de correo. No elimina otros datos de los equipos, como el servicio de charlas. Se recomienda que utilice las directivas de retención de los equipos para administrar correctamente todos los datos de los equipos. Una directiva de retención de los equipos quita los datos de los equipos de todas las ubicaciones, los buzones de correo, Chat servicio de almacenamiento, los clientes de los equipos. 

Nota: Lanzamiento de la característica de directivas de retención para los equipos se asegura de que las directivas de los equipos sólo eliminación elementos de los equipos almacenados dentro de las ubicaciones de buzón de correo de Exchange (usuario o grupo). El programa de instalación de otra directivas de buzones de correo no puede afectar a los elementos de los equipos. Era true en el pasado, pero se ha corregido con el lanzamiento de la función de las directivas de retención. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>¿Qué sucede con Skype para chats de interoperabilidad en línea de negocio y equipos – ¿están afectadas por las directivas de retención?

Sí, Skype para profesionales en línea y chats de interoperabilidad de los equipos funcionan del mismo modo. Una vez que el Skype para chat en línea de negocio entra en los equipos, se convierte en un mensaje en un subproceso de chat de los equipos y obtiene ingestión en el buzón apropiado. Por lo que el mismo flujo de works – directivas de eliminación de los equipos eliminará estos mensajes desde el subproceso de los equipos. Sin embargo, si el historial de conversaciones está activado para Skype para profesionales en línea y desde el Skype para cliente empresarial en línea los que se guardan en un buzón de correo, estos datos de chat no está controlados por una directiva de retención de los equipos.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>¿Puede hacer a través de los cmdlets de seguridad & Centro de cumplimiento? ¿Qué debo usar? 

Absolutamente. Puede crear directivas de retención de los equipos con [cmdlets de Powershell de centro de cumplimiento y seguridad]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Recuerde que estos no son los cmdlets de Exchange Online. Estos son los cmdlets que hemos creado para los equipos. Siguen nomenclatura existente y el estilo de los cmdlets de retención disponibles actualmente en el centro de cumplimiento y seguridad.

|Directiva|Regla|
|---|---|
|[Nueva TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nueva TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>¿Si hay varias directivas de retención para los equipos con distintas duraciones, cuál wins?

Se siguen los [principios de las políticas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)y se recomienda que haga lo demasiado. La respuesta breve es: 
-   Conservación siempre wins a través de eliminación
-   Período de conservación más larga siempre wins
-   Inclusión explícita wins a través de inclusión implícita en términos de ubicaciones
-   Más cortas wins período de eliminación
