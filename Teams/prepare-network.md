---
title: Preparar la red de la organización para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Obtenga información sobre cómo preparar la red de su organización para Microsoft Teams, incluidos los requisitos de red, la optimización de red y los requisitos de ancho de banda.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: d0ce589ef972639928e4c8696f3ed23146126086
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583899"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams 

## <a name="network-requirements"></a>Requisitos de red

Si ya ha [optimizado su red para microsoft 365 u Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), es probable que esté listo para usar Microsoft Teams. En cualquier caso, y especialmente si va a implementar los equipos rápidamente como la primera carga de trabajo de Microsoft 365 u Office 365 para admitir **trabajadores remotos** , compruebe lo siguiente antes de empezar con el lanzamiento de su equipo:

1.  ¿Todas las ubicaciones tienen acceso a Internet (para que puedan conectarse a Microsoft 365 u Office 365)? Como mínimo, además del tráfico normal de la web, asegúrese de que ha abierto lo siguiente, para todas las ubicaciones, para multimedia en Teams:

    |  |  |
    |---------|---------|
    |Puertos     |Puertos UDP <strong>3478</strong> a <strong>3481</strong>        |
    |[Direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>y <strong>52.120.0.0/14</strong>         |

> [!IMPORTANT]
> Si necesita federar con Skype empresarial, ya sea local o en línea, tendrá que configurar algunos registros DNS adicionales.
>
>|Registros CNAME/nombre de host  |TD  |Dirección o valor de destino  |
>|---------|---------|---------|
>|SIP     |    3600     |    sipdir.online.lync.com     |
>|lyncdiscover     |   3600      |    webdir.online.lync.com     |
>


    
2.  ¿Tiene un dominio verificado para Microsoft 365 u Office 365 (por ejemplo, contoso.com)?
    
      - Si su organización no ha implementado Microsoft 365 u Office 365, [consulte Introducción](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).
      - Si su organización no ha agregado ni configurado un dominio verificado para Microsoft 365 u Office 365, consulte las [preguntas más frecuentes sobre los dominios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).

3.  ¿Su organización ha implementado Exchange Online y SharePoint Online?
    
      - Si su organización no tiene Exchange Online, consulte [comprender cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md).
      - Si su organización no tiene SharePoint Online, consulte [comprender cómo SharePoint Online y OneDrive para la empresa interactúan con Microsoft Teams](sharepoint-onedrive-interact.md).

Una vez que haya verificado que cumple con estos requisitos de red, es posible que esté listo para [implementar Teams](How-to-roll-out-teams.md). Si es una gran empresa multinacional, o si sabe que tiene algunas limitaciones de red, siga leyendo para obtener información sobre cómo evaluar y optimizar su red para Teams.

> [!IMPORTANT]
> **Para instituciones educativas**: Si su organización es un centro educativo y usa un sistema de información de estudiante (SIS), [implemente School Data Sync](https://docs.microsoft.com/schooldatasync/) antes de implementar Teams.
>  
> **Ejecución local de Skype empresarial Server**: Si su organización ejecuta Skype empresarial Server local (o Lync Server), debe [configurar Azure ad Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar el directorio local con Microsoft 365 u Office 365...

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedimiento recomendado: supervisar la red con el análisis de llamadas y el CQD 

Use el [Panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) para obtener información sobre la calidad de las llamadas y las reuniones de Teams. El CQD puede ayudarte a optimizar tu red al mantener un vistazo a la calidad, la confiabilidad y la experiencia del usuario. El CQD busca la telemetría agregada de toda una organización, en la que se pueden aparentar patrones generales, lo que le permite identificar problemas y planear la corrección. Además, el CQD proporciona informes de métricas ricos que proporcionan una perspectiva de la calidad general, la confiabilidad y la experiencia del usuario. 

Usará el [análisis de llamadas](set-up-call-analytics.md) para investigar problemas de llamadas y reuniones para un usuario individual.

## <a name="network-optimization"></a>Optimización de red

Las siguientes tareas son opcionales y no son necesarias para distribuir equipos, especialmente si es pequeña empresa y si ya ha implementado Microsoft 365 u Office 365. Use esta guía para optimizar el rendimiento de su red y de Teams o si sabe que tiene algunas limitaciones de red.

Es posible que desee realizar una optimización de red adicional si:

  - Teams se ejecuta lentamente (es posible que no tenga suficiente ancho de banda)
  - Las llamadas siguen colocando (puede deberse a bloqueadores de proxy o firewall).
  - Las llamadas son estáticas y recortadas, o voces suenan como robots (pueden ser vibración o pérdida de paquetes).

Para obtener información detallada sobre la optimización de red, incluidas las pautas para identificar y resolver las deficiencias de red, lea los [principios de conectividad de red de Microsoft 365 y Office 365](https://aka.ms/pnc).

<table>
<thead>
<tr class="header">
<th><strong>Tarea de optimización de red</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planificador de redes</td>
<td><p>Para obtener ayuda para evaluar su red, incluidos los cálculos de ancho de banda y los requisitos de red en las ubicaciones físicas de su organización, consulte la herramienta <a href="https://docs.microsoft.com/microsoftteams/network-planner">planificador de redes</a> en el <a href="https://admin.teams.microsoft.com">centro de administración de Teams</a>. Cuando proporciona los detalles de red y el uso de Teams, Network Planner calcula los requisitos de red para implementar equipos y voz en la nube en las ubicaciones físicas de la organización.</p>
<p>Para ver un escenario de ejemplo, consulte <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">uso de Network Planner-ejemplo</a>.</p></td>
</tr>
<tr class="even">
<td>Asesor para equipos</td>
<td>El <a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Asesor de equipos</a> forma parte del <a href="https://admin.teams.microsoft.com">centro de administración de Teams</a>. Evalúa el entorno de Microsoft 365 u Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams.</td>
</tr>
<tr class="odd">
<td>Resolución de nombres externos</td>
<td>Asegúrese de que todos los equipos que ejecuten el cliente de Teams puedan resolver consultas DNS externas para descubrir los servicios proporcionados por Microsoft 365 u Office 365 y que los firewalls no impiden el acceso. Para obtener información sobre cómo configurar puertos de firewall, vaya a <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 y a intervalos IP e URL de Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Mantener la persistencia de la sesión</td>
<td>Asegúrese de que el Firewall no cambie los puertos o las direcciones de traducción de direcciones de red (NAT) asignados a UDP.</td>
</tr><tr class="odd">
<td>Validar tamaño del grupo NAT</td>
<td>Valide el tamaño de la agrupación de traducción de direcciones de red (NAT) necesario para conectividad de usuario. Cuando varios usuarios y dispositivos tienen acceso a Microsoft 365 u Office 365 mediante <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">traducción de direcciones de red (NAT) o traducción de direcciones de puerto (PAT)</a>, debe asegurarse de que los dispositivos que se encuentran detrás de cada dirección IP enrutada pública no superen el número admitido. Asegúrese de que las direcciones IP públicas adecuadas se asignen a los grupos NAT para evitar el agotamiento del puerto. El agotamiento del puerto contribuirá a que los usuarios internos y los dispositivos no puedan conectarse al servicio de Microsoft 365 u Office 365.</td>
</tr>
<tr class="even">
<td>Enrutamiento a centros de datos de Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implementar el enrutamiento más eficaz para los centros de datos de Microsoft</a>. Identifique las ubicaciones que pueden usar puntos de salida locales o regionales para conectarse a la red de Microsoft de la manera más eficaz posible.</td>
</tr>
<tr class="odd">
<td>Guía de detección y prevención de intrusiones</td>
<td>Si su entorno tiene un sistema de detección o prevención de <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">intrusiones</a> (IDS/IPS) implementado para una capa adicional de seguridad para conexiones salientes, asegúrese de permitir todas las direcciones URL de Microsoft 365 u Office 365.</td>
</tr>
<tr class="even">
<td>Configurar VPN de túnel dividido</td>
<td><p>Le recomendamos que proporcione una ruta de acceso alternativa para el tráfico de teams que omita la red privada virtual (VPN), generalmente conocida como [VPN de túnel dividido](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing). El túnel dividido significa que el tráfico de Microsoft 365 u Office 365 no atraviesa la red privada virtual, sino que se dirige directamente a Microsoft 365 u Office 365. Omitir su VPN tendrá un impacto positivo en la calidad de los equipos y reducirá la carga de los dispositivos VPN y de la red de la organización. Para implementar una VPN de túnel dividido, trabaje con su proveedor de VPN.</p>
<p>Otras razones por las que recomendamos omitir la red privada virtual:
<ul>
<li><p>Por lo general, las redes privadas virtuales no están diseñadas o configuradas para admitir medios en tiempo real.</p></li> 
<li><p>Es posible que algunas VPN tampoco admitan UDP (lo cual es necesario para los equipos).</p></li> 
<li><p>Las redes privadas virtuales también introducen una capa adicional de cifrado sobre el tráfico de medios que ya está cifrado.</p></li> 
<li><p>Es posible que la conectividad a teams no sea eficaz debido al tráfico de fijación de pelo a través de un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use calidad de servicio (QoS)</a> para configurar la priorización de paquetes. Esto mejora la calidad de las llamadas en Teams y te ayuda a supervisar y solucionar problemas de calidad de las llamadas. QoS debe implementarse en todos los segmentos de una red administrada. Incluso cuando una red ha sido aprovisionada de forma adecuada para el ancho de banda, QoS proporciona mitigación del riesgo en caso de eventos de red no previstos. Con QoS, el tráfico de voz se prioriza para que estos eventos no previstos no afecten negativamente a la calidad.</td>
</tr>
<tr class="even">
<td>Optimizar WiFi</td>
<td><p>De forma similar a la VPN, las redes WiFi no están necesariamente diseñadas o configuradas para admitir medios en tiempo real. La planificación o optimización de una red WiFi para admitir equipos es una consideración importante para una implementación de alta calidad. Considere estos factores:</p>
<ul>
<li><p>Implementa QoS o WiFi multimedia (WMM) para asegurar que el tráfico multimedia se establezca correctamente en las redes WiFi.</p></li>
<li><p>Planear y optimizar la ubicación de los puntos de acceso y las bandas WiFi. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero los puntos de acceso suelen verse afectados por otros dispositivos consumidores que operan en ese intervalo. El intervalo de 5 GHz es más adecuado para los medios en tiempo real debido a su gama densa, pero requiere más puntos de acceso para obtener la cobertura suficiente. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.</p></li>
<li><p>Si está usando redes WiFi de banda dual, considere la posibilidad de implementar la dirección de banda. La <em>dirección de banda</em> es una técnica implementada por proveedores de WiFi para que los clientes de banda dual usen el intervalo de 5 GHz.</p></li>
<li><p>Cuando los puntos de acceso del mismo canal están demasiado juntos, pueden provocar la superposición de señales y competir involuntariamente, lo que provoca una mala experiencia para el usuario. Asegúrese de que los puntos de acceso que se encuentran junto a los demás estén en canales que no se superponen.</p></li>
</ul>
<p>Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Consulta a tu proveedor de WiFi para obtener instrucciones específicas.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

Teams está diseñado para ofrecer la mejor experiencia de audio, vídeo y uso compartido de contenido, independientemente de las condiciones de la red. Dicho esto, cuando el ancho de banda es insuficiente, Teams da prioridad a la calidad de video.

En el caso de que el ancho de banda *no sea* limitado, Teams optimiza la calidad de los medios, incluida la resolución de video de 1080p, hasta 30 fps para video y 15fps para contenido y audio de alta fidelidad. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365 y Office 365](https://aka.ms/pnc)

[Puntos de conexión en todo el mundo: Skype empresarial online y Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para equipos](proxy-servers-for-skype-for-business-online.md)

[Multimedia en Teams: por qué las reuniones son sencillas](https://aka.ms/teams-media)

[Multimedia en Teams: profundización en flujos multimedia](https://aka.ms/teams-media-flows)

[Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md)

[Cómo implementar Teams](How-to-roll-out-teams.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
