---
title: Calidad de medios y rendimiento de conectividad de la red
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: En este tema se define el conjunto de requisitos de rendimiento de red para los servicios de Skype Empresarial Online y cómo puede elegir usar Internet o ExpressRoute para la conectividad entre su red y Skype Empresarial Online en función de la evaluación de la conectividad de la red. Si ha decidido implementar Azure ExpressRoute para conectividad dedicada a Microsoft 365 u Office 365, este documento también proporciona instrucciones sobre cómo planear las conexiones ExpressRoute en diferentes escenarios de implementación de Skype Empresarial Online.
ms.openlocfilehash: d49dd3e925c71a9e0f2b73bbe364ad4478566cad
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164769"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online

En este tema se define el conjunto de requisitos de rendimiento de red para los servicios de Skype Empresarial Online y cómo puede elegir usar Internet o ExpressRoute para la conectividad entre su red y Skype Empresarial Online en función de la evaluación de la conectividad de la red. Si ha decidido implementar Azure ExpressRoute para conectividad dedicada a Microsoft 365 u Office 365, este documento también proporciona instrucciones sobre cómo planear las conexiones ExpressRoute en diferentes escenarios de implementación de Skype Empresarial Online.
  
La calidad de Real-Time multimedia (audio, vídeo y uso compartido de aplicaciones) sobre IP se encuentra muy afectada por la calidad de la conectividad de red de un extremo a otro. Para obtener una calidad de medios óptima en Skype Empresarial Online, es importante que se asegura de que hay una conexión de alta calidad entre la red de su compañía y Skype Empresarial Online. La mejor forma de lograrlo es configurar su red interna y su conectividad a la nube en función de la capacidad de su red para dar cabida al pico de volumen de tráfico de Skype Empresarial Online en todas las conexiones.
  
Azure ExpressRoute no es un requisito para los servicios de Microsoft 365 y Office 365, incluido Skype Empresarial Online. Sin embargo, Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudarán a garantizar que la conectividad con Microsoft 365 u Office 365 cumple los requisitos de rendimiento de red de Skype Empresarial y garantiza una experiencia de calidad de medios óptima para Skype Empresarial Online.
  
