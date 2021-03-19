---
title: Preparar la red de la organización para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Descubra cómo preparar la red de su organización para Microsoft Teams, incluidos los requisitos de red, la optimización de red y los requisitos de ancho de banda.
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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099581"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams 

## <a name="network-requirements"></a>Requisitos de red

Si ya ha [optimizado la red para Microsoft 365 u Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), probablemente estará listo para usar Microsoft Teams. En cualquier caso, y especialmente si tiene que implementar Teams en poco tiempo como su primera carga de trabajo de Microsoft 365 u Office 365 con el fin de dar cabida a **trabajadores remotos**, lea lo siguiente antes de la implementación:

1.  ¿Tienen todas sus ubicaciones acceso a Internet para conectarse a Microsoft 365 u Office 365? Como mínimo, además del tráfico web normal, asegúrese de que ha abierto lo siguiente para permitir el contenido multimedia en Teams en todas las ubicaciones:

    |  |  |
    |---------|---------|
    |Puertos     |Puertos UDP de <strong>3478</strong> a <strong>3481</strong>        |
    |[Direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong> y <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Si necesita federar con Skype Empresarial, ya sea local o en línea, tendrá que configurar algunos registros DNS adicionales.
    >
    >|Registros CNAME/ Nombre de host  |TTL  |Apuntar a dirección o valor  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  ¿Tiene un dominio comprobado de Microsoft 365 u Office 365 (por ejemplo, contoso.com)?
    
    - Si su organización no ha implementado Microsoft 365 u Office 365, consulte esta [Introducción](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Si su organización aún no ha agregado o configurado un dominio comprobado para Microsoft 365 u Office 365, consulte las [Preguntas más frecuentes de dominios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).

3.  ¿Ha implementado su organización Exchange Online y SharePoint Online?
    
    - Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md).
    - Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md).

Cuando compruebe que cumple estos requisitos de red, puede que esté listo para la [Implementación de Teams](How-to-roll-out-teams.md). Tanto si está en una gran multinacional como si sabe que puede tener algunas limitaciones de red, le será útil seguir leyendo para saber cómo evaluar y optimizar su red para Teams.

