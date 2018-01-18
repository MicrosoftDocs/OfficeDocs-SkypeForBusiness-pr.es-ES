---
title: Calidad Media y rendimiento de la conectividad de red
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Este tema define el conjunto de requisitos de rendimiento de red para Skype para servicios empresariales en línea y cómo puede utilizar Internet o ExpressRoute para la conectividad entre la red y Skype para los negocios en línea en función de la evaluación de la red conectividad. Si ha decidido implementar Azure ExpressRoute de conectividad dedicada a Office 365, este documento también proporciona instrucciones acerca de cómo diseñar las conexiones ExpressRoute en Skype diferente para escenarios de implementación de negocios en línea."
ms.openlocfilehash: 438328058ace76beb24bbdf1d64804441694b045
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Calidad Media y rendimiento de conectividad de red en Skype para el negocio en línea

Este tema define el conjunto de requisitos de rendimiento de red para Skype para servicios empresariales en línea y cómo puede utilizar Internet o ExpressRoute para la conectividad entre la red y Skype para los negocios en línea en función de la evaluación de la red conectividad. Si ha decidido implementar Azure ExpressRoute de conectividad dedicada a Office 365, este documento también proporciona instrucciones acerca de cómo diseñar las conexiones ExpressRoute en Skype diferente para escenarios de implementación de negocios en línea.
  
La calidad de multimedia en tiempo real (audio, vídeo y uso compartido de aplicaciones) a través de IP está afectada en gran medida por la calidad de la conectividad de red end-to-end. Skype óptimo para los negocios en línea de calidad media, es importante que compruebe que hay una conexión de alta calidad entre la red de la compañía y Skype para los negocios en línea. La mejor forma de conseguirlo es configurar la red interna y la conectividad de nube basándose en la capacidad de la red para compensar el volumen de tráfico pico de Skype para los negocios en línea en todas las conexiones.
  
ExpressRoute de Azure no es un requisito para los servicios de Office 365 incluye Skype para los negocios en línea. Sin embargo, ExpressRoute de Azure es uno de la implementación de opciones disponibles que le ayudarán a Asegúrese de que cumple el Skype para requerimientos de performance de red empresarial conectividad a Office 365 y garantiza el óptimo Skype para los negocios en línea media experiencia de calidad.
  
