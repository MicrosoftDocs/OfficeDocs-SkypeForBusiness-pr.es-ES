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
description: Este tema define el conjunto de requisitos de rendimiento de red para los servicios de Skype empresarial online y cómo puede elegir usar Internet o ExpressRoute para la conectividad entre su red y Skype empresarial online según su evaluación de la conectividad de red. Si ha decidido implementar Azure ExpressRoute para conectividad dedicada a Office 365, este documento también proporciona instrucciones sobre cómo planear las conexiones de ExpressRoute en diferentes escenarios de implementación de Skype empresarial online.
ms.openlocfilehash: ed7ad6ebd456122e41ccd74269180ff9c79fa3fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776445"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online

Este tema define el conjunto de requisitos de rendimiento de red para los servicios de Skype empresarial online y cómo puede elegir usar Internet o ExpressRoute para la conectividad entre su red y Skype empresarial online según su evaluación de la conectividad de red. Si ha decidido implementar Azure ExpressRoute para conectividad dedicada a Office 365, este documento también proporciona instrucciones sobre cómo planear las conexiones de ExpressRoute en diferentes escenarios de implementación de Skype empresarial online.
  
La calidad de los medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) en IP se ve muy afectado por la calidad de la conectividad de red completa. Para una calidad multimedia óptima de Skype empresarial online, es importante que se asegure de que hay una conexión de alta calidad entre la red de su empresa y la de Skype empresarial online. La mejor manera de hacerlo es configurar la red interna y la conectividad en la nube en función de la capacidad de su red para dar cabida a un volumen de tráfico máximo para Skype empresarial online en todas las conexiones.
  
Azure ExpressRoute no es un requisito para los servicios de Office 365, incluido Skype empresarial online. Sin embargo, Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudarán a garantizar que la conectividad a Office 365 cumple los requisitos de rendimiento de la red de Skype empresarial y garantiza la mejor experiencia de calidad de medios de Skype empresarial online.
  