> [!IMPORTANT]
> **Para instituciones educativas**: si su organización es una institución educativa y usa un Sistema de información de estudiantes (SIS), [implemente School Data Sync](https://docs.microsoft.com/schooldatasync/) antes de implementar Teams.
>  
> **Ejecución local de Skype Empresarial Server**: si su organización ejecuta Skype Empresarial Server (o Lync Server) de forma local, deberá [Configurar Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar su directorio local con Microsoft 365 u Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedimiento recomendado: Supervisar su red con el Panel de calidad de llamadas y el análisis de llamadas 

Use el [Panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) para sacar conclusiones sobre la calidad de las llamadas y reuniones en Teams. El Panel de calidad de llamadas le permite seguir de cerca la calidad, la confiabilidad y la experiencia del usuario para optimizar su red. El Panel de calidad de llamadas examina la telemetría agregada de toda la organización. Esto puede sacar a la luz patrones generales que permitan identificar problemas y planear soluciones. Además, el Panel de calidad de llamadas proporciona informes de métricas enriquecidos que proporcionan información sobre la calidad, la confiabilidad y la experiencia del usuario generales. 

Usará las herramientas de [análisis de llamadas](set-up-call-analytics.md) para investigar los problemas de llamada y reunión de un usuario individual.

## <a name="network-optimization"></a>Optimización de la red

Las siguientes tareas son opcionales. No son necesarias para implementar Teams, especialmente si es una pequeña empresa y ya ha implementado Microsoft 365 u Office 365. Use esta guía para optimizar el rendimiento de la red y de Teams o si sabe que tiene algunas limitaciones de red.

Es posible que quiera realizar una optimización de red adicional si:

  - Teams se ejecuta lentamente (quizás tenga ancho de banda insuficiente)
  - Las llamadas siguen desconectándose (puede deberse a firewalls o bloqueadores de proxy)
  - Las llamadas tienen distorsiones, se cortan o los interlocutores suenan como robots (puede haber fluctuaciones o pérdida de paquetes)

Para obtener una explicación más detallada sobre la optimización de redes, con instrucciones para identificar y corregir los problemas de red, consulte [Principios de conectividad de red de Microsoft 365 y Office 365](https://aka.ms/pnc).

<table>
<thead>
<tr class="header">
<th><strong>Tarea de optimización de la red</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planeamiento de red</td>
<td><p>Si necesita ayuda para evaluar la red, incluidos los cálculos de ancho de banda y los requisitos de red en las ubicaciones físicas de su organización, consulte la herramienta <a href="https://docs.microsoft.com/microsoftteams/network-planner">Planeamiento de red</a>, en el <a href="https://admin.teams.microsoft.com">Centro de administración de Teams</a>. Cuando proporciona el uso de Teams y los detalles de la red, el Planeamiento de red calcula los requisitos de red para implementar Teams y voz en la nube en las ubicaciones físicas de su organización.</p>
<p>Para ver un escenario de ejemplo, consulte <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Uso del Planeamiento de red: escenario de ejemplo</a>.</p></td>
</tr>
<tr class="even">
<td>Asesor para Teams</td>
<td>El <a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Asesor de Teams</a> forma parte del <a href="https://admin.teams.microsoft.com">Centro de administración de Teams</a>. Evalúa el entorno de Microsoft 365 u Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams.</td>
</tr>
<tr class="odd">
<td>Resolución de nombres externos</td>
<td>Asegúrese de que todos los equipos cliente que ejecuten el cliente de Teams puedan resolver consultas DNS externas para detectar los servicios proporcionados por Microsoft 365 u Office 365 y de que sus firewall no evitan el acceso. Para obtener información sobre cómo configurar puertos de firewall, vaya a <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Direcciones URL e intervalos IP de Microsoft 365 y Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Mantener la conservación de sesiones</td>
<td>Asegúrese de que el firewall no cambia las direcciones o puertos de Traducción de Direcciones de Red (NAT) asignados para UDP.</td>
</tr><tr class="odd">
<td>Validar el tamaño del grupo NAT</td>
<td>Valide el tamaño de grupo de Traducción de Direcciones de Red (NAT) necesario para la conectividad de usuario. Cuando varios usuarios y dispositivos obtienen acceso a Microsoft 365 u Office 365 mediante la <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Traducción de Direcciones de Red (NAT) o la Traducción de Direcciones de Puertos (PAT)</a>, debe asegurarse de que los dispositivos que se encuentren detrás de cada dirección IP enrutable de forma pública no superen el número admitido. Asegúrese de que se asignan direcciones IP públicas adecuadas a los grupos de NAT para evitar el agotamiento de puertos. El agotamiento del puertos contribuye a que los usuarios y dispositivos internos no puedan conectarse al servicio de Microsoft 365 u Office 365.</td>
</tr>
<tr class="even">
<td>Enrutamiento a centros de datos de Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implemente el enrutamiento más eficaz a los centros de datos de Microsoft.</a> Identifique las ubicaciones que pueden usar puntos de salida locales o regionales para conectarse a la red de Microsoft de la manera más eficiente posible.</td>
</tr>
<tr class="odd">
<td>Detección de Intrusiones y Guía de Prevención</td>
<td>Si su entorno tiene implementado un sistema de <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Detección de Intrusiones</a> o un Sistema de Prevención (IDS/IPS) para obtener una capa adicional de seguridad para conexiones salientes, asegúrese de permitir todas las direcciones URL de Microsoft 365 u Office 365.</td>
</tr>
<tr class="even">
<td>Configurar una VPN de túnel dividido</td>
<td><p>Le recomendamos que proporcione una ruta alternativa para el tráfico de Teams que omita la red privada virtual (VPN). Esto se conoce como <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">VPN de túnel dividido</a>. De esta forma, el tráfico de Microsoft 365 u Office 365 no pasa por la VPN, sino que va directamente a Microsoft 365 u Office 365. Esto tiene un impacto positivo en la calidad de Teams y reduce la carga desde los dispositivos VPN y la red de la organización. Para implementar una VPN de túnel dividido, consulte con su proveedor de VPN.</p>
<p>Otras razones por las que recomendamos omitir la VPN:
<ul>
<li><p>Por lo general las VPN no se diseñan ni se configuran para admitir elementos multimedia en tiempo real.</p></li> 
<li><p>Es posible que algunas VPN tampoco admitan UDP (necesario para Teams).</p></li> 
<li><p>Las VPN también introducen una capa adicional de cifrado en el tráfico multimedia que ya está cifrado.</p></li> 
<li><p>La conectividad con Teams puede no ser eficiente debido al tráfico de redirección al origen que pasa a través de un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Calidad del Servicio (QoS)</a> para configurar la prioridad de paquetes. Esto mejorará la calidad de la llamada en Teams y le ayudará a supervisar y solucionar problemas de calidad de llamada. QoS debe implementarse en todos los segmentos de una red administrada. Incluso si una red se aprovisionó correctamente para el ancho de banda, QoS proporciona mitigación de riesgos en caso de eventos de red inesperados. Con QoS, el tráfico de voz tiene prioridad para que los eventos inesperados no afecten negativamente a la calidad.</td>
</tr>
<tr class="even">
<td>Optimizar la Wi-Fi</td>
<td><p>Como sucede con las redes VPN, las redes Wi-Fi no se han diseñado ni configurado necesariamente para admitir archivos multimedia en tiempo real. Planificar una red Wi-Fi u optimizarla para que admita Teams es un aspecto muy relevante en la implementación de calidad. Tenga en cuenta los siguientes factores:</p>
<ul>
<li><p>Implementar QoS o WiFi Multimedia (WMM) le asegura que el tráfico multimedia reciba la prioridad adecuada a través de las redes Wi-Fi.</p></li>
<li><p>Planear y optimizar las bandas Wi-Fi y la ubicación del punto de acceso. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero a los puntos de acceso normalmente también les afectan otros dispositivos de consumidores que funcionan en esa gama. El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura. Los puntos de conexión también necesitan admitir esa gama y se deben configurar para poder aprovechar esas bandas de forma adecuada.</p></li>
<li><p>Si usa redes Wi-Fi de doble banda, considere la posibilidad de implementar "band steering". <em>Band steering</em> es una técnica que implementan los proveedores Wi-Fi para que los clientes de doble banda usen el intervalo de 5 GHz.</p></li>
<li><p>Cuando los puntos de acceso del mismo canal están demasiado cerca entre sí, pueden generar superposición de señales y competir sin pretenderlo, lo que daría lugar a una mala experiencia para el usuario. Asegúrese de que los puntos de acceso que están próximos entre ellos se encuentran en canales que no se superponen.</p></li>
</ul>
<p>Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Consulte a su proveedor de Wi-Fi para obtener instrucciones específicas.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

Teams está concebido para ofrece las mejores posibilidades de uso compartido de audio, vídeo y contenido, independientemente de las condiciones de su red. Dicho esto, cuando el ancho de banda es insuficiente, Teams da prioridad a la calidad de audio sobre la de vídeo.

Cuando el ancho de banda *no esté* limitado, Teams optimizará la calidad multimedia con hasta 1080p de resolución de vídeo, 30 fps para vídeo y 15 fps para el contenido y el audio de alta fidelidad. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365 y Office 365](https://aka.ms/pnc)

[Puntos de conexión a nivel mundial: Skype Empresarial Online y Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para Teams](proxy-servers-for-skype-for-business-online.md)

[Multimedia en Teams: por qué las reuniones son sencillas](https://aka.ms/teams-media)

[Multimedia en Teams: profundizar en los flujos de medios](https://aka.ms/teams-media-flows)

[Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md)

[Cómo implementar Teams](How-to-roll-out-teams.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
