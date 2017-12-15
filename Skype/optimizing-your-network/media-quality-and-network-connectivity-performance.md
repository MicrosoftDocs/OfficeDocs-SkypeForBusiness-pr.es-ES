---
title: "Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "Este tema define el conjunto de requisitos de rendimiento de red de los servicios de Skype Empresarial Online. Además, aborda la elección de Internet o ExpressRoute para la conectividad entre su red y Skype Empresarial Online, según su evaluación de la conectividad de la red. Si ha decidido implementar Azure ExpressRoute para proporcionar conectividad dedicada a Office 365, este documento también le orientará sobre cómo planificar las conexiones ExpressRoute en distintos escenarios de implementación de Skype Empresarial Online."
---

# Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online

Este tema define el conjunto de requisitos de rendimiento de red de los servicios de Skype Empresarial Online. Además, aborda la elección de Internet o ExpressRoute para la conectividad entre su red y Skype Empresarial Online, según su evaluación de la conectividad de la red. Si ha decidido implementar Azure ExpressRoute para proporcionar conectividad dedicada a Office 365, este documento también le orientará sobre cómo planificar las conexiones ExpressRoute en distintos escenarios de implementación de Skype Empresarial Online.
  
La calidad de medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) sobre IP queda afectada de forma muy considerable por la calidad de la conectividad de la red de un extremo a otro. Para obtener una calidad de medios óptima en Skype Empresarial Online, es importante asegurarse de que hay una conexión de alta calidad entre la red de su compañía y Skype Empresarial Online. La mejor forma de lograrla es configurar la red interna y la conectividad con la nube de acuerdo con la capacidad de su red. De esta forma, podrá adaptarse al volumen de tráfico pico de Skype Empresarial Online de todas las conexiones.
  
Azure ExpressRoute no es un requisito de los servicios de Office 365 y, por lo tanto, tampoco para Skype Empresarial Online. Sin embargo, Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudarán a garantizar que la conectividad con Office 365 cumple los requisitos de rendimiento de red de Skype Empresarial, así como a disfrutar de una experiencia de calidad de medios óptima para Skype Empresarial Online.
  
