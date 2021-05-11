---
title: Introducción a Teams grabación basada en directivas para llamadas & reuniones
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
description: Obtenga más información Teams grabación basada en directivas para llamadas & reuniones
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
ms.openlocfilehash: ba99e49aa546a57d412492737cae8f6520a9eb84
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308369"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introducción a la Teams basada en directivas para llamadas & reuniones

La grabación basada en directivas permite que las organizaciones que adopten Microsoft Teams para llamadas y reuniones se estipulen mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse y capturarse automáticamente para su posterior procesamiento y retención, según lo requiera la directiva corporativa o normativa pertinente.

Teams se ha mejorado para admitir la integración de soluciones de grabación de terceros, incluidas la funcionalidad de la plataforma, las experiencias de usuario y las interfaces administrativas necesarias para proporcionar una solución integral para configurar, administrar, grabar, almacenar y analizar Teams comunicaciones. Entre las mejoras se incluyen las API de la plataforma de comunicaciones y los eventos para la grabación, que proporciona:

- Captura de medios sin problemas y de alta calidad en todos los dispositivos y todos los puntos de conexión compatibles para audio, vídeo, uso compartido de pantalla y chat.

- Compatibilidad para la captura de interacción entre Teams usuarios y puntos de conexión de llamadas admitidos (Teams, Teams móvil, Skype Empresarial, RTC)

- Nuevas directivas administrativas para la grabación de cumplimiento, incluida la integración con las Teams y las herramientas y directivas de reuniones y llamadas administrativas existentes

La grabación de cumplimiento se puede habilitar en Microsoft 365 usuarios de A3/A5/E3/E5/Business Premium y Office 365 A3/A5/E3/E5. 