> [!TIP]
> Aunque en este tema se proporciona orientación general sobre el rendimiento de las redes, hay directrices completas para la evaluación de la red fuera del ámbito de este documento. Para encontrar una lista de asociados de Skype Empresarial Online que pueden ayudarle con las medidas de rendimiento de red como parte de una evaluación de red exhaustiva y completa, visite Soluciones de socios de [Skype Empresarial.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividad de red para Skype Empresarial Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factores que afectan a la calidad de medios de Skype Empresarial Online

Hay muchos factores diferentes que contribuyen a la calidad de los medios Real-Time (audio, vídeo y uso compartido de aplicaciones) de Skype Empresarial Online, que incluyen los dispositivos usados, el entorno y la conectividad de red. 
  
#### <a name="devices"></a>Dispositivos

En una sesión Real-Time multimedia, los dispositivos de captura y representación de medios que usan todos los participantes, como los auriculares y cámaras web, afectan de forma importante a la calidad global del audio y el vídeo. Los dispositivos de audio y vídeo de menor calidad o que utilizan controladores incorrectos generan, respectivamente, sonido e imágenes de calidad reducida. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Aunque no son necesarios dispositivos de medios de audio y vídeo certificados, es muy recomendable que los certificados para Skype Empresarial para obtener una experiencia de medios óptima. Para obtener una lista de todos los dispositivos certificados para Skype Empresarial, consulte Teléfonos y [dispositivos para Skype Empresarial.](https://technet.microsoft.com/office/dn947482) Puede usar el panel de calidad de llamadas de Skype Empresarial [Online,](/microsoftteams/turning-on-and-using-call-quality-dashboard)que se encuentra en el Centro de administración de **Skype** Empresarial, para comprobar que los dispositivos en uso funcionan correctamente y supervisar la calidad de los medios de audio y vídeo.
  
> [!TIP]
> **Se requiere un dispositivo certificado para obtener una experiencia de calidad de** medios óptima en Skype Empresarial.
  
Es importante recordar que todos los dispositivos multimedia, los clientes de Skype Empresarial y Skype Empresarial Server a través de los cuales se Real-Time de medios en tiempo completo introducen cierta cantidad de latencia. La latencia de procesamiento del software y el dispositivo, junto con la de la red, afectan muy negativamente y contribuyen a la latencia global de un extremo a otro y a la experiencia del usuario final.
  
#### <a name="environment"></a>Entorno

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen más clara de la experiencia de audio y vídeo de un usuario, use las herramientas de la aplicación De Skype Empresarial, Opciones de dispositivo de audio o Dispositivo de vídeo, para realizar cambios en el dispositivo en uso y personalizar  >    >   su configuración. 

#### <a name="network"></a>Red

La calidad de Real-Time multimedia sobre IP se encuentra muy afectada por la calidad de la conectividad de la red, pero especialmente por la cantidad de:
  
- **Latencia** Este es el tiempo que se tarda en obtener un paquete IP desde el punto A al punto B en la red. Este retraso en la propagación de red básicamente está vinculado a la distancia física entre los dos puntos y a la velocidad de luz, incluidas las sobrecargas adicionales tomadas por los diversos enrutadores entre ellos. La latencia se mide como tiempo de ida y vuelta (RTT).
    
- **Pérdida de paquetes** Esto se suele definir como un porcentaje de paquetes que se pierden en un determinado período de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio: desde pérdidas pequeñas e individuales de paquetes que apenas afecten al audio, hasta pérdidas de ráfagas completas que causen cortes completos de audio.
    
- **Vibración entre llegada de paquetes o, simplemente, vibración** Este es el cambio medio en el retraso entre paquetes sucesivos. La mayoría de software voIP moderno, incluido Skype Empresarial, se puede adaptar a algunos niveles de vibración a través del almacenamiento en búfer. Solo cuando la vibración supera el almacenamiento en búfer, los participantes notan los efectos de la vibración.
    
> [!NOTE]
>  El almacenamiento en búfer para vibración aumentará la latencia de un extremo a otro.
  
Con muchas sesiones simultáneas de medios Real-Time de Skype Empresarial Online, así como otro tráfico de red generado por otros servicios de Microsoft 365 u Office 365 y otras aplicaciones empresariales, es fundamental asegurarse de que hay suficiente ancho de banda en toda la ruta de red que conecta su red con el servicio Skype Empresarial Online para evitar la congestión de la red y garantizar una excelente calidad de medios Real-Time medios (audio, vídeo y uso compartido de aplicaciones). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementación de Calidad de servicio (QoS) en redes congestionadas

Además, la congestión del tráfico en la red afecta muy negativamente a la calidad de medios. Para permitir que los paquetes de audio y vídeo viajen por la red de forma más rápida y se prioricen sobre otro tráfico de red en una red congestionada, se puede usar Calidad de servicio (QoS) para proporcionar una experiencia óptima al usuario final en comunicaciones de audio y vídeo.
  
QoS le permite asignar prioridades más altas a los paquetes de red que contienen datos de audio o vídeo. Al asignar una mayor prioridad a estos paquetes, es probable que las comunicaciones de audio y vídeo viajen por la red de forma más rápida y con menos interrupciones que las sesiones de red que implican transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que los paquetes de red usados para transferencias de archivos o copias de seguridad de bases de datos tienen asignados de forma predeterminada la prioridad "mejor esfuerzo" y la congestión de red tendrá un impacto tan grande. Si no asigna una mayor prioridad a los paquetes de medios (audio, vídeo y uso compartido de aplicaciones) y los deja asignados como "mejor esfuerzo", también se procesarán junto con el resto del tráfico de red. Dependiendo de la cantidad de congestión de la red, esto potencialmente terminará en una experiencia de calidad de audio y vídeo general menor para los usuarios.
  
Se recomienda encarecidamente que implemente QoS en su red para asegurarse de que la congestión de la red no tenga un impacto significativo. Sin embargo, para que esto tenga el máximo impacto, todos los puntos de conexión de red deben admitir QoS, lo que significa que todos los puntos de conexión deben respetar el marcado de QoS y la priorización de paquetes. Los servicios de Skype Empresarial Online respetan el marcado de QoS y la priorización dentro de la red de Microsoft. Sin embargo, el tráfico enrutado a través de una conexión pública (como Internet desde la red de su compañía a la red de Microsoft) no conserva el marcado de QoS ni la priorización de paquetes. Las conexiones privadas de su red a Microsoft 365 u Office 365 que usan [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) ofrecen una solución de implementación que conserva el marcado de QoS y la priorización de paquetes, lo que, a su vez, aumentará la calidad global de audio y vídeo para los usuarios finales.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de rendimiento de red para conectarse a Skype Empresarial Online
<a name="bkNetworkPerf"> </a>

Los medios de Real-Time de Skype Empresarial viajan a través de muchos dispositivos, aplicaciones cliente, software de servidor y redes diferentes. La latencia de un extremo a otro de un Real-Time multimedia es la cantidad total de latencia introducida en todos los componentes y segmentos de red. La calidad de la conexión de red de un extremo a otro está determinada por el segmento de red con la peor calidad. Este segmento actúa como un cuello de botella para este tráfico de red.
  
El siguiente diagrama ilustra un flujo de audio uní respecto a una conferencia entre dos participantes de Skype Empresarial.
  
![Flujo de llamadas de ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
En este escenario de conferencia, la ruta de medios comprende los siguientes segmentos de red:
  
1. **Conexión del usuario 1 al perímetro de la red de Microsoft** Normalmente, esto incluye una conexión de red como WiFi o Ethernet, la conexión WAN del Usuario 1 al punto de salida de Internet (el dispositivo del perímetro de su red) y la conexión a Internet desde el perímetro de su red al perímetro de la red de Microsoft.
    
2. **Conexión dentro de la red de Microsoft** Esto se hace entre el perímetro de Microsoft y el centro de datos de Skype Empresarial Online, donde se usan los servidores de conferencia A/V.
    
3. **Conexión dentro de la red de Microsoft** Esto se encuentra entre el centro de datos de Skype Empresarial Online y el perímetro de la red de Microsoft.
    
4. **Conexión del perímetro de la red de Microsoft al usuario 2** Esto incluye la conexión a Internet desde el perímetro de su red al perímetro de la red de Microsoft, la conexión WAN del usuario 2 al punto de salida de Internet (el perímetro de su red) y la conexión de red como WiFi o Ethernet.
    
El siguiente diagrama muestra un desglose de los componentes y segmentos de red de una llamada RTC de Skype Empresarial Online:
  
![Flujo de llamadas del operador RTC de ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
En un escenario de llamada RTC, la ruta multimedia cruza los siguientes segmentos de red:
  
1. **Conexión de un llamador de un cliente de Skype Empresarial al perímetro de la red de Microsoft** Normalmente, esto incluye una conexión de red como WiFi o Ethernet, la conexión WAN del cliente de Skype Empresarial al punto de salida de Internet (el dispositivo del perímetro de su red) y la conexión a Internet desde el perímetro de su red al perímetro de la red de Microsoft.
    
2. **Conexión dentro de la red de Microsoft** Esto se hace entre el perímetro de Microsoft y el centro de datos de Skype Empresarial Online, donde se usa un servidor de mediación.
    
3. **Conexión dentro de la red de Microsoft** Esto se encuentra entre el centro de datos de Skype Empresarial Online y el perímetro de la red de Microsoft.
    
4. **Conexión entre la red de Microsoft y los socios proveedores de servicios RTC** Esta es la conexión que existe para realizar una llamada RTC desde el cliente de Skype Empresarial que está fuera de la red de Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de Microsoft
<a name="bkSfBClienttoEdge"></a>

Para obtener una calidad de medios de Skype Empresarial óptima, se necesitan los siguientes objetivos o umbrales de métricas de rendimiento de red para una conexión desde la red de su empresa al perímetro de la red de Microsoft. Este segmento de la red incluye su red interna, todas las conexiones WiFi y Ethernet, cualquier tráfico de sitio a sitio de la compañía a través de una conexión WAN, por ejemplo Multiprotocol Label Switching (MPLS), así como las conexiones de Internet o ExpressRoute de asociados al perímetro de la red de Microsoft.
  
> [!CAUTION]
> **La conectividad entre un cliente de Skype Empresarial en la red de su compañía y los servicios de Microsoft 365 u Office 365 debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Target** <br/> |
|Latencia (solo ida)  <br/> |< 50 ms  <br/> |
|Latencia (RTT o tiempo de ida y vuelta)  <br/> |< 100 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |<10 % durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<1 % durante cualquier intervalo de 15 s  <br/> |
|Vibración entre llegada de paquetes  <br/> |<30 ms durante cualquier intervalo de 15 s  <br/> |
|Reordenación de paquetes  <br/> |<paquetes fuera de pedidos del 0,05 %  <br/> |
   
 **Otros requisitos de destino de rendimiento:**
  
- La red de Microsoft tiene más de 160 ubicaciones de perímetro en todo el mundo. Trabajamos con los principales proveedores de acceso a Internet (ISP) en todo el mundo mediante estos sitios perimetrales. El objetivo de la métrica de latencia asume que el sitio o sitios de su compañía y los bordes de Microsoft están en el mismo continente.
    
- El sitio o los sitios de su empresa a la conexión perimetral de la red de Microsoft incluyen el acceso de red del primer salto, que puede ser WiFi u otra tecnología inalámbrica. 
    
- El objetivo de rendimiento de la red asume que se debe planificar correctamente el ancho de banda o la calidad del servicio. En otras palabras, esto se aplica directamente al tráfico de medios Real-Time Skype Empresarial cuando la conexión de red tiene un pico de carga.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de rendimiento de red desde el perímetro de su red al perímetro de la red de Microsoft
<a name="bkYourNetworkEdge"> </a>

Estos son los objetivos o umbrales de rendimiento de red necesarios para la conexión entre el perímetro de su red y el perímetro de la red de Microsoft. Este segmento de la red excluye la red interna del cliente o la WAN, y está pensado como guía para probar el tráfico de red que se envía a través de Internet o a través de una red asociada ExpressRoute y también se puede usar para mejorar un acuerdo de nivel de servicio (SLA) con su proveedor de ExpressRoute.
  
> [!CAUTION]
> **La conectividad entre el perímetro de la red de su compañía y el perímetro de la red de Microsoft debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Target** <br/> |
|Latencia (solo ida)  <br/> |< 30 ms  <br/> |
|Latencia (RTT)  <br/> |< 60 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |<1 % durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<0,1 % durante cualquier intervalo de 15 s  <br/> |
|Vibración entre llegada de paquetes  <br/> |<15 ms durante cualquier intervalo de 15 s  <br/> |
|Reordenación de paquetes  <br/> |<paquetes fuera de orden del 0,01 %  <br/> |
   
 **Otros requisitos de destino de rendimiento:**
  
- El objetivo de rendimiento requiere que la conexión entre cualquiera de los perímetros de la red de su empresa y el perímetro de la red de Microsoft más cercano esté en el mismo continente.
    
- El objetivo de rendimiento de la red asume que se debe planificar correctamente el ancho de banda o la calidad del servicio. Esto también se aplica al tráfico de medios Real-Time skype empresarial cuando la conexión de red tiene un pico de carga. Para un ancho de banda y una planificación de QoS adecuados, consulte [ExpressRoute y QoS en Skype Empresarial Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Medición del rendimiento de la red
<a name="bkNetworkPerf"> </a>

Para medir el rendimiento real de la red, especialmente para la latencia y la pérdida de paquetes, desde cualquier sitio de red de la compañía hasta un perímetro de red, puede usar herramientas como ping, probar con un conjunto de servicios de retransmisión multimedia de Skype Empresarial que se ejecutan desde Microsoft Edge y sitios del centro de datos. 

>[!NOTE]
> Medir el rendimiento de la red mediante el ping (ICMP) no es eficaz. Por este motivo, la siguiente pantalla IP anycast dejará de responder a solicitudes ICMP a partir de enero de 2020. Para medir el rendimiento de la red de forma eficaz, Microsoft recomienda [la herramienta Desesmentación de red.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Para probar las conexiones de Internet a la red de Microsoft, se recomienda que pruebe con las siguientes VIP de los relés multimedia de Skype Empresarial. La *VIP Anycast resuelve*  a una dirección IP de un relé multimedia en el sitio perimetral de Microsoft más cercano a la ubicación donde se realizarán las pruebas.
  
||||
|:-----|:-----|:-----|
|**Dirección IP** <br/> |**Tipo** <br/> |**Ubicación** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **A continuación se incluyen algunas recomendaciones de alto nivel para evaluar el rendimiento de la red:**
  
- Debe evaluar la red interna, así como las conexiones a Microsoft 365 u Office 365.
    
- Debería evaluar y recopilar datos de todas sus redes durante un largo período de tiempo. Le recomendamos que realice pruebas de rendimiento de red durante un mínimo de una semana para poder ver los patrones de uso de todos los días y horas laborables. Esto le mostrará las horas punta.
    
- Debería tomar varias muestras de mediciones de rendimiento de red. Se recomienda realizar una medición en un sitio de la compañía cada 10 minutos durante todo el período de tiempo durante el que re recopila datos. Para comparar los requisitos de rendimiento de red de Skype Empresarial Online, tome el valor 90º percentil de este conjunto de datos de muestra. 
    
- Debe evaluar continuamente el rendimiento de la red. El uso de la red varía a lo largo del tiempo debido a los cambios en los patrones de uso, las nuevas aplicaciones basadas en la empresa que usan una gran cantidad de ancho de banda y los cambios en las ubicaciones de la organización o la empresa física. Es importante que supervise continuamente el rendimiento de su red frente a estos requisitos y objetivos/umbrales de rendimiento de red y realice los ajustes a tiempo para garantizar la mejor Real-Time de medios. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medición del rendimiento de red con máquinas virtuales de Azure
<a name="bkNetworkPerf"> </a>

Instead of testing against the Microsoft network Edge sites, there are network assessment solutions from Skype for Business customers and partners that leverage testing setup for services in the Microsoft Azure cloud. En esas soluciones, las herramientas de evaluación de red prueban la latencia, la pérdida de paquetes y la vibración con los puntos de conexión personalizados configurados como servicio en la nube de Azure. Como resultado, el tráfico de red de prueba viaja a través de un segmento de red adicional, que es la conexión dentro de la red de Microsoft entre los bordes de la red y los centros de datos de Azure que hospedan el servicio de evaluación de red.
  
For those network assessment solutions based on Azure hosted testing services. Se recomienda realizar la evaluación de la red dentro del país o la región. For example, for customer sites in east U.S., the assessment should be performed against a testing service instance hosted in Azure's east US data center region. 
  
A continuación se muestran los destinos de latencia (RTT) para la configuración de evaluación de red basada en el servicio de Azure. Los destinos de latencia un solo sentido serán la mitad de los destinos correspondientes a RTT. Los objetivos de pérdida de paquetes y vibración permanecen iguales a los definidos para las pruebas basadas en Skype Media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Región del cliente** <br/> |**Región de Azure** <br/> |**Your network Edge - Azure Round-trip Time (RTT)** <br/> |**Su sitio: Tiempo de ida y vuelta de Azure (RTT)** <br/> |
|Central US  <br/> |Central US  <br/> |99  <br/> |139  <br/> |
|East US  <br/> |East US  <br/> |86  <br/> |126  <br/> |
|North Central US  <br/> |North Central US  <br/> |97  <br/> |137  <br/> |
|South Central US  <br/> |South Central US  <br/> |94  <br/> |134  <br/> |
|West US  <br/> |West US  <br/> |94  <br/> |134  <br/> |
|Hawaii US  <br/> |West US  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Canada East  <br/> |Canada East  <br/> |131  <br/> |171  <br/> |
|North Europe  <br/> |North Europe  <br/> |99  <br/> |139  <br/> |
|West Europe  <br/> |West Europe  <br/> |95  <br/> |135  <br/> |
|Asia Oriental  <br/> |Asia Oriental  <br/> |118  <br/> |158  <br/> |
|Southeast Asia  <br/> |Southeast Asia  <br/> |97  <br/> |137  <br/> |
|Japan East  <br/> |Japan East  <br/> |111  <br/> |151  <br/> |
|Japan West  <br/> |Japan West  <br/> |118  <br/> |158  <br/> |
|Brazil South  <br/> |Brazil South  <br/> |70  <br/> |110  <br/> |
|Australia East  <br/> |Australia East  <br/> |124  <br/> |164  <br/> |
|Australia Southeast  <br/> |Australia Southeast  <br/> |124  <br/> |164  <br/> |
|Central India  <br/> |Central India  <br/> |103  <br/> |143  <br/> |
|South India  <br/> |South India  <br/> |103  <br/> |143  <br/> |
|West India  <br/> |West India  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |120  <br/> |160  <br/> |
|China North  <br/> |China North  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Calidad de medios y ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute para Microsoft 365 u Office 365 es una conexión de red dedicada para conectarse a Microsoft 365 u Office 365. Ofrece a los clientes la posibilidad de tener control sobre la ruta que lleva el tráfico de red. Ya no tienen que preocuparse por el enrutamiento impredecible que se produce en Internet cuando se realizan datos por operadores, proveedores e ISP desconocidos. El tráfico de red que se envía a través de ExpressRoute se envía directamente a través de la red asociada ExpressRoute a la red de Microsoft. Esto permite a los clientes tratar Microsoft 365 u Office 365 como si se encontraran en su propio centro de datos fuera del sitio con una conexión dedicada.
  
Azure ExpressRoute está disponible para todas las ofertas de licencias de Microsoft 365 y Office 365. Sin embargo, el complemento Premium de Azure ExpressRoute es necesario para que Microsoft 365 y Office 365 habiliten el enrutamiento global. Los clientes con al menos 500 puestos que implementen ExpressRoute pueden obtener el complemento premium de *ExpressRoute* sin coste adicional.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>¿Se requiere ExpressRoute para obtener una buena calidad de medios?

Azure ExpressRoute no es un requisito para obtener la mejor calidad de medios de Skype Empresarial Online. Sin embargo, es una de las opciones de implementación que le ayudan a garantizar que su conectividad a la nube cumple los objetivos o umbrales de rendimiento de red de Skype Empresarial.
  
Microsoft 365 y Office 365 son servicios de alto rendimiento y seguridad que usan Internet. Seguimos invirtiendo en nuevas capacidades de seguridad y en nuevos nodos perimetrales regionales para mejorar continuamente la seguridad y el rendimiento. Azure ExpressRoute no es un requisito para los servicios de Microsoft 365 u Office 365, incluido Skype Empresarial Online. Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudarán a garantizar que la conectividad con Microsoft 365 u Office 365 cumple los requisitos de rendimiento de red de Skype Empresarial y garantiza una experiencia de calidad de medios óptima para Skype Empresarial Online.
  
Para la calidad de medios de Skype Empresarial Online, es importante que la conexión entre los sitios de su compañía y los perímetros de la red de Microsoft cumpla los objetivos de rendimiento de los requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de [Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) y que la conexión entre los perímetros de su red y los perímetros de la red de Microsoft cumpla los objetivos de rendimiento de los requisitos de rendimiento de red desde el perímetro de su red al perímetro de la red de [Microsoft.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
También es importante que la conectividad de la red física de su compañía (incluida la capacidad de conectividad a la nube y a su red interna) se ajuste al pico de volumen del tráfico de medios. Azure ExpressRoute es una de las muchas formas que ayudan a los clientes a garantizar que su conectividad a la nube de Skype Empresarial Online cumple todos estos requisitos de rendimiento.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>¿Se requiere ExpressRoute para obtener un SLA de calidad de voz?

No, no se requiere ExpressRoute para obtener un SLA de calidad de voz de Skype Empresarial Online. El SLA de calidad de voz de Skype Empresarial [Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) se aplica a cualquier llamada válida realizada por cualquier usuario del servicio de voz de Skype Empresarial Online dentro de la licencia y la suscripción correctas que permite al usuario realizar cualquier tipo de llamada VoIP o RTC. Un SLA de calidad de voz debe incluir que se abordan todas las siguientes condiciones:
  
- Llamadas de teléfonos IP certificados por Microsoft.
    
- Conexiones Cableadas por Ethernet.
    
- Problemas de calidad de voz debidos a problemas de red de Microsoft.
    
> [!NOTE]
> El SLA de calidad de voz excluye las llamadas en las que la baja calidad de llamada se debe a problemas en redes que no son de Microsoft, incluidos los socios de ExpressRoute y otras redes. 
  
### <a name="internet-or-azure-expressroute"></a>¿Internet o Azure ExpressRoute?

Antes de tomar una decisión sobre las opciones de conectividad de red a Skype Empresarial Online, los clientes deben evaluar su red y su actual conectividad a Internet en función de los requisitos de rendimiento descritos en los requisitos de rendimiento de red para conectarse a [Skype Empresarial Online.](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
Si la conexión a Internet actual ofrece un rendimiento de red suficiente durante la hora punta y cumple los requisitos de rendimiento de red desde los sitios a los bordes de la red de Microsoft, y desde los bordes de la red a los bordes de la red de Microsoft, puede seguir usando la conectividad a Internet existente para conectarse a Skype Empresarial Online.
  
Para los sitios de la compañía en los que no se cumplen los requisitos de rendimiento de red, le recomendamos encarecidamente que primero trabaje con sus proveedores de servicios de red para mejorar el rendimiento general de la red. Sin embargo, si aún no se cumplen, azure ExpressRoute puede ayudar a garantizar que la conectividad a la nube de Skype Empresarial Online puede ayudarle a cumplir los requisitos de rendimiento de red.
  
Azure ExpressRoute ofrece las siguientes ventajas adicionales:
  
- Un acuerdo de nivel de servicio (SLA) sobre la disponibilidad de la conexión entre su red y la red de Microsoft. ExpressRoute tiene un SLA de disponibilidad garantizada de 99,9 %.
    
- Ancho de banda planificado y garantizado necesario para los servicios de Microsoft 365 y Office 365. Para ello, envíe solo tráfico de Microsoft 365, Office 365 o Skype Empresarial mediante ExpressRoute y, después, haga que el resto de tráfico de Internet se desvíe por otros puntos de entrada o salida de la red.
    
- ExpressRoute está diseñado para conservar el marcado de QoS de DSCP entre su red y la red de Microsoft.
    
Para obtener más información sobre la QoS de ExpressRoute y la planificación de capacidad, consulte [ExpressRoute y QoS en Skype Empresarial Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>¿Puedo configurar Azure ExpressRoute solo para Skype Empresarial Online?

Sí, puede configurar Azure ExpressRoute para garantizar una conectividad de red excelente desde la red de su compañía solo a Skype Empresarial Online. Esto le proporcionará la mejor calidad de medios Real-Time para sus usuarios, pero puede seguir conectando a otros servicios de Microsoft 365 u Office 365 a través de Internet.
  
El Border Gateway Protocol (BGP) es un protocolo de enrutamiento en Internet que se usa para enrutar el tráfico de red a través de Internet. It is designed to exchange routing information between autonomous systems (AS) found across the Internet. Los valores de las comunidades BGP son etiquetas de atributo que se pueden aplicar a las rutas entrantes y salientes. BGP communities are often used to signal to the receiving AS which outbound link to use to reach a given destination based on geography, service type or other criteria.
  
With BGP communities support, Microsoft will tag prefixes and routes with appropriate BGP community values based on the service they belong to. Microsoft etiqueta los prefijos anunciados mediante emparejamiento público y emparejamiento de Microsoft con los valores de comunidad BGP adecuados que indican la región en la que se hospedan los prefijos. Puede confiar en los valores de comunidad para tomar decisiones de enrutamiento adecuadas y ofrecer un enrutamiento óptimo. Puede usar el valor de comunidad de Skype Empresarial Online para configurar una conexión ExpressRoute solo para Skype Empresarial Online. Encontrará más información en los requisitos [de enrutamiento de ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Escenarios de conectividad de ExpressRoute para Skype Empresarial Online
<a name="bkNetworkPerf"> </a>

Si ha decidido que ExpressRoute basándose en las recomendaciones anteriores es para usted, estas son las recomendaciones sobre dónde y cuántas conexiones de ExpressRoute debería obtener.
  
### <a name="online-only-deployment---single-site"></a>Implementación solo en línea: un solo sitio

Si todos los usuarios usan el servicio Skype Empresarial Online, sus oficinas están centradas alrededor de una única ubicación física y decide implementar Azure ExpressRoute, debe configurar una sola conexión ExpressRoute entre el sitio de su compañía y la ubicación de emparejamiento [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)más cercana.
  
En el siguiente gráfico se muestra un ejemplo de este tipo de implementación. En este ejemplo, Contoso es una universidad ubicada en Orlando, Florida. Contoso tiene 10 000 profesores y estudiantes. Las pruebas de Internet desde su ubicación hasta los sitios del perímetro de Microsoft mostraban una pérdida de paquetes superior al 5 % durante horas punta de clase. Han decidido obtener una conexión dedicada a Microsoft 365 u Office 365 mediante ExpressRoute con ancho de banda sobreaprovisionamiento para evitar la congestión de la red para Microsoft 365 u Office 365, especialmente para el tráfico de Real-Time de Skype Empresarial Online. Se conectan a la nube de Microsoft a través de ExpressRoute en el sitio de emparejamiento de Atlanta, Georgia.
  
![Un solo sitio de ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implementación solo en línea: varios sitios en el mismo continente

Si su compañía usa los servicios de Skype Empresarial Online de varias oficinas en la misma región o continente y decide implementar Azure ExpressRoute, se recomienda conectar su sitio principal a través de ExpressRoute y, después, agregar emparejamientos ExpressRoute adicionales para otras ubicaciones que no cumplan los objetivos de rendimiento de red recomendados.
  
En el siguiente ejemplo, Contoso es una compañía de servicios de viajes de EE. UU. con sede en Nueva York y otras oficinas rebanadas por el país. Sus oficinas están conectadas a través de una WAN que usa MPLS para conectarse a Microsoft 365 u Office 365. Inicialmente, configurarán una conexión ExpressRoute desde su enrutador de Internet en Hoboken, Nueva Jersey al sitio de emparejamiento de Nueva York. 
  
Con esta configuración, el tráfico de red desde la mayoría de sus sitios a la red de Microsoft (sitio perimetral de Nueva York) cumple los objetivos de rendimiento de red de la conexión del cliente de Skype Empresarial descritos en los requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de [Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Sin embargo, la latencia entre las oficinas de la Costa Oeste de Contoso a Nueva York es de más de 50 ms de solo ida. Además, honolulu es la segunda oficina más grande de Contoso, la latencia desde Honolulu a Nueva York supera los 80 ms de solo ida. Para garantizar una buena calidad de medios a los usuarios en esas oficinas, Contoso ha decidido agregar una conexión ExpressRoute en la Costa Oeste entre su sitio de San José y el sitio de emparejamiento ExpressRoute de Silicon Valley.
  
![Varios sitios Express Router en el mismo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implementación solo en línea: varios sitios en distintos continentes

Si todos los usuarios usan el servicio Skype Empresarial Online y sus oficinas están en varias ubicaciones físicas en varios continentes, si decide implementar Azure ExpressRoute, debe configurar al menos una conexión ExpressRoute para cada continente entre el sitio principal de cada continente y su ubicación de emparejamiento [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)más cercana. En función de la comparación entre coste y beneficio, puede optar por implementar conexiones adicionales de ExpressRoute desde los sitios donde no se cumplen los objetivos de rendimiento de red.
  
En el siguiente ejemplo, Contoso es una gran corporación legal con oficinas en las principales ciudades de América del Norte y Europa. Tras realizar la evaluación del rendimiento de la conexión a Internet y la red interna, Contoso decidió implementar dos conexiones ExpressRoute en América del Norte y un solo circuito ExpressRoute para todas las oficinas europeas.
  
![ExpressRoute con varios sitios y continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implementación híbrida

Si dispone de una implementación local de Lync o Skype Empresarial Online y elige implementar una integración híbrida de Skype Empresarial Online, le recomendamos que, si decide implementar Azure ExpressRoute, tenga al menos una conexión ExpressRoute para cada sitio local de Lync o Skype Empresarial Online y al menos una conexión ExpressRoute para cada continente con oficinas. En función de la comparación entre coste y beneficio, para cada continente puede optar por implementar conexiones adicionales de ExpressRoute desde oficinas donde no se cumplen los objetivos de rendimiento de red.
  
Si tiene una implementación local de Skype Empresarial, debe seguir la Guía de planeación e implementación del servidor [perimetral.](https://technet.microsoft.com/library/mt346417.aspx) En concreto, los servidores perimetrales deben ser accesibles desde fuera de la red. Normalmente, esto se consigue asignando una dirección IP pública enrutable al servidor perimetral o mediante la traducción de direcciones de red (NAT).
  
En el ejemplo siguiente, Contoso tiene una implementación local de Skype Telefonía IP empresarial Empresa. Desean migrar usuarios locales a servicios en línea de Microsoft 365 u Office 365. También han decidido usar una implementación híbrida para que puedan seguir usando su infraestructura RTC existente para todos los usuarios locales y en línea. El centro de datos local de Contoso y los servidores perimetrales de Skype Empresarial están en Chicago. Para su implementación, Contoso decidió configurar una conexión ExpressRoute entre su centro de datos de Chicago y Chicago ExpressRoute. También agregaron una conexión ExpressRoute para la Costa Oeste para mejorar el servicio de su oficina de Honolulu.
  
![ExpressRoute híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implementación en línea con Cloud Connector Edition

Skype Empresarial Online Cloud Connector Edition es una oferta híbrida compuesta por un conjunto de máquinas virtuales (VM) empaquetadas que implementan la conectividad con RTC local. Mediante la implementación de una topología mínima de Skype Empresarial Server en un entorno virtualizado, podrá enviar y recibir llamadas con teléfonos fijos y móviles a través de la infraestructura de voz RTC local existente.
  
Si decide implementar Azure ExpressRoute y Cloud Connector Edition, le recomendamos que configure al menos una conexión ExpressRoute por cada continente, entre el sitio principal de cada continente y su ubicación de emparejamiento [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)más cercana. En función de la comparación entre coste y beneficio, para cada continente puede optar por implementar otras conexiones ExpressRoute desde sitios donde no se cumplen los objetivos de rendimiento de red.
  
Si dispone de una implementación local de Skype Empresarial, debe seguir la Guía de planificación de Skype Empresarial [Cloud Connector Edition.](https://technet.microsoft.com/library/mt605227.aspx) Específicamente, los servicios perimetrales de acceso y A/V deben tener asignadas direcciones IP públicas y centros de datos de Microsoft 365 u Office 365 accesibles.
  
En el siguiente ejemplo, Contoso es una firma de contabilidad europea con presencia en algunos de los principales países y ciudades de Europa. Cuando se suscribieron a Skype Empresarial Online para todas sus necesidades de colaboración, decidieron colocar un conector de nube para cada país o región donde tengan una ubicación física para seguir usando su infraestructura RTC y los contratos de operadores que ya existen. Basándose en las pruebas que realizaron desde todos sus sitios y el perímetro de la red de Microsoft, determinaron que una única conexión ExpressRoute en Londres ayudará a cumplir los objetivos de rendimiento de red de la conexión del cliente de Skype Empresarial descritos en los requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de [Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![Un conector de nube ExpressRoute.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A continuación se muestra otra opción de implementación de Contoso. En este caso, decidieron configurar una conexión ExpressRoute en cada sitio donde se implemente un conector de nube. 
  
![Dos conectores de nube ExpressRoute.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
