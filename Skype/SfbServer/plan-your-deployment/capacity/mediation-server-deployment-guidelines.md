---
title: Directrices de implementación para el servidor de mediación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: En este tema se describen las directrices de planeación para la implementación del servidor de mediación.
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800095"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Directrices de implementación para el servidor de mediación en Skype Empresarial Server
 
En este tema se describen las directrices de planeación para la implementación del servidor de mediación.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación local o independiente?

De forma predeterminada, el servidor de mediación se coloca en el servidor Standard Edition o el servidor front-end en un grupo de servidores front-end en los sitios centrales. El número de llamadas de la red telefónica conmutada (RTC) que se pueden controlar y el número de máquinas necesarias en el grupo de servidores dependerán de:
  
- El número de puertas de enlace del mismo nivel que controla el grupo de servidores de mediación.
    
- Los períodos de tráfico de gran volumen a través de esas puertas de enlace.
    
- Porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación.
    
Cuando planee, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y conferencias A/V que no admiten la omisión de medios, así como el procesamiento necesario para controlar las interacciones de señalización para el número de llamadas en hora punta que es necesario admitir. Si no tiene suficiente CPU, deberá implementar un grupo independiente de servidores de mediación. Además, las puertas de enlace RTC, ip-PBX y SBC tendrán que dividirse en subconjuntos controlados por los servidores de mediación de un grupo de servidores y los servidores de mediación independientes en uno o más grupos de servidores independientes.
  
Si implementó puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBC) que no tienen la capacidad de interactuar con un grupo de servidores de mediación, necesitará asociarse a un grupo independiente que consta de un único servidor de mediación. Algunas de las cosas que las puertas de enlace RTC, IP-PBXs o SBC tendrían que hacer son:
  
- Realizar el equilibrio de carga del Sistema de nombres de dominio (DNS) de la capa de red entre los servidores de mediación de un grupo de servidores (o enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo de servidores).
    
- Acepte el tráfico de cualquier servidor de mediación de un grupo de servidores.
    
Puede usar la Herramienta de planeación de Skype Empresarial para evaluar si la instalación del servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si su entorno no puede cumplir estos requisitos, deberá implementar un grupo de servidores de mediación independiente.
  
## <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y las sucursales

 Los servidores de mediación del sitio central se pueden usar para enrutar llamadas a puertas de enlace RTC o IP-PBX en las sucursales. Sin embargo, si implementa troncos SIP, debe implementar un servidor de mediación en el sitio donde termina cada tronco. Tener un servidor de mediación en el sitio central enruta llamadas para una puerta de enlace RTC o IP-PBX en un sitio de sucursal no requiere el uso de la omisión de medios, pero se recomienda una omisión de medios. Esto se debe a que, si puedes habilitar la omisión de medios, reducirá la latencia de la ruta de acceso a los medios y, por lo tanto, mejorará la calidad de los medios, ya que la ruta de acceso multimedia no es necesaria para seguir la ruta de señalización. El desvío de medios disminuirá también la carga de procesamiento del grupo de servidores.
  
> [!NOTE]
> La omisión de medios no interoperará con cada puerta de enlace RTC, IP-PBX y SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco. La omisión de medios solo se admite con los productos y las versiones enumerados en el Programa de interoperabilidad abierta de comunicaciones unificadas: Lync Server en Explorar dispositivos [probados,](http://partnersolutions.skypeforbusiness.com/solutionscatalog)infraestructura y herramientas que admiten y amplían su experiencia de Skype Empresarial. 
  
Si se necesita resistencia en la sucursal, se debe implementar una aplicación de sucursal con funciones de supervivencia o una combinación de servidor front-end, servidor de mediación y puerta de enlace en la sucursal. (La suposición con resistencia de sitios de sucursal es que la presencia y las conferencias no son resistentes en el sitio). For guidance on branch site planning for voice, see [Plan for Telefonía IP empresarial resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
En el caso de las interacciones con una IP-PBX, si la IP-PBX no admite correctamente interacciones de medios iniciales con varios cuadros de diálogo iniciales e interacciones RFC 3960, puede haber un recorte de las primeras palabras del saludo para las llamadas entrantes de ip-PBX a los extremos de Lync. Este suceso puede agravarse si un servidor de mediación del sitio central enruta llamadas a un IP-PBX en el que la ruta termina en una sucursal, porque se necesita más tiempo para que la señalización finalice. Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de sucursal es la única forma de reducir el recorte de las primeras palabras.
  
Por último, si el sitio central tiene un PBX TDM, o si el IP-PBX no evita la necesidad de una puerta de enlace RTC, deberá implementar una puerta de enlace en la ruta de la llamada para conectar el servidor de mediación y el PBX.
  
> [!NOTE]
> Para mejorar el rendimiento multimedia del servidor de mediación independiente, debe habilitar el ajuste de escala del lado de recepción (RSS) en los adaptadores de red de estos servidores. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, consulte["Mejoras de escalado del](https://go.microsoft.com/fwlink/p/?LinkId=268731)lado de recepción en Windows Server". Para obtener más información sobre cómo habilitar RSS, consulte la documentación del adaptador de red. 
  

