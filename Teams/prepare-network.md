---
title: "Preparar la red de la organización para Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Sepa cómo preparar y administrar la red de Microsoft Teams. La información incluye los requisitos de red, los requisitos de ancho de banda y otras consideraciones."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: a89d4f201a0ea8f9392146e23629e6dd671bb7c3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2017
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar la red de la organización para Microsoft Teams
=================================================

Microsoft Teams combina tres formas de tráfico:

-   Tráfico de datos entre el entorno en línea de Office 365 y el cliente de Microsoft Teams (señalización, presencia, chat, carga y descarga de archivos, sincronización de OneNote).

-   Tráfico de comunicaciones de par a par en tiempo real (audio, vídeo y escritorio compartido).

-   Tráfico de comunicaciones de conferencias en tiempo real (audio, vídeo y escritorio compartido).

Esto afecta la red de dos maneras: el tráfico fluirá entre los clientes de Microsoft Teams directamente para las comunicaciones de par a par, y entre el entorno de Office 365 y los clientes de Microsoft Teams en las reuniones. Para asegurar un flujo de tráfico óptimo, se debe permitir que el tráfico fluya entre los segmentos de red internos (por ejemplo, entre sitios a través de WAN), así como entre los sitios de red y Office 365. Si no se abren los puertos correctos o se bloquean activamente determinados puertos, se obtendrá una experiencia deficiente.



> [!IMPORTANT]
> En este momento, las reuniones se pueden realizar con dispositivos móviles Android y iOS, pero no en Windows Phone (la compatibilidad con Windows Phone estará disponible muy pronto).

Para obtener una experiencia óptima con los medios en tiempo real dentro de Microsoft Teams, se deben cumplir los requisitos de red para Office 365 (consulte la siguiente fuente para obtener más detalles: [Calidad de los medios y rendimiento de la conectividad de red para Skype Empresarial Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US))

Los dos segmentos de red definitivos (cliente a Microsoft Edge y perímetro de cliente a Microsoft Edge) deben cumplir con los siguientes requisitos:


|Valor   |Cliente a Microsoft Edge  |Perímetro de cliente a Microsoft Edge  |
|---------|---------|---------|
|**Latencia (unidireccional)**     |< 50 ms          |< 30 ms          |
|**Latencia (RTT o tiempo de ida y vuelta)** |< 100 ms         |< 60 ms         |
|**Pérdida de paquetes de ráfaga**    |< 10% durante un intervalo de 200 ms         |< 1% durante un intervalo de 200 ms         |
|**Pérdida de paquetes**     |< 1% durante un intervalo de 15 s          |< 0,1% durante un intervalo de 15 s         |
|**Vibración entre llegadas de paquetes**    |< 30 ms durante un intervalo de 15 s         |< 15 ms durante un intervalo de 15 s         |
|**Reordenamiento de paquetes**    |< 0,05% paquetes sin ordenar         |< 0,01% paquetes sin ordenar         |

