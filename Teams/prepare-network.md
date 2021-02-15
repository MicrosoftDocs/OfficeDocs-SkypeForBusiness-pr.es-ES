---
title: Preparar la red de la organización para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Obtenga información sobre cómo preparar la red de su organización para Microsoft Teams, incluidos los requisitos de red, la optimización de la red y los requisitos de ancho de banda.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099581"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams 

## <a name="network-requirements"></a>Requisitos de red

Si ya ha optimizado su red para [Microsoft 365 u Office 365,](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)ya está listo para Microsoft Teams. En cualquier caso, y especialmente si está implementando Teams rápidamente como su primera carga de trabajo de Microsoft 365 u Office 365 para dar soporte a los trabajadores **remotos,** compruebe lo siguiente antes de comenzar el lanzamiento de Teams:

1.  ¿Todas las ubicaciones tienen acceso a Internet (para que puedan conectarse a Microsoft 365 u Office 365)? Como mínimo, además del tráfico web normal, asegúrese de que ha abierto lo siguiente, para todas las ubicaciones, para los elementos multimedia en Teams:

    |  |  |
    |---------|---------|
    |Puertos     |Puertos UDP <strong>3478</strong> a <strong>3481</strong>        |
    |[Direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>y <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Si necesita federar con Skype Empresarial, ya sea de forma local o en línea, tendrá que configurar algunos registros DNS adicionales.
    >
    >|Registros CNAME/Nombre de host  |TTL  |Dirección o valor de destino  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  ¿Tiene un dominio comprobado de Microsoft 365 u Office 365 (por ejemplo, contoso.com)?
    
    - Si su organización no ha lanzado Microsoft 365 u Office 365, consulte [Introducción.](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - Si su organización no ha agregado o configurado un dominio comprobado para Microsoft 365 u Office 365, consulte Las preguntas más frecuentes [sobre dominios.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)

3.  ¿Su organización ha implementado Exchange Online y SharePoint Online?
    
    - Si su organización no tiene Exchange Online, consulte [Comprender cómo interactúan Exchange y Microsoft Teams.](exchange-teams-interact.md)
    - Si su organización no tiene SharePoint Online, consulte Comprender cómo SharePoint Online y OneDrive para la [Empresa interactúan con Microsoft Teams.](sharepoint-onedrive-interact.md)

Una vez que haya comprobado que cumple estos requisitos de red, es posible que esté listo para [la implementación de Teams.](How-to-roll-out-teams.md) Si es una gran empresa multinacional o sabe que tiene algunas limitaciones de red, siga leyendo para obtener información sobre cómo evaluar y optimizar su red para Teams.

> [!IMPORTANT]
> **Para instituciones educativas:** si su organización es una institución educativa y usa un sistema de información de estudiantes (SIS), implemente [School Data Sync](https://docs.microsoft.com/schooldatasync/) antes de implementar Teams.
>  
> **Ejecutar Skype** Empresarial Server local: si su organización ejecuta Skype Empresarial Server local (o Lync Server), debe configurar [Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar su directorio local con Microsoft 365 u Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedimiento recomendado: Supervisar su red con el CQD y análisis de llamadas 

Use el [panel de calidad de llamadas para](turning-on-and-using-call-quality-dashboard.md) obtener información sobre la calidad de las llamadas y las reuniones en Teams. El CQD puede ayudarle a optimizar su red vigilando la calidad, la confiabilidad y la experiencia del usuario. El CQD analiza la telemetría agregada de toda una organización en la que pueden detectarse patrones globales, lo que le permite identificar problemas y planear la corrección. Además, el CQD proporciona informes de métricas enriquecidos que ofrecen información sobre la calidad general, la confiabilidad y la experiencia del usuario. 

Usará análisis de llamadas [para investigar](set-up-call-analytics.md) los problemas de llamada y reunión de un usuario individual.

## <a name="network-optimization"></a>Optimización de la red

Las siguientes tareas son opcionales y no son necesarias para implementar Teams, especialmente si es una pequeña empresa y ya ha lanzado Microsoft 365 u Office 365. Use esta guía para optimizar el rendimiento de su red y Teams o si sabe que tiene algunas limitaciones de red.

Es posible que quiera realizar una optimización de red adicional si:

  - Teams se ejecuta lentamente (es posible que no tenga ancho de banda insuficiente)
  - Las llamadas se siguen soltando (puede deberse a bloqueadores de proxy o firewall)
  - Las llamadas son estáticas y cortadas, o las voces suenan como bandeja de salida (podría ser vibración o pérdida de paquetes)

Para obtener una explicación detallada de la optimización de la red, que incluye instrucciones para identificar y corregir deficiencias de red, lea Principios de conectividad de red de [Microsoft 365 y Office 365.](https://aka.ms/pnc)

<table>
<thead>
<tr class="header">
<th><strong>Tarea de optimización de la red</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planificador de red</td>
<td><p>Para obtener ayuda para evaluar la red, incluidos los cálculos de ancho de banda y los requisitos de red en las ubicaciones físicas de su organización, consulte la herramienta <a href="https://docs.microsoft.com/microsoftteams/network-planner">Organizador</a> de red, en el Centro de administración <a href="https://admin.teams.microsoft.com">de Teams.</a> Cuando proporciona los detalles de la red y el uso de Teams, el planificador de red calcula los requisitos de red para implementar Teams y la voz en la nube en las ubicaciones físicas de su organización.</p>
<p>Para ver un escenario de ejemplo, <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">vea Usar El planificador de red - escenario de ejemplo.</a></p></td>
</tr>
<tr class="even">
<td>Asesor para Teams</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">El asesor de Teams</a> forma parte del Centro <a href="https://admin.teams.microsoft.com">de administración de Teams.</a> Evalúa el entorno de Microsoft 365 u Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams.</td>
</tr>
<tr class="odd">
<td>Resolución de nombres externos</td>
<td>Asegúrese de que todos los equipos que ejecutan el cliente de Teams pueden resolver consultas DNS externas para detectar los servicios proporcionados por Microsoft 365 u Office 365 y que sus firewalls no están impidiendo el acceso. Para obtener información sobre cómo configurar puertos de firewall, vaya a Direcciones URL e <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">intervalos IP de Microsoft 365 y Office 365.</a></td>
</tr>
<tr class="odd">
<td>Mantener la conservación de las sesiones</td>
<td>Asegúrese de que el firewall no cambia las direcciones o puertos de UDP asignados para traducción de direcciones de red (NAT).</td>
</tr><tr class="odd">
<td>Validar el tamaño del grupo de NAT</td>
<td>Valide el tamaño del grupo de servidores de traducción de direcciones de red (NAT) necesario para la conectividad de usuario. Cuando varios usuarios y dispositivos tienen acceso a Microsoft 365 u Office 365 mediante la traducción de direcciones de red (NAT) o la traducción de direcciones de puerto <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">(PAT),</a>debe asegurarse de que los dispositivos ocultos detrás de cada dirección IP enrutable públicamente no superen el número admitido. Asegúrese de que se asignan direcciones IP públicas adecuadas a los grupos NAT para evitar que se agoten los puertos. El agotar el puerto hará que los usuarios internos y los dispositivos no puedan conectarse al servicio de Microsoft 365 u Office 365.</td>
</tr>
<tr class="even">
<td>Enrutamiento a centros de datos de Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implemente el enrutamiento más eficaz a los centros de datos de Microsoft.</a> Identifique las ubicaciones que pueden usar puntos de salida locales o regionales para conectarse a la red de Microsoft de la manera más eficiente posible.</td>
</tr>
<tr class="odd">
<td>Guía de detección de intrusión y prevención</td>
<td>Si su entorno <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a> tiene implementado un sistema de detección o prevención de intrusiones (IDS/IPS) para una capa adicional de seguridad para las conexiones salientes, asegúrese de permitir todas las direcciones URL de Microsoft 365 u Office 365.</td>
</tr>
<tr class="even">
<td>Configurar vpn de túnel dividido</td>
<td><p>Le recomendamos que proporcione una ruta alternativa para el tráfico de Teams que omita la red privada virtual (VPN), conocida habitualmente como VPN de túnel <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">dividido.</a> El túnel dividido significa que el tráfico de Microsoft 365 u Office 365 no pasa por una VPN, sino que va directamente a Microsoft 365 u Office 365. Omitir una VPN tendrá un impacto positivo en la calidad de Teams y reduce la carga de los dispositivos VPN y de la red de la organización. Para implementar una VPN de túnel dividido, trabaje con su proveedor de VPN.</p>
<p>Otros motivos por los que recomendamos omitir la VPN:
<ul>
<li><p>Normalmente, las VPN no están diseñadas ni configuradas para admitir medios en tiempo real.</p></li> 
<li><p>Es posible que algunas VPN tampoco admitan UDP (lo que es necesario para Teams).</p></li> 
<li><p>Las VPN también introducen una capa adicional de cifrado sobre el tráfico multimedia que ya está cifrado.</p></li> 
<li><p>Puede que la conectividad con Teams no sea eficiente debido al tráfico anclado a través de un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Calidad de servicio (QoS) para</a> configurar la priorización de paquetes. Esto mejorará la calidad de las llamadas en Teams y le ayudará a supervisar y solucionar los problemas de calidad de las llamadas. QoS debe implementarse en todos los segmentos de una red administrada. Incluso cuando una red se ha aprovisionado adecuadamente para el ancho de banda, QoS proporciona una mitigación de riesgos en caso de eventos de red imprevistos. Con QoS, el tráfico de voz tiene prioridad para que estos eventos imprevistos no afecten negativamente a la calidad.</td>
</tr>
<tr class="even">
<td>Optimizar WiFi</td>
<td><p>De forma similar a las VPN, las redes WiFi no están necesariamente diseñadas ni configuradas para admitir medios en tiempo real. Planear o optimizar una red WiFi para admitir Teams es un factor importante para una implementación de alta calidad. Tenga en cuenta estos factores:</p>
<ul>
<li><p>Implemente QoS o WiFi Multimedia (WMM) para asegurarse de que el tráfico multimedia se priorice adecuadamente sobre sus redes WiFi.</p></li>
<li><p>Planee y optimice la ubicación de las bandas WiFi y los puntos de acceso. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada según la ubicación del punto de acceso, pero los puntos de acceso suelen verse afectados por otros dispositivos de consumidor que operan en ese intervalo. El intervalo de 5 GHz es más adecuado a los medios en tiempo real debido a su rango denso, pero requiere más puntos de acceso para obtener una cobertura suficiente. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.</p></li>
<li><p>Si usa redes WiFi de doble banda, considere la posibilidad de implementar la dirección de banda. <em>La dirección</em> de banda es una técnica implementada por proveedores de WiFi para influir en clientes de banda dual para usar el intervalo de 5 GHz.</p></li>
<li><p>Cuando los puntos de acceso del mismo canal están demasiado juntos, pueden provocar solapamientos de señales y competencia involuntarla, lo que provoca una mala experiencia para el usuario. Asegúrese de que los puntos de acceso que están uno junto al otro están en canales que no se superponen.</p></li>
</ul>
<p>Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Consulte con su proveedor de WiFi para obtener instrucciones específicas.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

Teams está diseñado para ofrecer la mejor experiencia de uso compartido de contenido, vídeo y audio, independientemente de las condiciones de red. Dicho esto, cuando el ancho de banda no es suficiente, Teams da prioridad a la calidad de audio sobre la calidad del vídeo.

Donde  el ancho de banda no está limitado, Teams optimiza la calidad de medios, incluida una resolución de vídeo de hasta 1080p, hasta 30fps para vídeo y 15fps para contenido, y audio de alta fidelidad. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365 y Office 365](https://aka.ms/pnc)

[Puntos de conexión en todo el mundo: Skype Empresarial Online y Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para Teams](proxy-servers-for-skype-for-business-online.md)

[Multimedia en Teams: Por qué las reuniones son sencillas](https://aka.ms/teams-media)

[Multimedia en Teams: Profundizar en los flujos de medios](https://aka.ms/teams-media-flows)

[Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md)

[Cómo implementar Teams](How-to-roll-out-teams.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
