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
description: En este tema se define el conjunto de requisitos de rendimiento de red para los servicios de Skype Empresarial Online y cómo puede elegir usar Internet o ExpressRoute para la conectividad entre su red y Skype Empresarial Online en función de su evaluación de la conectividad de red. Si ha decidido implementar Azure ExpressRoute para la conectividad dedicada a Microsoft 365 o Office 365, este documento también proporciona instrucciones sobre cómo planear las conexiones de ExpressRoute en diferentes escenarios de implementación de Skype Empresarial Online.
ms.openlocfilehash: 0bb750be4d4c21c8fec3cc8dc5d0ab5cf0b4cb6a
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240250"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este tema se define el conjunto de requisitos de rendimiento de red para los servicios de Skype Empresarial Online y cómo puede elegir usar Internet o ExpressRoute para la conectividad entre su red y Skype Empresarial Online en función de su evaluación de la conectividad de red. Si ha decidido implementar Azure ExpressRoute para la conectividad dedicada a Microsoft 365 o Office 365, este documento también proporciona instrucciones sobre cómo planear las conexiones de ExpressRoute en diferentes escenarios de implementación de Skype Empresarial Online.
  
La calidad de Real-Time multimedia (audio, vídeo y uso compartido de aplicaciones) a través de IP se encuentra muy afectada por la calidad de la conectividad de red de un extremo a otro. Para obtener una Skype Empresarial de medios en línea, es importante que se asegúrese de que hay una conexión de alta calidad entre la red de su empresa y Skype Empresarial Online. La mejor manera de lograrlo es configurar la conectividad interna de la nube y la red en función de la capacidad de la red para adaptarse al volumen máximo de tráfico de Skype Empresarial Online en todas las conexiones.
  
Azure ExpressRoute no es un requisito para los servicios Microsoft 365 y Office 365, incluido Skype Empresarial Online. Sin embargo, Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudará a asegurarse de que la conectividad a Microsoft 365 o Office 365 cumpla los requisitos de rendimiento de red de Skype Empresarial y garantice la experiencia de calidad de medios de Skype Empresarial Online más óptima.
  