Para probar los dos segmentos de red, puede utilizarse una herramienta de evaluación de red (fuente: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799)). Esta herramienta puede implementarse en el equipo cliente directamente, así como en un equipo de escritorio o portátil que esté conectado al perímetro de red de cliente. La herramienta incluye documentación limitada, pero se puede ver una documentación más profunda sobre el uso de la herramienta aquí: [Evaluación de preparación de la red](https://go.microsoft.com/fwlink/?linkid=855800). Al ejecutar la evaluación de preparación de la red, puede validar la preparación de la red para ejecutar aplicaciones de medios en tiempo real, como Microsoft Teams.



> [!NOTE]
> Se trata de la misma evaluación de preparación de la red que se recomienda ejecutar para los clientes que buscan implementar correctamente Skype Empresarial.

<a name="bandwidth-requirements"></a>Requisitos de ancho de banda
----------

Los cálculos de ancho de banda para Microsoft Teams son complejos por lo que, para ayudar con esta tarea, se creó una calculadora. Para acceder a ella, vaya a: <http://aka.ms/bwcalc/>.

El contenido que encontrará a continuación puede utilizarse como información complementaria; sin embargo, se recomienda que los clientes usen la [calculadora de ancho de banda](https://aka.ms/bwcalc) para hacer un seguimiento de sus necesidades.



> [!IMPORTANT]
>Si el ancho de banda requerido no está disponible, los medios apilados dentro de Microsoft Teams degradarán la calidad de la sesión de audio o vídeo para adaptarse al ancho de banda más bajo, lo que afectará la calidad de la llamada o reunión. El cliente de Microsoft Teams intentará priorizar la calidad del audio por sobre la calidad del vídeo. Por lo tanto, es sumamente importante tener disponible la cantidad de ancho de banda esperada.


|Actividad  |Descargar ancho de banda  |Cargar ancho de banda  |Flujo de tráfico |
|---------|---------|---------|---------|
|**Llamada de audio de par a par**     |0,1 MB         |0,1 MB         |Cliente <> Cliente         |
|**Videollamada de par a par (pantalla completa)**     |4 MB         |4Mb         |Cliente <> Cliente          |
|**Compartir escritorio de par a par (resolución de 1920*1080)**     |4 MB         |4 MB         |Cliente <> Cliente          |
|**Reunión de dos participantes**     |4 MB         |4 MB         |Cliente <> Office 365         |
|**Reunión de tres participantes**     |8 MB         |6,5 MB         |Cliente <> Office 365           |
|**Reunión de cuatro participantes**     |5,5 MB         |4 MB         |Cliente <> Office 365           |
|**Reunión de cinco participantes o más**     |6 MB         |1,5 MB         |Cliente <> Office 365           |


<a name="additional-network-considerations"></a>Otras consideraciones sobre la red
---------------

#### <a name="external-name-resolution"></a>**Resolución de nombre externo**

Asegúrese de que todos los equipos cliente que ejecutan el cliente de Microsoft Teams pueden resolver las consultas DNS externas para detectar los servicios brindados por Office 365.

#### <a name="nat-pool-size"></a>**Tamaño de grupo de NAT**

Cuando varios dispositivos y usuarios acceden a Office 365 mediante traducción de direcciones de red (NAT) o traducción de direcciones de puertos (PAT), es necesario asegurarse de que los dispositivos ocultos detrás de cada dirección IP de enrutamiento público no superen el número admitido.

Para mitigar el riesgo, asegúrese de que se asignen direcciones IP públicas adecuadas a los grupos de NAT para evitar el agotamiento de puertos. El agotamiento de puertos ocasionará que los usuarios internos y los dispositivos tengan problemas al conectarse con los servicios de Office 365. Para obtener más información, consulte la guía [Admisión de NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Instrucciones para detener y prevenir intrusiones**

Si su entorno tiene un sistema de detección o prevención de intrusiones (IDS/IPS) implementado para brindar una capa adicional de seguridad para las conexiones salientes, asegúrese de que el tráfico con destino a URL de Office 365 se agregue a una lista de permitidos.

<a name="network-health-determination"></a>Determinación del estado de la red
-----------------

Al planificar la implementación de Microsoft Teams dentro de la red, debe asegurarse de tener el ancho de banda necesario, acceso a todas las direcciones IP necesarias y los puertos correctos abiertos, así como de cumplir los requisitos de rendimiento para los medios en tiempo real.

Si sabe que no cumplirá con estos criterios, sus usuarios finales no obtendrán una experiencia óptima de Microsoft Teams, debido a que la calidad durante las llamadas y las reuniones será deficiente.

Si llegara a suceder que no cumple con estos criterios, este es el momento de pensar en pausar el proyecto para asegurarse de cumplir los criterios antes de continuar.


|  |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Punto de decisión         |¿Ha evaluado la capacidad de la red para admitir medios en tiempo real?<br></br>Si su red no ha sido evaluada correctamente, o si sabe que no admitirá los medios en tiempo real, ¿deshabilitaría las funciones de vídeo y pantalla compartida para disminuir el impacto en la red y las experiencias deficientes en Teams?         |
|![Icono de Siguientes pasos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Siguientes pasos         |Calidad de red desconocida: Siga la guía de evaluación de preparación de la red en skypeoperationsframework.com para determinar si la red está lista para medios en tiempo real.<br></br>Calidad de red deficiente: Realice los pasos para reparar la red a fin de proporcionar un entorno adecuado para medios en tiempo real de alta calidad.<br></br>Red satisfactoria: Asegúrese de que se pueda acceder correctamente a todos los puertos y las direcciones IP.           |

