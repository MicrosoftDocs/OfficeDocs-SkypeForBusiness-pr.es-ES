---
title: Introducción a la grabación basada en directivas de Teams para llamar & reuniones
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Obtener información sobre la grabación basada en directivas de Teams para llamar & reuniones
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ef9ca9a5f03ecffe1460a24db186a266fd4a84c
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326677"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introducción a la grabación basada en directivas de Teams para realizar llamadas & reuniones

La grabación basada en directivas permite a las organizaciones que adoptan Microsoft Teams las llamadas y reuniones que estipulan, mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse automáticamente para su procesamiento y retención posterior, según lo requiera la política corporativa o normativa pertinente.

Teams ha sido mejorado para admitir la integración de soluciones de grabación de terceros, entre las que se incluyen la funcionalidad de plataforma, las experiencias de usuario y las interfaces administrativas necesarias para proporcionar una solución completa para configurar, administrar, registrar, almacenar y analizar comunicaciones de Teams. Esto incluye las API y eventos de la plataforma de comunicaciones para la grabación, que ofrece:

- Captura multimedia sin problemas y de alta calidad en todos los dispositivos y todos los puntos de conexión compatibles con audio, vídeo, pantalla compartida y chat.

- Compatibilidad con la captura de interacción entre usuarios de equipos y puntos de conexión de llamadas compatibles (equipos, equipos móviles, Skype empresarial, RTC)

- Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las herramientas y políticas de reuniones y herramientas administrativas existentes de Teams

- Habilitado para los usuarios de Teams con una licencia independiente

Las capacidades de integración de soluciones de grabación de cumplimiento también fueron revisadas en el encendido 2019 de la [<span class="underline">sesión de cumplimiento y Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).

## <a name="teams-interaction-recording-overview"></a>Introducción a la grabación de interacción de Teams

Los casos de uso de grabación de interacción pueden dividirse en cuatro categorías principales de funcionalidad de grabación: conveniencia, funcional, organizacional e intercepta legal, tal y como se muestra en la imagen:

