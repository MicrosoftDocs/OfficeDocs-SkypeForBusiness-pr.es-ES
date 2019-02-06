---
title: Preparar la red de la organización para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Sepa cómo preparar y administrar la red de Microsoft Teams. La información incluye los requisitos de red, los requisitos de ancho de banda y otras consideraciones.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6b95da8ee416d4f64d22a8c0622acd417b7bb1d
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742851"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams
=================================================

> [!Tip]
> Vea la sesión siguiente para obtener más información cómo los equipos aprovecha la red y cómo planear mejor para la conectividad de red óptima: [Planeación de los equipos de red](https://aka.ms/teams-networking)


Teams combina tres formas de tráfico:

-   Tráfico de datos entre el entorno en línea de Office 365 y el cliente de Teams (señalización, presencia, chat, carga y descarga de archivos, sincronización de OneNote).

-   Tráfico de comunicaciones punto a punto en tiempo real (audio, vídeo y escritorio compartido).

-   Tráfico de comunicaciones de conferencias en tiempo real (audio, vídeo y escritorio compartido).

Esto afecta la red de dos maneras: el tráfico fluirá entre los clientes de Microsoft Teams directamente para las comunicaciones de par a par, y entre el entorno de Office 365 y los clientes de Microsoft Teams en los escenarios de reuniones. Para asegurar un flujo de tráfico óptimo, se debe permitir que el tráfico fluya entre los segmentos de red internos (por ejemplo, entre sitios a través de WAN), así como entre los sitios de red y Office 365. Si no se abren los puertos correctos o se bloquean activamente determinados puertos, se obtendrá una experiencia deficiente.

> [!NOTE]
> Las reuniones son compatibles con iOS y Android dispositivos móviles. 

Para obtener una experiencia óptima con los elementos multimedia en tiempo real dentro de Microsoft Teams, se deben cumplir los requisitos de red para Office 365. Para obtener más información, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Para los dos definen segmentos de red (cliente a Microsoft Edge) y borde de cliente a Microsoft Edge, tenga en cuenta las siguientes recomendaciones.


|Valor  |Cliente a Microsoft Edge  |Perímetro de cliente a Microsoft Edge  |
|---------|---------|---------|
|**Latencia (unidireccional)**     |< 50 ms          |< 30 ms          |
|**Latencia (RTT o tiempo de ida y vuelta)** |< 100 ms         |< 60 ms         |
|**Pérdida de paquetes de ráfaga**    |< 10% durante un intervalo de 200 ms         |< 1% durante un intervalo de 200 ms         |
|**Pérdida de paquetes**     |< 1% durante un intervalo de 15 s          |< 0,1% durante un intervalo de 15 s         |
|**Vibración entre llegadas de paquetes**    |< 30 ms durante un intervalo de 15 s         |< 15 ms durante un intervalo de 15 s         |
|**Reordenamiento de paquetes**    |< 0,05% paquetes sin ordenar         |< 0,01% paquetes sin ordenar         |

Para probar los dos segmentos de red, puede usar la [herramienta de evaluación de red](https://go.microsoft.com/fwlink/?linkid=855799). Esta herramienta puede implementarse en el equipo cliente directamente y en un equipo que esté conectado al perímetro de red de cliente. La herramienta incluye documentación limitada, pero se puede ver una documentación más profunda sobre el uso de la herramienta aquí: [herramienta de evaluación de red](https://go.microsoft.com/fwlink/?linkid=855800). Al ejecutar la evaluación de preparación de la red, puede validar la preparación de la red para ejecutar aplicaciones multimedia en tiempo real, como Microsoft Teams.

> [!NOTE]
> Se trata de la misma evaluación de preparación de la red que se recomienda ejecutar para los clientes que buscan implementar correctamente Skype Empresarial.

<a name="bandwidth-requirements"></a>Requisitos de ancho de banda
----------

Los cálculos de ancho de banda para Microsoft Teams son complejos por lo que, para ayudar con esta tarea, se creó una calculadora. Para acceder a la calculadora, vaya a [Network Planner en MyAdvisor](https://aka.ms/bwcalc/).

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

<a name="additional-network-considerations"></a>Otras consideraciones sobre la red
---------------

#### <a name="external-name-resolution"></a>**Resolución de nombre externo**

Asegúrese de que todos los equipos cliente que ejecutan el cliente de Teams pueden resolver las consultas DNS externas para detectar los servicios brindados por Office 365.

#### <a name="nat-pool-size"></a>**Tamaño de grupo de NAT**

Cuando varios dispositivos y usuarios acceden a Office 365 mediante traducción de direcciones de red (NAT) o traducción de direcciones de puertos (PAT), es necesario asegurarse de que los dispositivos ocultos detrás de cada dirección IP de enrutamiento público no superen el número admitido.

Para mitigar el riesgo, asegúrese de que se asignen direcciones IP públicas adecuadas a los grupos de NAT para evitar el agotamiento de puertos. El agotamiento de puertos ocasionará que los usuarios internos y los dispositivos tengan problemas al conectarse con los servicios de Office 365. Para obtener más información, consulte [Compatibilidad de NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Instrucciones para detener y prevenir intrusiones**

Si su entorno tiene un sistema de detección o prevención de intrusiones (IDS/IPS) implementado para brindar una capa adicional de seguridad para las conexiones salientes, asegúrese de que el tráfico con destino a URL de Office 365 se agregue a una lista de permitidos.

<a name="network-health-determination"></a>Determinación del estado de la red
-----------------

Al planificar la implementación de Microsoft Teams dentro de la red, debe asegurarse de tener el ancho de banda necesario, tener acceso a todas las direcciones IP necesarias y los puertos correctos abiertos, así como de cumplir los requisitos de rendimiento para los elementos multimedia en tiempo real.

Si sabe que no cumplirá con estos criterios, sus usuarios finales no obtendrán una experiencia óptima de Teams, debido a que la calidad durante las llamadas y las reuniones será deficiente.

Si llegara a suceder que no cumple con estos criterios, este es el momento de pensar en pausar el proyecto para asegurarse de cumplir los criterios antes de continuar.


|  |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Punto de decisión         |¿Ha evaluado la capacidad de la red para admitir elementos multimedia en tiempo real?<br></br>Si su red no ha sido evaluada correctamente, o si sabe que no admitirá los elementos multimedia en tiempo real, ¿deshabilitaría las funciones de vídeo y pantalla compartida para disminuir el impacto en la red y las experiencias deficientes en Teams?         |
|![Icono de Siguientes pasos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Siguientes pasos         |Calidad de red desconocida: Siga la guía de [evaluación de preparación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) para determinar si la red está lista para elementos multimedia en tiempo real.<br></br>Calidad de red deficiente: Siga los pasos para reparar la red a fin de proporcionar un entorno adecuado para elementos multimedia en tiempo real de alta calidad.<br></br>Red satisfactoria: Asegúrese de que se pueda acceder correctamente a todos los puertos y las direcciones IP.           |

## <a name="related-topics"></a>Temas relacionados

[Vídeo: Planeación de red](https://aka.ms/teams-networking)