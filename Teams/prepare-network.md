---
title: Preparar la red de la organización para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Sepa cómo preparar y administrar la red de Microsoft Teams. La información incluye los requisitos de red, los requisitos de ancho de banda y otras consideraciones.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640733"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams

> [!Tip]
> Vea la sesión siguiente para obtener más información cómo los equipos aprovecha la red y cómo planear mejor para la conectividad de red óptima: [Planeación de los equipos de red](https://aka.ms/teams-networking)


Los equipos combina tres formas de tráfico:

-   Tráfico de datos entre el entorno de Office 365 en línea y el cliente de los equipos (señalización, presencia, chat, carga de archivos y descarga, sincronización de OneNote).

-   Tráfico de comunicaciones en tiempo real de punto a punto (audio, vídeo, escritorio uso compartido).

-   Tráfico de comunicaciones en tiempo real de conferencia (audio, vídeo, escritorio uso compartido).

Esto afecta a la red en dos niveles: fluirá el tráfico entre los clientes de Microsoft Teams directamente para escenarios de punto a punto y fluirá el tráfico entre el entorno de Office 365 y los clientes de Microsoft Teams para escenarios de la reunión. Para garantizar un flujo de tráfico sea óptima, se debe permitir el tráfico de flujo de ambos entre los segmentos de red interna (por ejemplo, entre los sitios a través de la WAN), así como entre los sitios de red y Office 365. No abrir los puertos adecuados o activamente el bloqueo de puertos específicos conducirá a una experiencia de degradado.

> [!NOTE]
> Las reuniones son compatibles con iOS y Android dispositivos móviles. 

Para obtener una experiencia óptima con multimedia en tiempo real dentro de Microsoft Teams, la red debe cumplir los requisitos de red para Office 365. Para obtener más información, vea [calidad de los medios y el rendimiento de la conectividad de red para Skype para profesionales en línea](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Para los dos definen segmentos de red (cliente a Microsoft Edge) y borde de cliente a Microsoft Edge, tenga en cuenta las siguientes recomendaciones.


|Valor  |Cliente hasta el borde de Microsoft  |Borde de cliente hasta el borde de Microsoft  |
|:--- |:--- |:--- |
|**Latencia (unidireccional)**\*  |< 50 ms.          |< 30ms         |
|**Latencia (RTT o tiempo de ida y vuelta)**\* |< 100 ms   |< 60ms |
|**Ráfagas de pérdida de paquetes**    |<10% durante cualquier intervalo 200ms         |<1% durante cualquier intervalo 200ms         |
|**Pérdida de paquetes**     |<1% durante cualquier 15s intervalo          |<0.1% durante cualquier 15s intervalo         |
|**Vibración de llegada entre granjas de paquetes**    |<30ms durante cualquier 15s intervalo         |<15ms durante cualquier 15s intervalo         |
|**Reaprovisionamiento de paquetes**    |paquetes de salida de orden <0.05%         |paquetes de salida de orden <0.01%         |

\*Los destinos de métricas de latencia asumen su sitio de empresa o los sitios y los bordes de Microsoft se encuentran en el mismo continente.

La conexión del sitio de empresa para el perímetro de red de Microsoft incluye primer salto acceso a la red, que puede ser WiFi u otra tecnología inalámbrica.

Los objetivos de rendimiento de red suponen ancho de banda adecuado o [QoS de planeación](QoS-in-Teams.md). En otras palabras, los requisitos se aplican directamente al tráfico de medios en tiempo real de los equipos cuando la conexión de red está bajo una carga máxima.

Para probar ambos segmentos de red, puede usar la [Herramienta de evaluación de la red](https://go.microsoft.com/fwlink/?linkid=855799). Esta herramienta se puede implementar en el cliente PC directamente y en un PC conectado hasta el borde de la red del cliente. La herramienta incluye documentación limitada, pero una documentación más profunda alrededor el uso de la herramienta se puede encontrar aquí: [Evaluación de preparación de la red](https://go.microsoft.com/fwlink/?linkid=855800). Mediante la ejecución de esta evaluación de disponibilidad de red, puede validar preparación de su red para ejecutar aplicaciones de multimedia en tiempo real, como Microsoft Teams.

> [!NOTE]
> Este es el mismo Readiness Assessment de red que se recomienda que se ejecute para los clientes que desean para implementar correctamente Skype para la empresa.


## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

Los cálculos de ancho de banda para Microsoft Teams son complejos y para ayudar a con esto, se ha creado una calculadora. Para obtener acceso a la Calculadora, vaya al [Organizador de la red](https://aka.ms/bwcalc/) en MyAdvisor.

> [!NOTE]
> Mejora el control de ancho de banda de los equipos en Skype para profesionales en línea: para una alta calidad de llamada o reunión experiencia (con audio, vídeo y uso compartido), los equipos requiere sólo 1,2 Mbps. También puede escalar más allá de super alta calidad si no hay suficiente ancho de banda disponible. Cuando una solicitud de los equipos encuentra una condición de ancho de banda bajo, los equipos pueden reajustar rápidamente el uso de ancho de banda para adaptarse al ancho de banda disponible.

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>Consideraciones de red adicionales
---------------

#### <a name="external-name-resolution"></a>Resolución de nombres externos

Asegúrese de que todos los equipos cliente que ejecutan los equipos cliente pueden resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365, y que los firewalls no impiden el acceso. Para obtener información acerca de cómo configurar los puertos de firewall, vaya a [las direcciones URL de Office 365 e intervalos IP](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Tamaño del grupo de servidores NAT

Cuando varios usuarios o dispositivos acceso a Office 365 con traducción de direcciones de red (NAT) o traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos ocultos detrás de cada dirección IP enrutable públicamente no supera el número compatible.

Para mitigar este riesgo, asegúrese de direcciones IP públicas adecuadas se asignan a los grupos de NAT para evitar el agotamiento de puerto. Agotamiento del puerto hará que los usuarios finales internos y los dispositivos hacer frente a problemas al conectarse a los servicios de Office 365. Para obtener más información, vea [admitir NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Guía de prevención de detección de intrusiones e**

Si su entorno tiene una detección de intrusiones o sistema de prevención (identificadores/IP) implementado para obtener un nivel adicional de seguridad para las conexiones salientes, asegúrese de que todo el tráfico con destino a las direcciones URL de Office 365 está en la lista blanca.

<a name="network-health-determination"></a>Determinación de mantenimiento de red
-----------------

Cuando planee en la implementación de Microsoft Teams dentro de la red, debe asegurarse de tener el ancho de banda, tiene acceso a todas las direcciones IP necesarias, los puertos adecuados que se abre, y se cumplen los requisitos de rendimiento para los medios en tiempo real .

Si sabe que no se cumplan estos criterios, los usuarios finales no obtendrá una experiencia óptima de los equipos debido a la mala calidad durante las llamadas y reuniones.

Debe no cumplan estos criterios, esto es el tiempo que se deben considerar pausar el proyecto para asegurarse de que cumple los criterios antes de continuar.


|  |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Punto de decisión         |¿Se evalúan las funciones de red para la compatibilidad con multimedia en tiempo real?<br></br>¿Si la red no se ha evaluado correctamente o si se sabe que no será compatible con multimedia en tiempo real, se deshabilitará vídeo y uso compartido de capacidades para reducir el impacto en la red y una mala experiencia de los equipos de pantalla?         |
|![Icono de Siguientes pasos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Siguientes pasos         |Calidad de red desconocido: siga las instrucciones de [Evaluación de disponibilidad de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) para determinar si la red está preparada para multimedia en tiempo Real.<br></br>Mala calidad de red: Realizar los pasos de corrección de red para proporcionar un entorno adecuado para alta calidad multimedia en tiempo Real.<br></br>Red satisfactorio: Asegúrese de todas las direcciones IP y puertos son accesibles correctamente.           |

## <a name="related-topics"></a>Temas relacionados

[Vídeo: Planeación de red](https://aka.ms/teams-networking)