> [!TIP]
> Aunque este tema proporciona orientación general sobre el rendimiento de las redes, ofrecer una descripción detallada de cómo evaluar su red queda fuera del ámbito de este documento. Consulte las [soluciones de socios de Skype Empresarial](http://partnersolutions.skypeforbusiness.com/) para encontrar una lista de socios de Skype Empresarial Online que le pueden ayudar en la medición del rendimiento de red en el marco de una evaluación de red completa y exhaustiva.
  
## Requisitos de conectividad de red para Skype Empresarial Online

### Factores que afectan a la calidad de medios de Skype Empresarial Online

Hay diversos factores que afectan a la calidad de los medios en tiempo real (audio, vídeo y uso compartido de aplicaciones), entre los cuales se cuentan los dispositivos utilizados, el entorno y la conectividad de la red. 
  
#### Dispositivos

En una sesión de medios en tiempo real, los dispositivos que utilizan todos los participantes para capturar y procesar los medios, como los auriculares y cámaras web, afectan de forma importante a la calidad global del audio y el vídeo. Los dispositivos de audio y vídeo de menor calidad o que utilizan controladores incorrectos generan, respectivamente, sonido e imágenes de calidad reducida. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Aunque no se requieren dispositivos de medios de audio y vídeo certificados, es muy recomendable utilizarlos con Skype Empresarial para lograr una experiencia de medios óptima. Para obtener una lista de todos los dispositivos certificados para Skype Empresarial, consulte [Teléfonos y dispositivos para Skype Empresarial](https://technet.microsoft.com/en-us/office/dn947482). Además, puede utilizar [el panel de calidad de Skype Empresarial Online](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US), ubicado en el **Centro de administración de Skype Empresarial** para verificar que los dispositivos utilizados funcionan correctamente y controlar la calidad de medios de vídeo y audio.
  
> [!TIP]
> **Se requiere un dispositivo certificado para lograr una experiencia de calidad de medios óptima en Skype Empresarial**.
  
Es importante recordar que todo dispositivo de medios, cliente de Skype Empresarial y Skype Empresarial Server por los cuales se transmiten los medios en tiempo real introducen cierta cantidad de latencia. La latencia de procesamiento del software y el dispositivo, además de la de la red, afectan muy notablemente, sea de forma positiva o negativa, a la latencia global de un extremo a otro y a la experiencia del usuario final.
  
#### Entorno

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una perspectiva más clara de la experiencia de audio y vídeo del usuario, utilice las opciones ** Herramientas** > **Opciones** > **Dispositivo de audio** o **Dispositivo de vídeo** de la aplicación Skype Empresarial. De esta forma, podrá realizar cambios en el dispositivo en uso y personalizar su configuración. También puede comprobar la calidad de audio de una llamada haciendo clic en **Comprobar calidad de llamada**. Al hacer clic en esta opción, podrá informar de la calidad y los problemas detectados en la llamada de prueba.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### Network

La calidad de medios en tiempo real sobre IP queda afectada de forma muy considerable por la calidad de la conectividad de la red, pero en especial por la cantidad de:
  
- **Latencia:** el tiempo que se tarda en llevar un paquete IP del punto A al punto B a través de la red. Este retraso en la propagación por la red básicamente está vinculado a la distancia física entre los dos puntos y a la velocidad de la luz, e incluye la sobrecarga adicional que implican los diversos enrutadores entre ambos puntos. La latencia se mide según el tiempo de solo ida o el tiempo de ida y vuelta (RTT).
    
- **Pérdida de paquetes:** a menudo se define como un porcentaje de los paquetes que se pierden en un determinado espacio de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio. Pueden ser pérdidas menores de paquetes sueltos que apenas afecten al audio o pérdidas de ráfagas completas que causen graves cortes en el audio.
    
- **Vibración entre llegada de paquetes ( o, simplemente, vibración):** este es el promedio de cambio en el retraso entre la llegada de paquetes sucesivos. La mayoría de software de VoIP moderno, como Skype Empresarial, se puede adaptar a algunos niveles de vibración mediante el almacenamiento en búfer. Los participantes solo notan los efectos de la vibración cuando esta supera el almacenamiento en búfer.
    
> [!NOTE]
>  El almacenamiento en búfer para la vibración incrementa la latencia de un extremo a otro.
  
Si hay varias sesiones simultáneas de medios en tiempo real de Skype Empresarial Online (o tráfico de red generado por otros servicios de Office 365 y otras aplicaciones empresariales), es esencial garantizar que hay suficiente ancho de banda en toda la ruta de red que conecta su red con el servicio de Skype Empresarial Online. De esta forma se evita la congestión de la red y se garantiza que la calidad de medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) sea excelente. 
  
#### Implementación de Calidad de servicio (QoS) de un extremo a otro en redes congestionadas

Además, la congestión del tráfico en la red afecta muy negativamente a la calidad de medios. Para permitir que los paquetes de audio y vídeo viajen por la red de forma más rápida y se prioricen sobre otro tráfico de red en una red congestionada, se puede utilizar Calidad de servicio (QoS) para proporcionar una experiencia óptima al usuario final en comunicaciones de audio y vídeo.
  
La calidad de servicio le ofrece una forma de asignar prioridades más altas a los paquetes de red que contienen datos de audio o vídeo. Al asignar una prioridad mayor a estos paquetes, es más probable que las comunicaciones de audio y vídeo viajen por la red de forma más rápida y con menos interrupciones que sesiones de red de transferencia de archivos, navegación por la web o copia de seguridad de bases de datos. Esto se debe a que los paquetes de red utilizados para transferencias de archivos o copias de seguridad de bases de datos tienen asignados de forma predeterminada la prioridad "mejor esfuerzo", por lo que la congestión de red tendrá menor impacto. Si no asigna una prioridad mayor a los paquetes de medios (audio, vídeo y uso compartido de aplicaciones) y también los deja asignados como "mejor esfuerzo", estos también se procesarán con el resto de tráfico de red. Según el grado de congestión de la red, esto puede generar potencialmente una experiencia de calidad de audio y vídeo globalmente menor para los usuarios.
  
Se recomienda encarecidamente que implemente QoS de un extremo a otro en su red para garantizar que la congestión de red no tenga un impacto tan profundo. Sin embargo, todos los puntos de conexión a la red deben ser compatibles con QoS, lo que significa que todos deberán cumplir el marcado de QoS y la priorización de paquetes. Los servicios de Skype Empresarial Online cumplen el marcado de QoS y la priorización dentro de la red de Microsoft. Sin embargo, el tráfico enrutado a través de una conexión pública (como acceder a la red de Microsoft mediante Internet desde la red de su compañía) no conserva el marcado de QoS ni la priorización de paquetes. Las conexiones privadas de su red a Office 365 que utilizan [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) ofrecen una solución de implementación que conserva el marcado de QoS y la priorización de paquetes lo cual, a su vez, aumentará la calidad de audio y vídeo global de los usuarios finales.
  
## Requisitos de rendimiento de red para conectar con Skype Empresarial Online
<a name="bk_NetworkPerf"> </a>

Los medios en tiempo real de Skype Empresarial viajan a través de gran cantidad de dispositivos, aplicaciones cliente, software de servidor y redes distintas. La latencia de un extremo a otro de los medios en tiempo real es la cantidad total de latencia introducida a lo largo de todos los componentes y segmentos de red. La calidad de la conexión de red de un extremo a otro está determinada por el segmento de red con la peor calidad. Este segmento actúa como un cuello de botella para el tráfico de red.
  
El siguiente diagrama ilustra un flujo de audio de solo ida en una conferencia entre dos participantes de Skype Empresarial.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
En este escenario de conferencia, la ruta de medios comprende los siguientes segmentos de red:
  
1. **Conexión del Usuario 1 al perímetro de la red de Microsoft:** esto suele incluir una conexión de red como WiFi o Ethernet, la conexión WAN del Usuario 1 al punto de salida a Internet (el dispositivo del perímetro de su red) y la conexión a Internet desde el perímetro de su red al perímetro de la red de Microsoft.
    
2. **Conexión dentro de la red de Microsoft:** se produce entre el perímetro de la red de Microsoft y el centro de datos de Skype Empresarial Online, donde se utilizan los servidores de conferencia de A/V.
    
3. **Conexión dentro de la red de Microsoft:** se produce entre el centro de datos de Skype Empresarial Online y el perímetro de la red de Microsoft.
    
4. **Conexión del perímetro de la red de Microsoft al Usuario 2**: esto incluye la conexión a Internet del perímetro de su red al perímetro de la red de Microsoft, la conexión WAN del Usuario 2 al punto de salida a Internet (el perímetro de su red) y la conexión a la red (por ejemplo, WiFi o Ethernet).
    
Los siguientes diagramas muestran un desglose de los componentes y segmentos de red que participan en una llamada RTC de Skype Empresarial Online:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
En este escenario de llamada RTC, la ruta de medios transcurre por los siguientes segmentos de red:
  
1. **Conexión de un llamador mediante el cliente de Skype Empresarial al perímetro de la red de Microsoft:** esto suele incluir una conexión de red como WiFi o Ethernet, la conexión WAN del llamador desde el cliente de Skype Empresarial al punto de salida a Internet (el dispositivo del perímetro de su red) y la conexión a Internet desde el perímetro de su red al perímetro de la red de Microsoft.
    
2. **Conexión dentro de la red de Microsoft:** se produce entre el perímetro de Microsoft y el centro de datos de Skype Empresarial Online, donde se utiliza un servidor de mediación.
    
3. **Conexión dentro de la red de Microsoft:** se produce entre el centro de datos de Skype Empresarial Online y el perímetro de la red de Microsoft.
    
4. **Conexión entre la red de Microsoft y los socios proveedores de servicios RTC:** esta es una conexión que se utiliza para realizar una llamada RTC desde un cliente de Skype Empresarial que se encuentra fuera de la red de Microsoft.
    
### Requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de Microsoft
<a name="bk_SfBClienttoEdge"> </a>

Para obtener una calidad de medios de Skype Empresarial óptima, es necesario que la conexión de la red de su compañía al perímetro de la red de Microsoft se ajuste a los siguientes objetivos o umbrales de métricas. Este segmento de red incluye su red interna, todas las conexiones WiFi y Ethernet, todo el tráfico de sitio a sitio de la compañía que transcurre por una conexión WAN [por ejemplo, Multiprotocol Label Switching (MPLS)], así como las conexiones de Internet o ExpressRoute de asociados al perímetro de la red de Microsoft.
  
> [!CAUTION]
> **La conectividad entre un cliente de Skype Empresarial en la red de su compañía y los servicios de Office 365 debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latencia (solo ida)  <br/> |< 50 ms  <br/> |
|Latencia (RTT o tiempo de ida y vuelta)  <br/> |< 100 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |<10 % durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<1 % durante cualquier intervalo de 15 s  <br/> |
|Vibración entre llegada de paquetes  <br/> |<30 ms durante cualquier intervalo de 15 s  <br/> |
|Reordenación de paquetes  <br/> |<0,05 % de paquetes desordenados  <br/> |
   
 **Otros objetivos de rendimiento requeridos:**
  
- La red de Microsoft tiene más de 160 ubicaciones de perímetro en todo el mundo. Trabajamos con los principales proveedores de servicios de Internet (ISP) en todo el mundo mediante estos sitios perimetrales. El objetivo de la métrica de latencia asume que el sitio o sitios de su compañía y los perímetros de Microsoft están en el mismo continente.
    
- La conexión del sitio o sitios de su compañía al perímetro de la red de Microsoft incluye el acceso de red de primer salto, que puede ser WiFi u otra tecnología inalámbrica. 
    
- El objetivo de rendimiento de la red asume que existe una planificación adecuada de la calidad del servicio y el ancho de banda. En otras palabras, este objetivo se aplica directamente al tráfico de medios en tiempo real de Skype Empresarial cuando la conexión de red presenta un pico de carga.
    
### Requisitos de rendimiento de red desde el perímetro de su red al perímetro de la red de Microsoft
<a name="bk_YourNetworkEdge"> </a>

Los siguientes son los objetivos o umbrales del rendimiento de la red requeridos para una conexión entre el perímetro de su red y el perímetro de la red de Microsoft. Este segmento de la red excluye la red interna del cliente o WAN y está concebida para ofrecer orientación para realizar pruebas en el tráfico de red enviado por Internet o mediante una red asociada ExpressRoute. Asimismo, se puede utilizar para negociar un acuerdo de nivel de servicio (SLA) con el proveedor de ExpressRoute.
  
> [!CAUTION]
> **La conectividad entre el perímetro de la red de su compañía y el perímetro de la red de Microsoft debe cumplir los siguientes requisitos y umbrales de rendimiento de red.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latencia (solo ida)  <br/> |< 30 ms  <br/> |
|Latencia (RTT)  <br/> |< 60 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |<1 % durante cualquier intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |<0,1 % durante cualquier intervalo de 15 s  <br/> |
|Vibración entre llegada de paquetes  <br/> |<15 ms durante cualquier intervalo de 15 s  <br/> |
|Reordenación de paquetes  <br/> |<0,01 % paquetes desordenados  <br/> |
   
 **Otros objetivos de rendimiento requeridos:**
  
- El objetivo de rendimiento requiere que la conexión entre cualquiera de los perímetros de la red de su compañía y el perímetro de la red de Microsoft más cercano estén en el mismo continente.
    
- El objetivo de rendimiento de la red asume que existe una planificación adecuada de la calidad del servicio (QoS) y el ancho de banda. Este objetivo también se aplica directamente al tráfico de medios en tiempo real de Skype Empresarial cuando la conexión de red presenta un pico de carga. Para planificar adecuadamente la calidad del servicio y el ancho de banda, consulte [ExpressRoute y QoS en Skype Empresarial Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## Medición del rendimiento de la red
<a name="bk_NetworkPerf"> </a>

Puede medir el rendimiento real de la red desde cualquier sitio de red de la compañía hasta un perímetro de Microsoft, especialmente en lo que se refiere a la latencia y la pérdida de paquetes. Para ello, puede utilizar herramientas como ping, PSPinghttps://technet.microsoft.com/en-us/sysinternals/psping.aspx o tcpinghttp://www.elifulkerson.com/projects/tcping.php para realizar pruebas con un conjunto de servicios de relé multimedia que se ejecutan desde los sitios de los centros de datos y el perímetro de Microsoft. 
  
Para probar las conexiones de Internet a la red de Microsoft, se recomienda que realice la prueba con las siguientes VIP de los relés multimedia. La  *VIP Anycast*  resuelve a una dirección IP de un relé multimedia en el sitio perimetral de Microsoft más cercano a la ubicación donde se realizan las pruebas.
  
||||
|:-----|:-----|:-----|
|**Dirección IP** <br/> |**Tipo** <br/> |**Ubicación** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP global de Anycast  <br/> |
   
 **A continuación se enumeran algunas recomendaciones de alto nivel para evaluar el rendimiento de la red:**
  
- Debería evaluar la red interna además de las conexiones a Office 365.
    
- Debería recopilar y evaluar datos de todas sus redes durante un período amplio de tiempo. Se recomienda que realice pruebas de rendimiento de red durante un mínimo de una semana para poder ver los patrones de uso de todos los días y las horas laborables. De esta forma podrá ver las horas punta.
    
- Debería reunir varias muestras de mediciones de rendimiento de la red. Se recomienda realizar una medición en un sitio de la compañía cada 10 minutos durante todo el período de tiempo durante el que recabe datos. Para comparar los requisitos de rendimiento de red de Skype Empresarial Online, utilice los valores por debajo de 90% de este conjunto de datos de muestra. 
    
- Debería evaluar continuamente el rendimiento de la red. La utilización de la red varía a lo largo del tiempo debido a los cambios en los patrones de uso, las nuevas aplicaciones de empresa que utilizan gran cantidad de ancho de banda y los cambios organizativos o físicos de las ubicaciones de la compañía. Es importante que controle continuamente el funcionamiento de la red, comparándolo a estos requisitos, objetivos y umbrales de rendimiento de red. Asimismo, deberá realizar sin dilación los ajustes oportunos para garantizar una calidad de medios en tiempo real óptima. 
    
## Measuring Network Performance using Azure VMs
<a name="bk_NetworkPerf"> </a>

Instead of testing against the Microsoft network Edge sites, there are network assessment solutions from Skype for Business customers and partners that leverage testing setup for services in the Microsoft Azure cloud. In those solutions, the network assessment tools test latency, packet loss and jitter against custom endpoints set up as a service in the Azure cloud. As a result, the test network traffic travels through one additional network segment, which is the connection within the Microsoft network between the network edges and Azure data centers that hosts the network assessment service.
  
For those network assessment solutions based on Azure hosted testing services. We recommend performing the network assessment within country and/or region. For example, for customer sites in east U.S., the assessment should be performed against a testing service instance hosted in Azure's east US data center region. 
  
Below are the latency (RTT) targets for the Azure service based network assessment setup. The one-way latency targets will be half of the corresponding RTT targets. The packet loss and jitter goals stays the same as those defined for Skype Media Relay based testing.
  
|||||
|:-----|:-----|:-----|:-----|
|**Customer region** <br/> |**Azure region** <br/> |**Your network Edge - Azure Round-trip Time (RTT)** <br/> |**Your Site - Azure Round-trip Time (RTT)** <br/> |
|Central US  <br/> |Central US  <br/> |99  <br/> |139  <br/> |
|East US  <br/> |East US  <br/> |86  <br/> |1:26  <br/> |
|North Central US  <br/> |North Central US  <br/> |Excel 97  <br/> |1:37  <br/> |
|South Central US  <br/> |South Central US  <br/> |94  <br/> |1:34  <br/> |
|West US  <br/> |West US  <br/> |94  <br/> |1:34  <br/> |
|Hawaii US  <br/> |West US  <br/> |1:16  <br/> |156-  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |1:38  <br/> |178  <br/> |
|Canada East  <br/> |Canada East  <br/> |(*^13)\\1@  <br/> |1,71  <br/> |
|North Europe  <br/> |North Europe  <br/> |99  <br/> |139  <br/> |
|West Europe  <br/> |West Europe  <br/> |95  <br/> |-135  <br/> |
|Contacto de Asia Oriental  <br/> |Contacto de Asia Oriental  <br/> |1:18  <br/> |1:58  <br/> |
|Southeast Asia  <br/> |Southeast Asia  <br/> |Excel 97  <br/> |1:37  <br/> |
|Japan East  <br/> |Japan East  <br/> |1:11  <br/> |1:51  <br/> |
|Japan West  <br/> |Japan West  <br/> |1:18  <br/> |1:58  <br/> |
|Brazil South  <br/> |Brazil South  <br/> |70  <br/> |110 (0x6E)  <br/> |
|Australia East  <br/> |Australia East  <br/> |1:24  <br/> |16^4  <br/> |
|Australia Southeast  <br/> |Australia Southeast  <br/> |1:24  <br/> |16^4  <br/> |
|Central India  <br/> |Central India  <br/> |103  <br/> |143  <br/> |
|South India  <br/> |South India  <br/> |103  <br/> |143  <br/> |
|West India  <br/> |West India  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |1:20  <br/> |160 %  <br/> |
|China North  <br/> |China North  <br/> |1:20  <br/> |160 %  <br/> |
   
## Calidad de medios y ExpressRoute
<a name="bk_NetworkPerf"> </a>

Azure ExpressRoute para Office 365 es una conexión de red dedicada que permite conectar a Office 365 sin utilizar el Internet público. Ofrece a los clientes la posibilidad de tener control sobre la ruta de su tráfico de red de Office 365. Los clientes ya no tendrán que preocuparse sobre la impredecibilidad del enrutamiento que se produce en Internet cuando se envían datos a través de operadores, proveedores e ISP desconocidos. El tráfico de red que se envía mediante ExpressRoute se desplaza directamente a través de la red asociada ExpressRoute a la red de Microsoft. Esto permite a los clientes tratar Office 365 como si estuviera ubicado en su propio centro de datos con una conexión dedicada.
  
Azure ExpressRoute está disponible para todas las licencias de Office 365. Sin embargo, es necesario disponer del complemento premium de Azure ExpressRoute para habilitar el enrutamiento global en Office 365. Los clientes de Office 365 con al menos 500 puestos que implementen ExpressRoute pueden obtener el  *complemento premium de ExpressRoute*  sin coste adicional.
  
### ¿Se requiere ExpressRoute para obtener una buena calidad de medios?

No es necesario disponer de Azure ExpressRoute para obtener la mejor calidad de medios de Skype Empresarial Online. Sin embargo, es una de las opciones de implementación que le ayudan a garantizar que su conectividad a la nube cumple los objetivos o umbrales de rendimiento de red de Skype Empresarial.
  
Office 365 es un servicio de alto rendimiento y seguridad basado en Internet. Seguimos invirtiendo en nuevas funciones de seguridad y en nuevos nodos perimetrales regionales para mejorar continuamente la seguridad y el rendimiento. Azure ExpressRoute no es un requisito de los servicios de Office 365 y, por lo tanto, tampoco para Skype Empresarial Online. Azure ExpressRoute es una de las opciones de implementación disponibles que le ayudarán a garantizar que la conectividad con Office 365 cumple los requisitos de rendimiento de red de Skype Empresarial, así como a disfrutar de una experiencia de calidad de medios óptima para Skype Empresarial Online.
  
Para la calidad de medios de Skype Empresarial Online es importante que la conexión entre los sitios de su compañía y los perímetros de la red de Microsoft cumplan los objetivos de rendimiento descritos en [Requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) y que la conexión entre sus perímetros de red y los de Microsoft satisfagan los requisitos de rendimiento descritos en[Requisitos de rendimiento de red desde el perímetro de su red al perímetro de la red de Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge). 
  
También es importante que la conectividad de la red física de su compañía (donde se incluye la capacidad de la conectividad a la nube y a su red interna) se adapte al pico de volumen del tráfico de medios. Azure ExpressRoute es solo una de las muchas opciones que ayudan a los clientes a asegurar que su conectividad a la nube de Skype Empresarial Online cumple todos estos requisitos de rendimiento.
  
### ¿Se requiere ExpressRoute para obtener una SLA de calidad de voz?

No, no es necesario disponer de ExpressRoute para disponer de un SLA de calidad de voz de Skype Empresarial Online. El [SLA de calidad de voz de Skype Empresarial Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) se aplica a cualquier llamada elegible realizada por cualquier usuario del servicio de voz de Skype Empresarial Online que disponga de una licencia y suscripción adecuadas que permitan al usuario realizar cualquier tipo de llamada VoIP o RTC. Los SLA de calidad de voz deberían cubrir todas las siguientes situaciones:
  
- Llamadas de teléfonos de IP certificada por Microsoft.
    
- Conexiones cableadas por Ethernet.
    
- Problemas de calidad de voz debidos a problemas de la red de Microsoft.
    
> [!NOTE]
> El SLA de calidad de voz excluye las llamadas en que la baja calidad está causada por problemas en redes que no son de Microsoft, entre las que se incluyen las del socio ExpressRoute, entre otras. 
  
### ¿Internet o Azure ExpressRoute?

Antes de tomar una decisión sobre las opciones de conectividad de red para Skype Empresarial Online, los clientes deben evaluar su red y su actual conectividad a Internet en función de los requisitos de rendimiento descritos en [Requisitos de rendimiento de red para conectar con Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf).
  
Si la actual conexión a Internet está configurada para ofrecer un rendimiento de red suficiente durante la hora punta y cumple los requisitos de rendimiento de red desde los sitios a los perímetros de la red de Microsoft, así como desde los perímetros de su red a los perímetros de la red de Microsoft, puede continuar utilizando la conectividad a Internet existente para conectar a Skype Empresarial Online.
  
Para los sitios de la compañía en los que no se cumplen los requisitos de rendimiento de red, se recomienda encarecidamente que primero trabaje con sus proveedores de servicios de red para mejorar el rendimiento global de la red. Si tras ello todavía no se cumplen los requisitos, Azure ExpressRoute puede contribuir a garantizar que la conectividad a la nube de Skype Empresarial Online cumple los requisitos de rendimiento de la red.
  
Azure ExpressRoute ofrece los siguientes beneficios adicionales:
  
- Un acuerdo de nivel de servicio (SLA) para la disponibilidad de la conexión entre su red y la red de Microsoft. ExpressRoute tiene un SLA de disponibilidad garantizada de 99,9 %.
    
- El ancho de banda planificado y garantizado que requieren los servicios de Office 365. Este ancho de banda se obtiene al enviar solo tráfico de Office 365 o Skype Empresarial mediante ExpressRoute y hacer que el resto de tráfico de Internet circule por otros puntos de entrada o salida de la red.
    
- ExpressRoute is designed to preserve DSCP QoS markings between your network and the Microsoft Network.
    
Para obtener más información sobre la calidad de servicio de ExpressRoute y la planificación de capacidad, consulte [ExpressRoute y QoS en Skype Empresarial Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### ¿Puedo configurar Azure ExpressRoute solo para Skype Empresarial Online?

Sí, puede configurar Azure ExpressRoute para garantizar una conectividad de red excelente desde la red de su compañía a Skype Empresarial Online exclusivamente. Ello le proporcionará la mejor calidad de medios en tiempo real para sus usuarios, pero podrá continuar conectando a otros servicios de Office 365 mediante Internet.
  
The Border Gateway Protocol (BGP) is a routing protocol on the Internet that is used to route network traffic across the Internet. It is designed to exchange routing information between autonomous systems (AS) found across the Internet. BGP communities values are attribute tags that can be applied to incoming or outgoing routes. BGP communities are often used to signal to the receiving AS which outbound link to use to reach a given destination based on geography, service type or other criteria.
  
Con el soporte de las comunidades de BGP, Microsoft etiqueta los prefijos y las rutas con los valores de comunidad de BGP apropiados, según el servicio al que pertenecen. Microsoft etiqueta los prefijos anunciados mediante emparejamiento público con los valores de comunidad de BGP adecuados que indican la región en la que los prefijos se hospedan. Puede confiar en los valores de comunidad para tomar decisiones de enrutamiento apropiadas a fin de ofrecer un enrutamiento óptimo. Puede utilizar el valor de comunidad de Skype Empresarial Online para configurar una conexión ExpressRoute solo para Skype Empresarial Online. Encontrará más información en [Requisitos de enrutamiento de ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## Escenarios de conectividad de Azure ExpressRoute para Skype Empresarial Online
<a name="bk_NetworkPerf"> </a>

Si tras leer las recomendaciones anteriores ha decidido que ExpressRoute es la opción adecuada para usted, a continuación le ofrecemos algunas guías sobre el número de redes que debería obtener y cómo elegir su ubicación.
  
### Implementación solo en línea: un solo sitio

Si todos sus usuarios utilizan el servicio Skype Empresarial Online, sus oficinas están centradas alrededor de una sola ubicación física y decide implementar Azure ExpressRoute, debería configurar una sola conexión ExpressRoute entre el sitio de su compañía y la [ubicación de emparejamiento ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) más cercana.
  
El siguiente gráfico muestra un ejemplo de este tipo de implementación. En este ejemplo, Contoso es una universidad ubicada en Orlando, Florida. Contoso tiene 10 000 usuarios entre profesores y estudiantes. Las pruebas de Internet desde su ubicación hasta los sitios del perímetro de Microsoft mostraban una pérdida de paquetes de más del 5 % durante horas punta de clases. La universidad ha decidido adquirir una conexión dedicada a Office 365 mediante ExpressRoute con sobreaprovisionamiento de ancho de banda para evitar la congestión de red de Office 365, en especial para el tráfico en tiempo real de Skype Empresarial Online. Los usuarios de la universidad conectan a la nube de Microsoft mediante ExpressRoute en el sitio de emparejamiento de Atlanta, Georgia.
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### Implementación solo en línea: Varios sitios en el mismo continente

Si su compañía utiliza los servicios de Skype Empresarial Online desde varias oficinas en la misma región o continente y decide implementar Azure ExpressRoute, se recomienda conectar el sitio principal por medio de ExpressRoute. A continuación, opcionalmente, puede agregar emparejamientos ExpressRoute adicionales para otras ubicaciones que no cumplen los objetivos de rendimiento de red recomendados.
  
En el siguiente ejemplo, Contoso es una compañía de servicios de viajes de EE. UU. con sede en Nueva York y otras oficinas repartidas por el país o región. Las oficinas están interconectadas mediante una WAN que utiliza MPLS para conectar a Office 365. Inicialmente, la compañía configura una conexión ExpressRoute desde su enrutador de Internet en Hoboken, Nueva Jersey al sitio de emparejamiento de Nueva York. 
  
Con esta configuración, el tráfico de red desde la mayoría de sus sitios a la red de Microsoft (sitio perimetral de Nueva York) cumple los objetivos de rendimiento de red de la conexión del cliente de Skype empresarial que se describen en [Requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge). Sin embargo, la latencia entre las oficinas de la Costa Oeste de Contoso a Nueva York es superior a 50 ms de solo ida. Además, desde la oficina de Honolulu (la segunda más grande de Contoso) a Nueva York, la latencia es de más de 80 ms de solo ida. Para garantizar una buena calidad de medios a los usuarios en estas oficinas, Contoso decide agregar una conexión ExpressRoute en la Costa Oeste, entre su sitio en San José y su sitio de emparejamiento ExpressRoute en Silicon Valley.
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### Implementación solo en línea: varios sitios en distintos continentes

Si todos sus usuarios utilizan el servicio Skype Empresarial Online, sus oficinas están en varias ubicaciones físicas en distintos continentes y decide implementar Azure ExpressRoute, debería configurar al menos una conexión ExpressRoute para cada continente, entre el sitio principal de cada continente y su [ubicación de emparejamiento ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) más cercana. Según la relación entre coste y beneficio, puede elegir implementar otras conexiones ExpressRoute en los sitios en que no se cumplen los objetivos de rendimiento de red.
  
En el siguiente ejemplo, Contoso es una gran corporación legal con oficinas en las principales ciudades de América del Norte y Europa. Tras realizar la evaluación del rendimiento de la conexión a Internet y la red interna, Contoso decidió implementar dos conexiones ExpressRoute en América de Norte y un solo circuito ExpressRoute para todas las oficinas europeas.
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### Implementación híbrida

Si dispone de una implementación local de Lync o Skype Empresarial Online y elige implementar una integración híbrida de Skype Empresarial Online, recomendamos que, si decide implementar Azure ExpressRoute, disponga al menos de una conexión ExpressRoute para cada sitio local de Lync o Skype Empresarial Online y de al menos una conexión ExpressRoute por cada continente con oficinas. En función de la relación entre coste y beneficio, para cada continente puede optar por implementar conexiones adicionales en las oficinas donde no se cumplen los objetivos de rendimiento.
  
Si tiene una implantación local de Skype Empresarial, debe seguir los pasos descritos en la [Guía de planificación e implementación del servidor perimetral](https://technet.microsoft.com/en-us/library/mt346417.aspx). Específicamente, los servidores perimetrales deben resultar accesibles desde fuera de la red. Esto suele lograrse asignando una dirección IP pública enrutable al servidor perimetral o bien utilizando la traducción de direcciones de red (NAT).
  
En el siguiente ejemplo, Contoso tiene una implementación de telefonía IP empresarial de Skype Empresarial. La compañía desea migrar los usuarios locales a los servicios en línea de Office 365. También ha decidido utilizar una implementación híbrida para poder seguir utilizando su infraestructura RTC para todos los usuarios locales y en línea. Los centros de datos y servidores perimetrales de Skype Empresarial de Contoso están ubicados en Chicago. Para su implementación, Contoso ha decidido configurar una conexión ExpressRoute entre el centro de datos de Chicago y Skype Empresarial. También se ha agregado una conexión ExpressRoute para la Costa Oeste para mejorar el servicio de la oficina de Honolulu.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### Implementación en línea con Cloud Connector Edition

Skype Empresarial Online Cloud Connector Edition es una oferta híbrida compuesta por un conjunto de máquinas virtuales (VM) empaquetadas que implementan la conectividad local con RTC. Mediante la implementación de una topología mínima de Skype Empresarial Server en un entorno virtualizado, podrá enviar y recibir llamadas con teléfonos fijos y móviles mediante la infraestructura de voz RTC local ya existente.
  
Si decide implementar Azure ExpressRoute y Cloud Connector Edition, le recomendamos que configure al menos una conexión ExpressRoute para cada continente, entre el sitio principal de cada continente y su [ubicación de emparejamiento ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) más cercana. Según la relación entre coste y beneficio, puede elegir implementar otras conexiones ExpressRoute en los sitios en que no se cumplen los objetivos de rendimiento de red.
  
Si dispone de una implementación local de Skype Empresarial, debe seguir las indicaciones de la [Guía de planificación para Skype Empresarial Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Específicamente, los servicios de A/V del perímetro y el perímetro de acceso deben tener asignados direcciones IP públicas que resulten accesibles desde los centros de datos de Office 365.
  
En el siguiente ejemplo Contoso es una firma de contabilidad europea presente en varios de los principales países, regiones y ciudades de Europa. Cuando adquieren Skype Empresarial Online para todas sus necesidades de colaboración, deciden colocar un conector de nube para cada país o región donde tienen una ubicación física a fin de utilizar su infraestructura RTC y los contratos de operadores ya existentes. Según las pruebas realizadas en todos sus sitios y el perímetro de la red de Microsoft, determinan que una sola conexión ExpressRoute en Londres ayudaría a cumplir los objetivos de rendimiento de red de la conexión del cliente de Skype Empresarial Online descritos en [Requisitos de rendimiento de red desde un cliente de Skype Empresarial al perímetro de la red de Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A continuación se muestra otra opción de implementación de Contoso. En este caso, la empresa ha decidido configurar una conexión ExpressRoute en cada sitio donde hay implementado un conector de nube.
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## Vea también
<a name="bk_NetworkPerf"> </a>

#### 

[ExpressRoute y QoS en Skype Empresarial Online](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