> [!TIP]
> Aunque este tema le proporciona orientación de rendimiento de red general, una guía completa para la evaluación de la red está fuera del alcance de este documento. Para obtener una lista de Skype para asociados de negocios en línea que le pueden ayudar con las mediciones de rendimiento de la red como parte de una evaluación de red completa y minuciosa, visite [Skype para soluciones de socios de negocios](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividad de red para Skype para los negocios en línea

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factores que afectan a Skype para los negocios en línea de calidad media

Hay muchos factores diferentes que contribuyen con Skype para la calidad de los medios (audio, vídeo y aplicaciones para compartir) en tiempo real en línea de negocios que incluyen los dispositivos que se utilizan, el entorno y la conectividad de red. 
  
#### <a name="devices"></a>Dispositivos

En una sesión multimedia en tiempo real, los medios de captura y dispositivos que son utilizados por todos los participantes como auriculares y cámaras Web de procesamiento tienen un gran impacto en la calidad de vídeo y audio general. Menor calidad dispositivos o con los controladores de dispositivo incorrectos producirá más baja la calidad del sonido de calidad de imagen inferior y audio para vídeo. Certificado o dispositivos de buena calidad, por otra parte, ayuda con cancelación de eco, filtrado de ruido, resolución de vídeo y reducir la latencia.
  
Aunque el certificado no se necesitan dispositivos multimedia de audio y vídeo, se recomienda dispositivos certificación para Skype para el negocio para la mejor experiencia multimedia. Para obtener una lista de todos los Skype para empresas dispositivos certificados, consulte [los teléfonos y dispositivos de Skype para el negocio](https://technet.microsoft.com/en-us/office/dn947482). Puede utilizar el [Skype para negocios en línea panel calidad llamar](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md), encontrado en **Skype para Business admin center**, para comprobar el funcionan de dispositivos en uso y controlar la calidad de audio y vídeo.
  
> [!TIP]
> **Un dispositivo certificado es necesario para la óptima Skype para la experiencia de calidad de los medios empresariales**.
  
Es importante recordar que los dispositivos de medios, Skype para clientes de empresa y Skype para servidores empresariales a través de qué flujos multimedia en tiempo real, introducen cierta cantidad de latencia. El dispositivo y el software de procesamiento de latencia, junto con la latencia de la red, tienen un gran impacto en y contribuyen a la latencia total end-to-end y la experiencia del usuario final.
  
#### <a name="environment"></a>Entorno de

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen clara sobre el uso de audio y vídeo de experiencia del usuario la Skype para **Herramientas**de la aplicación empresarial > **Opciones** > **Dispositivo de sonido** o **Dispositivo de vídeo** para realizar cambios en el dispositivo en uso y personalizar su configuración. También puede comprobar la calidad de audio de una llamada haciendo clic en **Comprobar calidad de llamar**. Si hacen clic en **Comprobar calidad de llamar**, a continuación, puede informar la calidad y los problemas encontrados en la llamada de la prueba.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>Red

La calidad de los medios de comunicación en tiempo real sobre la red IP en gran medida se ve afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:
  
- **Latencia** Esto es el tiempo que se tarda en obtener un paquete IP desde el punto al punto B de la red. Este retardo en la propagación red esté esencialmente ligado a la distancia física entre los dos puntos y la velocidad de la luz, incluyendo tomada por los diversos enrutadores entre una sobrecarga adicional. La latencia se mide como el tiempo de ida o de ida y vuelta (RTT).
    
- **Pérdida de paquetes** Esto a menudo se define como un porcentaje de paquetes que se pierden en un determinado intervalo de tiempo. Pérdida de paquetes directamente afecta a la calidad de audio, desde pequeñas, individuo perdido paquetes con casi ningún impacto, a las pérdidas de ráfagas de extremo a extremo que causan completa audio a recorte.
    
- **Variación de llegada entre paquete o simplemente de vibración** Éste es el cambio promedio de retardo entre envíos sucesivos de paquetes. Software de VoIP más moderno incluyendo Skype para empresas puede adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Es sólo cuando la variación supera el búfer que un participante observará los efectos de vibración.
    
> [!NOTE]
>  El almacenamiento en búfer de jitter aumentará la latencia end-to-end.
  
Con muchos Skype simultáneos para sesiones de multimedia en tiempo real de negocio en línea, así como otro tráfico de red generado por otros servicios de Office 365 y otras aplicaciones empresariales, asegurándose de que hay suficiente ancho de banda a través de la ruta de acceso de toda la red que conecta la red a la Skype para servicios en línea de negocio es fundamental para evitar la congestión de la red y garantizar un medio excelente calidad de multimedia en tiempo real (compartir aplicaciones, audio y video). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementación de calidad de servicio (QoS) en redes congestionadas

Además, congestión del tráfico a través de una red influirá notablemente calidad media. Para permitir paquetes de audio y vídeo para viajar a la red más rápida y priorizarse otro tráfico de red en un red saturada, calidad de servicio (QoS) puede utilizarse para ayudar a proporcionar una experiencia óptima para las comunicaciones de audio y vídeo.
  
QoS proporciona una forma de asignar una mayor prioridad a los paquetes de red que están llevando a los datos de audio o vídeo. Al asignar una mayor prioridad a estos paquetes, comunicaciones de audio y vídeo son aptos para circular por la red con mayor rapidez y con menos interrupciones, de sesiones de red relacionadas con cosas como las transferencias de archivos, navegación por la web o las copias de seguridad de la base de datos. Eso es porque los paquetes de red que se utilizan para transferencias de archivos o copias de seguridad de base de datos predeterminada se asignan "mejor esfuerzo" como una prioridad y congestión de la red no tiene como gran impacto. Si no asigna una mayor prioridad a los paquetes de multimedia (audio, vídeo y aplicaciones para compartir) y dejarlos asignados también como el "mejor esfuerzo", también sean procesados junto con el resto del tráfico de red. Dependiendo de la cantidad de congestión de la red, esto potencialmente acabará en una experiencia de calidad general de audio y vídeo más baja para los usuarios.
  
Se recomienda que implemente QoS de la red para asegurarse de que la congestión de la red dentro de la red no tendrá un impacto. Sin embargo, para que esto tenga el máximo impacto, todos los extremos de red deben ser compatible con QoS, lo que significa que todos los extremos deben respetar QoS marcado y prioridad de los paquetes. Skype para los servicios electrónicos de negocios cumplir con QoS marcado y prioridades dentro de la red de Microsoft. Sin embargo, el tráfico se enruta a través de una conexión pública como Internet desde la red de su empresa a the Microsoft network no conserva marcadores de QoS y prioridad de los paquetes. Las conexiones privadas de la red a Office 365 con [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) ofrecen una solución de implementación que conserva los marcadores de QoS y prioridad de los paquetes que a su vez aumentará en general audio y una calidad de vídeo para los usuarios finales.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de rendimiento de red para conectar con Skype para los negocios en línea
<a name="bkNetworkPerf"> </a>

Skype para medios de comunicación en tiempo real de negocio viaja a través de muchos dispositivos diferentes, las aplicaciones cliente, software de servidor y red. La latencia end-to-end de medios de comunicación en tiempo real es la cantidad total de latencia que se introduce a través de todos los componentes y segmentos de red. La calidad de la conexión de red end-to-end se determina por el segmento de red con la peor calidad. Este segmento actúa como un cuello de botella para el tráfico de red.
  
El siguiente diagrama ilustra el flujo de audio unidireccional en una conferencia de un Skype participante del negocio.
  
![Flujo de llamadas de ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
En este escenario de conferencias, consiste en la ruta de acceso de medios a través de los siguientes segmentos de red:
  
1. **Conexión de usuario 1 hasta el borde de la red de Microsoft** Normalmente incluye una conexión de red como WiFi o Ethernet, la conexión WAN de usuario 1 hasta el punto de salida de Internet (el dispositivo de borde de red) y la conexión a Internet de la red de borde a borde de red de Microsoft.
    
2. **Conexión en red de Microsoft** Esto es entre Microsoft Edge a Skype para centro de datos empresarial en línea, donde A se utilizan los servidores de conferencias audiovisuales.
    
3. **Conexión en red de Microsoft** Esto es entre el Skype para centros de datos empresariales en línea y borde de Microsoft network.
    
4. **Conexión desde el perímetro de la red de Microsoft al usuario 2** Esto incluye la conexión a Internet de la red de borde a borde, la conexión WAN de usuario 2 hasta el punto de salida de Internet (la red perimetral) y la conexión de red como un WiFi o Ethernet de red de Microsoft.
    
El siguiente diagrama muestra el desglose de los componentes y segmentos de red de un Skype para llamadas PSTN en línea de negocio:
  
![Flujo de llamadas de portadora ExpressRoute PSTN.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
En un escenario de llamadas PSTN, la ruta de acceso de medios cruza los segmentos de red siguiente:
  
1. **Conexión de un Skype para llamadas de cliente empresarial hasta el borde de la red de Microsoft** Normalmente incluye una conexión de red como WiFi o Ethernet, la conexión WAN desde el Skype para llamadas de cliente de empresa hasta el punto de salida de Internet (el dispositivo de borde de red) y la conexión a Internet de la red de borde a borde de red de Microsoft.
    
2. **Conexión en red de Microsoft** Esto es entre Microsoft Edge a Skype para centro de datos empresarial en línea, donde se utiliza un servidor de mediación.
    
3. **Conexión en red de Microsoft** Esto es entre el Skype para centros de datos empresariales en línea y borde de Microsoft network.
    
4. **Conexión entre la red de Microsoft y los socios de proveedor de servicio RTC** Ésta es la conexión que existe para realizar una llamada PSTN desde el Skype para Business client que se encuentra fuera de la red de Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de rendimiento de red a red perimetral de Microsoft desde un Skype para cliente de negocios
<a name="bkSfBClienttoEdge"></a>

Para Skype óptimo para la calidad de los medios empresariales, los siguientes objetivos de métricas de performance de red o umbrales son necesarios para una conexión de red de su empresa a la red perimetral de Microsoft. Este segmento de la red incluye la red interna, lo que incluye todas las conexiones WiFi y Ethernet, cualquier tráfico de sitio a sitio de empresa a través de una conexión WAN, por ejemplo Multiprotocol Label Switching (MPLS), así como el socio de Internet o ExpressRoute conexiones a la red perimetral de Microsoft.
  
> [!CAUTION]
> **Conectividad entre un Skype para cliente de negocios en la red de su empresa a los servicios de Office 365 debe cumplir los siguientes requisitos de rendimiento de red y umbrales.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latencia (unidireccional)  <br/> |< 50 ms  <br/> |
|Latencia (RTT o tiempo de ida y vuelta)  <br/> |< 100 ms  <br/> |
|Pérdida de paquetes ráfaga  <br/> |< 10% durante un intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |< 1% durante un intervalo de 15 s  <br/> |
|Vibración de llegada entre paquetes  <br/> |< 30 ms durante un intervalo de 15 s  <br/> |
|Reaprovisionamiento de paquete  <br/> |< 0,05% paquetes sin ordenar  <br/> |
   
 **Otros requisitos del destino de rendimiento:**
  
- La red de Microsoft tiene más de 160 borde ubicaciones en todo el mundo. Trabajamos con los principales proveedores de servicios Internet (ISP) en todo el mundo a través de esos sitios de borde. El destino de métrica de latencia supone que su sitio de empresa o los sitios y los Edges de Microsoft están en el mismo continente.
    
- Su sitio de empresa o sitios para la conexión del extremo de red de Microsoft incluyen el primer salto acceso a la red, que puede ser WiFi u otra tecnología inalámbrica. 
    
- El destino de rendimiento de red supone el ancho de banda adecuado o la calidad de la planificación del servicio. En otras palabras, esto se aplica directamente a Skype para tráfico multimedia en tiempo real del negocio cuando la conexión de red está bajo una carga máxima.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de rendimiento de red de la red de borde a borde de red de Microsoft
<a name="bkYourNetworkEdge"> </a>

Los siguientes son los objetivos de performance de la red o umbrales necesarios para la conexión entre la red perimetral y la red de Microsoft Edge. Este segmento de la red excluye WAN o red interna del cliente y sirve como guía al probar el tráfico de red que se envía a través de Internet o a través de una red de socios de ExpressRoute y también puede utilizarse cuando se negocia un rendimiento Acuerdo de nivel de servicio (SLA) con el proveedor de ExpressRoute.
  
> [!CAUTION]
> **Conectividad entre la red de su empresa borde hasta el borde de la red de Microsoft debe cumplir los siguientes requisitos de rendimiento de red y umbrales.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latencia (unidireccional)  <br/> |< 30 ms  <br/> |
|Latencia (RTT)  <br/> |< 60 ms  <br/> |
|Pérdida de paquetes ráfaga  <br/> |< 1% durante un intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |< 0,1% durante un intervalo de 15 s  <br/> |
|Vibración de llegada entre paquetes  <br/> |< 15 ms durante un intervalo de 15 s  <br/> |
|Reaprovisionamiento de paquete  <br/> |< 0,01% paquetes sin ordenar  <br/> |
   
 **Otros requisitos del destino de rendimiento:**
  
- El destino de rendimiento requiere conexión entre cualquiera de la red de borde y su red de Microsoft más cercano borde, en el mismo continente.
    
- El destino de rendimiento de red supone el ancho de banda adecuado o la calidad de la planificación del servicio. Esto también se aplica a Skype para tráfico multimedia en tiempo real del negocio cuando la conexión de red está bajo una carga máxima. Ancho de banda apropiado y planificación de QoS, consulte [ExpressRoute y QoS en Skype para los negocios en línea](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Medir el rendimiento de la red
<a name="bkNetworkPerf"> </a>

Para medir el rendimiento real de la red, especialmente para la latencia y pérdida de paquetes, desde cualquier sitio de la red de empresa a una red perimetral, puede utilizar herramientas como ping, comparar con un conjunto de Skype para servicios de retransmisión de media Business ejecutando desde el Microsoft Edge y los datos sitios del centro. 
  
Para probar las conexiones de Internet a la red de Microsoft, se recomienda que pruebe con el siguiente VIP de la Skype para transmisores de media Business. La *VIP de difusión por proximidad* se resolverá en una dirección IP de un relé de medios en un sitio de borde de red de Microsoft más cercano a la ubicación de la prueba.
  
||||
|:-----|:-----|:-----|
|**Dirección IP** <br/> |**Tipo** <br/> |**Ubicación** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide IP de difusión por proximidad  <br/> |
   
 **Éstas son algunas recomendaciones de alto niveles a seguir para evaluar el rendimiento de la red:**
  
- Debe evaluar la red interna, así como las conexiones a Office 365.
    
- Debe evaluar y recopilar datos de todos sus redes durante un período largo de tiempo. Se recomienda para que realizar las pruebas de rendimiento de la red durante un mínimo de una semana, para que puedan ver los patrones de uso para todos los días laborables y horas. Esto le mostrará las horas.
    
- Deberá tomar muestras de varias de las medidas de rendimiento de red. Se recomienda realizar una medición cada 10 minutos desde un sitio de la empresa durante todo el período de tiempo de que recopilación de datos. Para comparar el Skype para requerimientos de performance de red negocios en línea, tomar el valor de medida del percentil 90 de este conjunto de datos de ejemplo. 
    
- Debe evaluar continuamente el rendimiento de la red. Utilización de la red varía con el tiempo debido a cambios de patrones de uso, nuevas aplicaciones basadas en empresas que utilizan una gran cantidad de ancho de banda y cambios en las ubicaciones de empresa organizativa o físico. Es importante supervisar el rendimiento de la red frente a estos requisitos de rendimiento de red y objetivos y umbrales continuamente y realizar ajustes oportunos para garantizar la óptima calidad de multimedia en tiempo real. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medir el rendimiento de la red mediante máquinas virtuales de Azure
<a name="bkNetworkPerf"> </a>

En lugar de probar frente a los sitios de borde de red de Microsoft, hay soluciones de evaluación de red de Skype para clientes de negocios y socios que aprovechan la configuración de pruebas para los servicios en la nube de Microsoft Azure. En estas soluciones, las herramientas de evaluación de red probar la latencia, pérdida de paquetes y vibración contra extremos personalizados configurado como un servicio en la nube de Azure. Como resultado, el tráfico de red de prueba viaja a través de un segmento de red adicional, que es la conexión dentro de la red de Microsoft, entre los bordes de la red y centros de datos de Azure que hospeda el servicio de evaluación de la red.
  
Para esos red soluciones de evaluación basadas en Azure alojan servicios de pruebas. Le recomendamos que realice la evaluación de la red dentro de país o región. Por ejemplo, para los sitios de los clientes de Estados Unidos de Oriente, la evaluación debe realizarse frente a una instancia de servicio prueba alojada en el este de Azure región de centro de datos de EE. 
  
A continuación se muestran la latencia destinos (RTT) para la configuración de evaluación de red de servicio Azure basado. Los destinos de latencia unidireccional será la mitad de los destinos RTT correspondientes. Los objetivos de variación y pérdida de paquetes se mantiene como los definidos para la transmisión de medios de Skype en función de pruebas.
  
|||||
|:-----|:-----|:-----|:-----|
|**Región del cliente** <br/> |**Región de Azure** <br/> |**La red perimetral - tiempo de ida y vuelta de Azure (RTT)** <br/> |**Su sitio - Azure tiempo de ida y vuelta (RTT)** <br/> |
|Central de EE.  <br/> |Central de EE.  <br/> |99  <br/> |139  <br/> |
|Oriental de EE.  <br/> |Oriental de EE.  <br/> |86  <br/> |126  <br/> |
|Norte Central de EE.  <br/> |Norte Central de EE.  <br/> |97  <br/> |137  <br/> |
|Sur Central de EE.  <br/> |Sur Central de EE.  <br/> |94  <br/> |134  <br/> |
|Oeste de EE.  <br/> |Oeste de EE.  <br/> |94  <br/> |134  <br/> |
|Hawai EE.  <br/> |Oeste de EE.  <br/> |116  <br/> |156  <br/> |
|Canadá Central  <br/> |Canadá Central  <br/> |138  <br/> |178  <br/> |
|Canadá oriental  <br/> |Canadá oriental  <br/> |131  <br/> |171  <br/> |
|Europa del Norte  <br/> |Europa del Norte  <br/> |99  <br/> |139  <br/> |
|Europa occidental  <br/> |Europa occidental  <br/> |95  <br/> |135  <br/> |
|Asia oriental  <br/> |Asia oriental  <br/> |118  <br/> |158  <br/> |
|Sudeste de Asia  <br/> |Sudeste de Asia  <br/> |97  <br/> |137  <br/> |
|Japón oriental  <br/> |Japón oriental  <br/> |111  <br/> |151  <br/> |
|Oeste de Japón  <br/> |Oeste de Japón  <br/> |118  <br/> |158  <br/> |
|Sur de Brasil  <br/> |Sur de Brasil  <br/> |70  <br/> |110  <br/> |
|Australia Oriental  <br/> |Australia Oriental  <br/> |124  <br/> |164  <br/> |
|Sudeste de Australia  <br/> |Sudeste de Australia  <br/> |124  <br/> |164  <br/> |
|Centro de la India  <br/> |Centro de la India  <br/> |103  <br/> |143  <br/> |
|Sur de la India  <br/> |Sur de la India  <br/> |103  <br/> |143  <br/> |
|La India del oeste  <br/> |La India del oeste  <br/> |103  <br/> |143  <br/> |
|China oriental  <br/> |China oriental  <br/> |120  <br/> |160  <br/> |
|Norte de China  <br/> |Norte de China  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Calidad Media y ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute de Azure para Office 365 es una conexión de red dedicada para conectarse a Office 365. Ofrece a los clientes la capacidad de tener control sobre la ruta de acceso de su tráfico de red de Office 365. Ya no tienen que preocuparse por el enrutamiento impredecible que sucede en Internet donde se realice datos desconocidos de los transportistas, proveedores y ISP. Se envía tráfico de red que se envía a través de ExpressRoute directamente a través de la red de socios de ExpressRoute a la red de Microsoft. Esto permite a los clientes tratar Office 365, como si se encuentra en su propio centro de datos fuera del sitio con una conexión dedicada.
  
ExpressRoute de Azure está disponible para todas las ofertas de licencias de Office 365. Sin embargo, el complemento de prima de Azure ExpressRoute es necesario para Office 365 habilitar el enrutamiento global. Los clientes de Office 365 con al menos 500 asientos que están implementando ExpressRoute pueden obtener el necesario *Complemento de la prima de ExpressRoute* sin cargo adicional.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>¿Se requiere ExpressRoute de calidad media buena?

ExpressRoute de Azure no es un requisito para obtener el Skype más óptimo para los negocios en línea de calidad media. Es, sin embargo, uno de la implementación de opciones que le ayudarán a comprobar que la conectividad de la nube cumple el Skype para objetivos de performance de red empresarial o umbrales.
  
Office 365 es un alto rendimiento y servicio seguro que utiliza Internet. Seguimos invirtiendo en nuevas capacidades de seguridad y nodos de borde regional para mejorar continuamente la seguridad y el rendimiento. ExpressRoute de Azure no es un requisito para los servicios de Office 365 incluye Skype para los negocios en línea. ExpressRoute de Azure es uno de la implementación de opciones disponibles que le ayudarán a Asegúrese de que cumple el Skype para requerimientos de performance de red empresarial conectividad a Office 365 y garantiza el óptimo Skype para los negocios en línea de calidad media experiencia.
  
Por Skype para los negocios en línea de calidad media, es importante que la conexión entre los sitios de la empresa y los bordes de la red Microsoft cumple los objetivos de performance en requisitos de [rendimiento de la red desde un Skype para Business client para Microsoft network Borde](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) y que la conexión entre los bordes de la red y los bordes de la red de Microsoft cumple los objetivos de performance en [los requisitos de rendimiento de red de la red de borde a borde de red de Microsoft](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
También es importante que conectividad de red física de su empresa, incluyendo su capacidad interna de conectividad de red y la nube acomodar el volumen de tráfico de punta media. ExpressRoute de Azure es una de muchas maneras en que ayudarán a los clientes a asegurar que su Skype para conectividad de nube en línea Business cumple todos estos requisitos de rendimiento.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>¿Se requiere ExpressRoute de SLA de calidad de voz?

No, no es necesario para Skype para negocios SLA de calidad de voz en línea ExpressRoute. El [Skype para negocios SLA de calidad de voz en línea](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) se aplica a cualquier llamada elegible realizado por cualquier Skype para usuario de servicio de voz empresarial en línea dentro de la licencia correcta y suscripción que permite que el usuario realice cualquier tipo de llamada de VoIP o PSTN. Debe incluir un acuerdo SLA de calidad de voz que se satisfacen todas las condiciones siguientes:
  
- Llamadas de Microsoft certificación teléfonos IP.
    
- Conexiones Ethernet cableadas.
    
- Problemas de calidad de voz debido a los problemas de Microsoft Network.
    
> [!NOTE]
> El SLA de calidad de voz excluye las llamadas donde la calidad de las llamadas baja es causada por problemas en las redes no son de Microsoft como socio de ExpressRoute y otras redes. 
  
### <a name="internet-or-azure-expressroute"></a>¿Internet o ExpressRoute de Azure?

Antes de tomar una decisión sobre la red de opciones de conectividad para Skype para los negocios en línea, los clientes deben evaluar su red y conectividad a Internet actual basada en los requisitos de rendimiento de red descritos en [requisitos de rendimiento de red para conectar con Skype para los negocios en línea](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Si se establece el rendimiento de la red a través de la conexión actual a Internet para capacidad suficiente durante las horas pico y cumple los requisitos de rendimiento de red de sitios a los bordes de red de Microsoft y de sus bordes de red a los bordes de red de Microsoft, puede seguir utilizando la conexión a Internet existente para conectar con Skype para los negocios en línea.
  
Para los sitios de la empresa donde no se cumplen los requisitos de rendimiento de red, se recomienda que primero trabajar con los proveedores de servicios de red existente para mejorar el rendimiento de la red. Sin embargo, si todavía no se cumplen, ExpressRoute de Azure puede ayudarle a garantizar que su Skype para conectividad de nube en línea Business puede ayudarle a satisfacer los requerimientos de performance de la red.
  
ExpressRoute de Azure ofrece las siguientes ventajas adicionales:
  
- Un nivel acuerdo de servicio (SLA) de la disponibilidad de la conexión entre la red y la red de Microsoft. ExpressRoute tiene un SLA de disponibilidad garantizada de un 99,9%.
    
- Planificada y garantizada ancho de banda necesario para los servicios de Office 365. Puede lograr esto mediante el envío de sólo tráfico de Office 365 o Skype para tráfico de negocios mediante el ExpressRoute y hacer que todos los otros tráfico atraviesan otros puntos de entrada/salida de Internet para la red de Internet.
    
- ExpressRoute está diseñado para conservar el marcado de DSCP QoS entre la red y Microsoft Network.
    
Para obtener más información acerca de ExpressRoute QoS y planificación de capacidad, consulte [ExpressRoute y QoS en Skype para los negocios en línea](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>¿Puedo configurar ExpressRoute de Azure de Skype para el negocio en línea sólo?

Sí, puede configurar ExpressRoute de Azure para garantizar la conectividad de la red excelente de la red de su empresa con Skype sólo para los negocios en línea. Esto proporcionará la óptima calidad de multimedia en tiempo real para los usuarios pero, a continuación, aún puede conectarse a otros servicios de Office 365 a través de Internet.
  
Border Gateway Protocol (BGP) es un protocolo de enrutamiento de Internet que se utiliza para enrutar el tráfico de red a través de Internet. Está diseñado para intercambiar información de enrutamiento entre sistemas autónomos (AS) se encuentra a través de Internet. Los valores de las Comunidades BGP son etiquetas de atributo que se pueden aplicar a las rutas entrantes o salientes. Comunidades BGP se utilizan a menudo para señalar a la recepción como qué vínculo saliente para llegar a un destino dado, basado en la geografía, tipo de servicio u otros criterios.
  
Con el apoyo de Comunidades BGP, Microsoft etiqueta prefijos y rutas con valores de comunidad BGP adecuados basados en el servicio al que pertenecen. Microsoft etiqueta prefijos anunciados a través de la interconexión pública y Microsoft con los valores apropiados de comunidad BGP que indica la región que se alojan los prefijos en. Puede confiar en los valores de la Comunidad para tomar decisiones de enrutamiento apropiadas ofrecer enrutamiento óptimo. Puede usar el Skype para valor de comunidad de BGP en línea de negocio para configurar una conexión de ExpressRoute sólo para Skype para los negocios en línea. Puede encontrar más información en [requisitos de enrutamiento ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Escenarios de conectividad de ExpressRoute de Skype para los negocios en línea
<a name="bkNetworkPerf"> </a>

Si ha decidido que es ExpressRoute que se basa en las recomendaciones anteriores, aquí están las recomendaciones sobre dónde y cuántas conexiones de ExpressRoute debe obtener.
  
### <a name="online-only-deployment---single-site"></a>Implementación sólo en línea - único sitio

Si todos los usuarios utilizan el Skype para servicio de los negocios en línea y sus oficinas se centran en una sola ubicación física y decide implementar ExpressRoute de Azure, debe establecer una única conexión de ExpressRoute entre el sitio de su compañía a lo más cercano [Ubicación de interconexión de ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
El gráfico siguiente muestra un ejemplo de este tipo de implementación. Para este ejemplo, Contoso es una universidad en Orlando, FL. Contoso tiene 10.000 miembros del profesorado y los alumnos. Las pruebas de Internet desde su ubicación a sitios de borde de Microsoft mostraron mayores pérdida de paquetes de 5% durante las horas de clase. El ha decidido obtener una conexión dedicada a Office 365 con ExpressRoute un provisioning excesivo ancho de banda para que pueden evitar la congestión de la red para Office 365 especialmente para Skype para el tráfico en tiempo real de negocio en línea. Se conectan a la nube de Microsoft a través de ExpressRoute en el sitio de Atlanta, Georgia, MeetMe.
  
![Sitio de ExpressRoute único.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implementación sólo en línea - varios sitios en el mismo continente

Si su empresa utiliza Skype para servicios en línea de negocio de varias oficinas de la misma región o continente, y decidió implementar ExpressRoute de Azure, se recomienda conectar el sitio principal a través de ExpressRoute y, a continuación, opcionalmente Agregar adicional ExpressRoute de interconexión para otras ubicaciones que no cumplan los objetivos de rendimiento de red recomendados.
  
En el siguiente ejemplo, Contoso es una empresa de servicios de viaje de Estados Unidos que tiene su sede en Nueva York, pero cuenta con otras oficinas en Estados Unidos. Sus oficinas están interconectadas a través de una WAN que utiliza MPLS para conectarse a Office 365. Configura inicialmente una conexión ExpressRoute de su enrutador de Internet en Hoboken, New Jersey al sitio MeetMe de Nueva York. 
  
Con esta configuración, el tráfico de red de la mayoría de los sitios de Microsoft Network (sitio de Nueva York Edge) puede satisfacer el Skype para objetivos de performance de red en conexión de negocio cliente descrito en [requisitos de rendimiento de la red desde un Skype para el cliente de Business para Microsoft, red perimetral](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Sin embargo, latencia entre las oficinas de la costa oeste de Contoso a Nueva York va a través de 50 ms. unidireccional. Además, Honolulu es la segunda oficina de Contoso, latencia de Honolulu a Nueva York supera 80 ms unidireccional. Para asegurar una calidad media buena para los usuarios de dichas oficinas, Contoso decidió agregar una costa oeste ExpressRoute conexión entre sus sitios de San José y Silicon Valley ExpressRoute MeetMe.
  
![Express enrutador de múltiples sitios en el mismo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implementación sólo en línea - varios sitios en diferentes países

Si todos los usuarios utilizan Skype para servicio de los negocios en línea, y sus oficinas se encuentran en varias ubicaciones físicas en varios continentes, si decide implementar ExpressRoute de Azure, debe configurar al menos una conexión de ExpressRoute para cada continente entre el sitio principal de cada continente a su [ubicación de interconexión ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)de más cercano. Función costo vs beneficio, puede implementar conexiones adicionales de ExpressRoute de sitios donde no se cumplen los objetivos de performance de la red.
  
En el siguiente ejemplo, Contoso es una empresa de abogados corporativos de gran tamaño con oficinas en las principales ciudades en Norteamérica y Europa. Basándose en su evaluación de rendimiento de la red interna y de su conexión a Internet, Contoso decidió implementar dos conexiones ExpressRoute en América del Norte y un circuito de ExpressRoute única para todas sus oficinas europeas.
  
![ExpressRoute con varios sitios y continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implementación híbrida

Si tienes un Lync en locales o Skype para la implementación en la empresa y se decide implementar un híbrido Skype para la integración de los negocios en línea, le recomendamos que si decide implementar ExpressRoute de Azure, debe tener al menos una conexión de ExpressRoute para cada uno local Lync o Skype para sitio de borde del negocio y al menos una conexión de ExpressRoute para cada continente con oficinas. Función costo vs beneficio, para cada continente puede implementar conexiones de ExpressRoute adicionales de oficinas donde no se cumplen los objetivos de performance de la red.
  
Si tienes un Skype local para la implementación en la empresa, debe seguir el [borde Server Planning and Deployment Guide](https://technet.microsoft.com/en-us/library/mt346417.aspx). En concreto, los servidores perimetrales deben ser accesibles desde fuera de la red. Normalmente, esto se logra mediante la asignación de una dirección IP pública enrutable para el servidor perimetral o mediante el uso de traducción de direcciones de red (NAT).
  
En el siguiente ejemplo, Contoso tiene un Skype en instalaciones existentes para la implementación de Telefonía IP empresarial de negocios. Desean migrar usuarios locales a los servicios en línea de Office 365. También decidieron utilizar una implementación híbrida, por lo que puede seguir usando su infraestructura PSTN existente para todos los usuarios en línea y locales. Centro de datos local de Contoso y Skype para servidores de borde empresariales están en Chicago. Para su implementación, Contoso decidió establecer una conexión de ExpressRoute entre su data center de Chicago y el ExpressRoute de Chicago. También conferían una costa oeste ExpressRoute conexión para servir mejor a su oficina de Honolulu.
  
![ExpressRoute híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implantación en línea con la edición de conector de nube

Skype para Business Edition de conector de nube en línea es ofrecer un híbrido que consta de un conjunto de paquetes máquinas virtuales (VMs) que implementan conectividad de RTC local. Al implementar una mínima Skype para topología Business Server en un entorno virtualizado, podrá enviar y recibir llamadas con teléfonos fijos y móviles a través de la infraestructura de voz de RTC local existente.
  
Si decide implementar ExpressRoute de Azure y la nube conector Edition, se recomienda para que configurar al menos una conexión directa para cada continente entre el sitio Web principal de cada continente a su más cercano [ExpressRoute interconexión ubicación](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Función costo vs beneficio, para cada continente puede implementar conexiones adicionales de ExpressRoute de sitios donde no se cumplen los objetivos de performance de la red.
  
Si tienes un Skype local para la implementación en la empresa, debe seguir la [Guía de planificación para Skype para conector de nube Business Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). En concreto, el servidor perimetral de acceso y A / servicios de borde V deben asignarse direcciones IP públicas y son accesibles desde los centros de datos de Office 365.
  
En el siguiente ejemplo, Contoso es una empresa de contabilidad Europea con presencia en algunos de los principales países europeos y ciudades. Al inscribirse para Skype para los negocios en línea para todas sus necesidades de colaboración, decidió poner una nube de conector para cada país que tienen una ubicación física para seguir utilizando su infraestructura PSTN y los contratos de transporte que ya existen. Basado en las pruebas de todos sus sitios y borde de Microsoft network, determinó que una sola conexión de ExpressRoute de Londres ayudará a cumplir el Skype para objetivos de performance de red en conexión de negocio cliente descrito en el rendimiento de la red de [ Borde de red requisitos desde un Skype para Business client para Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Nube de ExpressRoute conector uno.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A continuación es otra opción de implementación de Contoso. En este caso, decidieron establecer una conexión de ExpressRoute en cada sitio donde se implementa un conector de nube. 
  
![Nube de ExpressRoute conector dos.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)

