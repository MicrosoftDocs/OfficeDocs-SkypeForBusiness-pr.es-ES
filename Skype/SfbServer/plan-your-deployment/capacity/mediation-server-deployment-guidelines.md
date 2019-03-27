---
title: Instrucciones de implementación para el servidor de mediación en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: En este tema se describe las instrucciones de planeación para la implementación de servidor de mediación.
ms.openlocfilehash: 1a35d2f0bb74cfd78cba8924e6cafb6ce601d647
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896116"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Instrucciones de implementación para el servidor de mediación en Skype para Business Server
 
En este tema se describe las instrucciones de planeación para la implementación de servidor de mediación.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación independientes o combinados?

De forma predeterminada, el servidor de mediación está, combinado en el servidor Standard Edition o un servidor Front-End en un grupo de servidores Front-End en las sedes centrales. El número de llamadas de la red telefónica conmutada (RTC) que se puede administrar y el número de máquinas necesarias en el grupo de servidores dependerán de los factores siguientes:
  
- El número de mismo nivel de puerta de enlace que controla el grupo de servidores de mediación.
    
- Los períodos de alto volumen de tráfico que atraviesa las puertas de enlace.
    
- El porcentaje de llamadas cuyos medios omiten el servidor de mediación.
    
Al realizar el planeamiento, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y conferencias de A/V no compatibles con la omisión de medios, además del procesamiento necesario para administrar las interacciones de señalización del número de llamadas que es necesario admitir en las horas de más actividad. Si no tiene suficiente CPU, debe implementar un grupo de servidores de mediación independiente. Además, las puertas de enlace RTC, IP-PBX y SBCs tendrá que se pueden dividir en subconjuntos que se controlan mediante los servidores de mediación combinado en un grupo de servidores y los servidores de mediación independiente en uno o varios grupos de servidores independientes.
  
Si ha implementado las puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBCs) que carecen de la capacidad de interactuar con un grupo de servidores de mediación, deben asociarse con un grupo de servidores independiente que consta de un único servidor de mediación. Estas son algunas de las acciones que es necesario realizar con las puertas de enlace RTC, IP-PBX o SBC:
  
- Realizar la capa de red a través de los servidores de mediación en un grupo de servidores de equilibrio de carga de sistema de nombres de dominio (DNS) (o enrutar el tráfico uniformemente a todos los servidores de mediación en un grupo de servidores).
    
- Aceptar el tráfico desde cualquier servidor de mediación en un grupo de servidores.
    
Puede usar el Skype para la herramienta de planeación de negocio para evaluar si combinar el servidor de mediación con el grupo de servidores Front-End puede administrar la carga. Si el entorno no cumple estos requisitos, que necesitará para implementar un grupo de servidores de mediación independiente.
  
## <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

 Los servidores de mediación en el sitio central pueden utilizarse para enrutar las llamadas de IP-PBX o puertas de enlace RTC en sitios de sucursal. Si implementa troncos SIP, sin embargo, se debe implementar un servidor de mediación en el sitio donde se finaliza cada tronco. Tener un servidor de mediación en el sitio central enrutar llamadas para un sistema IP-PBX o puerta de enlace RTC en un sitio de sucursal no requiere el uso de medios de desvío, pero se recomienda un desvío de medios. Pero, si puede habilitar la omisión de medios, se reducirá la latencia de la ruta de acceso a medios y, por lo tanto, mejorará la calidad de los medios, ya que la ruta de acceso a medios ya no será necesaria para seguir la ruta de acceso de señalización. La omisión de medios también reducirá la carga de procesamiento del grupo.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, sistemas IP-PBX y SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con asociados certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Desvío de medios es compatible solo con productos y versiones que aparecen en Unified Communications Open Interoperability Program - Lync Server en [Explorar probado dispositivos, infraestructura y las herramientas que admiten y extensión su Skype para que la experiencia empresarial](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si se requiere la resistencia de la sucursal, una aplicación de sucursal con funciones de supervivencia o una combinación de un servidor Front-End, un servidor de mediación y una puerta de enlace debe estar implementado en el sitio de sucursal. (La suposición de resistencia de la sucursal es que presencia y conferencia no son resistentes en el sitio). Para obtener orientación sobre planeación de voz de sitio de sucursal, consulte [Plan para la resistencia de Enterprise Voice en Skype para Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Para las interacciones con un IP-PBX, si el IP-PBX no admite correctamente anticipado interacciones de medios con varios diálogos iniciales y las interacciones de RFC 3960, puede haber algunas palabras del saludo para las llamadas entrantes de la IP-PBX a extremos de Lync el recorte de la primera. Este comportamiento puede ser más grave si un servidor de mediación en un sitio central es enrutamiento de llamadas para un sistema IP-PBX donde finaliza la ruta en un sitio de sucursal, ya que se necesita más tiempo para señalización para llevar a cabo. Si experimenta este comportamiento, la implementación de un servidor de mediación en el sitio de sucursal es la única forma para reducir el recorte de la primera primeras palabras.
  
Por último, si el sitio central tiene una PBX TDM, o si el IP-PBX no elimina la necesidad de una puerta de enlace de RTC, debe implementar una puerta de enlace en la ruta de llamada de conexión de servidor de mediación y el sistema PBX.
  
> [!NOTE]
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener información detallada, consulte "[Mejoras de escala en el lado de recepción en Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red. 
  

