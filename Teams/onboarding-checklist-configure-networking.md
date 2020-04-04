---
title: 'Lista de comprobación de la incorporación: configuración de redes-Microsoft Teams'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga las actividades básicas y tareas pendientes de esta lista de comprobación cuando configure su red para Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b4780e0509598406b25c1b8145a29a6aeef0423f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43138320"
---
# <a name="configure-networking"></a>Configurar redes

| No | Actividad o tarea | Descripción | ¿Completado? | Información adicional |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Revisar los requisitos de red de Teams | Tenga una visión general de los requisitos de su red antes de pasar a los detalles de la red. | | [Preparar la red de la organización para Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 1  | Ofrecer el taller de preparación de redes | Realizar una evaluación de la disponibilidad de red. | |  |
| 3  | Usar el planificador de redes | Planear el ancho de banda de red. | | |
| 4  | Validar el tamaño del grupo NAT necesario para conectividad de usuario | Asegúrese de que las direcciones IP públicas adecuadas se asignen a los grupos NAT para evitar el agotamiento del puerto. El agotamiento del puerto contribuirá a que los usuarios internos y los dispositivos no puedan conectarse al servicio de Office 365. <br/><br/>Los problemas de conectividad son una causa principal de los problemas de percepción de los usuarios en los servicios en la nube. | | [Compatibilidad de NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | Implementar el enrutamiento más eficaz a los centros de recursos de Microsoft | Identifique las ubicaciones que pueden usar puntos de salida locales o regionales para conectarse a la red de Microsoft de la manera más eficaz posible. <br/><br/>En el artículo de la columna **información adicional** se describe cómo los clientes pueden aprovechar las características de la resolución de nombres de Office 365 y el enrutamiento IP para conectarse de forma eficaz al centro de datos regional más cercano. | | [Conectividad de cliente de Office 365](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | Configurar los puertos de Firewall solicitados para conectividad con Teams | Revise las direcciones URL e IP de Office 365 para identificar y probar los puertos de Firewall necesarios para la conectividad entre clientes y servidores locales y servicios de Office 365. <br/><br/>Para un entorno compatible, debe abrir todos los puertos de los firewalls. Si no abre algunos puertos o intervalos, la experiencia del usuario se verá afectada. Configure los puertos de medios en sus firewalls en función de las instrucciones de la columna **información adicional** . | | [Direcciones URL e IP de Office 365: Microsoft Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | Configurar servidores proxy | Configure su entorno de modo que los servidores proxy se omitan y pueda conectar a los usuarios directamente a Office 365 mediante UDP, para obtener la mejor calidad de audio y vídeo. Cuando los medios en tiempo real se ven obligados a atravesar un servidor proxy, la pila de medios de Teams se ve obligada a migrar tras error a TCP, que afecta negativamente a la calidad. <br/><br/>Para obtener la experiencia de usuario de mayor calidad, siempre prefiere UDP por TCP. | | [Planificación de la calidad y la administración de servicios](https://docs.microsoft.com/MicrosoftTeams/prepare-network) |
| 4,8  | Configurar túnel dividido VPN | Le recomendamos que proporcione una ruta de acceso alternativa para el tráfico de teams que omite la VPN, conocida comúnmente como *VPN de túnel dividido*. El túnel dividido significa que el tráfico de Office 365 no atraviesa la red privada virtual, pero va directamente a Office 365. Este cambio tendrá un impacto positivo en la calidad, pero también proporciona la ventaja secundaria de reducir la carga de los dispositivos VPN y de la red de la organización. | | Para implementar una VPN de túnel dividido, consulte con su proveedor de VPN para obtener detalles de configuración. |
| 99,999  | Configurar la priorización de paquetes mediante QoS | QoS debe implementarse en todos los segmentos de una red administrada. Incluso cuando una red ha sido aprovisionada de forma adecuada para el ancho de banda, QoS proporciona mitigación del riesgo en caso de eventos de red no previstos. Cuando se implementa QoS, se prioriza el tráfico de voz para que estos eventos no previstos no afecten negativamente a la calidad. | | [Planificación de la calidad y la administración de servicios](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[Calidad de servicio (QoS) en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| base10 | Optimizar la calidad y el rendimiento de las redes Wi-Fi | Al optimizar su red Wi-Fi, surgen varios factores: <ul><li>Implementación de QoS o multimedia Wi-Fi (WMM) para garantizar la priorización del tráfico multimedia en las redes Wi-Fi.</li><li>Planear y optimizar las bandas Wi-Fi y la ubicación de puntos de acceso. El intervalo de 2,4 GHz puede proporcionar un rendimiento adecuado, en función de la ubicación del punto de acceso.</li></ul> Consulta a tu proveedor de Wi-Fi para obtener instrucciones específicas. | | [Recomendaciones de Wi-Fi para puntos de conexión](https://docs.microsoft.com/MicrosoftTeams/prepare-network#wi-fi-recommendations-for-endpoints) |
| once | Validar la conectividad de red con la herramienta de evaluación de red | Use la herramienta de evaluación de redes de Skype empresarial y Teams para probar la conectividad con todas las direcciones IP y los puertos que se usan en las llamadas y reuniones de Skype empresarial online y Teams. Descargue la herramienta y vea Usage. docx para obtener información sobre cómo usar la herramienta e interpretar los resultados de la prueba. Le recomendamos que ejecute la herramienta desde un equipo cliente en cada ubicación en la que se vayan a usar los equipos. | | [Herramienta de evaluación de redes de Skype empresarial y Teams](https://go.microsoft.com/fwlink/?linkid=855799) |
