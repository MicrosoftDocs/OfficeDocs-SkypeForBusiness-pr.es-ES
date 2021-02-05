---
title: Introducción a la grabación basada en directivas de Teams para llamar & reuniones
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Más información sobre la grabación basada en directivas de Teams para llamar & reuniones
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
ms.openlocfilehash: fe1ef675396d5d858dea9430182d182a87f46beb
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110253"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introducción a la grabación basada en directivas de Teams para llamadas & reuniones

La grabación basada en directivas permite a las organizaciones que adoptan Microsoft Teams para realizar llamadas y reuniones de manera sencilla, usar una directiva administrativa, cuando las llamadas y reuniones en línea deben grabarse y capturarse automáticamente para su posterior procesamiento y retención, según lo requiera la política corporativa o normativa pertinente.

Teams se ha mejorado para admitir la integración de soluciones de grabación de terceros, incluidas la funcionalidad de plataforma, las experiencias de usuario y las interfaces administrativas necesarias para proporcionar una solución integral para configurar, administrar, grabar, almacenar y analizar las comunicaciones de Teams. Entre las mejoras se incluyen las API de la plataforma de comunicaciones y los eventos para la grabación, que proporciona:

- Captura de medios sin problemas y de alta calidad entre dispositivos y todos los puntos de conexión admitidos para audio, vídeo, uso compartido de pantalla y chat.

- Compatibilidad para la captura de interacciones entre los usuarios de Teams y los puntos de conexión de llamadas admitidos (Teams, Teams Mobile, Skype Empresarial, RTC)

- Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las directivas y herramientas y directivas de llamadas administrativas existentes de Teams

La grabación de cumplimiento se puede habilitar en los usuarios de Microsoft 365 A3/A5/E3/E5/Empresa Premium y Office 365 A3/A5/E3/E5. 

