---
title: Planificar los requisitos de red para Skype Empresarial 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Summary: Review the network component considerations below before implementing Skype for Business Server 2015.'
ms.openlocfilehash: 3d3fd2141da93a9b0b866fe44e2ed8dee6942f3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-network-requirements-for-skype-for-business-2015"></a>Planificar los requisitos de red para Skype Empresarial 2015
 
**Summary:** Review the network component considerations below before implementing Skype for Business Server 2015.
  
The information in these topics is also discussed in the whitepaper [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) with additional details and depth. While the content refers explicitly to Lync 2010 and Lync 2013, the considerations for Skype for Business Server 2015 are unchanged.
  
Likewise, if your network involves wi-fi as well as wired access, the whitepaper [Delivering Lync 2013 Real-Time Communications over Wi-Fi](http://www.microsoft.com/en-us/download/details.aspx?id=36494) is a good reference and is equally applicable to Skype for Business Server 2015.
  
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

The network adapter of each server in the Skype for Business Server topology must support at least 1 gigabit per second (Gbps). In general, you should connect all server roles within the Skype for Business Server topology using a low latency and high bandwidth local area network (LAN). El tamaño de la LAN depende del tamaño de la topología: 
  
- In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.
    
- In Enterprise Edition topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.
    
Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.
  
## <a name="audiovideo-network-requirements"></a>Requisitos de red para el audio y vídeo
<a name="AV_req"> </a>

Network requirements for audio/video (A/V) in a Skype for Business Server deployment include the following:
  
- If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the  _external_ firewall to perform network address translation (NAT). You can't configure the _internal_ firewall to perform NAT. For details, see [Determining Firewall and 50k Port Range Requirements](http://technet.microsoft.com/library/3b849dc7-175d-40d1-820d-80e6ade6d332.aspx).
    
    > [!IMPORTANT]
    > If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on the Edge Servers and you can't use NAT for the servers or the pool at your NAT-capable device (for example, a firewall appliance or LAN switch. For details, see [Port Summary - Scaled Consolidated Edge with Hardware Load Balancers](http://technet.microsoft.com/library/91213b1e-f875-464b-83e8-fe3a351595a4.aspx). 
  
- Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente. 
    
- Si usa el protocolo de seguridad de Internet (IPsec), recomendamos deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. For details, see [IPsec Exceptions](http://technet.microsoft.com/library/241f1eca-6f2f-44de-90b1-2cb659cbe27c.aspx).
    
Para proporcionar una calidad óptima de los medios, siga este procedimiento:
  
- Aprovisione los vínculos de red para admitir un rendimiento de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo (en caso de estar habilitados) durante los períodos de uso máximo. Una sesión bidireccional de audio o de vídeo usa dos secuencias, por lo que una conexión de audio o de vídeo necesitará 130 Kbps para cubrir cada secuencia. Video will likewise use 1000 Kbps total to carry an upstream and downstream connection. 
    
- To cope with unexpected spikes in traffic and increased usage over time, Skype for Business Server media endpoints can adapt to varying network conditions and support three times the throughput for audio and video while still maintaining acceptable quality. Pero, no se puede dar por sentado que esta capacidad de adaptación enmascarará el problema cuando una red esté mal aprovisionada. In an under-provisioned network, the ability of the Skype for Business Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.
    
- En el caso de los vínculos de red en los que el aprovisionamiento resulta muy costoso y difícil, puede que se vea obligado a considerar un aprovisionamiento para un volumen de tráfico menor. In this scenario, let the elasticity of the Skype for Business Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality. También habrá una disminución en el margen que normalmente está disponible para absorber los picos de tráfico repentinos.
    
- En el caso de los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN de muy poca calidad), considere la posibilidad de deshabilitar el vídeo para algunos usuarios.
    
- Aprovisione la red para asegurar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) con carga máxima. Latency is the one network impairment that Skype for Business Server media components can't reduce, and it is important to find and eliminate the weak points.
    
- For servers that are running antivirus software, include all servers that are running Skype for Business Server in the exception list to provide optimal performance and audio quality. 
    
## <a name="conferencing-network-requirements"></a>Requisitos de red de la conferencia
<a name="Conf_req"> </a>