![Captura de pantalla que muestra la interacción que registra qué es y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")

Cada una de las categorías conlleva diferentes requisitos sobre cómo se inician las grabaciones, qué se graba, dónde se almacenan las grabaciones, a quién se notifica, quién controla Access y cómo se administra la retención.

|                        | Prácticos        | Funcionan         | Organización general      | Regulado por la organización | Interceptación lícita   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| Inició              | Usuario               | Aplicación/solución       | Administrador (sistema)     | Administrador (sistema)  | LEA                |
| Target                 | Por llamada/reunión | Por llamada/reunión | Por llamada/reunión | Por usuario        | Por punto de conexión/ha |
| Propietario del almacenamiento          | Usuario               | Aplicación                | Administrador              | Respeto      | LEA                |
| ¿Se requiere notificación? | Sí                 | Sí                 | Sí                 | Sí             | No                 |
| Propietario de acceso           | Usuario               | Aplicación                | Administrador              | Respeto      | LEA                |
| ¿Directiva de retención?      | Opcional           | Sí                 | Sí                 | Sí              | Sí                |

Teams proporciona diversas funciones para la grabación [<span class="underline">cómoda</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) y funcional de reuniones y eventos en directo. La grabación organizacional significa permitir a las organizaciones que adoptan equipos de llamadas y reuniones establecerse, a través de una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse de forma automática para su procesamiento y retención posterior, según lo requiera la política corporativa o normativa pertinente. Los usuarios de esta Directiva serán conscientes de que sus interacciones digitales con equipos se graban, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción. La grabación se convierte en parte del archivo organizativo disponible para el cumplimiento y el personal legal de eDiscovery, la retención legal y otros usos de la retención corporativa.

## <a name="example-user-needs"></a>Necesidades de usuario de ejemplo

<table>
<thead>
<tr class="header">
<th><strong>Rol</strong></th>
<th><strong>Necesaria</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuarios grabados</td>
<td><ul>
<li><p>Recibir una notificación cuando la grabación esté en curso.</p></li>
<li><p>Informarse cuando el error de la Directiva o de la grabadora provoca cambios en el comportamiento de la llamada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicaciones</td>
<td><ul>
<li><p>Comprender por qué y cómo aplicar o exigir directivas de registro a usuarios y puntos de conexión de Teams.</p></li>
<li><p>Configurar y mantener directivas de grabación de Teams para la organización.</p></li>
<li><p>Supervisar y solucionar problemas relacionados con el registro con llamadas y reuniones de Teams.</p></li>
<li><p>Apoyar al funcionario de cumplimiento interno con análisis operacional sobre el uso, la calidad y la confiabilidad.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Funcionario encargado del cumplimiento</td>
<td><ul>
<li><p>Recopilar todas las comunicaciones de Teams de la forma requerida para cumplir con las obligaciones reglamentarias vigentes.</p></li>
<li><p>Buscar interacciones en función de metadatos relacionados con la comunicación o contenido de interacción. Algunos ejemplos comunes son:</p>
<ul>
<li><p><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos profesionales personalizados</p></li>
<li><p><strong>Contenido</strong> : transcripción, sentimientos, fonética, interacciones relacionadas</p></li>
</ul></li>
<li><p>Analizar e interactuar con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</p></li>
<li><p>Garantizar la seguridad de las comunicaciones recopiladas e impedir alteraciones en todas las etapas.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Descripción general de la arquitectura de soluciones

Las soluciones de grabación de cumplimiento están integradas con Teams, tal y como se muestra en el siguiente diagrama:

![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe una llamada o una reunión de Teams.")

## <a name="recorder"></a>Magnetoscopio

El componente principal de la solución de grabación de cumplimiento es el grabador.
Los grabadores se crean como servicios escalables basados en Azure (bots) que [<span class="underline">aprovechan la plataforma de comunicaciones de Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) y se registran como aplicaciones con Microsoft Graph. La grabadora proporciona la interacción directa con las API de la [<span class="underline">plataforma de comunicaciones</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) de las llamadas y reuniones de Teams y proporciona el punto final para la recopilación de medios.

[<span class="underline">Hay disponible una aplicación de grabadora de cumplimiento de ejemplo</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento. El ejemplo también tiene ejemplos sobre el uso de la API para registrar interacciones específicas, como el control del enrutamiento de [<span class="underline">llamadas entrantes</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , el [<span class="underline">cambio de Estados de grabación</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)y [<span class="underline">la eliminación del usuario que se está grabando</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
La documentación de Graph en las API específicas se puede encontrar aquí para [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) y [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).

La implementación exacta del servicio de grabadora varía según el socio, pero debe estar diseñada para admitir varios registros a fin de lograr una alta disponibilidad y una distribución geográfica de la implementación a fin de reducir la latencia de los equipos a la grabadora. Además, se espera que los grabadores se diseñen con la resistencia y la redundancia en mente.

Los socios deben confirmar la versión de lanzamiento mínima requerida de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución de certificación para garantizar que se admitan todos los requisitos de integración de grabaciones de cumplimiento.

Dos requisitos específicos fundamentales para el escenario de grabación de cumplimiento son:

- El bot de grabadora debe implementarse en Azure

- El bot de grabadora debe ejecutarse en una VM de Windows en Azure

Los requisitos de Windows VM de Azure y Windows solo se aplican al componente bot de Teams, lo que significa que un asociado puede implementar el resto de la plataforma de su elección, siempre y cuando cumplan con los requisitos de rendimiento y funcionales pertinentes para la grabación de cumplimiento.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Aprovisionamiento y asignación de directivas de grabación de cumplimiento normativo

Los administradores de TI pueden determinar qué usuarios se grabarán y qué grabadora se usará para cada usuario mediante la creación y asignación de directivas de grabación de cumplimiento. Los grabadores se invitan automáticamente a participar en las conversaciones basándose en la configuración de estas directivas cuando tiene lugar una interacción de comunicación. Las directivas de grabación de cumplimiento se administran con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) y se pueden aplicar en el espacio empresarial y en el nivel de usuario para cada organización. Puede encontrar más información sobre [<span class="underline">las directivas de reuniones</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) y las [<span class="underline">directivas de llamadas</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)en Microsoft docs.

1. Cree una instancia de la aplicación en su espacio empresarial.

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. Crear una directiva de grabación de cumplimiento.

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Asignar la Directiva de grabación de cumplimiento a un usuario.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Experiencias de usuario

La compatibilidad con las notificaciones se habilita con las experiencias del cliente de Teams. Las experiencias pueden ser visuales o de audio.

**Clientes de Teams: aviso visual**
- Escritorio/web
- Móvil (iOS/Android)
- Teléfonos de equipos
- Salas de equipos

**Otros puntos de conexión-aviso de audio**
- Teléfonos SIP
- Skype Empresarial
- Audioconferencia
- Autores de llamadas RTC

## <a name="compliance-recording-for-teams-certification-programs"></a>Grabación de cumplimiento para los programas de certificación de Teams

Además de publicar API disponibles públicamente para que los socios puedan desarrollar e integrar soluciones de CCaaS con Teams, hemos desarrollado el programa de certificación de la grabación de cumplimiento para Microsoft Teams a fin de proporcionar a los clientes la seguridad de que la solución de cada socio participante ha sido probada y verificada para proporcionar la calidad, la compatibilidad y la confiabilidad que esperan de las soluciones de Microsoft.  

Los siguientes socios están en el proceso de certificar su solución para Microsoft Teams.  

|Servidor|Sitio web de soluciones |
|:--|:--|
|Tecnologías ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|ALINEA |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Cuadro rojo |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Esta lista se actualizará a medida que se unan más socios y cumplan los criterios de certificación.

## <a name="next-steps"></a>Pasos siguientes

Si eres un proveedor y deseas participar en el programa de certificación, envía un mensaje de correo <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.