> [!TIP]
> Aunque este tema le proporciona instrucciones generales sobre el rendimiento de las redes, las instrucciones completas para la evaluación de red están fuera del ámbito de este documento. Para encontrar una lista de los partners de Skype Empresarial Online que pueden ayudarle con las medidas de rendimiento de la red como parte de una evaluación de red exhaustiva y completa, visite Skype Empresarial Soluciones de [partners.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividad de red Skype Empresarial Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factores que afectan a la Skype Empresarial multimedia en línea

Hay muchos factores diferentes que contribuyen Skype Empresarial la calidad de los medios Real-Time en línea (audio, vídeo y uso compartido de aplicaciones) que incluyen los dispositivos que se usan, el entorno y la conectividad de red. 
  
#### <a name="devices"></a>Dispositivos

En una sesión Real-Time multimedia, los dispositivos de captura y representación de medios que usan todos los participantes, como auriculares y cámaras web, tienen un gran impacto en la calidad general de audio y vídeo. Los dispositivos de audio y vídeo de menor calidad o que utilizan controladores incorrectos generan, respectivamente, sonido e imágenes de calidad reducida. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Aunque los dispositivos multimedia de audio y vídeo certificados no son necesarios, son dispositivos altamente recomendados certificados Skype Empresarial para obtener la experiencia multimedia más óptima. Para obtener una lista de todos Skype Empresarial dispositivos certificados, vea Teléfonos [y dispositivos para Skype Empresarial](../../SfbPartnerCertification/certification/devices-ip-phones.md). Puede usar el panel de calidad de llamadas [de Skype Empresarial Online](/microsoftteams/turning-on-and-using-call-quality-dashboard), que se encuentra en el Centro de administración de **Skype Empresarial,** para comprobar que los dispositivos en uso funcionan correctamente y supervisar la calidad de los medios de audio y vídeo.
  
> [!TIP]
> **Se requiere un dispositivo certificado para obtener la** experiencia más Skype Empresarial calidad de los medios.
  
Es importante recordar que todos los dispositivos multimedia, Skype Empresarial clientes y servidores Skype Empresarial a través de los cuales Real-Time los medios, introducen cierta cantidad de latencia. La latencia de procesamiento de dispositivos y software, junto con la latencia de red, tienen un gran impacto en la latencia general de un extremo a otro y contribuyen a la experiencia del usuario final.
  
#### <a name="environment"></a>Entorno

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen más clara de la experiencia de audio y vídeo de un usuario, use la aplicación Herramientas de Skype Empresarial Opciones Dispositivo de audio o Dispositivo de vídeo para realizar cambios en el dispositivo en uso y personalizar su  >    >   configuración. 

#### <a name="network"></a>Red

La calidad de los Real-Time multimedia a través de la red IP se encuentra muy afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:
  
- **Latencia** Este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B en la red. Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida la sobrecarga adicional que han tomado los distintos enrutadores entre sí. La latencia se mide como tiempo de ida o de ida y vuelta (RTT).
    
- **Pérdida de paquetes** Esto suele definirse como un porcentaje de paquetes que se pierden en una ventana de tiempo determinada. La pérdida de paquetes afecta directamente a la calidad de audio, desde pequeños paquetes perdidos individuales que casi no tienen impacto, hasta pérdidas de ráfagas back-to-back que provocan un corte total de audio.
    
- **Vibración de llegada entre paquetes o simplemente vibración** Este es el cambio promedio de retraso entre paquetes sucesivos. La mayoría del software VoIP moderno Skype Empresarial puede adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Solo cuando el vibración supera el almacenamiento en búfer, un participante notará los efectos de la vibración.
    
> [!NOTE]
>  El almacenamiento en búfer para vibración aumentará la latencia de un extremo a otro.
  
Con muchas sesiones multimedia de Skype Empresarial Online Real-Time simultáneas, así como otro tráfico de red generado por otros servicios Microsoft 365 o Office 365 y otras aplicaciones empresariales, asegurarse de que hay ancho de banda suficiente en toda la ruta de red que conecta su red con el servicio de Skype Empresarial Online es fundamental para evitar la congestión de la red y garantizar una calidad excelente de medios Real-Time multimedia (audio, vídeo y uso compartido de aplicaciones). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementar calidad de servicio (QoS) en redes congestionadas

Además, la congestión del tráfico en una red afectará enormemente a la calidad de los medios. Para permitir que los paquetes de audio y vídeo viajen más rápido por la red y que se prioricen sobre otro tráfico de red en una red congestionada, calidad de servicio (QoS) puede usarse para ayudar a proporcionar una experiencia óptima para el usuario final para las comunicaciones de audio y vídeo.
  
QoS proporciona una manera de asignar prioridades más altas a los paquetes de red que transportan datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, es probable que las comunicaciones de audio y vídeo viajen por la red más rápido y con menos interrupciones que las sesiones de red que implican cosas como transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que los paquetes de red que se usan para las transferencias de archivos o copias de seguridad de bases de datos de forma predeterminada se asignan "mejor esfuerzo" como prioridad y la congestión de red no tendrá un impacto tan grande. Si no asigna una prioridad más alta a los paquetes multimedia (audio, vídeo y uso compartido de aplicaciones) y los deja asignados también como "mejor esfuerzo", también se procesarán junto con el resto del tráfico de red. Dependiendo de la cantidad de congestión de red, esto potencialmente acabará en una experiencia de calidad general de audio y vídeo más baja para los usuarios.
  
Es muy recomendable que implemente QoS en su red para asegurarse de que la congestión de la red dentro de la red no tenga un impacto. Sin embargo, para que esto tenga el máximo impacto, todos los puntos de conexión de red deben admitir QoS, lo que significa que todos los puntos de conexión deben respetar el marcado de QoS y la priorización de paquetes. Skype Empresarial Los servicios en línea respetan el marcado y la priorización de QoS dentro de la red de Microsoft. Sin embargo, el tráfico que se enruta a través de una conexión pública como Internet desde la red de su empresa a la red de Microsoft no conserva las marcas de QoS y la priorización de paquetes. Las conexiones privadas de su red a Microsoft 365 o Office 365 con [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) ofrecen una solución de implementación que conserva las marcas de QoS y la priorización de paquetes que, a su vez, aumentarán la calidad general de audio y vídeo para los usuarios finales.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de rendimiento de red para conectarse a Skype Empresarial Online
<a name="bkNetworkPerf"> </a>

Skype Empresarial Real-Time multimedia viaja a través de muchos dispositivos diferentes, aplicaciones cliente, software de servidor y entre redes diferentes. La latencia de un extremo a otro de Real-Time multimedia es la cantidad total de latencia que se introduce en todos los componentes y segmentos de red. La calidad de la conexión de red de un extremo a otro se determina por el segmento de red con la peor calidad. Este segmento actúa como cuello de botella para este tráfico de red.
  
En el siguiente diagrama se muestra el flujo de audio uníz en una conferencia de un Skype Empresarial participante a otro.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
En este escenario de conferencia, la ruta de acceso multimedia se compone de los siguientes segmentos de red:
  
1. **Conexión del usuario 1 al borde de la red de Microsoft** Normalmente, se incluye una conexión de red como WiFi o Ethernet, la conexión WAN del usuario 1 al punto de salida de Internet (el dispositivo perimetral de red) y la conexión a Internet desde el perímetro de red a Microsoft Network Edge.
    
2. **Conexión dentro de la red de Microsoft** Esto se encuentra entre la Microsoft Edge a Skype Empresarial de datos en línea, donde se usan los servidores de conferenciaS/V.
    
3. **Conexión dentro de Microsoft Network** Esto se encuentra entre el centro de Skype Empresarial de datos en línea y el perímetro de red de Microsoft.
    
4. **Conexión del borde de red de Microsoft al usuario 2** Esto incluye la conexión a Internet desde el perímetro de red a Microsoft, la conexión WAN del usuario 2 al punto de salida de Internet (el perímetro de red) y la conexión de red, como un WiFi o un Ethernet.
    
En el siguiente diagrama se muestra el desglose de los componentes y segmentos de red de Skype Empresarial llamada RTC en línea:
  
![ExpressRoute RTC Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
En un escenario de llamada RTC, la ruta de acceso multimedia cruza los siguientes segmentos de red:
  
1. **Conexión desde un Skype Empresarial cliente al borde de Microsoft Network** Normalmente, se incluye una conexión de red como WiFi o Ethernet, la conexión WAN desde el autor de la llamada de cliente Skype Empresarial al punto de salida de Internet (el dispositivo perimetral de red) y la conexión a Internet desde el perímetro de red a Microsoft network Edge.
    
2. **Conexión dentro de la red de Microsoft** Esto se encuentra entre el Microsoft Edge a Skype Empresarial de datos en línea, donde se usa un servidor de mediación.
    
3. **Conexión dentro de Microsoft Network** Esto se encuentra entre el centro de Skype Empresarial de datos en línea y el perímetro de red de Microsoft.
    
4. **Conexión entre Microsoft Network y los partners del proveedor de servicios RTC** Esta es la conexión que existe para realizar una llamada RTC desde el Skype Empresarial cliente que está fuera de la red de Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de rendimiento de red de Skype Empresarial cliente a Microsoft network Edge
<a name="bkSfBClienttoEdge"></a>

Para una calidad Skype Empresarial multimedia, se necesitan los siguientes objetivos o umbrales de métricas de rendimiento de red para una conexión desde la red de su empresa al perímetro de red de Microsoft. Este segmento de la red incluye su red interna, esto incluye todas las conexiones WiFi y Ethernet, cualquier tráfico de sitio a sitio de la empresa a través de una conexión WAN, por ejemplo, Multiprotocol Label Switching (MPLS), así como las conexiones de partners de Internet o ExpressRoute a microsoft network Edge.
  
> [!CAUTION]
> **La conectividad entre un Skype Empresarial en la red de su empresa para Microsoft 365 o Office 365 deben cumplir estos siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latencia (una manera)  <br/> |< 50 ms  <br/> |
|Latencia (RTT o Tiempo de ida y vuelta)  <br/> |< 100 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |<10 % durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<1 % durante cualquier intervalo de 15s  <br/> |
|Vibración entre llegadas de paquetes  <br/> |<30 ms durante cualquier intervalo de 15s  <br/> |
|Reordenación de paquetes  <br/> |<0,05 % de paquetes no pedidos  <br/> |
   
 **Otros requisitos de destino de rendimiento:**
  
- La red de Microsoft tiene más de 160 ubicaciones perimetrales en todo el mundo. Trabajamos con los principales proveedores de servicios de Internet (ISP) en todo el mundo a través de esos sitios perimetrales. El destino de la métrica de latencia asume que el sitio o los sitios de su empresa y los bordes de Microsoft están en el mismo continente.
    
- El sitio de la empresa o los sitios a la conexión perimetral de red de Microsoft incluyen el acceso de red de primer salto, que puede ser WiFi u otra tecnología inalámbrica. 
    
- El destino de rendimiento de red asume el ancho de banda adecuado y/o la calidad de la planificación del servicio. En otras palabras, esto se aplica directamente al tráfico Skype Empresarial Real-Time multimedia cuando la conexión de red está bajo una carga máxima.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de rendimiento de red desde el perímetro de red hasta el perímetro de red de Microsoft
<a name="bkYourNetworkEdge"> </a>

A continuación se deberán ver los límites o los objetivos de rendimiento de red necesarios para la conexión entre el perímetro de red y el perímetro de red de Microsoft. Este segmento de la red excluye la red interna o WAN del cliente, y está pensado como guía al probar el tráfico de red que se envía a través de Internet o a través de una red asociada de ExpressRoute y también se puede usar al negociar un contrato de nivel de servicio (SLA) de rendimiento con su proveedor de ExpressRoute.
  
> [!CAUTION]
> **La conectividad entre el perímetro de red de su empresa con el perímetro de red de Microsoft debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latencia (una manera)  <br/> |< 30 ms  <br/> |
|Latencia (RTT)  <br/> |< 60 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |<1 % durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<0,1 % durante cualquier intervalo de 15s  <br/> |
|Vibración entre llegadas de paquetes  <br/> |<15 ms durante cualquier intervalo de 15 s  <br/> |
|Reordenación de paquetes  <br/> |<0,01 % de paquetes no pedidos  <br/> |
   
 **Otros requisitos de destino de rendimiento:**
  
- El objetivo de rendimiento requiere la conexión entre cualquiera de los perímetros de red de su empresa y su perímetro de red de Microsoft más próximo, para estar en el mismo continente.
    
- El destino de rendimiento de red asume el ancho de banda adecuado y/o la calidad de la planificación del servicio. Esto también se aplica al Skype Empresarial Real-Time multimedia cuando la conexión de red está bajo una carga máxima. Para obtener el ancho de banda adecuado y la planificación de QoS, consulte [ExpressRoute y QoS en Skype Empresarial Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Medir el rendimiento de la red
<a name="bkNetworkPerf"> </a>

Para medir el rendimiento real de la red, especialmente para la latencia y la pérdida de paquetes, desde cualquier sitio de red de la empresa hasta un perímetro de red, puede usar herramientas como ping, probar un conjunto de servicios de retransmisión multimedia Skype Empresarial que se ejecutan desde los sitios de Microsoft Edge y del centro de datos. 

>[!NOTE]
> Medir el rendimiento de la red mediante ping (ICMP) no es eficaz. Por ese motivo, la siguiente exposición IP de anycast dejará de responder a las solicitudes ICMP a partir de enero de 2020. Para medir el rendimiento de la red de forma eficaz, Microsoft recomienda la [herramienta Desesmentación de red.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Para probar las conexiones de Internet a la red de Microsoft, se recomienda realizar pruebas con los siguientes VIP de los Skype Empresarial multimedia. Anycast *VIP se*  resolverá en una dirección IP de un Media Relay en un sitio perimetral de red de Microsoft que esté más cerca de la ubicación de prueba.
  
||||
|:-----|:-----|:-----|
|**Dirección IP** <br/> |**Tipo** <br/> |**Ubicación** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP de Anycast para todo el mundo  <br/> |
   
 **Estas son algunas recomendaciones de alto nivel que debe seguir para evaluar el rendimiento de la red:**
  
- Debe evaluar su red interna, así como las conexiones a Microsoft 365 o Office 365.
    
- Debe evaluar y recopilar datos de todas las redes durante un largo período de tiempo. Le recomendamos que realice las pruebas de rendimiento de red durante un mínimo de una semana, para que pueda ver los patrones de uso de todos los días laborables y horas. Esto le mostrará las horas punta.
    
- Debe tomar varias muestras de medidas de rendimiento de red. Le recomendamos que tome una medida cada 10 minutos desde un sitio de la compañía durante todo el período de tiempo que está recopilando datos. Para comparar los requisitos Skype Empresarial rendimiento de red en línea, tome el valor de medida del percentil 90 de este conjunto de datos de ejemplo. 
    
- Debe evaluar continuamente el rendimiento de la red. El uso de la red varía a lo largo del tiempo debido a los cambios en el patrón de uso, las nuevas aplicaciones basadas en la empresa que usan una gran cantidad de ancho de banda y los cambios en las ubicaciones físicas o organizativas de la empresa. Es importante que supervise continuamente el rendimiento de la red frente a estos requisitos y objetivos/umbrales de rendimiento de red y realice ajustes a tiempo para garantizar la calidad de medios Real-Time óptima. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medir el rendimiento de la red con máquinas virtuales de Azure
<a name="bkNetworkPerf"> </a>

En lugar de realizar pruebas con los sitios perimetrales de la red de Microsoft, hay soluciones de evaluación de red de Skype Empresarial clientes y partners que aprovechan la configuración de pruebas para los servicios en Microsoft Azure nube. En esas soluciones, las herramientas de evaluación de red prueban la latencia, la pérdida de paquetes y el vibración frente a puntos de conexión personalizados configurados como servicio en la nube de Azure. Como resultado, el tráfico de red de prueba viaja a través de un segmento de red adicional, que es la conexión dentro de la red de Microsoft entre los bordes de la red y los centros de datos de Azure que hospedan el servicio de evaluación de red.
  
Para esas soluciones de evaluación de red basadas en servicios de prueba hospedados en Azure. Se recomienda realizar la evaluación de red dentro de un país o región. Por ejemplo, para los sitios de clientes en el este de EE. UU., la evaluación debe realizarse en una instancia de servicio de prueba hospedada en la región del centro de datos de Azure, en el este de EE. UU.. 
  
A continuación se muestran los destinos de latencia (RTT) para la configuración de evaluación de red basada en servicios de Azure. Los destinos de latencia unía serán la mitad de los destinos RTT correspondientes. Los objetivos de pérdida de paquetes y vibración permanecen iguales que los definidos para las Skype pruebas basadas en Media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Región de clientes** <br/> |**Región de Azure** <br/> |**El perímetro de red: hora de ida y vuelta de Azure (RTT)** <br/> |**Su sitio: hora de ida y vuelta de Azure (RTT)** <br/> |
|Centro de EE. UU.  <br/> |Centro de EE. UU.  <br/> |99  <br/> |139  <br/> |
|Este de EE. UU.  <br/> |Este de EE. UU.  <br/> |86  <br/> |126  <br/> |
|Centro norte de EE. UU.  <br/> |Centro norte de EE. UU.  <br/> |97  <br/> |137  <br/> |
|Centro sur de EE. UU.  <br/> |Centro sur de EE. UU.  <br/> |94  <br/> |134  <br/> |
|Oeste de EE. UU.  <br/> |Oeste de EE. UU.  <br/> |94  <br/> |134  <br/> |
|Hawái EE. UU.  <br/> |Oeste de EE. UU.  <br/> |116  <br/> |156  <br/> |
|Canadá Central  <br/> |Canadá Central  <br/> |138  <br/> |178  <br/> |
|Canadá Este  <br/> |Canadá Este  <br/> |131  <br/> |171  <br/> |
|Norte de Europa  <br/> |Norte de Europa  <br/> |99  <br/> |139  <br/> |
|Europa occidental  <br/> |Europa occidental  <br/> |95  <br/> |135  <br/> |
|Asia oriental  <br/> |Asia oriental  <br/> |118  <br/> |158  <br/> |
|Sureste asiático  <br/> |Sureste asiático  <br/> |97  <br/> |137  <br/> |
|Japón Este  <br/> |Japón Este  <br/> |111  <br/> |151  <br/> |
|Japón Oeste  <br/> |Japón Oeste  <br/> |118  <br/> |158  <br/> |
|Brasil Sur  <br/> |Brasil Sur  <br/> |70  <br/> |110  <br/> |
|Australia Este  <br/> |Australia Este  <br/> |124  <br/> |164  <br/> |
|Australia Sureste  <br/> |Australia Sureste  <br/> |124  <br/> |164  <br/> |
|Central India  <br/> |Central India  <br/> |103  <br/> |143  <br/> |
|Sur de la India  <br/> |Sur de la India  <br/> |103  <br/> |143  <br/> |
|Oeste de la India  <br/> |Oeste de la India  <br/> |103  <br/> |143  <br/> |
|China Este  <br/> |China Este  <br/> |120  <br/> |160  <br/> |
|China North  <br/> |China North  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Calidad multimedia y ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute para Microsoft 365 o Office 365 es una conexión de red dedicada para conectarse a Microsoft 365 o Office 365. Ofrece a los clientes la capacidad de tener control sobre la ruta que toma su tráfico de red. Ya no tienen que preocuparse por el enrutamiento impredecible que ocurre en Internet, donde los datos son llevados por operadores, proveedores e ISP desconocidos. El tráfico de red que se envía a través de ExpressRoute se envía directamente a la red del partner de ExpressRoute a la red de Microsoft. Esto permite a los clientes tratar Microsoft 365 o Office 365 como si se encuentra en su propio centro de datos fuera del sitio con una conexión dedicada.
  
Azure ExpressRoute está disponible para todas las Microsoft 365 y Office 365 de licencias. Sin embargo, el complemento Premium Azure ExpressRoute es necesario para Microsoft 365 y Office 365 habilitar el enrutamiento global. Los clientes con al menos 500 puestos que implementen ExpressRoute pueden obtener el complemento *ExpressRoute* Premium sin gastos adicionales.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>¿ExpressRoute es necesario para una buena calidad multimedia?

Azure ExpressRoute no es un requisito para obtener la mejor calidad Skype Empresarial multimedia en línea. Sin embargo, es una de las opciones de implementación que le ayudan a asegurarse de que la conectividad en la nube cumple los Skype Empresarial o los umbrales de rendimiento de red.
  
Microsoft 365 y Office 365 son servicios seguros y de alto rendimiento que usan Internet. Seguimos invirtiendo en nuevas capacidades de seguridad y nodos perimetrales regionales para mejorar continuamente la seguridad y el rendimiento. Azure ExpressRoute no es un requisito para los servicios Microsoft 365 o Office 365, incluido Skype Empresarial Online. Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudará Microsoft 365 asegurarse de que la conectividad Microsoft 365 o Office 365 cumpla los requisitos de rendimiento de red de Skype Empresarial y garantiza la experiencia de calidad de medios en línea Skype Empresarial óptima.
  
Para Skype Empresarial Calidad multimedia en línea, es importante que la conexión entre los sitios de su empresa y los bordes de red de Microsoft cumpla los objetivos de rendimiento de los requisitos de rendimiento de red de un cliente [de Skype Empresarial a Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Network Edge y que la conexión entre los bordes de red y los bordes de red de Microsoft cumpla los objetivos de rendimiento de los requisitos de rendimiento de red desde el perímetro de red al perímetro de red de [Microsoft.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
También es importante que la conectividad de red física de su empresa, incluida su capacidad de conectividad interna de red y nube, acote el volumen máximo de tráfico multimedia. Azure ExpressRoute es una de las muchas formas que ayudarán a los clientes a garantizar que Skype Empresarial conectividad en la nube en línea cumpla con todos estos requisitos de rendimiento.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>¿ExpressRoute es necesario para sla de calidad de voz?

No, ExpressRoute no es necesario para Skype Empresarial sla de calidad de voz en línea. El SLA de calidad de voz de [Skype Empresarial](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) Online se aplica a cualquier llamada válida realizada por cualquier usuario del servicio de voz de Skype Empresarial Online dentro de la licencia y suscripción correctas que permite a ese usuario realizar cualquier tipo de llamada VoIP o RTC. Un SLA de calidad de voz debe incluir que se aborde todas las condiciones siguientes:
  
- Llamadas desde teléfonos IP certificados por Microsoft.
    
- Conexiones Ethernet cableadas.
    
- Problemas de calidad de voz debidos a problemas de Microsoft Network.
    
> [!NOTE]
> El SLA de calidad de voz excluye las llamadas en las que la baja calidad de la llamada se debe a problemas en redes que no son de Microsoft, incluido el partner de ExpressRoute y otras redes. 
  
### <a name="internet-or-azure-expressroute"></a>¿Internet o Azure ExpressRoute?

Antes de tomar una decisión sobre las opciones de conectividad de red para Skype Empresarial Online, los clientes deben evaluar su conectividad a Internet actual y de red en función de los requisitos de rendimiento de red descritos en Requisitos de rendimiento de red para conectarse a [Skype Empresarial Online.](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
Si el rendimiento de la red a través de la conexión a Internet actual está configurado para una capacidad suficiente durante la hora punta y cumple los requisitos de rendimiento de red de los sitios a los bordes de red de Microsoft y de los bordes de la red a los bordes de red de Microsoft, puede seguir usando la conectividad a Internet existente para conectarse a Skype Empresarial Online.
  
Para los sitios de empresa en los que no se cumplen los requisitos de rendimiento de red, le recomendamos encarecidamente que primero trabaje con los proveedores de servicios de red existentes para mejorar el rendimiento general de la red. Sin embargo, si aún no se cumplen, usar Azure ExpressRoute puede ayudar a garantizar que la conectividad en la nube de Skype Empresarial Online puede ayudarle a cumplir los requisitos de rendimiento de la red.
  
Azure ExpressRoute ofrece las siguientes ventajas adicionales:
  
- Un contrato de nivel de servicio (SLA) sobre la disponibilidad de la conexión entre su red y la red de Microsoft. ExpressRoute tiene un SLA de disponibilidad garantizado del 99,9 %.
    
- Ancho de banda planeado y garantizado necesario para Microsoft 365 y Office 365 servicios. Para ello, solo puede enviar Microsoft 365, Office 365 o Skype Empresarial mediante ExpressRoute y, después, hacer que el resto del tráfico de Internet pase por otros puntos de salida o entrada de Internet para su red.
    
- ExpressRoute está diseñado para conservar las marcas de QoS de DSCP entre su red y Microsoft Network.
    
Para obtener más información sobre el QoS de ExpressRoute y la planificación de capacidad, consulte [ExpressRoute y QoS en Skype Empresarial Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>¿Puedo configurar Azure ExpressRoute para Skype Empresarial solo en línea?

Sí, puede configurar Azure ExpressRoute para garantizar una conectividad de red excelente desde la red de su empresa a solo Skype Empresarial Online. Esto proporcionará la calidad de Real-Time multimedia más óptima para los usuarios, pero, a continuación, puede seguir conectándose a otros Microsoft 365 o Office 365 a través de Internet.
  
El protocolo Border Gateway (BGP) es un protocolo de enrutamiento en Internet que se usa para enrutar el tráfico de red a través de Internet. Está diseñado para intercambiar información de enrutamiento entre sistemas autónomos (AS) que se encuentran en Internet. Los valores de las comunidades BGP son etiquetas de atributo que se pueden aplicar a las rutas entrantes o salientes. Las comunidades BGP se usan a menudo para indicar al receptor como qué vínculo saliente usar para llegar a un destino determinado en función de la geografía, el tipo de servicio u otros criterios.
  
Con la compatibilidad de comunidades BGP, Microsoft etiquetará prefijos y rutas con los valores de comunidad BGP adecuados en función del servicio al que pertenezcan. Microsoft etiquetará prefijos anunciados mediante emparejamiento público y emparejamiento de Microsoft con valores de comunidad BGP adecuados que indiquen la región en la que se hospedan los prefijos. Puede confiar en los valores de la comunidad para tomar decisiones de enrutamiento adecuadas para ofrecer un enrutamiento óptimo. Puede usar el valor de Skype Empresarial comunidad BGP en línea para configurar una conexión de ExpressRoute solo para Skype Empresarial Online. Puede obtener más información en Requisitos de enrutamiento [de ExpressRoute.](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Escenarios de conectividad de ExpressRoute para Skype Empresarial Online
<a name="bkNetworkPerf"> </a>

Si ha decidido que ExpressRoute basado en las recomendaciones anteriores es para usted, estas son las recomendaciones sobre dónde y cuántas conexiones de ExpressRoute debe obtener.
  
### <a name="online-only-deployment---single-site"></a>Implementación solo en línea: un solo sitio

Si todos los usuarios usan el servicio Skype Empresarial Online y sus oficinas están centradas en una única ubicación física y decide implementar Azure ExpressRoute, debe configurar una única conexión ExpressRoute entre el sitio de su empresa a la ubicación de emparejamiento de [ExpressRoute](/azure/expressroute/expressroute-locations)más cercana.
  
En el siguiente gráfico se muestra un ejemplo de este tipo de implementación. Para este ejemplo, Contoso es una universidad ubicada en Orlando, FL. Contoso tiene 10 000 profesores y alumnos. Las pruebas de Internet desde su ubicación a sitios perimetrales de Microsoft mostraron una pérdida de paquetes superior al 5 % durante las horas pico de clase. Han decidido obtener una conexión dedicada a Microsoft 365 o Office 365 con ExpressRoute con ancho de banda sobre aprovisionado para que puedan evitar la congestión de la red para Microsoft 365 o Office 365 especialmente para Skype Empresarial Online Real-Time tráfico. Se conectan a la nube de Microsoft a través de ExpressRoute en el sitio meetme de Atlanta, GA.
  
![Sitio único de ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implementación solo en línea: varios sitios en el mismo continente

Si su empresa usa los servicios de Skype Empresarial Online desde varias oficinas de la misma región o continente y ha elegido implementar Azure ExpressRoute, se recomienda conectar su sitio principal a través de ExpressRoute y, opcionalmente, agregar emparejamiento de ExpressRoute adicional para otras ubicaciones que no cumplan los objetivos de rendimiento de red recomendados.
  
En el siguiente ejemplo, Contoso es una compañía de servicios de viajes de Estados Unidos con sede en Nueva York pero que tiene otras oficinas en todos los Estados Unidos. Sus oficinas están conectadas a través de una WAN que usa MPLS para conectarse a Microsoft 365 o Office 365. Inicialmente, configuraron una conexión ExpressRoute desde su enrutador de Internet en Hoboken, Nueva Jersey, al sitio de MeetMe de Nueva York. 
  
Con esta configuración, el tráfico de red desde la mayoría de sus sitios al sitio Microsoft Network (sitio de Nueva York Edge) puede cumplir los objetivos de rendimiento de red de conexión de cliente de Skype Empresarial que se describen en Requisitos de rendimiento de red de un cliente Skype Empresarial a [Microsoft Network Edge.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Sin embargo, la latencia entre las oficinas de la costa oeste de Contoso a Nueva York supera los 50 ms de un solo sentido. Además, Honolulu es la segunda oficina más grande para Contoso, la latencia de Honolulu a Nueva York supera los 80 ms de un solo sentido. Para garantizar una buena calidad de medios para los usuarios de esas oficinas, Contoso decidió agregar una conexión ExpressRoute de la costa oeste entre su sitio de San José y el sitio de MeetMe de Silicon Valley ExpressRoute.
  
![Multis sitios de Express Router en el mismo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implementación solo en línea: varios sitios en diferentes continentes

Si todos los usuarios usan el servicio de Skype Empresarial Online y sus oficinas están en varias ubicaciones físicas en varios continentes, si decide implementar Azure ExpressRoute, debe configurar al menos una conexión ExpressRoute para cada continente entre el sitio principal de cada continente a su ubicación de emparejamiento de [ExpressRoute](/azure/expressroute/expressroute-locations)más cercana. Dependiendo del costo y de la ventaja, puede elegir implementar conexiones expressroute adicionales desde sitios donde no se cumplen los objetivos de rendimiento de red.
  
En el siguiente ejemplo, Contoso es un gran bufete de abogados corporativos con oficinas en las principales ciudades de Norteamérica y Europa. En función de su conexión a Internet y su evaluación de rendimiento de red interna, Contoso decidió implementar dos conexiones ExpressRoute en Norteamérica y un único circuito ExpressRoute para todas sus oficinas europeas.
  
![ExpressRoute con varios sitios y continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implementación híbrida

Si tiene una implementación local de Lync o Skype Empresarial y elige implementar una integración híbrida de Skype Empresarial Online, le recomendamos que si decide implementar Azure ExpressRoute, tenga al menos una conexión ExpressRoute para cada sitio local de Lync o Skype Empresarial Edge y al menos una conexión ExpressRoute para cada continente con oficinas. En función de los costos frente a los beneficios, para cada continente puede elegir implementar conexiones expressroute adicionales desde oficinas en las que no se cumplen los objetivos de rendimiento de red.
  
Si tiene una implementación local Skype Empresarial implementación, debe seguir la Guía de planeación e implementación del servidor [perimetral.](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md) En concreto, los servidores perimetrales deben ser accesibles desde fuera de la red. Esto suele lograrse asignando una dirección IP pública enrutable al servidor perimetral o mediante la traducción de direcciones de red (NAT).
  
En el ejemplo siguiente, Contoso tiene una implementación local existente Skype Empresarial Telefonía IP empresarial implementación. Desean migrar usuarios locales a Microsoft 365 o Office 365 en línea. También han decidido usar una implementación híbrida para que puedan seguir usando su infraestructura RTC existente para todos los usuarios locales y en línea. El centro de datos local de Contoso y Skype Empresarial servidores perimetrales están en Chicago. Para su implementación, Contoso decidió configurar una conexión de ExpressRoute entre su centro de datos de Chicago y Chicago ExpressRoute. También agregaron una conexión ExpressRoute de la costa oeste para prestar un mejor servicio a su oficina de Honolulu.
  
![ExpressRoute Híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implementación en línea con Cloud Connector Edition

Skype Empresarial Online Cloud Connector Edition es una oferta híbrida que consta de un conjunto de máquinas virtuales (VM) empaquetadas que implementan conectividad RTC local. Al implementar una topología de Skype Empresarial Server mínima en un entorno virtualizado, podrá enviar y recibir llamadas con fijos y teléfonos móviles a través de la infraestructura de voz RTC local existente.
  
Si decide implementar Azure ExpressRoute y Cloud Connector Edition, le recomendamos que configure al menos una conexión de Express Route para cada continente entre el sitio principal de cada continente a su ubicación de emparejamiento de [ExpressRoute](/azure/expressroute/expressroute-locations)más cercana. Según el costo y la ventaja, para cada continente puede elegir implementar conexiones ExpressRoute adicionales desde sitios en los que no se cumplen los objetivos de rendimiento de red.
  
Si tiene una implementación local Skype Empresarial, debe seguir la Guía de planeación [para Skype for Business Edición de conector de nube](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md). En concreto, los servicios perimetrales y perimetrales de Access deben tener asignadas direcciones IP públicas y centros de datos accesibles Microsoft 365 o Office 365 de datos.
  
En el ejemplo siguiente, Contoso es una firma de contabilidad europea con presencia en algunos países y ciudades europeas importantes. Cuando se suscribieron a Skype Empresarial Online para todas sus necesidades de colaboración, decidieron poner un conector en la nube para cada país que tengan una ubicación física para seguir usando sus contratos de infraestructura RTC y operadores que ya existen. En función de las pruebas de todos sus sitios y del perímetro de red de Microsoft, determinaron que una única conexión ExpressRoute en Londres ayudará a cumplir los objetivos de rendimiento de red de conexión de cliente de Skype Empresarial que se describen en Requisitos de rendimiento de red de un cliente Skype Empresarial a [Microsoft Network Edge.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A continuación se muestra otra opción de implementación para Contoso. En este caso, decidieron configurar una conexión ExpressRoute en cada sitio donde se implementa un conector en la nube. 
  
![Conector en la nube de ExpressRoute Dos.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)

  