The bandwidth used to download conference content from the Internet Information Services (IIS) server depends on the size of the content. Puede optar por supervisar el uso real y ajustar la planeación del ancho de banda según convenga.
  
## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia
<a name="Conf_req"> </a>

An important part of network planning is ensuring that your network can handle the media traffic generated by Skype for Business Server. Esta sección le ayudará a planear dicho tráfico multimedia. 
  
### <a name="media-traffic-network-usage"></a>Uso de red de tráfico de medios
<a name="Net_req"> </a>

El uso del ancho de banda de tráfico multimedia puede resultar difícil de calcular por la cantidad de variables distintas, como el uso de códecs, la resolución y los niveles de actividad. El uso del ancho de banda es una función del códec usado y la actividad de la secuencia, y ambos pueden variar entre escenarios. The following table lists the audio codecs typically used in Skype for Business Server scenarios.
  
**Audio codec bandwidth**

|**Audio codec**|**Scenario**|**Audio payload bit rate (KBPS)**|**Bandwidth audio payload and IP header only (Kbps)**|**Bandwidth audio payload, IP header, UDP, RTP and SRTP (Kbps)**|**Bandwidth audio payload, IP header, UDP, RTP, SRTP and forward error correction (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ancha de RTAudio  <br/> |Punto a punto  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda estrecha de RTAudio  <br/> |Punto a punto, RTC  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferencia  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 estéreo  <br/> |Punto a punto, conferencias  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |RTC, conferencias  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferencia  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|SILK wideband/narrowband  <br/> |Punto a punto  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |
   
Las cantidades del ancho de banda de la tabla anterior se basan en los paquetes de 20 ms (50 paquetes por segundo) y para los códecs Siren y G.722 se incluyen las sobrecargas adicionales del protocolo de transporte seguro en tiempo real (SRTP) de los escenarios de conferencia y asumen que la secuencia está 100 % activa. La corrección de error de reenvío (FEC) se utiliza de forma dinámica cuando existe una pérdida de paquetes en el vínculo para ayudar a mantener la calidad de la secuencia de audio. 
  
La versión estéreo del códec G.722 se utiliza en los sistemas basados en el sistema de la Sala de reuniones de Lync, que utiliza un micrófono estéreo o un par de micrófonos mono para permitir que los oyentes puedan distinguir mejor a varios hablantes en la sala de reuniones.
  
**Video Resolution Bandwidth**

|**Video codec**|**Resolution and aspect ratio**|**Maximum video payload bit rate (Kbps)**|**Minimum video payload bit rate (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424 x 240 (16:9))  <br/> 320 x 240 (4:3  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960 x 540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920 x 1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |
   
Para el vídeo, el códec predeterminado es el estándar de codificación de vídeo avanzado H.264/MPEG-4 Parte 10, junto con sus extensiones de codificación de vídeo escalable. To maintain interoperability with legacy clients, the RTVideo codec is still used for peer-to-peer calls between Skype for Business Server and legacy clients. In conference sessions with both Skype for Business Server and legacy clients the Skype for Business Server endpoint may encode the video using both video codecs and send the H.264 bitstream to the Skype for Business Server clients and the RTVideo bitstream to legacy clients.
  
El ancho de banda necesario depende de la resolución, la calidad, la velocidad de fotogramas y los movimientos o cambios de la imagen. Para cada resolución existen dos secuencias de bits interesantes:
  
- **Maximum payload bit rate** This is the bit rate that an endpoint will use for resolution at the maximum frame rate. Es el valor que permite la máxima calidad de vídeo y de sonido.
    
- **Minimum payload bit rate** This is the bit rate below which a Skype for Business Server endpoint will switch to the next lower resolution. Para garantizar una determinada resolución, la velocidad de bits de carga de vídeo disponible no tiene que ser menor que esta velocidad de bits mínima para dicha resolución. Este valor le ayuda a comprender el valor mínimo posible en los casos en los que la velocidad de bits máxima no está disponible o no resulta práctica. Para algunos usuarios, esta baja velocidad de bits de vídeo puede considerarse una experiencia de vídeo no aceptable, por lo que aconsejamos precaución al considerar estas velocidades de bits mínimas de vídeo. Tenga en cuenta que en las escenas de vídeo estáticas o invariables, la velocidad de bits real puede descender temporalmente por debajo de la velocidad de bits mínima.
    
Skype for Business Server supports many resolutions. This allows Skype for Business Server to adjust to different network bandwidth and receiving client capabilities. The default aspect ratio for Skype for Business Server is 16:9. The legacy 4:3 aspect ratio is still supported for webcams which don't allow capture in the 16:9 aspect ratio.
  
La FEC de vídeo siempre se incluye en la velocidad de bits de carga de vídeo cuando se usa para que no existan valores independientes con la FEC de vídeo y sin esta. 
  
Los extremos no hacen fluir los paquetes de audio y vídeo continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares: 
  
- Los extremos solo envían secuencias de audio cuando los usuarios hablan.
    
- Ambos participantes reciben secuencias de audio.
    
- Si se utiliza el vídeo, ambos extremos envían y reciben secuencias de vídeo durante la llamada.
    
- Para las escenas de vídeo estáticas, la velocidad de bits real puede llegar a ser considerablemente lenta de forma temporal, ya que el códec de vídeo omitirá la codificación de las regiones del vídeo sin cambios desde la muestra anterior.
    
En un escenario de conferencias:
  
- Los extremos envían secuencias de audio solo cuando los usuarios hablan.
    
- Todos los participantes reciben secuencias de audio.
    
- Si se utiliza el vídeo, los participantes pueden recibir hasta cinco secuencias de vídeo de recepción y una panorámica (por ejemplo, con una relación de aspecto de 20:3). De forma predeterminada, las cinco secuencias de vídeo de recepción se basan en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual los participantes de los que desean recibir una secuencia de vídeo. Si el multivídeo está habilitado, los requisitos de resolución y de ancho de banda de cada secuencia de vídeo serán menores.
    
- Each participant that turns on the user's send video stream will send one or more video streams. Skype for Business Server has the capability of sending up to five video streams to optimize the video quality for all the receiving clients. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la CPU, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de vídeo. El caso más común es el de H.264 y una secuencia de vídeo de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de vídeo diferente) se envían para acomodar diferentes solicitudes de receptor. 
    
Además del ancho de banda necesario para el tráfico del protocolo de transporte seguro en tiempo real (RTP) para los medios de audio o vídeo, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar de estadísticas y del control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda de la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo usado para RTCP y difieren entre las secuencias de audio y vídeo por las diferencias en los datos de control. 
  
**RTCP Bandwidth**

|**Media**|**RTCP maximum bandwidth (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vídeo (solo se envía/recibe H.264 o RTVideo)  <br/> |10  <br/> |
|Vídeo (se envía/recibe H.264 y RTVideo)  <br/> |15  <br/> |
   
Para la planeación de la capacidad, las dos estadísticas siguientes son de interés:
  
- **Maximum bandwidth without FEC** The maximum bandwidth that a stream will consume. This includes the typical activity of the stream and the typical codec that is used in the scenario without FEC. This is the bandwidth when the stream is at 100% activity and there is no packet loss triggering the use of FEC. This is useful for computing how much bandwidth must be allocated to allow the codec to be used in a given scenario. FEC is not expected to be a requirement on a managed network.
    
- **Maximum bandwidth with FEC** The maximum bandwidth that a stream consumes. This includes the typical activity of the stream and the typical codec that is used in the scenario with FEC. This is the bandwidth when the stream is at 100% activity and there is packet loss triggering the use of FEC to improve quality. This is useful for computing how much bandwidth must be allocated to allow the codec to be used in a given scenario and allow the use of FEC to preserve quality under packet-loss conditions.
    
The following tables also list an additional bandwidth value, **Typical bandwidth**. This is the average bandwidth that a stream consumes. This includes the typical activity of the stream and the typical codec that is used in the scenario. This bandwidth can be used for approximating how much bandwidth is being consumed by media traffic at a specific time, but should not be used for capacity planning, because individual calls will exceed this value when the activity level is greater than average. The typical video stream bandwidth in the tables below is based on a mix of different video resolutions as observed in measured customer data, and smaller installations are likely to have actual numbers that differ from the table data. For example, in peer-to-peer sessions most users would use the default video render window whereas some percentage of users would increase or maximize the Skype for Business Server application to allow better video resolutions.
  
En las siguientes tablas se proporcionan los valores para los distintos escenarios.
  
**Audio/Video Capacity Planning for Peer-to-Peer Sessions**

|**Media**|**Codec**|**Typical stream bandwidth (Kbps)**|**Maximum stream bandwidth without FEC**|**Maximum stream bandwidth with FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda ancha de RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |Banda ancha SILK  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Main video when calling Skype for Business Server endpoints  <br/> |H.264  <br/> |460  <br/> |4010 (para una resolución máxima de 1920 x 1080)  <br/> |Ya incluido  <br/> |
|Main video when calling Lync 2010 or Office Communicator 2007 R2 endpoints  <br/> |RTVideo  <br/> |460  <br/> |2510 (para una resolución máxima de 1920 x 720)  <br/> |Ya incluido  <br/> |
|Panoramic video when calling Skype for Business Server endpoints  <br/> |H.264  <br/> |190  <br/> |2010 (para una resolución máxima de 1920 x 288)  <br/> |Ya incluido  <br/> |
|Panoramic video when calling Lync 2010 endpoints  <br/> |RTVideo  <br/> |190  <br/> |510 (para una resolución máxima de 1920 x 144)  <br/> |Ya incluido  <br/> |
   
**Audio/Video Capacity Planning for Conferences**

|**Media**|**Typical codec**|**Typical stream bandwidth (Kbps)**|**Maximum stream bandwidth without FEC**|**Maximum stream bandwidth with FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Recepción principal de vídeo  <br/> |H.264 y RTVideo¹  <br/> |260  <br/> |8015  <br/> |No aplicable  <br/> |
|Envío principal de vídeo  <br/> |H.264 y RTVideo  <br/> |270  <br/> |8015  <br/> |No aplicable  <br/> |
|Recepción de vídeo panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2010 (para una resolución máxima de 1920 x 288)  <br/> |No aplicable  <br/> |
|Envío de vídeo panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2515 ²  <br/> |No aplicable  <br/> |
   
1. RT Video is sent in addition to H.264 when Lync 2010 clients are connected to the conference.
  
2. If there are multiple streams, they dynamically share the allocated bandwidth.
  
Para el vídeo principal, el ancho de banda de secuencia típico es el ancho de banda agregado sobre todas las secuencias de vídeo recibidas, mientras que la secuencia máxima es el ancho de banda sobre todas las secuencias de vídeo enviadas. Aun con varias secuencias de vídeo, el ancho de banda típico para vídeo es más pequeño que en el escenario punto a punto, ya que muchas conferencias de vídeo utilizan el uso compartido de contenidos, que hace que las ventanas de vídeo sean más pequeñas y, por lo tanto, las resoluciones de vídeo son inferiores. El ancho de banda máximo de carga de vídeo agregada compatible es de 8000 Kbps para las secuencias de envío y de recepción que se utilizarían (por ejemplo, si hay dos secuencias de vídeo entrantes de 1920 x 1080 p). Los valores máximos se ven con poca frecuencia en las implementaciones reales.
  
When building out a multiparty conference that uses the gallery view feature, bandwidth utilization increases initially as participants join, then decreases as resolutions are dropped to fit within the maximum. 
  
||**2 Participants**|**3 Participants**|**4 Participants**|**5 Participants**|**6 Participants**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluciones máx. recibidas** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Velocidad de bits media total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocidad de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |
   
El ancho de banda de secuencia típico para los vídeos panorámicos se basa en los dispositivos que solo transmiten en secuencias un vídeo panorámico de hasta 960 x 144. Tenga en cuenta que el ancho de banda de secuencia típico puede aumentar al utilizar dispositivos con un vídeo panorámico de 1920 x 288. 
  
**Audio Capacity Planning for PSTN**

|**Media**|**Typical codec**|**Typical stream bandwidth (Kbps)**|**Maximum stream bandwidth without FEC**|**Maximum stream bandwidth with FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (this includes PSTN participants in conferences)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |
   
Las cifras de ancho de banda de red de estas tablas representan solamente tráfico unidireccional; incluyen 5 Kpbs para sobrecarga de tráfico RTPC de cada secuencia. 
  
## <a name="managing-quality-of-service"></a>Administración de la Calidad de servicio (QoS)
<a name="man_QOS"> </a>

La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en las redes en las que el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.
  
> [!NOTE]
> Como regla general, la QoS se aplica solamente a las sesiones de comunicación de la red interna. Al implementar la QoS necesita configurar los servidores y los enrutadores para que admitan el marcado de paquetes de un modo especial que puede que no se admita en Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no existe ninguna garantía de que se configure de la misma manera que configuró el servicio. Si utiliza MPLS tendrá que colaborar junto con su proveedor de MPLS. 
  
Skype for Business Server does not require QoS, but it is strongly recommended. If you experience packet loss issues on the network your available solutions are to add more bandwidth or to implement QoS. Si no puede agregar más ancho de banda, la implementación de la QoS puede ser la única solución al problema.
  
Skype for Business Server offers full support for QoS: that means that organizations that are already using QoS can easily integrate Skype for Business Server into their existing network infrastructure. Para ello, es necesario llevar a cabo los siguientes pasos:
  
- [Enabling QoS for Non-Windows Devices](http://technet.microsoft.com/library/26f793df-aef8-4028-9e3b-6c2c37ea61b9.aspx). De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Although you can use Skype for Business Server to enable and disable QoS for devices, you typically can't use the product to change the DSCP codes used by these devices.
    
- [Configuring Port Ranges for Your Conferencing, Application, and Mediation Servers](http://technet.microsoft.com/library/4d6eaa5d-0127-453f-be6a-e55384772d83.aspx). Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo. By using Skype for Business Server you do not enable or disable QoS by setting a property value to True or to False. En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos y al crear y aplicar posteriormente una directiva de grupo. If you later decide not to use QoS you can "disable" QoS by removing the appropriate Group Policy objects.
    
- [Configuring Port Ranges for Your Edge Servers](http://technet.microsoft.com/library/6f0ae442-6624-4e3f-849a-5b9e387fb8cf.aspx). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.
    
- [Configuring Port Ranges for Your Microsoft Lync Clients](http://technet.microsoft.com/library/287d5cea-7ada-461c-9b4a-9da2af315e71.aspx). Estos intervalos de puertos solo se aplican a equipos cliente y, por lo general, no son los mismos que los intervalos de puertos configurados en los servidores.
    
- [Configuring a Quality of Service Policy for Your Conferencing, Application, and Mediation Servers](http://technet.microsoft.com/library/8adcbbc5-c9f5-476d-ab7f-72e61859cacf.aspx). Estas directivas determinan los códigos DSCP que se aplican a diferentes tipos de paquetes.
    
- [Configuring a Quality of Service Policy for Your A/V Edge Servers](http://technet.microsoft.com/library/119ee1f5-45b9-40ba-98e5-c694dd2fc5c2.aspx). This should only be done for the internal side of your Edge servers. That's because QoS is designed for use on your internal network and not on the Internet.
    
- [Configuring Peer-to-Peer Quality of Service Policies for Clients Running on Windows 7 or Windows 8](http://technet.microsoft.com/library/efff2b98-b3fb-4183-a4f0-329a9105ce2c.aspx). Note that Skype for Business Server does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.
    
- [Configuring Quality of Service on Microsoft Lync Phone Edition Devices](http://technet.microsoft.com/library/a6eb2620-a512-4ab6-bdfd-eb76be43bbfe.aspx). By default, QoS is enabled for Lync Phone Edition devices. Pero, tal vez desee cambiar el valor predeterminado de DSCP a fin de garantizar que todos los paquetes de audio de la organización usen el mismo código DSCP.
    
> [!NOTE]
> If you are using Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing QoS on that platform. For more information, see [Network QoS Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379). 
  
QoS is also discussed in the whitepaper [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) with additional details and depth. While the content refers explicitly to Lync 2010 and Lync 2013, the considerations for Skype for Business Server 2015 are unchanged.
  
## <a name="see-also"></a>Vea también
<a name="man_QOS"> </a>

#### 

[Plan for IPv6 in Skype for Business](ipv6.md)
  
[Load balancing requirements for Skype for Business](load-balancing.md)
  
[DNS requirements for Skype for Business Server 2015](dns.md)
  
[Port and protocol requirements for servers](ports-and-protocols.md)

