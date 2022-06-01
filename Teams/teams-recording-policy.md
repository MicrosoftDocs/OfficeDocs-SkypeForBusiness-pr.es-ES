---
title: Introducción a la grabación basada en directivas de Teams para llamadas & reuniones
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: Más información sobre la grabación basada en directivas de Teams para llamadas & reuniones
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
ms.openlocfilehash: 6a86535c701b38b65d1610dc3aa8af2b5616d4a3
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823009"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introducción a Teams grabación basada en directivas para llamadas & reuniones

La grabación basada en directivas permite que las organizaciones que adopten Microsoft Teams para llamadas y reuniones estipulen, mediante una directiva administrativa, cuándo las llamadas y las reuniones en línea se registren y capturen automáticamente para su procesamiento y retención posteriores según lo requiera la directiva corporativa o normativa pertinente.

Teams se ha mejorado para admitir la integración de soluciones de grabación de terceros, incluida la funcionalidad de la plataforma, experiencias de usuario e interfaces administrativas necesarias para proporcionar una solución de un extremo a otro para configurar, administrar, grabar, almacenar y analizar las comunicaciones Teams. Entre las mejoras se incluyen las API de la plataforma de comunicaciones y los eventos para la grabación, que proporcionan:

- Captura de medios fluida y de alta calidad entre dispositivos y todos los puntos de conexión admitidos para audio, vídeo, uso compartido de pantalla y chat.

- Compatibilidad con la captura de interacción entre los usuarios de Teams y los puntos de conexión de llamada admitidos (Teams, Teams Mobile, Skype Empresarial, RTC)

- Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las herramientas y directivas de llamadas y reuniones administrativas de Teams existentes

La grabación de cumplimiento se puede habilitar en Microsoft 365 A3/A5/E3/E5/Business Premium y usuarios de Office 365 A3/A5/E3/E5. 