Las capacidades de integración de la solución de grabación de cumplimiento también se revisaron en Ignite 2019 en la sesión Grabación de cumplimiento [y Microsoft Teams cumplimiento.](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Teams información general sobre la grabación de interacciones

Los casos de uso de grabaciones de interacción se pueden separar en cuatro categorías principales de funcionalidad de grabación: Comodidad, Funcionalidad, Organización e Interceptación legal, como se muestra en la imagen:

> [!div class="mx-imgBorder"]
> ![Captura de pantalla que muestra la interacción que registra qué y por qué.](media/recording-taxonomy.png "La imagen muestra las categorías de grabación.")

Cada una de las categorías implica requisitos diferentes para cómo se inician las grabaciones, qué se graba, dónde se almacenan las grabaciones, quién se notifica, quién controla el acceso y cómo se controla la retención.

| Tipo                   | Comodidad (grabación Teams normal) | Organización: regulado (grabación de cumplimiento) |
| ---------------------- | ------------------ | --------------- |
| Iniciador              | Usuario               | Administrador (sistema)  |
| Destino                 | Por llamada /reunión | Por usuario        |
| Storage propietario          | Usuario               | Cumplimiento      |
| ¿Se requiere notificación? | Sí                | Sí             |
| Propietario de Access           | Usuario               | Cumplimiento      |
| ¿Directiva de retención?      | Opcional           | Sí             |

Teams ofrece varias capacidades para [la grabación](./cloud-recording.md) práctica y funcional para reuniones y eventos en directo. La grabación de la organización significa permitir que las organizaciones que adopten Teams para llamadas y reuniones se estipulen, mediante una directiva administrativa, cuando las llamadas y las reuniones en línea deben grabarse automáticamente y capturarse para su posterior procesamiento y retención según lo requiera la directiva corporativa o normativa pertinente. Los usuarios de esta directiva serán conscientes de que se están grabando sus interacciones digitales con Teams, pero no podrán deshabilitar la grabación y no tendrán acceso a la grabación una vez completada la interacción. La grabación forma parte del archivo organizativo disponible para el personal legal y de cumplimiento para eDiscovery, retención legal y otros usos de retención corporativa.

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
<li><p>Recibir una notificación cuando la grabación esté en curso.</p></li>
<li><p>Esté informado cuando el error de la directiva o la grabadora esté provocando cambios en el comportamiento de las llamadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicaciones</td>
<td><ul>
<li><p>Comprender por qué y cómo aplicar o aplicar directivas de grabación a Teams usuarios o puntos de conexión.</p></li>
<li><p>Configure y mantenga Teams de grabación para la organización.</p></li>
<li><p>Supervise y solucione problemas relacionados con la grabación Teams llamadas y reuniones.</p></li>
<li><p>Soporte técnico de cumplimiento interno con análisis operativos sobre uso, calidad y confiabilidad.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Oficial de cumplimiento</td>
<td><ul>
<li><p>Recopile todas Teams comunicaciones de la forma necesaria para cumplir con las obligaciones de cumplimiento en los límites regionales adecuados.</p></li>
<li><p>Busque interacciones basadas en metadatos relacionados con la comunicación o contenido de interacción. Algunos ejemplos comunes son:</p>
<ul>
<li><p><strong>Metadatos</strong> - Participantes, hora, dirección, número marcado, número de origen, datos empresariales personalizados</p></li>
<li><p><strong>Contenido:</strong> transcripción, sentimientos, fonéticas, interacciones relacionadas</p></li>
</ul></li>
<li><p>Analice e interactúe con las comunicaciones recopiladas, incluida la capacidad de supervisar las interacciones a medida que se recopilan.</p></li>
<li><p>Garantizar la seguridad de las comunicaciones recopiladas y evitar la manipulación en todas las fases.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Introducción a la arquitectura de la solución

Las soluciones de grabación de cumplimiento se integran Teams como se muestra en el siguiente diagrama:

> [!div class="mx-imgBorder"]
> ![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Las imágenes muestran el flujo cuando se envía y recibe Teams reunión o llamada.")

## <a name="recorder"></a>Grabadora

El componente principal de la solución de grabación de cumplimiento es la grabadora.
Las grabadoras se han creado como servicios escalables basados en Azure (bots) que aprovechan la plataforma de comunicaciones de [Microsoft](/graph/cloud-communications-concept-overview) y se registran como aplicaciones con Microsoft Graph. La grabadora proporciona la interacción directa con las [](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) API Teams de la plataforma de comunicaciones de llamadas y reuniones y proporciona el punto de conexión para la ingestión de medios.

Hay [disponible una aplicación de](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) grabadora de cumplimiento de ejemplo que muestra cómo configurar el bot, crear la instancia de la aplicación y asignar las directivas de cumplimiento. El ejemplo también tiene ejemplos sobre el uso [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) de la API para registrar interacciones específicas, como el control del enrutamiento de llamadas entrantes, [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)el cambio de estados de grabación y la eliminación del usuario que se está [grabando.](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
Graph documentación sobre las API específicas se puede encontrar aquí para [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) y [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).

La implementación exacta del servicio de grabadora variará según el asociado, pero debe diseñarse para admitir varias grabadoras con el fin de lograr una alta disponibilidad y distribución geográfica de la implementación para reducir la latencia de Teams a la grabadora. Además, se espera que los propios Grabadores se diseñen pensando en la resistencia y redundancia.

Los partners deben confirmar la versión mínima necesaria de las API y SDK de comunicaciones de Microsoft Graph con Microsoft antes de enviar su solución para la certificación para asegurarse de que todos los requisitos de integración de grabaciones de cumplimiento son compatibles.

Dos requisitos específicos que son fundamentales para el escenario de grabación de cumplimiento son:

- El bot de grabadora debe implementarse en Azure

- El bot grabadora debe ejecutarse en una máquina Windows en Azure

Los requisitos de máquina virtual de Azure y Windows solo se aplican al componente bot de Teams, lo que significa que un partner puede implementar el resto de la plataforma de su elección siempre que puedan cumplir los requisitos de rendimiento y funcionalidad relevantes para la grabación de cumplimiento.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Asignación y aprovisionamiento de directivas de registro de cumplimiento

Los administradores de TI pueden determinar qué usuarios se van a grabar y qué grabadora se usará para cada usuario, creando y asignando directivas de grabación de cumplimiento. Las grabadoras se invitan automáticamente a participar en conversaciones en función de la configuración de estas directivas cuando se produce una interacción de comunicación. Las directivas de registro de cumplimiento se administran con [Microsoft PowerShell](./teams-powershell-overview.md) y se pueden aplicar en el nivel de inquilino, por usuario y grupo de seguridad de cada organización. Puede encontrar más información sobre directivas de Microsoft Docs para [reuniones,](./meeting-policies-in-teams.md)directivas [de llamadas y](./teams-calling-policy.md) directivas de [grupo.](./assign-policies.md#assign-a-policy-to-a-group)

1. Cree una instancia de aplicación en el espacio empresarial.

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

   Vea [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).

3. Asigne la directiva grabación de cumplimiento a un usuario.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Vea [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Experiencias de usuario

El soporte para notificaciones está habilitado con las Teams cliente. Las experiencias pueden ser visuales o de audio.

**Teams clientes: aviso visual**
- Escritorio/web
- Móvil (iOS/Android)
- Teams teléfonos
- Teams salas

**Otros puntos de conexión: aviso de audio**
- Teléfonos SIP
- Skype Empresarial
- Audioconferencia
- Autores de llamadas RTC

## <a name="compliance-recording-for-teams-certification-programs"></a>Grabación de cumplimiento para Teams de certificación

Además de publicar API disponibles públicamente que permiten a los partners desarrollar e integrar soluciones de CCaaS con Teams Microsoft Teams, hemos desarrollado la grabación de cumplimiento para un programa de certificación para proporcionar a los clientes la garantía de que la solución de cada partner participante se ha probado y comprobado para proporcionar la calidad, compatibilidad y confiabilidad que esperan de las soluciones de Microsoft.  

Los siguientes partners han certificado su solución para Microsoft Teams.<br/><br/>

|Partner|Sitio web de soluciones |
|:--|:--|
|TECNOLOGÍAS ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Muy bien |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Lago Theta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |

<br/>
Los siguientes partners están en proceso de certificar su solución para Microsoft Teams.<br/><br/>

|Partner|Sitio web de soluciones |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Innovación de roble |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Cuadro rojo |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

Esta lista se actualizará a medida que más partners se unan y cumplan los criterios de certificación.

## <a name="next-steps"></a>Pasos siguientes

Si es un proveedor que desea unirse al programa de certificación, envíe un correo  <a href= "mailto:Teamscategorypartner@microsoft.com">electrónico Teamscategorypartner@microsoft.com</a>.