Las capacidades de integración de la solución de grabación de cumplimiento también se revisaron en Ignite 2019 en la sesión Grabación de cumplimiento [<span class="underline">y Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Información general sobre la grabación de interacciones de Teams

Los casos de uso de la grabación de interacciones se pueden separar en cuatro categorías principales de funcionalidad de grabación: Comodidad, Funcional, Organizativa e Intersección Lícito, tal como se muestra en la imagen:

![Captura de pantalla que muestra la interacción que graba qué y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")

Cada una de las categorías implica diferentes requisitos en cuanto a cómo se inician las grabaciones, lo que se graba, dónde se almacenan las grabaciones, a quién se notifica, quién controla el acceso y cómo se controla la retención.

| Tipo                   | Comodidad (grabación normal de Teams) | Organización: regulada (grabación de cumplimiento) |
| ---------------------- | ------------------ | --------------- |
| Insondía              | Usuario               | Administrador (sistema)  |
| Target                 | Durante la llamada y la reunión | Por usuario        |
| Propietario del almacenamiento          | Usuario               | Cumplimiento      |
| ¿Se requiere una notificación? | Sí                | Sí             |
| Propietario de Access           | Usuario               | Cumplimiento      |
| ¿Directiva de retención?      | Opcional           | Sí             |

Teams ofrece varias capacidades para [<span class="underline">grabar de forma</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) conveniente y funcional para reuniones y eventos en directo. La grabación de la organización implica que las organizaciones adopten Teams para realizar llamadas y reuniones de manera obligatoria, a través de una política administrativa, cuando las llamadas y reuniones en línea deben grabarse y capturarse automáticamente para su posterior procesamiento y retención, según lo requiera la política corporativa o normativa relevante. Los usuarios en virtud de esta directiva serán conscientes de que sus interacciones digitales con Teams se están grabando, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción. La grabación pasa a formar parte del archivo de la organización disponible para el cumplimiento y el personal legal para eDiscovery, retención legal y otros usos de retención corporativa.

## <a name="example-user-needs"></a>Ejemplo de necesidades del usuario

<table>
<thead>
<tr class="header">
<th><strong>Rol</strong></th>
<th><strong>Necesidades</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuarios grabados</td>
<td><ul>
<li><p>Recibir una notificación cuando la grabación esté en curso.</p></li>
<li><p>Informe cuando los errores de directiva o grabadora causen cambios en el comportamiento de las llamadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicaciones</td>
<td><ul>
<li><p>Entender por qué y cómo aplicar o aplicar directivas de grabación a los usuarios o puntos de conexión de Teams.</p></li>
<li><p>Configure y mantenga directivas de grabación de Teams para la organización.</p></li>
<li><p>Supervise y solucione los problemas relacionados con la grabación de llamadas y reuniones de Teams.</p></li>
<li><p>Admita a los responsables de cumplimiento interno con análisis de operaciones sobre uso, calidad y confiabilidad.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsable de cumplimiento normativo</td>
<td><ul>
<li><p>Recopile todas las comunicaciones de Teams de la forma necesaria para cumplir las obligaciones de cumplimiento en los límites regionales adecuados.</p></li>
<li><p>Busque interacciones basadas en metadatos relacionados con la comunicación o contenido de interacción. Algunos ejemplos comunes son:</p>
<ul>
<li><p><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos empresariales personalizados</p></li>
<li><p><strong>Contenido:</strong> transcripción, opinión, fonética, interacciones relacionadas</p></li>
</ul></li>
<li><p>Analice e interactúe con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</p></li>
<li><p>Garantice la seguridad de las comunicaciones recopiladas y evite la manipulación en todas las fases.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Información general sobre arquitectura de soluciones

Las soluciones de grabación de cumplimiento están integradas con Teams, tal y como se muestra en el siguiente diagrama:

![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe una llamada o reunión de Teams.")

## <a name="recorder"></a>Grabador

El componente principal de la solución de grabación de cumplimiento es la grabadora.
Los grabadores se construyen como bots (servicios basados en Azure escalables) que aprovechan la plataforma de comunicaciones de [<span class="underline">Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) y se registran como aplicaciones en Microsoft Graph. La grabadora proporciona la interacción directa con las [<span class="underline">API</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) de la plataforma de comunicaciones de llamadas y reuniones de Teams y proporciona el punto de conexión para la ingestión de medios.

Hay [<span class="underline">disponible una aplicación de grabadora de cumplimiento</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) de ejemplo que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento. El ejemplo también muestra ejemplos de uso de [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) la API para registrar interacciones específicas como tratar el enrutamiento de llamadas entrantes, [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)cambiar los estados de grabación y quitar el usuario que se está [<span class="underline">grabando.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
La documentación de Graph sobre las API específicas puede encontrarse aquí para [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) [<span class="underline">y incomingContext.</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)

La implementación exacta del servicio de grabación variará según el asociado, pero debe diseñarse para admitir varias grabadoras con el fin de lograr alta disponibilidad y distribución geográfica de implementación para reducir la latencia de Teams al grabador. Además, se espera que las grabadoras propiamente dichas se diseñen pensando en la resistencia y redundancia.

Los partners deben confirmar la versión mínima necesaria de la versión de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución para la certificación para asegurarse de que todos los requisitos de integración de la grabación de cumplimiento son compatibles.

Dos requisitos específicos que son fundamentales para el escenario de grabación de cumplimiento son:

- El bot grabador debe implementarse en Azure

- El bot grabador debe ejecutarse en una máquina virtual de Windows en Azure

Los requisitos de Azure y Windows VM solo se aplican al componente bot de Teams, lo que significa que un partner puede implementar el resto de la plataforma de su elección, siempre que pueda cumplir los requisitos funcionales y de rendimiento relevantes para la grabación de cumplimiento.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Asignación y aprovisionamiento de directivas de grabación de cumplimiento

Los administradores de TI pueden determinar qué usuarios se grabarán y qué grabadora se usará para cada usuario, creando y asignando directivas de grabación de cumplimiento. Se invita automáticamente a los grabadores a participar en conversaciones en función de la configuración de estas directivas cuando se produce una interacción de comunicación. Las directivas de grabación de cumplimiento se administran con [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) y se pueden aplicar en el nivel de inquilino, usuario y grupo de seguridad para cada organización. Puede encontrar más información sobre las directivas de Reuniones de Microsoft Docs [<span class="underline">para reuniones,</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)las [<span class="underline">directivas de llamada</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) y las directivas de [<span class="underline">grupo.</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Asigne la directiva de Grabación de cumplimiento a un usuario.

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

La compatibilidad con las notificaciones se habilita con las experiencias de cliente de Teams. Las experiencias pueden ser tanto visuales como de audio.

**Clientes de Teams: aviso visual**
- Escritorio/web
- Móvil (iOS/Android)
- Teléfonos de Teams
- Salas de Teams

**Otros puntos de conexión: aviso de audio**
- Teléfonos SIP
- Skype Empresarial
- Audioconferencia
- Autores de llamadas RTC

## <a name="compliance-recording-for-teams-certification-programs"></a>Grabación de cumplimiento para programas de certificación de Teams

Además de publicar API disponibles públicamente que permiten a los partners desarrollar e integrar soluciones CCaaS con Teams, hemos desarrollado la grabación de cumplimiento del programa de certificación Microsoft Teams para ofrecer a los clientes la garantía de que las soluciones de cada partner participante se han probado y comprobado para proporcionar la calidad, la compatibilidad y la confiabilidad que esperan de las soluciones de Microsoft.  

Los siguientes partners han certificado su solución para Microsoft Teams.

|Partner|Sitio web de la solución |
|:--|:--|
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Muy bien |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


Los siguientes partners están en proceso de certificar su solución para Microsoft Teams.

|Partner|Sitio web de la solución |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Innovación de los robles |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Cuadro rojo |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Esta lista se actualizará a medida que más partners se unan y cumplan los criterios de certificación.

## <a name="next-steps"></a>Pasos siguientes

Si eres un proveedor que solicita unirse al programa de certificación, envía un correo <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a>
