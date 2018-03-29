---
title: Instrucciones de implementación para el servidor de mediación en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Este tema describe las directrices para planear la implementación de servidor de mediación.
ms.openlocfilehash: e1017e9fab43578fd3c10e8043c7dcc747d313b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server-2015"></a>Instrucciones de implementación para el servidor de mediación en Skype Empresarial Server 2015
 
Este tema describe las directrices para planear la implementación de servidor de mediación.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación colocadas o independiente?

De forma predeterminada, el servidor de mediación es, ubicado en el servidor Standard Edition o un servidor Front-End en un grupo de servidores Front-End en las sedes centrales. El número de llamadas de la red telefónica conmutada (RTC) que se puede administrar y el número de máquinas necesarias en el grupo de servidores dependerán de los factores siguientes:
  
- El número de pares de gateway que controla el grupo de servidor de mediación.
    
- Los períodos de alto volumen de tráfico que atraviesa las puertas de enlace.
    
- Porcentaje de llamadas de llamadas cuyos medios omiten el servidor de mediación.
    
Al realizar el planeamiento, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y conferencias de A/V no compatibles con la omisión de medios, además del procesamiento necesario para administrar las interacciones de señalización del número de llamadas que es necesario admitir en las horas de más actividad. Si no tiene suficiente CPU, debe implementar un conjunto independiente de servidores de mediación. Además, las puertas de enlace PSTN, PBX IP y SBCs debe dividirse en subconjuntos que son controlados por los servidores de mediación colocadas en un grupo de servidores y los servidores de mediación independientes en uno o más grupos independientes.
  
Si implementó gateways PSTN, PBX IP o controladores de borde de sesión (SBCs) que carecen de la capacidad de interactuar con un grupo de servidores de mediación, necesitan estar asociado con un grupo independiente que consta de un único servidor de mediación. Estas son algunas de las acciones que es necesario realizar con las puertas de enlace RTC, IP-PBX o SBC:
  
- Realizar la capa de red, sistema de nombres de dominio (DNS) equilibrio de carga en los servidores de mediación en un grupo (o lo contrario enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo).
    
- Aceptar el tráfico desde cualquier servidor de mediación en una agrupación.
    
Puede utilizar el servidor de Microsoft Lync 2013, herramienta de planeación para evaluar si la colocación del servidor de mediación con el grupo de servidores Front-End puede manejar la carga. Si su entorno no cumple estos requisitos, deberá implementar un conjunto de servidor de mediación de independiente.
  
## <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

 Servidores de mediación en el sitio central sirve para dirigir las llamadas de IP-PBX o puertas de enlace PSTN en sitios de sucursal. Sin embargo, si implementa los troncos SIP, tiene que implementar un servidor de mediación en el sitio donde termina cada tronco. Tener un servidor de mediación en el sitio central ruta llama de una PBX IP o puerta de enlace PSTN en un sitio de sucursal no requiere el uso de medios de derivación, pero se recomienda una omisión de medios. Pero, si puede habilitar la omisión de medios, se reducirá la latencia de la ruta de acceso a medios y, por lo tanto, mejorará la calidad de los medios, ya que la ruta de acceso a medios ya no será necesaria para seguir la ruta de acceso de señalización. La omisión de medios también reducirá la carga de procesamiento del grupo.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, sistemas IP-PBX y SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con asociados certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Omisión de medios es compatible sólo con los productos y versiones que se enumeran en Unified Communications interoperabilidad programa abierto - Lync Server en [Explorar probado dispositivos, infraestructura y herramientas que admitan y amplíen su Skype para la experiencia del negocio](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si se requiere la resistencia del sitio de sucursal, se debe implementar un dispositivo de sucursal que sobreviven o la combinación de un servidor Front-End, un servidor de mediación y una puerta de enlace en el sitio de la sucursal. (La suposición con resiliencia del sitio de sucursal es que presencia y conferencias no son flexibles en el sitio). Para obtener consejos sobre la planificación para la voz el sitio de sucursal, consulte nuestra documentación de [diseño para el sitio de la sucursal resistencia de voz](https://technet.microsoft.com/en-us/library/gg398477%28v=ocs.15%29.aspx) , como debería ser relevante para Skype para Business Server 2015.
  
Para las interacciones con un IP-PBX, si el IP-PBX no admite correctamente temprano media interacciones con varios diálogos tempranas y RFC 3960 interacciones, puede haber algunas palabras del saludo para llamadas entrantes de la IP-PBX a Lync extremos de recorte de la primera. Este comportamiento puede ser más grave si un servidor de mediación en un sitio central es enrutar las llamadas de un IP-PBX donde finaliza la ruta en un sitio de sucursal, ya que se necesita más tiempo para señalización completar. Si experimenta este comportamiento, la implementación de un servidor de mediación en el sitio de la sucursal es la única forma de reducir el recorte de la primera pocas palabras.
  
Por último, si el sitio central tiene una PBX TDM o el IP-PBX no elimina la necesidad de una puerta de enlace PSTN, debe implementar una puerta de enlace en la ruta de llamada de conexión de servidor de mediación y la PBX.
  
> [!NOTE]
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte "[Mejoras escala en lado de recepción en Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Para obtener más detalles sobre cómo habilitar RSS, mira la documentación de tu adaptador de red. 
  