> [!TIP]
> Aunque en este tema se proporcionan instrucciones generales sobre el rendimiento de la red, la orientación completa de la evaluación de red está fuera del ámbito de este documento. Para obtener una lista de los socios de Skype empresarial online que pueden ayudarle con las medidas de rendimiento de la red como parte de una evaluación completa y completa de la red, visite [soluciones de socios de Skype empresarial](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividad de red para Skype empresarial online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factores que afectan a la calidad de los medios de Skype empresarial online

Hay muchos factores diferentes que contribuyen a la calidad de los medios en tiempo real de Skype empresarial online (audio, vídeo y uso compartido de aplicaciones), que incluyen los dispositivos que se usan, el entorno y la conectividad de red. 
  
#### <a name="devices"></a>Dispositivos

En una sesión de medios en tiempo real, los dispositivos de captura de contenido multimedia que usan todos los participantes, como los auriculares con micrófono y las cámaras Web, tienen un gran impacto en la calidad de audio y video general. Los dispositivos de audio y vídeo de menor calidad o que utilizan controladores incorrectos generan, respectivamente, sonido e imágenes de calidad reducida. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Aunque los dispositivos de medios de audio y vídeo certificados no son obligatorios, se recomiendan los dispositivos altamente certificados para Skype empresarial para obtener la mejor experiencia multimedia. Para obtener una lista de todos los dispositivos certificados de Skype para empresas, consulte [teléfonos y dispositivos para Skype empresarial](https://technet.microsoft.com/office/dn947482). Puede usar el [Panel de calidad de llamadas de Skype empresarial online](/microsoftteams/turning-on-and-using-call-quality-dashboard), que se encuentra en el centro de administración de **Skype empresarial**, para comprobar que los dispositivos en uso funcionan correctamente y supervisar la calidad de los medios de audio y vídeo.
  
> [!TIP]
> **Para obtener la mejor experiencia de calidad de medios de Skype para empresas, se necesita un dispositivo certificado**.
  
Es importante recordar que cualquier dispositivo de medios, clientes de Skype empresarial y servidores de Skype empresarial a través de los cuales se transmiten los medios en tiempo real, introducen cierta cantidad de latencia. La latencia de procesamiento de software y dispositivos, junto con la latencia de red, tienen un gran impacto en la latencia general de extremo a extremo y en la experiencia del usuario final.
  
#### <a name="environment"></a>Entorno

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen más nítida de la experiencia de audio y vídeo de un usuario, use el dispositivo de**audio** o el dispositivo de **vídeo** **de las** >  **herramientas** > de aplicaciones de Skype empresarial para realizar cambios en el dispositivo en uso y personalizar su configuración.

#### <a name="network"></a>Red

La calidad de los medios en tiempo real a través de la red IP se ve muy afectada por la calidad de la conectividad de la red, pero especialmente por la cantidad de:
  
- **Latencia** Este es el tiempo que se tarda en obtener un paquete IP desde el punto a al punto B de la red. Este retraso de propagación de red está esencialmente unido a la distancia física entre los dos puntos y la velocidad de luz, incluida la sobrecarga adicional que realizan los distintos enrutadores entre. La latencia se mide como el tiempo unidireccional o de ida y vuelta (RTT).
    
- **Pérdida de paquetes** Esto se suele definir como un porcentaje de paquetes que se pierden en una ventana determinada de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales, casi sin impacto, hasta pérdidas de ráfagas en el fondo que causan un recorte completo del audio.
    
- **Vibración de llegada del paquete entre paquetes o simplemente vibración** Este es el cambio medio en el retraso entre paquetes sucesivos. La mayoría de los programas de VoIP modernos, incluidos Skype empresarial, pueden adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Solo cuando la vibración supera el búfer que un participante observará de los efectos de la vibración.
    
> [!NOTE]
>  El almacenamiento en búfer para la vibración incrementa la latencia de un extremo a otro.
  
Con muchas sesiones de medios en tiempo real de Skype empresarial online simultáneas, así como otro tráfico de red generado por otros servicios de Office 365 y otras aplicaciones empresariales, asegurarse de que hay suficiente ancho de banda en toda la ruta de red que conecta su red con el servicio de Skype empresarial online es fundamental para evitar la congestión de la red y garantizar un medio en tiempo real multimedia (audio , video y uso compartido de aplicaciones). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementación de calidad de servicio (QoS) en redes congestionadas

Además, la gestión del tráfico en toda la red afectará enormemente la calidad de los medios. Para permitir que los paquetes de audio y vídeo viajen a través de la red más rápido y se les asigne prioridad a través de otro tráfico de red en una red congestionada, se puede usar la calidad de servicio (QoS) para proporcionar una experiencia de usuario final óptima para las comunicaciones de audio y vídeo.
  
QoS le permite asignar prioridades mayores a los paquetes de red que transportan datos de audio o vídeo. Al asignar una prioridad mayor a estos paquetes, es probable que las comunicaciones de audio y vídeo se transmitan a través de la red más rápido y con menos interrupciones, que sesiones de red en las que se utilizan tareas como las transferencias de archivos, la navegación por Internet o las copias de seguridad de la base de datos. Esto se debe a que los paquetes de red que se usan para las transferencias de archivos o las copias de seguridad de la base de datos tienen asignados "el mejor esfuerzo" como prioridad y la configuración de la red no tendrá un gran impacto. Si no asigna una prioridad más alta a los paquetes multimedia (audio, vídeo y uso compartido de aplicaciones) y deja que también se les haya asignado como "el mejor esfuerzo", también se procesarán con el resto del tráfico de red. En función de la cantidad de congestión de la red, esto puede acabar con una experiencia general de calidad de audio y video inferior para los usuarios.
  
Se recomienda encarecidamente implementar QoS en la red para asegurarse de que la congestión de la red dentro de la red no tenga ningún impacto. Sin embargo, para que esto tenga el máximo impacto, todos los puntos de conexión de red deben admitir QoS, lo que significa que todos los puntos de conexión deben respetar la marcación QoS y la prioridad de los paquetes. Los servicios de Skype empresarial online admiten la marcación de QoS y la priorización en la red de Microsoft. Sin embargo, el tráfico que se redirige a través de una conexión pública, como Internet, desde la red de la empresa a la red de Microsoft, no conserva las marcas de QoS ni el establecimiento de prioridades de los paquetes. Las conexiones privadas de su red a Office 365 con [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) ofrecen una solución de implementación que conserva las marcas de QoS y el establecimiento de prioridades de los paquetes que, a su vez, aumentará la calidad general de audio y vídeo de los usuarios finales.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de rendimiento de red para conectarse a Skype empresarial online
<a name="bkNetworkPerf"> </a>

Los medios en tiempo real de Skype empresarial viajan a través de muchos dispositivos, aplicaciones cliente, software de servidor y redes diferentes. La latencia completa de los medios en tiempo real es la cantidad total de latencia que se introduce en todos los componentes y segmentos de red. La calidad de la conexión de red completa viene determinada por el segmento de red con la peor calidad. Este segmento actúa como un cuello de botella para este tráfico de red.
  
En el siguiente diagrama se muestra un flujo de audio unidireccional en una conferencia de un participante de Skype empresarial a otro.
  
![Flujo de llamadas de ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
En este escenario de conferencia, la ruta multimedia se compone de los siguientes segmentos de red:
  
1. **Conexión del usuario 1 al perímetro de la red de Microsoft** Normalmente, esto incluye una conexión de red, como WiFi o Ethernet, la conexión WAN del usuario 1 al punto de salida de Internet (el dispositivo perimetral de red) y la conexión a Internet del perímetro de la red al perímetro de la red de Microsoft.
    
2. **Conexión en Microsoft Network** Esto se encuentra entre el Microsoft Edge y el centro de datos de Skype empresarial online, donde se usan los servidores de conferencia A/V.
    
3. **Conexión en Microsoft Network** Esto se encuentra entre el centro de datos de Skype empresarial online y el perímetro de la red de Microsoft.
    
4. **Conexión del perímetro de la red de Microsoft al usuario 2** Esto incluye la conexión a Internet del perímetro de la red al perímetro de la red de Microsoft, la conexión WAN del usuario 2 al punto de salida de Internet (el perímetro de la red) y la conexión de red, por ejemplo, WiFi o Ethernet.
    
En el siguiente diagrama se muestra un desglose de los componentes y segmentos de red de una llamada RTC de Skype empresarial online:
  
![Flujo de llamadas del operador RTC de ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
En un escenario de llamada RTC, la ruta multimedia cruza los siguientes segmentos de red:
  
1. **Conexión desde un cliente de Skype empresarial a la periferia de la red de Microsoft** Normalmente, esto incluye una conexión de red, como WiFi o Ethernet, la conexión WAN desde el cliente de Skype empresarial al punto de salida de Internet (el dispositivo perimetral de red) y la conexión a Internet del perímetro de la red al perímetro de la red de Microsoft.
    
2. **Conexión en Microsoft Network** Esto se encuentra entre el Microsoft Edge y el centro de datos de Skype empresarial online, donde se usa un servidor de mediación.
    
3. **Conexión en Microsoft Network** Esto se encuentra entre el centro de datos de Skype empresarial online y el perímetro de la red de Microsoft.
    
4. **Conexión entre los socios de los proveedores de servicios de red de Microsoft y RTC** Esta es la conexión que existe para realizar una llamada RTC desde el cliente de Skype empresarial que está fuera de la red de Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de rendimiento de red desde un cliente de Skype empresarial al perímetro de la red de Microsoft
<a name="bkSfBClienttoEdge"></a>

Para una óptima calidad de medios de Skype empresarial, se necesitan los siguientes umbrales o destinos de métrica de rendimiento de red para una conexión de la red de su empresa con el perímetro de la red de Microsoft. Este segmento de la red incluye su red interna, lo cual incluye todas las conexiones WiFi y Ethernet, cualquier tráfico de sitio a sitio de la empresa a través de una conexión WAN, por ejemplo, la conmutación de etiquetas multiprotocolo (MPLS), así como las conexiones de Internet o ExpressRoute Partner al perímetro de la red de Microsoft.
  
> [!CAUTION]
> **La conectividad entre un cliente de Skype empresarial de la red de la empresa y los servicios de Office 365 debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Target** <br/> |
|Latencia (unidireccional)  <br/> |< 50ms  <br/> |
|Latencia (RTT o tiempo de ida y vuelta)  <br/> |< 100 ms  <br/> |
|Pérdida de paquetes en ráfagas  <br/> |<el 10% durante cualquier intervalo de 200ms  <br/> |
|Pérdida de paquetes  <br/> |<1% durante cualquier intervalo de 15S  <br/> |
|Vibración de llegada entre paquetes  <br/> |<30ms durante cualquier intervalo de 15S  <br/> |
|Reordenación de paquetes  <br/> |<% 0,05% de paquetes fuera de servicio  <br/> |
   
 **Otros requisitos de rendimiento objetivo:**
  
- La red de Microsoft tiene más de 160 ubicaciones periféricas de todo el mundo. Trabajamos con proveedores de servicios de Internet (ISP) de todo el mundo a través de esos sitios perimetrales. El destino de la métrica de latencia supone que el sitio o los sitios de la empresa y los bordes de Microsoft están en el mismo continente.
    
- El sitio o los sitios de su compañía a la conexión perimetral de la red de Microsoft incluyen acceso de red de primer salto, que puede ser WiFi u otra tecnología inalámbrica. 
    
- El objetivo de rendimiento de red supone un ancho de banda adecuado o una planificación de calidad de servicio. En otras palabras, esto se aplica directamente al tráfico de medios en tiempo real de Skype empresarial cuando la conexión de red está por debajo de un pico de carga.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de rendimiento de red desde el perímetro de la red al perímetro de la red de Microsoft
<a name="bkYourNetworkEdge"> </a>

A continuación se muestran los límites de rendimiento de red o los umbrales necesarios para la conexión entre el perímetro de la red y el perímetro de la red de Microsoft. Este segmento de la red excluye la red interna o la WAN del cliente, y está pensada como orientación al probar el tráfico de red que se envía a través de Internet, o a través de una red asociada de ExpressRoute, y también puede usarse al negociar un contrato de nivel de servicio (SLA) de rendimiento con su proveedor de ExpressRoute.
  
> [!CAUTION]
> **La conectividad entre el perímetro de la red de la compañía y el perímetro de la red de Microsoft debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Target** <br/> |
|Latencia (unidireccional)  <br/> |< 30ms  <br/> |
|Latencia (RTT)  <br/> |< 60ms  <br/> |
|Pérdida de paquetes en ráfagas  <br/> |<1% durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<0,1% durante cualquier intervalo de 15S  <br/> |
|Vibración de llegada entre paquetes  <br/> |<15ms durante cualquier intervalo de 15S  <br/> |
|Reordenación de paquetes  <br/> |<% 0,01% de paquetes fuera de servicio  <br/> |
   
 **Otros requisitos de rendimiento objetivo:**
  
- El objetivo de rendimiento requiere que la conexión entre cualquiera de los perímetros de la red de tu empresa y el perímetro de la red de Microsoft más cercano se encuentre en el mismo continente.
    
- El objetivo de rendimiento de red supone un ancho de banda adecuado o una planificación de calidad de servicio. Esto también se aplica al tráfico de medios en tiempo real de Skype empresarial cuando la conexión de red está por debajo de un pico de carga. Para un buen ancho de banda y planificación de QoS, consulte [ExpressRoute y QoS en Skype empresarial online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
    
## <a name="measuring-network-performance"></a>Medir el rendimiento de la red
<a name="bkNetworkPerf"> </a>

Para medir el rendimiento real de la red, especialmente en cuanto a la latencia y la pérdida de paquetes, desde cualquier sitio de red de la empresa a un perímetro de la red, puede usar herramientas como el ping, probar con un conjunto de servicios de transmisión de multimedia de Skype empresarial que se ejecuten desde los sitios de Microsoft Edge y de centro de datos. 

>[!NOTE]
> Medir el rendimiento de la red mediante ping (ICMP) no es efectivo. Por ese motivo, la IP que se exponen a continuación detendrá la respuesta a las solicitudes de ICMP a partir de ene, 2020. Para medir eficazmente el rendimiento de la red, Microsoft recomienda la herramienta de evaluación de [redes](https://www.microsoft.com/download/details.aspx?id=53885).
  
Para probar las conexiones a través de Internet a la red de Microsoft, se recomienda que pruebe los siguientes VIP de las retransmisiones de multimedia de Skype empresarial. La *VIP de difusión por proximidad* se resolverá como una dirección IP de una retransmisión multimedia en un sitio perimetral de red de Microsoft más cercano a la ubicación de las pruebas.
  
||||
|:-----|:-----|:-----|
|**Dirección IP** <br/> |**Tipo** <br/> |**Ubicación** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP para Anycast mundo  <br/> |
   
 **A continuación se muestran algunas recomendaciones de alto nivel para evaluar el rendimiento de la red:**
  
- Debe evaluar su red interna, así como las conexiones a Office 365.
    
- Debe evaluar y recopilar datos de todas las redes durante un período de tiempo prolongado. Le recomendamos que realice las pruebas de rendimiento de red durante un mínimo de una semana, de modo que pueda ver los patrones de uso de todos los días y horas laborables. Esto le mostrará horas pico.
    
- Debe tomar varias muestras de las medidas de rendimiento de la red. Se recomienda tomar una medida cada 10 minutos desde un sitio de la empresa durante todo el período de tiempo que se recopilan datos. Para comparar los requisitos de rendimiento de la red de Skype empresarial online, tome el valor de medida del nonagésimo percentil de este conjunto de datos de ejemplo. 
    
- Debe evaluar de forma continua el rendimiento de la red. La utilización de redes varía a lo largo del tiempo debido a cambios de patrones de uso, nuevas aplicaciones basadas en la empresa que usan una gran cantidad de ancho de banda y cambios en las ubicaciones de la compañía o de la empresa. Es importante que usted supervise continuamente el rendimiento de la red en relación con estos requisitos de rendimiento de red, objetivos o umbrales y realice ajustes oportunos para garantizar la calidad de los medios en tiempo real más óptimos. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medir el rendimiento de la red con máquinas virtuales de Azure
<a name="bkNetworkPerf"> </a>

En lugar de realizar pruebas en los sitios perimetrales de la red de Microsoft, hay soluciones de evaluación de redes de clientes y socios de Skype empresarial que aprovechan la configuración de pruebas de servicios en la nube de Microsoft Azure. En esas soluciones, la latencia de prueba de las herramientas de evaluación de redes, la pérdida de paquetes y la vibración de los extremos personalizados se configuran como un servicio en la nube de Azure. Como resultado, el tráfico de red de prueba se desplaza por un segmento de red adicional, que es la conexión dentro de la red de Microsoft entre los límites de red y los centros de datos de Azure que hospeda el servicio de evaluación de red.
  
Para las soluciones de evaluación de red basadas en los servicios de pruebas hospedadas de Azure. Recomendamos realizar la evaluación de la red dentro del país o de la región. Por ejemplo, en el caso de los sitios de clientes de Estados Unidos de EE. UU., la evaluación debe realizarse en una instancia de servicio de pruebas hospedada en la región del centro de datos de Estados Unidos de Azure. 
  
A continuación se muestran los destinos de latencia (RTT) de la configuración de evaluación de red basada en servicios de Azure. Los objetivos de latencia unidireccionales serán la mitad de los destinos de RTT correspondientes. La pérdida de paquetes y los objetivos de vibración permanecen iguales a los definidos para las pruebas basadas en Skype media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Región del cliente** <br/> |**Región de Azure** <br/> |**Su red perimetral-tiempo de ida y vuelta (RTT) de Azure** <br/> |**Su sitio-tiempo de ida y vuelta (RTT) de Azure** <br/> |
|Centro de EE. UU.  <br/> |Centro de EE. UU.  <br/> |99  <br/> |139  <br/> |
|Este de EE. UU.  <br/> |Este de EE. UU.  <br/> |86  <br/> |126  <br/> |
|Centro de EE. UU. de Estados Unidos  <br/> |Centro de EE. UU. de Estados Unidos  <br/> |97  <br/> |137  <br/> |
|Centro de EE. UU. de Estados Unidos  <br/> |Centro de EE. UU. de Estados Unidos  <br/> |94  <br/> |134  <br/> |
|Oeste de EE. UU.  <br/> |Oeste de EE. UU.  <br/> |94  <br/> |134  <br/> |
|Hawai  <br/> |Oeste de EE. UU.  <br/> |116  <br/> |156  <br/> |
|Centro de Canadá  <br/> |Centro de Canadá  <br/> |138  <br/> |178  <br/> |
|Canadá este  <br/> |Canadá este  <br/> |131  <br/> |171  <br/> |
|Europa del norte  <br/> |Europa del norte  <br/> |99  <br/> |139  <br/> |
|Europa occidental  <br/> |Europa occidental  <br/> |95  <br/> |135  <br/> |
|Asia oriental  <br/> |Asia oriental  <br/> |118  <br/> |158  <br/> |
|Sudeste de Asia  <br/> |Sudeste de Asia  <br/> |97  <br/> |137  <br/> |
|Este de Japón  <br/> |Este de Japón  <br/> |111  <br/> |151  <br/> |
|Oeste de Japón  <br/> |Oeste de Japón  <br/> |118  <br/> |158  <br/> |
|Sur de Brasil  <br/> |Sur de Brasil  <br/> |70  <br/> |110  <br/> |
|Este de Australia  <br/> |Este de Australia  <br/> |124  <br/> |164  <br/> |
|Sudeste de Australia  <br/> |Sudeste de Australia  <br/> |124  <br/> |164  <br/> |
|Central India  <br/> |Central India  <br/> |103  <br/> |143  <br/> |
|Sudáfrica de India  <br/> |Sudáfrica de India  <br/> |103  <br/> |143  <br/> |
|Oeste de la India  <br/> |Oeste de la India  <br/> |103  <br/> |143  <br/> |
|Este de China  <br/> |Este de China  <br/> |120  <br/> |160  <br/> |
|Norte de China  <br/> |Norte de China  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Calidad de medios y ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute para Office 365 es una conexión de red dedicada para conectarse a Office 365. Ofrece a los clientes la posibilidad de controlar la ruta que toma su tráfico de red de Office 365. Ya no tienen que preocuparse por el enrutamiento impredecible que se produce en Internet, en el que los datos los transmiten los operadores, proveedores e ISPs desconocidos. El tráfico de red que se envía a través de ExpressRoute se envía directamente a través de la red del colaborador de ExpressRoute a la red de Microsoft. Esto permite a los clientes tratar Office 365 como si estuviera ubicado en su propio centro de datos fuera del sitio con una conexión dedicada.
  
Azure ExpressRoute está disponible para todas las ofertas de licencias de Office 365. Sin embargo, el complemento Azure ExpressRoute Premium es necesario para que Office 365 pueda habilitar el enrutamiento global. Los clientes con un mínimo de 500 puestos de implementación de ExpressRoute pueden obtener el *complemento de Expressroute Premium* necesario sin cargos adicionales.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>¿Se requiere ExpressRoute para obtener una buena calidad de medios?

Azure ExpressRoute no es un requisito para obtener la mejor calidad de multimedia de Skype empresarial online. Sin embargo, se trata de una de las opciones de implementación que te ayudan a asegurarte de que tu conectividad en la nube cumple con los umbrales de rendimiento de red de Skype empresarial.
  
Office 365 es un servicio seguro y de alto rendimiento que usa Internet. Seguimos invirtiendo en nuevas capacidades de seguridad y nodos perimetrales regionales para mejorar continuamente la seguridad y el rendimiento. Azure ExpressRoute no es un requisito para los servicios de Office 365, incluido Skype empresarial online. Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudarán a garantizar que la conectividad a Office 365 cumple los requisitos de rendimiento de la red de Skype empresarial y garantiza la mejor experiencia de calidad de medios de Skype empresarial online.
  
Para la calidad de los medios de Skype empresarial online, es importante que la conexión entre los sitios de la compañía y los bordes de la red de Microsoft cumpla los objetivos de rendimiento en [los requisitos de rendimiento de red desde un cliente de Skype empresarial al perímetro](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) de la red y que la conexión entre los bordes de la red y los bordes de la red de Microsoft cumpla con los requisitos de rendimiento de [la](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)red  
  
También es importante que la conectividad de la red física de su empresa, incluida la red interna y la conectividad en la nube, admita el volumen de tráfico multimedia máximo. Azure ExpressRoute es una de las muchas maneras que pueden ayudar a los clientes a garantizar que la conectividad de la nube de Skype empresarial online cumpla con todos estos requisitos de rendimiento.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>¿Se requiere ExpressRoute para obtener una SLA de calidad de voz?

No, ExpressRoute no es necesario para el SLA de calidad de voz de Skype empresarial online. El [SLA de calidad de voz de Skype empresarial online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) se aplica a cualquier llamada elegible realizada por cualquier usuario del servicio de voz de Skype empresarial online dentro de la licencia y la suscripción correctas que permiten a ese usuario hacer cualquier tipo de llamada VoIP o RTC. Un SLA de calidad de voz debe incluir que se solucionen todas las condiciones siguientes:
  
- Llamadas desde teléfonos IP Microsoft Certified.
    
- Conexiones cableadas por Ethernet.
    
- Problemas de calidad de voz causados por problemas de la red de Microsoft.
    
> [!NOTE]
> El SLA de calidad de voz excluye las llamadas en las que la baja calidad de llamada se debe a problemas de redes ajenas a Microsoft, como el socio de ExpressRoute y otras redes. 
  
### <a name="internet-or-azure-expressroute"></a>¿Internet o Azure ExpressRoute?

Antes de tomar una decisión sobre las opciones de conectividad de red para Skype empresarial online, los clientes deben evaluar su red y la conectividad actual a Internet según los requisitos de rendimiento de red que se describen en [requisitos de rendimiento de red para conectarse a Skype empresarial online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Si el rendimiento de la red a través de la conexión a Internet actual está configurado con suficiente capacidad durante el tiempo máximo y cumple los requisitos de rendimiento de red de los sitios y los bordes de red de Microsoft, y de los bordes de la red a los bordes de la red de Microsoft, puede seguir usando su conectividad a Internet existente para conectarse a Skype empresarial online.
  
Para los sitios de la compañía en los que no se cumplen los requisitos de rendimiento de red, le recomendamos encarecidamente que primero trabaje con los proveedores de servicios de red existentes para mejorar el rendimiento general de la red. Sin embargo, si aún no se cumplen, el uso de Azure ExpressRoute puede ayudar a garantizar que la conectividad de la nube de Skype empresarial online pueda ayudarle a cumplir los requisitos de rendimiento de la red.
  
Azure ExpressRoute ofrece las siguientes ventajas adicionales:
  
- Un contrato de nivel de servicio (SLA) sobre la disponibilidad de la conexión entre la red y la red de Microsoft. ExpressRoute tiene un SLA de disponibilidad garantizado de 99,9%.
    
- Ancho de banda previsto y garantizado necesario para los servicios de Office 365. Para ello, envíe solo el tráfico de Office 365 o el tráfico de Skype empresarial con ExpressRoute y, a continuación, haga que el resto del tráfico de Internet pase por otros puntos de salida o entrada de Internet para su red.
    
- ExpressRoute está diseñado para conservar las marcas QoS de DSCP entre su red y la red de Microsoft.
    
Para obtener más información sobre la calidad de servicios de ExpressRoute y la planeación de capacidad, consulte [ExpressRoute y QoS en Skype empresarial online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>¿Puedo configurar Azure ExpressRoute solo para Skype empresarial online?

Sí, puede configurar Azure ExpressRoute para garantizar una conectividad de red excelente desde la red de su empresa solo para Skype empresarial online. Esto proporcionará la calidad de medios en tiempo real más óptima para los usuarios, pero podrá seguir conectándose a otros servicios de Office 365 a través de Internet.
  
El protocolo de puerta de enlace de borde (BGP) es un protocolo de enrutamiento en Internet que se usa para enrutar tráfico de red a través de Internet. Está diseñado para intercambiar información de enrutamiento entre sistemas autónomos que se encuentran en Internet. Los valores de comunidades BGP son etiquetas de atributo que se pueden aplicar a rutas entrantes o salientes. Las comunidades BGP suelen usarse para indicar la recepción como el vínculo saliente que se usará para comunicarse con un destino determinado basándose en la geografía, el tipo de servicio u otros criterios.
  
Con la compatibilidad de comunidades BGP, Microsoft etiquetará los prefijos y las rutas con valores de comunidad BGP apropiados según el servicio al que pertenecen. Microsoft etiquetará los prefijos anunciados mediante el emparejamiento público y el emparejamiento de Microsoft con valores de comunidad BGP apropiados, indicando la región en la que se hospedan los prefijos. Puede confiar en los valores de la comunidad para tomar las decisiones de enrutamiento adecuadas para ofrecer un enrutamiento óptimo. Puede usar el valor de la comunidad BGP de Skype empresarial online para configurar una conexión de ExpressRoute solo para Skype empresarial online. Puede obtener más información en [requisitos de enrutamiento de ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Escenarios de conectividad de ExpressRoute para Skype empresarial online
<a name="bkNetworkPerf"> </a>

Si ha decidido que ExpressRoute basado en las recomendaciones anteriores le corresponde, estas son las recomendaciones sobre dónde y cuántas conexiones de ExpressRoute debe obtener.
  
### <a name="online-only-deployment---single-site"></a>Implementación solo en línea: un único sitio

Si todos los usuarios usan el servicio Skype empresarial online y se centran en una única ubicación física y decide implementar Azure ExpressRoute, debe configurar una sola conexión de ExpressRoute entre el sitio de la empresa en la [Ubicación de emparejamiento de expressroute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)más cercana.
  
En el siguiente gráfico se muestra un ejemplo de este tipo de implementación. Para este ejemplo, contoso es una Universidad que se encuentra en Orlando, Florida. Contoso tiene miembros de profesores de 10.000 y estudiantes. Las pruebas de Internet desde su ubicación a sitios de Microsoft Edge mostraron una pérdida de paquetes superior al 5% durante las horas de máxima clase. Han decidido obtener una conexión dedicada a Office 365 usando ExpressRoute con ancho de banda aprovisionado para que puedan evitar la congestión de la red para Office 365 especialmente para el tráfico en tiempo real de Skype empresarial online. Se conectan a la nube de Microsoft a través de ExpressRoute en el sitio de Atlanta, GA MeetMe.
  
![Un solo sitio de ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implementación solo en línea: varios sitios en el mismo continente

Si su empresa usa servicios de Skype empresarial online de varias oficinas en la misma región o continente y elige implementar Azure ExpressRoute, se recomienda que conecte su sitio principal a través de ExpressRoute y, opcionalmente, agregue el emparejamiento de ExpressRoute para otras ubicaciones que no cumplan con los objetivos de rendimiento de red recomendados.
  
En el siguiente ejemplo, contoso es una empresa de servicios de viajes de los Estados Unidos que tiene sede en Nueva York, pero tiene otras oficinas en todos los Estados Unidos. Sus oficinas están interconectadas a través de una WAN que usa MPLS para conectarse a Office 365. Inicialmente, configuramos una conexión de ExpressRoute desde su router de Internet en Hoboken, Nueva Jersey al sitio de MeetMe de Nueva York. 
  
Con esta configuración, el tráfico de red de la mayoría de sus sitios a la red de Microsoft (nuevo sitio Edge) puede cumplir los objetivos de rendimiento de red de la conexión de cliente de Skype empresarial descritos en [requisitos de rendimiento de red desde un cliente de Skype empresarial hasta el perímetro de la red de Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Sin embargo, la latencia entre las oficinas de la costa oeste de Contoso a Nueva York pasa de 50ms unidireccional. Además, Honolulu es la segunda oficina de Contoso más grande, la latencia de Honolulu a Nueva York supera 80ms un método. Para garantizar una buena calidad de soporte a los usuarios de estas oficinas, contoso decidió agregar una conexión West Coast ExpressRoute entre su sitio San José y el sitio de MeetMe de Silicon Valley ExpressRoute.
  
![Sitio múltiple de enrutador urgente en el mismo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implementación solo en línea: varios sitios en diferentes continentes

Si todos los usuarios usan el servicio Skype empresarial online y sus oficinas están en varias ubicaciones físicas en varios continentes, si decide implementar Azure ExpressRoute, debe configurar al menos una conexión de ExpressRoute para cada continente entre el sitio principal de cada continente y la [Ubicación de emparejamiento de expressroute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)más cercana. Según el costo de la ventaja, puede elegir implementar conexiones de ExpressRoute adicionales desde sitios en los que no se cumplen los objetivos de rendimiento de red.
  
En el siguiente ejemplo, contoso es un gran bufete legal corporativo con oficinas en las principales ciudades de Norteamérica y Europa. En función de su conexión a Internet y de su evaluación de rendimiento de red interna, contoso decidió implementar dos conexiones de ExpressRoute en Norteamérica y un único circuito ExpressRoute para todas sus oficinas europeas.
  
![ExpressRoute con varios sitios y continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implementación híbrida

Si tiene una implementación local de Lync o Skype empresarial y elige implementar una integración híbrida de Skype empresarial online, le recomendamos que si decide implementar Azure ExpressRoute, debe tener al menos una conexión de ExpressRoute para cada sitio perimetral local de Lync o Skype empresarial, y al menos una conexión de ExpressRoute para cada continente con oficinas. Según el costo de la prestación, por cada continente puede elegir implementar conexiones de ExpressRoute adicionales de oficinas en las que no se cumplen los objetivos de rendimiento de red.
  
Si dispone de una implementación local de Skype empresarial, debe seguir la [Guía de planeación e implementación del servidor perimetral](https://technet.microsoft.com/library/mt346417.aspx). En concreto, los servidores perimetrales deben ser accesibles desde fuera de la red. Esto suele lograrse asignando una dirección IP pública enrutable al servidor perimetral o mediante la traducción de direcciones de red (NAT).
  
En el siguiente ejemplo, Contoso tiene una implementación de Skype empresarial Enterprise Voice existente. Desean migrar usuarios locales a Office 365 Online Services. También decidieron usar una implementación híbrida para que puedan seguir usando su infraestructura RTC existente para todos los usuarios locales y en línea. El centro de datos local de Contoso y los servidores perimetrales de Skype empresarial están en Chicago. Para su implementación, contoso decidió configurar una conexión de ExpressRoute entre su centro de datos de Chicago y Chicago ExpressRoute. También añadieron una conexión West Coast ExpressRoute para brindar un mejor servicio a su oficina de Honolulu.
  
![ExpressRoute híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implementación en línea con Cloud Connector Edition

Skype empresarial online Cloud Connector Edition es una oferta híbrida que consta de un conjunto de máquinas virtuales (VMs) empaquetadas que implementan conectividad con RTC local. Al implementar una topología mínima de Skype empresarial Server en un entorno virtualizado, podrá enviar y recibir llamadas con teléfonos fijos y móviles a través de la infraestructura de voz local de RTC existente.
  
Si decide implementar Azure ExpressRoute y Cloud Connector Edition, le recomendamos que configure al menos una conexión Express de expressroute para cada continente entre el sitio principal de cada continente y la [Ubicación de emparejamiento de ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)más cercana. Según el costo de la prestación, por cada continente puede elegir implementar conexiones de ExpressRoute adicionales desde sitios en los que no se cumplen los objetivos de rendimiento de red.
  
Si dispone de una implementación local de Skype empresarial, debe seguir la [Guía de planeación de la edición Cloud Connector de Skype empresarial](https://technet.microsoft.com/library/mt605227.aspx). En concreto, el límite de acceso y los servicios perimetrales A/V deberían tener asignadas direcciones IP públicas y accesibles desde los centros de datos de Office 365.
  
En el siguiente ejemplo, contoso es una empresa de contabilidad Europea con presencia en unos cuantos países y ciudades europeos importantes. Cuando se suscriben a Skype empresarial online para todas sus necesidades de colaboración, decidieron colocar un conector en la nube para cada país que tengan una ubicación física para continuar usando su infraestructura de RTC y contratos de operador que ya existan. En función de sus pruebas de todos los sitios y del perímetro de la red de Microsoft, determinó que una única conexión de ExpressRoute en Londres le ayudará a cumplir los objetivos de rendimiento de red de la conexión de cliente de Skype empresarial descritos en [requisitos de rendimiento de red desde un cliente de Skype empresarial hasta el perímetro de la red de Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![El conector de nube de ExpressRoute uno.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A continuación se muestra otra opción de implementación de contoso. En este caso, decidieron configurar una conexión de ExpressRoute en cada sitio en el que se implementó un conector en la nube. 
  
![Dos conectores de nube ExpressRoute.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
