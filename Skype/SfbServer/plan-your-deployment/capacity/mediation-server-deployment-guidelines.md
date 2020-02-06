---
title: Directrices de implementación para el servidor de mediación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: En este tema se describen las directrices de planeación para la implementación de Media Server.
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816059"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Directrices de implementación para el servidor de mediación en Skype empresarial Server
 
En este tema se describen las directrices de planeación para la implementación de Media Server.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediación colocada o independiente?

El servidor de mediación se encuentra, de forma predeterminada, en el servidor Standard Edition o en el servidor front-end de un grupo de servidores front-end en los sitios centrales. El número de llamadas de la red telefónica conmutada (RTC) que se puede administrar y el número de máquinas necesarias en el grupo de servidores dependerán de los factores siguientes:
  
- El número de puertas de enlace o gateways controladas por el grupo de servidores de mediación.
    
- Los períodos de alto volumen de tráfico que atraviesa las puertas de enlace.
    
- El porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación.
    
Al realizar el planeamiento, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y conferencias de A/V no compatibles con la omisión de medios, además del procesamiento necesario para administrar las interacciones de señalización del número de llamadas que es necesario admitir en las horas de más actividad. Si no tiene suficiente CPU, tendrá que implementar un grupo independiente de servidores de mediación. Además, las puertas de enlace RTC, las PBX IP y SBCs deberán dividirse en subconjuntos que se controlan mediante los servidores de mediación en un mismo grupo y los servidores de mediación independientes en uno o más grupos de servidores independientes.
  
Si ha implementado puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBCs) que no tienen la capacidad de interactuar con un grupo de servidores de mediación, necesitarán estar asociados con un grupo independiente que contenga un solo servidor de mediación. Estas son algunas de las acciones que es necesario realizar con las puertas de enlace RTC, IP-PBX o SBC:
  
- Realizar el equilibrio de carga del sistema de nombres de dominio (DNS) de nivel de red en los servidores de mediación de un grupo (o bien enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo).
    
- Acepte el tráfico de cualquier servidor de mediación de un grupo.
    
Puede usar la herramienta de planeación de Skype empresarial para evaluar si collocating el servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si su entorno no puede cumplir estos requisitos, tendrá que implementar un grupo de servidores de mediación independiente.
  
## <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

 Los servidores de mediación del sitio central se pueden usar para enrutar llamadas para IP-PBX o puertas de enlace RTC en sitios de sucursales. Sin embargo, si implementas los troncos SIP, debes implementar un servidor de mediación en el sitio en el que termina cada tronco. Tener un servidor de mediación en el sitio central las llamadas a una puerta de enlace IP o RTC en un sitio de sucursal no requieren el uso de la omisión de medios, pero se recomienda una omisión de medios. Pero, si puede habilitar la omisión de medios, se reducirá la latencia de la ruta de acceso a medios y, por lo tanto, mejorará la calidad de los medios, ya que la ruta de acceso a medios ya no será necesaria para seguir la ruta de acceso de señalización. La omisión de medios también reducirá la carga de procesamiento del grupo.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, sistemas IP-PBX y SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con asociados certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. La omisión de contenido multimedia solo se admite con productos y versiones incluidos en el programa de interoperabilidad abierto de comunicaciones unificadas, Lync Server en [explorar dispositivos, infraestructura y herramientas probados que admiten y amplían su experiencia con Skype empresarial](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si se requiere resistencia al sitio de la sucursal, se debe implementar en el sitio de la sucursal un dispositivo de aplicación de media o una combinación de un servidor front-end, un servidor de mediación y una combinación. (La hipótesis con la resistencia de los sitios de las sucursales es que la presencia y las conferencias no son resistentes en el sitio). Para obtener instrucciones sobre el planeamiento de sitios de las sucursales de voz, consulte [planear la resistencia de telefonía IP empresarial en Skype empresarial Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
En el caso de interacciones con un IP-PBX, si el IP-PBX no es compatible con las interacciones de medios iniciales con varios cuadros de diálogo y interacciones de RFC 3960, puede recortar las primeras palabras del saludo para las llamadas entrantes desde el IP-PBX a los puntos de conexión de Lync. Este comportamiento puede ser más grave si un servidor de mediación de un sitio central está enrutando las llamadas a un IP-PBX donde la ruta termina en un sitio de sucursal, porque se necesita más tiempo para que se complete la señalización. Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de la sucursal es la única forma de reducir el recorte de las primeras palabras.
  
Por último, si su sitio central tiene un sistema PBX con TDM, o si su IP-PBX no elimina la necesidad de una puerta de enlace RTC, debe implementar una puerta de enlace en la ruta de llamada y en el servidor PBX.
  
> [!NOTE]
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, vea "[mejoras en la escala del lado de recepción en Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red. 
  