Las capacidades de integración de la solución de grabación de cumplimiento también se revisaron en Ignite 2019 en la [sesión grabación de cumplimiento y Microsoft Teams](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>Teams introducción a la grabación de la interacción

Los casos de uso de la grabación de interacción pueden separarse efectivamente en cuatro categorías principales de funcionalidad de grabación: Comodidad, Funcional, Organizativo e Interceptación Legal, como se muestra en la imagen:

> [!div class="mx-imgBorder"]
> ![Captura de pantalla que muestra la interacción que registra qué y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")

Cada una de las categorías conlleva requisitos diferentes para la forma en que se inician las grabaciones, lo que se graba, dónde se almacenan las grabaciones, quién recibe una notificación, quién controla el acceso y cómo se controla la retención.

| Tipo                   | Comodidad (grabación normal de Teams) | Organización: regulada (grabación de cumplimiento normativo) |
| ---------------------- | ------------------ | --------------- |
| Iniciador              | Usuario               | Administración (sistema)  |
| Destino                 | Llamada por llamada o reunión | Por usuario        |
| propietario de Storage          | Usuario               | Cumplimiento      |
| ¿Se requiere notificación? | Sí                | Sí             |
| Propietario de Access           | Usuario               | Cumplimiento      |
| ¿Directiva de retención?      | Opcional           | Sí             |

Teams ofrece varias capacidades para grabar reuniones y eventos en directo de forma [cómoda](./cloud-recording.md) y funcional. La grabación organizativa significa permitir que las organizaciones que adopten Teams para llamadas y reuniones estipulen, mediante una directiva administrativa, cuándo las llamadas y las reuniones en línea se registren y capturen automáticamente para su procesamiento y retención posteriores según lo requiera la directiva corporativa o normativa pertinente. Los usuarios bajo esta directiva serán conscientes de que sus interacciones digitales con Teams se están grabando, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción. La grabación pasa a formar parte del archivo de la organización disponible para el personal legal y de cumplimiento normativo para eDiscovery, retención legal y otros usos de retención corporativa.

## <a name="example-user-needs"></a>Necesidades de usuario de ejemplo

<table>
<thead>
<tr class="header">
<th>Rol</th>
<th>Necesidades</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuarios grabados</td>
<td><ul>
<li><p>Reciba una notificación cuando la grabación esté en curso.</p></li>
<li><p>Esté informado cuando el error de la directiva o del grabador está causando cambios en el comportamiento de las llamadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicaciones</td>
<td><ul>
<li><p>Comprenda por qué y cómo aplicar o aplicar directivas de grabación a Teams usuarios o puntos de conexión.</p></li>
<li><p>Configure y mantenga Teams directivas de grabación para la organización.</p></li>
<li><p>Supervise y solucione problemas relacionados con la grabación de llamadas y reuniones de Teams.</p></li>
<li><p>Apoye al responsable de cumplimiento interno con análisis operativos sobre uso, calidad y confiabilidad.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsable de cumplimiento</td>
<td><ul>
<li><p>Recopile todas las Teams comunicaciones de la manera necesaria para cumplir con las obligaciones de cumplimiento en los límites regionales adecuados.</p></li>
<li><p>Busque interacciones basadas en metadatos relacionados con la comunicación o contenido de interacción. Algunos ejemplos comunes son:</p>
<ul>
<li><p><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos profesionales personalizados</p></li>
<li><p><strong>Contenido</strong> : transcripción, opinión, fonética, interacciones relacionadas</p></li>
</ul></li>
<li><p>Analice e interactúe con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</p></li>
<li><p>Garantizar la seguridad de las comunicaciones recopiladas y evitar la manipulación en todas las etapas.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Información general sobre la arquitectura de soluciones

Las soluciones de grabación de cumplimiento están integradas con Teams como se muestra en el siguiente diagrama:

> [!div class="mx-imgBorder"]
> ![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe una llamada o reunión de Teams.")

> [!NOTE]
> Esta solución está diseñada específicamente para habilitar la grabación de cumplimiento basada en directivas con Teams. No se admitirá ningún otro uso de esta solución.

## <a name="recorder"></a>Grabadora

El componente principal de la solución de grabación de cumplimiento es el grabador.
Los grabadores se crean como servicios escalables basados en Azure (bots) que [usan la plataforma de comunicaciones de Microsoft](/graph/cloud-communications-concept-overview) y se registran como aplicaciones en Microsoft Graph. La grabadora proporciona la interacción directa con las API de la [plataforma de comunicaciones de llamadas](/graph/api/resources/communications-api-overview) y reuniones de Teams y proporciona el punto de conexión para la ingestión de medios.

Hay [disponible una aplicación de grabación de cumplimiento de ejemplo](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento. El ejemplo también tiene ejemplos sobre el uso de la API para registrar interacciones específicas, como el control del enrutamiento de [llamadas entrantes](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , [el cambio de los estados de grabación](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) y [la eliminación del usuario que se está grabando](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph documentación sobre las API específicas puede encontrarse aquí para [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) y [incomingContext](/graph/api/resources/incomingcontext).

La implementación exacta del servicio de grabación variará según el partner, pero debe diseñarse para admitir varios grabadores para lograr una alta disponibilidad y distribución geográfica de la implementación, para reducir la latencia de Teams al grabador. Además, se espera que los propios grabadores estén diseñados teniendo en cuenta la resistencia y redundancia.

Los partners deben confirmar la versión mínima necesaria de la versión de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución para la certificación, con el fin de garantizar que todos los requisitos de integración de grabación de cumplimiento son compatibles.

Dos requisitos específicos que son fundamentales para el escenario de grabación de cumplimiento son:

- El recorder bot debe implementarse en Azure

- El bot grabador debe ejecutarse en una máquina virtual de Windows en Azure

Los requisitos de Azure y Windows VM solo se aplican al componente Teams Bot, lo que significa que un partner puede implementar el resto de la plataforma de su elección, siempre que pueda cumplir los requisitos funcionales y de rendimiento relevantes para la grabación de cumplimiento normativo.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Asignación y aprovisionamiento de directivas de registro de cumplimiento

Los administradores de TI pueden determinar qué usuarios se grabarán y qué grabadora se usará para cada usuario, creando y asignando directivas de grabación de cumplimiento normativo. Se invita automáticamente a los grabadores a participar en conversaciones en función de la configuración de estas directivas cuando se produce una interacción de comunicación. Las directivas de grabación de cumplimiento se administran con [Microsoft PowerShell](./teams-powershell-overview.md) y se pueden aplicar en el nivel de inquilino, usuario y grupo de seguridad de cada organización. Encontrará más información sobre Microsoft Docs para [directivas de reunión](./meeting-policies-overview.md), [directivas de llamada](./teams-calling-policy.md) y [directivas de grupo](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

1. Cree una instancia de aplicación en su espacio empresarial.

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

   Consulte [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Asigne la directiva de grabación de cumplimiento a un usuario.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Consulte [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Experiencias de usuario

La compatibilidad con notificaciones se habilita con las experiencias de cliente Teams. Las experiencias pueden ser visuales o de audio.

**clientes Teams: aviso visual**
- Escritorio/web
- Móvil (iOS/Android)
- teléfonos Teams
- Teams habitaciones

**Otros puntos de conexión: aviso de audio**
- Teléfonos SIP
- Skype Empresarial
- Audioconferencia
- Autores de llamadas RTC

> [!NOTE]
> La grabación de cumplimiento no es compatible con las colas de llamadas del modo de conferencia. Usa las colas de llamadas del modo transferencia.
> La grabación de cumplimiento no funcionará si los usuarios han experimentado una interrupción de Internet y están realizando y recibiendo llamadas RTC con un SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Grabación de cumplimiento de Teams programas de certificación

Además de publicar API disponibles públicamente que permiten a los partners desarrollar e integrar soluciones de CCaaS con Teams, hemos desarrollado la grabación de cumplimiento normativo para Microsoft Teams programa de certificación para ofrecer a los clientes la garantía de que la solución de cada partner participante se ha probado y comprobado para proporcionar la calidad, compatibilidad y confiabilidad que esperan de las soluciones de Microsoft.  

Los siguientes partners han certificado su solución para Microsoft Teams.<br/><br/>

|Socio|Sitio web de la solución |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Doblador |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Tecnología perspicaz |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Innovación en roble |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Cuadro rojo |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Lago Theta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Innovación en roble |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Los siguientes partners están en proceso de certificar su solución para Microsoft Teams.<br/><br/>

|Socio|Sitio web de la solución |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Software de software |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


Esta lista se actualizará a medida que se unan más partners y cumplan los criterios de certificación.

## <a name="next-steps"></a>Pasos siguientes

Si eres un proveedor que busca unirse al programa de certificación, envía un correo a [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
