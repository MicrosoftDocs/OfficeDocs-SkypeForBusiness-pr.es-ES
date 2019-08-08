---
title: Preparar la red de la organización para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Sepa cómo preparar y administrar la red de Microsoft Teams. La información incluye los requisitos de red, los requisitos de ancho de banda y otras consideraciones.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31c06403dc3dec9322e984e012fe597254db8f33
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235182"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams


Teams combina tres formas de tráfico:

-   Tráfico de datos entre el entorno en línea de Office 365 y el cliente de Teams (señalización, presencia, chat, carga y descarga de archivos, sincronización de OneNote).

-   Tráfico de comunicaciones punto a punto en tiempo real (audio, vídeo y escritorio compartido).

-   Tráfico de comunicaciones de conferencias en tiempo real (audio, vídeo y escritorio compartido).

Esto afecta la red de dos maneras: el tráfico fluirá entre los clientes de Microsoft Teams directamente para las comunicaciones de par a par, y entre el entorno de Office 365 y los clientes de Microsoft Teams en los escenarios de reuniones. Para asegurar un flujo de tráfico óptimo, se debe permitir que el tráfico fluya entre los segmentos de red internos (por ejemplo, entre sitios a través de WAN), así como entre los sitios de red y Office 365. Si no se abren los puertos correctos o se bloquean activamente determinados puertos, se obtendrá una experiencia deficiente.

> [!NOTE]
> Las reuniones son compatibles con dispositivos móviles iOS y Android. 

Para obtener una experiencia óptima con medios en tiempo real en Microsoft Teams, su red debe cumplir con los requisitos de red de Office 365. Para obtener más información, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Para los dos segmentos de red definitivos (cliente a Microsoft Edge y perímetro de cliente a Microsoft Edge), tenga en cuenta las siguientes recomendaciones.


|Valor  |Cliente a Microsoft Edge  |Perímetro de cliente a Microsoft Edge  |
|:--- |:--- |:--- |
|**Latencia (unidireccional)**\*  |< 50 ms          |< 30 ms         |
|**Latencia (RTT o tiempo de ida y vuelta)**\* |< 100 ms   |< 60 ms |
|**Pérdida de paquetes de ráfaga**    |< 10% durante un intervalo de 200 ms         |< 1% durante un intervalo de 200 ms         |
|**Pérdida de paquetes**     |< 1% durante un intervalo de 15 s          |< 0,1% durante un intervalo de 15 s         |
|**Vibración entre llegadas de paquetes**    |< 30 ms durante un intervalo de 15 s         |< 15 ms durante un intervalo de 15 s         |
|**Reordenamiento de paquetes**    |< 0,05% paquetes sin ordenar         |< 0,01% paquetes sin ordenar         |

\*El objetivo de la métrica de latencia supone que el sitio o los sitios de la empresa y los bordes de Microsoft están en el mismo continente.

La conexión del sitio de su empresa con el perímetro de la red de Microsoft incluye acceso de red de primer salto, que puede ser WiFi u otra tecnología inalámbrica.

Los objetivos de rendimiento de red suponen un ancho de banda adecuado o un [plan QoS](QoS-in-Teams.md). En otras palabras, los requisitos se aplican directamente al tráfico de medios en tiempo real de Teams cuando la conexión de red está por debajo de una carga máxima.

Para obtener más ayuda con la preparación de la red para Teams, consulte [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).


## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda
Microsoft Teams te ofrece la mejor experiencia de audio, vídeo y uso compartido de contenido, independientemente de las condiciones de tu red. Con los códecs variables, los medios se pueden negociar en entornos de ancho de banda limitados con un impacto mínimo. Pero donde el ancho de banda no es un problema, las experiencias se pueden optimizar para la calidad, incluida la resolución de video de 1080p, hasta 30 fps para video y 15fps para el contenido y el audio de alta fidelidad.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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

Asegúrese de que todos los equipos cliente que ejecutan el cliente de Teams puedan resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365 y que los firewalls no impiden el acceso. Para obtener información sobre cómo configurar puertos de firewall, vaya a [Office 365 URL e intervalos IP](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Tamaño del grupo NAT

Cuando varios usuarios o dispositivos obtienen acceso a Office 365 mediante la traducción de direcciones de red (NAT) o la traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos que se encuentran detrás de cada dirección IP enrutable pública no superen el número admitido.

Para mitigar este riesgo, asegúrese de que se asignan direcciones IP públicas adecuadas a los grupos NAT para evitar el agotamiento del puerto. El agotamiento del puerto provocará problemas a los usuarios finales internos y los dispositivos al conectarse a los servicios 365 de Office. Para obtener más información, consulte [compatibilidad de NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Guía de detección y prevención de intrusiones**

Si su entorno tiene un sistema de detección o prevención de intrusiones (IDS/IPS) implementado para una capa adicional de seguridad para conexiones salientes, asegúrese de que todo el tráfico con destino a las direcciones URL de Office 365 se encuentra en la lista blanca.

<a name="network-health-determination"></a>Determinación del estado de la red
-----------------

Al planear la implementación de Microsoft Teams en su red, debe asegurarse de que tiene el ancho de banda necesario, que tiene acceso a todas las direcciones IP requeridas, que se han abierto los puertos correctos y que está cumpliendo los requisitos de rendimiento para los medios en tiempo real .

Si sabe que no cumplirá estos criterios, los usuarios finales no obtendrán una experiencia óptima de Teams debido a la mala calidad de las llamadas y las reuniones.

Si no cumple estos criterios, es el momento de considerar pausar el proyecto para asegurarse de que cumple los criterios antes de continuar.


|  |  |  |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Punto de decisión         |¿Ha evaluado sus capacidades de red para admitir medios en tiempo real?<br></br>Si su red no se ha evaluado correctamente o sabe que no es compatible con los medios en tiempo real, deshabilitará las funciones de vídeo y pantalla compartida para reducir el impacto de la red y las experiencias de equipos deficientes.         |
|![Un icono que representa los pasos siguientes](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Siguientes pasos         |Calidad de red desconocida: realice una evaluación de la disponibilidad de red para determinar si su red está lista para los medios en tiempo real.<br></br>Calidad de red deficiente: realice los pasos de corrección de red para proporcionar un entorno adecuado para los medios en tiempo real de alta calidad.<br></br>Red satisfactoria: Asegúrese de que todas las direcciones IP y los puertos son accesibles correctamente.           |

## <a name="related-topics"></a>Temas relacionados

[Vídeo: planificación de red](https://aka.ms/teams-networking)
