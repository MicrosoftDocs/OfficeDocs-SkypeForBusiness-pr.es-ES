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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: En este tema define el conjunto de requisitos de rendimiento de red de Skype para servicios en línea de negocio y cómo se puede optar por usar Internet o ExpressRoute para la conectividad entre la red y Skype para profesionales en línea en función de la evaluación de la red conectividad. Si ha decidido implementar ExpressRoute de Azure para la conectividad dedicada a Office 365, este documento también proporciona orientación sobre cómo planear las conexiones ExpressRoute en diferente Skype para escenarios de implementación empresarial en línea.
ms.openlocfilehash: dbe927794d8660a801596dac32623574e314ee44
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295548"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online

En este tema define el conjunto de requisitos de rendimiento de red de Skype para servicios en línea de negocio y cómo se puede optar por usar Internet o ExpressRoute para la conectividad entre la red y Skype para profesionales en línea en función de la evaluación de la red conectividad. Si ha decidido implementar ExpressRoute de Azure para la conectividad dedicada a Office 365, este documento también proporciona orientación sobre cómo planear las conexiones ExpressRoute en diferente Skype para escenarios de implementación empresarial en línea.
  
La calidad de medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) a través de IP simplifica en gran medida se ve afectada por la calidad de la conectividad de red de extremo a otro. Para Skype óptima para la calidad de medios en línea de negocio, es importante que para asegurarse de que hay una conexión de alta calidad entre la red de empresa y Skype para profesionales en línea. La mejor forma de hacerlo es configurar la red interna y la conectividad de la nube en función de la capacidad de la red para dar cabida a para el volumen del tráfico pico de Skype para profesionales en línea a través de todas las conexiones.
  
ExpressRoute Azure no es un requisito para servicios de Office 365, incluidos Skype para profesionales en línea. Sin embargo, ExpressRoute de Azure es uno de la implementación de las opciones que están disponibles que ayuda a asegurarse de que conectividad a Office 365 cumple el Skype los requisitos de rendimiento de red empresarial y garantiza la Skype más óptimo para los medios de negocio en línea experiencia de calidad.
  
> [!TIP]
> Aunque este tema proporciona orientación de rendimiento de red general, una guía completa para la evaluación de la red está fuera del alcance de este documento. Para obtener una lista de Skype para los socios empresariales en línea que pueden ayudarle con las mediciones de rendimiento de red como parte de una evaluación exhaustiva y completa de red, visite [Skype para las soluciones de socios de negocio](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividad de red a Skype para profesionales en línea

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factores que afectan a Skype para calidad de medios en línea de negocio

Hay muchos distintos factores que contribuyen a Skype para la calidad de los medios (audio, vídeo y aplicaciones de uso compartido) en tiempo real en línea de negocio que incluyen los dispositivos que se usan, el entorno y la conectividad de red. 
  
#### <a name="devices"></a>Dispositivos

En una sesión de medios en tiempo real, medios capturar y representación de los dispositivos que se utilizan por todos los participantes, como auriculares con micrófono y cámaras Web tienen un gran impacto en el audio general y la calidad de vídeo. Los dispositivos de audio y vídeo de menor calidad o que utilizan controladores incorrectos generan, respectivamente, sonido e imágenes de calidad reducida. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Aunque la certificación dispositivos multimedia de audio y vídeo no son necesarios, se recomienda dispositivos certificación para Skype para la empresa para la experiencia de medios óptima. Para obtener una lista de todos los Skype para la empresa certificados dispositivos, consulte [teléfonos y dispositivos de Skype para la empresa](https://technet.microsoft.com/en-us/office/dn947482). Puede usar el [Skype para profesionales Online panel calidad de llamadas](/microsoftteams/turning-on-and-using-call-quality-dashboard), que se encuentra en el **Centro de Skype para administración empresarial**, para comprobar los dispositivos en uso funcionan correctamente y supervisar la calidad de los medios de audio y vídeo.
  
> [!TIP]
> **Se requiere un dispositivo certificado para la Skype más óptima para la experiencia de calidad de medios de Business**.
  
Es importante recordar que los dispositivos de medios, Skype para clientes empresariales y Skype para servidores empresariales a través de qué flujos de medios en tiempo real, presentan cierta cantidad de latencia. El dispositivo y el software de procesamiento de latencia, junto con la latencia de red, tienen un gran impacto en y contribuyan a la latencia general-to-end y la experiencia del usuario final.
  
#### <a name="environment"></a>Entorno de

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen más clara de uso de la experiencia de audio y vídeo de un usuario la Skype para la aplicación empresarial de **las herramientas de** > **Opciones** > **Dispositivo de Audio** o **Dispositivo de vídeo** para realizar cambios en el dispositivo en uso y personalizar su configuración.

#### <a name="network"></a>Network

La calidad de los medios en tiempo real a través de la red IP en gran medida se ve afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:
  
- **Latencia** Esto es el tiempo necesario para obtener un paquete IP de punto A punto b en la red. Este retraso de propagación de red básicamente está asociado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una sobrecarga adicional realizada por los diversos enrutadores intermedios. Latencia se mide como tiempo unidireccional o de ida y vuelta (RTT).
    
- **Pérdida de paquetes** A menudo se define como un porcentaje de paquetes que se pierden en una determinada ventana de tiempo. Pérdida de paquetes afecta directamente a la calidad de audio: desde pequeñas, individual perdido paquetes no tener casi ningún impacto, a las pérdidas de ráfagas opuesta que provocar cut-salida de audio completa.
    
- **Llegada entre paquete vibración o simplemente vibración** Éste es el cambio promedio de retraso entre envíos sucesivos de paquetes. Software de VoIP más moderno incluidos Skype para la empresa puede adaptarse a algunos niveles de vibración a través de almacenamiento en búfer. Es sólo cuando la vibración supera el almacenamiento en búfer que un participante se tenga en cuenta los efectos de vibración.
    
> [!NOTE]
>  Almacenamiento en búfer de vibración aumentará la latencia de extremo a otro.
  
Con muchos Skype simultáneos para sesiones de medios en tiempo real en línea de negocio, así como otro tráfico de red generado por otros servicios de Office 365 y otras aplicaciones empresariales, asegurándose de que hay suficiente ancho de banda a través de la ruta de acceso de toda la red que conecta la red a la Skype para servicios en línea de negocio es fundamental para evitar la congestión de la red y asegúrese de medios excelentes calidad multimedia en tiempo real (audio, vídeo y aplicaciones de uso compartido). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementación de calidad de servicio (QoS) a través de redes congestionadas

Además, congestión del tráfico a través de una red en gran medida tendrá un impacto calidad de los medios. Para permitir que los paquetes de audio y vídeos a la red más rápida de viajes y prioridad a través de otro tráfico de red en una red congestionada, calidad de servicio (QoS) puede usarse para ayudar a proporcionar una experiencia óptima para el usuario final para las comunicaciones de audio y vídeos.
  
QoS proporciona un método asignar prioridades mayores a los paquetes de red que están llevando a los datos de audio o vídeos. Mediante la asignación de una prioridad superior a estos paquetes, están probable que viajar a través de la red con mayor rapidez y con menos interrupciones, de sesiones de red con cosas como las transferencias de archivos, exploración web o las copias de seguridad de la base de datos comunicaciones de audio y vídeo. Eso es porque los paquetes de red se usan para las transferencias de archivos o las copias de seguridad de base de datos de forma predeterminada se asignan "mejor esfuerzo" como una prioridad y congestión de la red no tendrá como gran impacto. Si no asignar una mayor prioridad a los paquetes multimedia (audio, vídeo y aplicaciones de uso compartido) y dejarlos asigna también como "mejor esfuerzo", demasiado sean procesados junto con el resto del tráfico de red. Según la cantidad de congestión de la red, esto potencialmente acabará en una experiencia de calidad de vídeo y audio general inferior para los usuarios.
  
Se recomienda que implemente QoS en la red para asegurarse de que la congestión de la red dentro de la red no tendrá un impacto. Sin embargo, para que esto tiene el máximo impacto, todos los extremos de redes deben admitir QoS, lo que significa que todos los extremos deben respetar QoS marcar y prioridad de los paquetes. Skype para servicios en línea de negocio respetan QoS marcar y priorización dentro de la red de Microsoft. Sin embargo, el tráfico que se enruta a través de una conexión pública como Internet desde la red de su empresa a la red de Microsoft no conserva las marcas de QoS y prioridad de los paquetes. Las conexiones privadas desde la red a Office 365 con [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) ofrecen una solución de implementación que conserva el audio QoS marcas y prioridad de los paquetes que a su vez aumentará general y la calidad de vídeo para los usuarios finales.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de rendimiento de red para conectarse a Skype para profesionales en línea
<a name="bkNetworkPerf"> </a>

Skype para multimedia en tiempo real de negocio internos se enruta a través de muchos dispositivos diferentes, aplicaciones de cliente, software de servidor y a través de redes diferentes. La latencia de end-to-end de medios en tiempo real es la cantidad total de latencia que se introdujeron en todos los componentes y segmentos de red. La calidad de la conexión de red de extremo a extremo se determina por el segmento de red con la calidad peor. Este segmento actúa como un cuello de botella para el tráfico de red.
  
El siguiente diagrama ilustra el flujo de audio unidireccional en una conferencia desde una Skype para participante de negocio a otra.
  
![Flujo de llamadas de ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
En este escenario de conferencias, consiste en la ruta de acceso de medios a través de los segmentos de red siguientes:
  
1. **Conexión de usuario 1 hasta el borde de la red de Microsoft** Normalmente, esto incluye una conexión de red como WiFi o Ethernet, la conexión WAN de usuario 1 hasta el punto de salida de Internet (el dispositivo de red perimetral) y la conexión a Internet desde la red perimetral a la red perimetral de Microsoft.
    
2. **Conexión dentro de la red de Microsoft** Esto es entre Microsoft Edge a Skype para el centro de datos profesionales en línea, donde el se utilizan los servidores de conferencia A/v.
    
3. **Conexión dentro de la red de Microsoft** Esto es entre el Skype para el centro de datos profesionales en línea y la red perimetral de Microsoft.
    
4. **Conexión desde el perímetro de red de Microsoft al usuario 2** Esto incluye la conexión a Internet desde la red perimetral a la red perimetral, la conexión WAN del usuario 2 para el punto de salida de Internet (la red perimetral) y la conexión de red como un WiFi o Ethernet de Microsoft.
    
El siguiente diagrama muestra el desglose de los componentes y segmentos de red de un Skype para llamada de RTC en línea de negocio:
  
![Flujo de llamadas de operador de RTC de ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
En un escenario de llamada de RTC, la ruta de acceso de medios cruza los segmentos de red siguientes:
  
1. **Conexión desde una Skype para profesionales cliente autor de la llamada hasta el borde de la red de Microsoft** Normalmente, esto incluye una conexión de red como WiFi o Ethernet, la conexión WAN desde el Skype para profesionales cliente autor de la llamada hasta el punto de salida de Internet (el dispositivo de red perimetral) y la conexión a Internet desde la red perimetral a la red perimetral de Microsoft.
    
2. **Conexión dentro de la red de Microsoft** Esto es entre Microsoft Edge a Skype para el centro de datos profesionales en línea, donde se usa un servidor de mediación.
    
3. **Conexión dentro de la red de Microsoft** Esto es entre el Skype para el centro de datos profesionales en línea y la red perimetral de Microsoft.
    
4. **Conexión entre la red de Microsoft y los socios de proveedor de servicio RTC** Ésta es la conexión que existe para realizar una llamada de RTC desde el Skype para clientes empresariales que está fuera de la red de Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de rendimiento de red desde un Skype para cliente de negocio a Microsoft de la red perimetral
<a name="bkSfBClienttoEdge"></a>

Para Skype óptima para la calidad de los medios empresariales, los destinos de las métricas de rendimiento de red o umbrales siguientes son necesarios para una conexión de red de su empresa a la red perimetral de Microsoft. En este segmento de la red incluye la red interna, esto incluye todas las conexiones WiFi y Ethernet, cualquier tráfico de sitio a sitio de empresa a través de una conexión WAN, por ejemplo de conmutación de etiqueta de multiprotocolo (MPLS), así como el socio de Internet o ExpressRoute conexiones a la red perimetral de Microsoft.
  
> [!CAUTION]
> **Conectividad entre un Skype para cliente de negocio en la red de su empresa a los servicios de Office 365 debe cumplir estos requisitos de rendimiento de red siguientes y umbrales.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino ** <br/> |
|Latencia (unidireccional)  <br/> |< 50 ms  <br/> |
|Latencia (RTT o tiempo de ida y vuelta)  <br/> |< 100 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |< 10% durante un intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |< 1% durante un intervalo de 15 s  <br/> |
|Vibración entre llegadas de paquetes  <br/> |< 30 ms durante un intervalo de 15 s  <br/> |
|Reordenamiento de paquetes  <br/> |< 0,05% paquetes sin ordenar  <br/> |
   
 **Otros requisitos de destino de rendimiento:**
  
- La red de Microsoft tiene más de 160 perimetral ubicaciones en todo el mundo. Trabajamos con los principales proveedores de servicios de Internet (ISP) en todo el mundo a través de dichos sitios perimetral. El destino de métricas de latencia, se da por supuesto su sitio de empresa o los sitios y los Edges de Microsoft se encuentran en el mismo continente.
    
- Su sitio de empresa o los sitios a la conexión del extremo de red de Microsoft incluyen el primer salto acceso a la red, que puede ser WiFi u otra tecnología inalámbrica. 
    
- Ancho de banda adecuado o la calidad de la planeación de servicio, supone el destino de rendimiento de red. En otras palabras, esto se aplica directamente a Skype para el tráfico de medios en tiempo real de negocio cuando la conexión de red está bajo una carga máxima.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de rendimiento de red de la red perimetral a la red perimetral de Microsoft
<a name="bkYourNetworkEdge"> </a>

Los siguientes son los umbrales que son necesarios para la conexión entre la red perimetral y la red perimetral de Microsoft o los objetivos de rendimiento de red. Excluye de la red interna del cliente o WAN este segmento de la red y sirve como guía cuando se prueba el tráfico de red que se envía a través de Internet o a través de una red de socios de ExpressRoute y también se puede usar al negociar un rendimiento Contrato de nivel de servicio (SLA) con su proveedor de ExpressRoute.
  
> [!CAUTION]
> **Conectividad entre la red de su empresa perimetral hasta el borde de la red de Microsoft debe cumplir estos requisitos de rendimiento de red siguientes y umbrales.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino ** <br/> |
|Latencia (unidireccional)  <br/> |< 30 ms  <br/> |
|Latencia (RTT)  <br/> |< 60 ms  <br/> |
|Pérdida de paquetes de ráfaga  <br/> |< 1% durante un intervalo de 200 ms  <br/> |
|Pérdida de paquetes  <br/> |< 0,1% durante un intervalo de 15 s  <br/> |
|Vibración entre llegadas de paquetes  <br/> |< 15 ms durante un intervalo de 15 s  <br/> |
|Reordenamiento de paquetes  <br/> |< 0,01% paquetes sin ordenar  <br/> |
   
 **Otros requisitos de destino de rendimiento:**
  
- El destino de rendimiento requiere conexión entre cualquiera de la red perimetral de su compañía y su red de Microsoft más cercano perimetral, que esté en el mismo continente.
    
- Ancho de banda adecuado o la calidad de la planeación de servicio, supone el destino de rendimiento de red. Esto también se aplica a Skype para el tráfico de medios en tiempo real de negocio cuando la conexión de red está bajo una carga máxima. Para la planeación de QoS y el ancho de banda adecuado, consulte [ExpressRoute y QoS en Skype para profesionales en línea](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Medición del rendimiento de la red
<a name="bkNetworkPerf"> </a>

Para medir el rendimiento real de la red, especialmente para la latencia y la pérdida de paquetes, desde cualquier sitio de red de empresa a una red perimetral, puede utilizar herramientas como ping, con un conjunto de Skype para servicios de retransmisión de medios empresariales que se ejecutan desde el Microsoft Edge y los datos de prueba sitios del centro. 
  
Para probar las conexiones de Internet a la red de Microsoft, se recomienda probar frente a las direcciones VIP siguientes de la Skype para transmisiones de medios de negocio. La *Dirección VIP de difusión por proximidad* se puede resolver en una dirección IP de un relé de medios en un sitio de perímetro de red de Microsoft más cercano a la ubicación de prueba.
  
||||
|:-----|:-----|:-----|
|**Dirección IP** <br/> |**Tipo** <br/> |**Ubicación** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP de difusión por proximidad todo el mundo  <br/> |
   
 **Éstas son algunas recomendaciones de alto niveles que se deben seguir para evaluar el rendimiento de red:**
  
- Debe evaluar la red interna, así como las conexiones a Office 365.
    
- Debe evaluar y recopilar datos para todas las redes durante un largo período de tiempo. Se recomienda que debe realizar las pruebas de rendimiento de la red de un mínimo de una semana, para que puedan ver los patrones de uso para todos los días laborables y horas. Esto le mostrará las horas pico.
    
- Debe realizar varios ejemplos de las mediciones de rendimiento de red. Se recomienda obtener una medición a cada 10 minutos desde un sitio de la empresa durante todo el período de tiempo de que recopilación de datos. Para comparar la Skype para requisitos de rendimiento de red en línea de negocio, tomar el valor de medida del percentil 90 de este conjunto de datos de ejemplo. 
    
- Continuamente debe evaluar el rendimiento de la red. Utilización de la red varía con el tiempo debido a cambios de patrón de uso, las aplicaciones de empresa nuevo que usan una gran cantidad de ancho de banda y los cambios realizados en las ubicaciones de la compañía organizativa o físico. Es importante supervisar el rendimiento de la red frente a estos requisitos de rendimiento de red y los objetivos y umbrales continuamente y realizar ajustes oportunos para garantizar la calidad de medios en tiempo real más óptima. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medición del rendimiento de la red con máquinas virtuales de Azure
<a name="bkNetworkPerf"> </a>

En lugar de probar frente a los sitios de Microsoft red perimetral, existen soluciones de evaluación de red de Skype para los clientes empresariales y socios que aprovechan las prueba del programa de instalación para los servicios en la nube de Microsoft Azure. En estas soluciones, las herramientas de evaluación de la red probar la latencia, la pérdida de paquetes y vibración contra extremos personalizados configurado como un servicio en la nube de Azure. Como resultado, se transporta el tráfico de red de prueba a través de un segmento de red adicionales, que es la conexión dentro de la red de Microsoft, entre los bordes de la red y centros de datos de Azure que hospeda el servicio de evaluación de la red.
  
Para esas red soluciones de evaluación basadas en Azure servicios hospedan de pruebas. Le recomendamos que realice la evaluación de la red dentro de país o región. Por ejemplo, para sitios de clientes en Estados Unidos de Asia oriental, debe realizar la evaluación frente a una instancia de servicio de prueba hospedada en Asia de Azure región del centro de datos de Estados Unidos. 
  
A continuación encontrará la latencia destinos (RTT) para la configuración de evaluación de red de servicios de Azure en función. Los objetivos de latencia unidireccional será la mitad de los destinos RTT correspondientes. Los objetivos de variación y pérdida de paquetes se mantiene el mismo como los definidos para la transmisión de medios de Skype en función de las pruebas.
  
|||||
|:-----|:-----|:-----|:-----|
|**Región cliente** <br/> |**Área de Azure** <br/> |**La red perimetral - tiempo de ida y vuelta de Azure (RTT)** <br/> |**Su sitio - Azure tiempo de ida y vuelta (RTT)** <br/> |
|Central de EE.  <br/> |Central de EE.  <br/> |99  <br/> |139  <br/> |
|Asia oriental de Estados Unidos  <br/> |Asia oriental de Estados Unidos  <br/> |86  <br/> |126  <br/> |
|Norte Central de EE.  <br/> |Norte Central de EE.  <br/> |97  <br/> |137  <br/> |
|Sur Central de EE.  <br/> |Sur Central de EE.  <br/> |94  <br/> |134  <br/> |
|Estados Unidos occidental  <br/> |Estados Unidos occidental  <br/> |94  <br/> |134  <br/> |
|Hawai EE.  <br/> |Estados Unidos occidental  <br/> |116  <br/> |156  <br/> |
|Canadá Central  <br/> |Canadá Central  <br/> |138  <br/> |178  <br/> |
|Canadá oriental  <br/> |Canadá oriental  <br/> |131  <br/> |171  <br/> |
|Norte Europa  <br/> |Norte Europa  <br/> |99  <br/> |139  <br/> |
|Europa occidental  <br/> |Europa occidental  <br/> |95  <br/> |135  <br/> |
|Asia oriental  <br/> |Asia oriental  <br/> |118  <br/> |158  <br/> |
|Sureste de Asia  <br/> |Sureste de Asia  <br/> |97  <br/> |137  <br/> |
|Asia oriental de Japón  <br/> |Asia oriental de Japón  <br/> |111  <br/> |151  <br/> |
|Japón oeste  <br/> |Japón oeste  <br/> |118  <br/> |158  <br/> |
|Sur de Brasil  <br/> |Sur de Brasil  <br/> |70  <br/> |110  <br/> |
|Australia Oriental  <br/> |Australia Oriental  <br/> |124  <br/> |164  <br/> |
|Australia sureste  <br/> |Australia sureste  <br/> |124  <br/> |164  <br/> |
|India central  <br/> |India central  <br/> |103  <br/> |143  <br/> |
|India sur  <br/> |India sur  <br/> |103  <br/> |143  <br/> |
|India occidental  <br/> |India occidental  <br/> |103  <br/> |143  <br/> |
|Asia oriental China  <br/> |Asia oriental China  <br/> |120  <br/> |160  <br/> |
|Norte de China  <br/> |Norte de China  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Calidad de los medios y ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute Azure para Office 365 es una conexión de red dedicada para conectarse a Office 365. Ofrece a los clientes la capacidad para tener control sobre la ruta de acceso de sus toma el tráfico de red de Office 365. Ya no tienen que preocuparse por el enrutamiento impredecible que suceda en Internet donde se lleva a datos por operadores desconocidos, proveedores e ISP. El tráfico de red que se envía a través de ExpressRoute se envía directamente a través de la red del socio ExpressRoute a la red de Microsoft. Esto permite a los clientes tratar Office 365 como si se encuentra en su propio centro de datos fuera del sitio con una conexión dedicada.
  
ExpressRoute Azure está disponible para todas las ofertas de licencias de Office 365. Sin embargo, el complemento de Azure ExpressRoute Premium es necesario para Office 365 habilitar el enrutamiento global. Los clientes de Office 365 con al menos 500 puestos que están implementando ExpressRoute pueden obtener el necesario *ExpressRoute Premium complemento* sin cargo adicional.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>¿Es necesario ExpressRoute para la calidad de los medios buena?

ExpressRoute Azure no es un requisito para obtener el más óptimo Skype para calidad de medios en línea de negocio. Es, sin embargo, uno de la implementación de opciones que le ayudarán a Asegúrese de que la conectividad de la nube cumple el Skype para los objetivos de rendimiento de red empresarial o umbrales.
  
Office 365 es un alto rendimiento y el servicio seguro que usa Internet. Se seguirán invertir en nuevas capacidades de seguridad y nodos perimetrales regionales para mejorar constantemente la seguridad y el rendimiento. ExpressRoute Azure no es un requisito para servicios de Office 365, incluidos Skype para profesionales en línea. ExpressRoute Azure es uno de la implementación de las opciones que están disponibles que ayuda a asegurarse de que conectividad a Office 365 cumple el Skype los requisitos de rendimiento de red empresarial y garantiza la Skype más óptima para la calidad de medios en línea de negocio experiencia.
  
Para Skype para calidad de medios en línea de negocio, es importante que la conexión entre los sitios de la empresa y los bordes de la red Microsoft cumple los objetivos de rendimiento en los requisitos de [rendimiento de la red desde un Skype para clientes empresariales a la red de Microsoft Borde](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) y que la conexión entre los bordes de red y los bordes de la red de Microsoft cumple los objetivos de rendimiento en [los requisitos de rendimiento de red de la red perimetral a la red perimetral de Microsoft](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
También es importante que conectividad de red físico de su compañía, incluida la capacidad de conectividad de red y en la nube interno acomodar el volumen de tráfico de medios máximo. ExpressRoute Azure es una de las muchas maneras que ayudan a los clientes a asegurarse de que sus Skype para la conectividad de la nube en línea de negocio cumple todos estos requisitos de rendimiento.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>¿Es necesario ExpressRoute para SLA de calidad de voz?

No, ExpressRoute no se necesita para Skype para profesionales SLA de calidad de voz en línea. El [Skype para profesionales SLA de calidad de voz en línea](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) se aplica a cualquier llamada optan realizada por cualquier Skype para usuario de servicio de voz empresarial en línea dentro de la licencia correcta y suscripción que permite que el usuario realice cualquier tipo de llamada de VoIP o RTC. Debe incluir un SLA de calidad de voz que se tratan todas las condiciones siguientes:
  
- Las llamadas de Microsoft certificación teléfonos IP.
    
- Conexiones Ethernet por cable.
    
- Problemas de calidad de voz debido a problemas de Microsoft Network.
    
> [!NOTE]
> El SLA de calidad de voz excluye esas llamadas donde la calidad de las llamadas baja está causada por problemas en las redes que no son de Microsoft como socio de ExpressRoute y otras redes. 
  
### <a name="internet-or-azure-expressroute"></a>¿Internet o ExpressRoute Azure?

Antes de tomar una decisión de red opciones de conectividad a Skype de negocio en línea, deben evaluar los clientes de su red y la conectividad de Internet actual en función de los requisitos de rendimiento de red que se describen en requisitos de rendimiento de red de [a conectarse a Skype para profesionales Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Si se establece el rendimiento de la red a través de la conexión actual a Internet permitiendo suficiente capacidad durante el tiempo máximo y cumple los requisitos de rendimiento de red de los sitios de los bordes de la red de Microsoft y de sus bordes de red a bordes de red de Microsoft, puede seguir usando la conectividad a Internet existente para conectarse a Skype para profesionales en línea.
  
Para los sitios de la empresa donde no se cumplen los requisitos de rendimiento de red, se recomienda que primero funcionan con los proveedores de servicios de red existente para mejorar el rendimiento general de la red. Sin embargo, si aún no se cumplen, utilizando ExpressRoute de Azure puede ayudar a garantizar su Skype para la conectividad de la nube en línea de negocio le ayudará a cumplir los requisitos de rendimiento de red.
  
ExpressRoute Azure ofrece las siguientes ventajas adicionales:
  
- Un nivel acuerdo de servicio (SLA) de la disponibilidad de la conexión entre la red y la red de Microsoft. ExpressRoute tiene un SLA de disponibilidad garantizada del 99,9%.
    
- Planeada y garantizada requerido ancho de banda para servicios de Office 365. Puede realizar esta acción mediante el envío de sólo el tráfico de Office 365 o Skype para el tráfico de negocio mediante la ExpressRoute y, a continuación, tener todos los otro Internet el tráfico pase a través de otros puntos de entrada/salida de Internet de la red.
    
- ExpressRoute está diseñado para conservar el marcado de DSCP QoS entre la red y Microsoft Network.
    
Para obtener más información acerca de ExpressRoute QoS y planeación de la capacidad, consulte [ExpressRoute y QoS en Skype para profesionales en línea](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>¿Instalación ExpressRoute de Azure para Skype para sólo empresarial en línea?

Sí, puede configurar ExpressRoute de Azure para garantizar la conectividad de red excelente de red de su empresa con sólo Skype para profesionales en línea. Esto proporcionará la calidad de medios en tiempo real más óptima para los usuarios pero, a continuación, puede continuar conecta a otros servicios de Office 365 a través de Internet.
  
El protocolo de puerta de enlace de borde (BGP) es un protocolo de enrutamiento en Internet que se usa para enrutar el tráfico de red a través de Internet. Está diseñado para intercambiar información de enrutamiento entre sistemas autónomos (AS) que se encuentra a través de Internet. Los valores de las Comunidades BGP son las etiquetas de atributo que se pueden aplicar a las rutas entrantes o salientes. Las Comunidades BGP se suelen usar para señalar a la recepción como qué vínculo saliente para llegar a un destino determinado en función de geografía, tipo de servicio u otros criterios.
  
Con compatibilidad con las Comunidades BGP, Microsoft va a marcar prefijos y rutas con valores adecuados de la Comunidad BGP basados en el servicio que pertenecen. Microsoft va a etiquetar prefijos anunciados a través de interconexión pública y los prefijos de Microsoft interconexión con los valores de la Comunidad BGP adecuados, que indica la región se hospedan en. Puede confiar en los valores de la Comunidad para tomar decisiones de enrutamiento apropiadas para ofrecer enrutamiento óptimo. Puede usar el Skype para el valor de la Comunidad de BGP en línea de negocio para el programa de instalación de una conexión a ExpressRoute sólo para Skype para profesionales en línea. Puede encontrar más información en [los requisitos de enrutamiento ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Escenarios de conectividad de ExpressRoute de Skype para profesionales en línea
<a name="bkNetworkPerf"> </a>

Si ha decidido que ExpressRoute según las recomendaciones anteriores es para usted, aquí están las recomendaciones sobre dónde y cuántas conexiones ExpressRoute debe obtener.
  
### <a name="online-only-deployment---single-site"></a>Implementación solo Online - único sitio

Si todos los usuarios utilizan la Skype para servicios en línea de negocio y sus oficinas se centran en una sola ubicación física y decide implementar ExpressRoute de Azure, debe configurar conexión de ExpressRoute único entre el sitio de su compañía a la más cercano [Ubicación de interconexión ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
El gráfico siguiente muestra un ejemplo de este tipo de implementación. Para este ejemplo, Contoso es una universidad que se encuentra en Orlando, FL. Contoso tiene 10.000 miembros profesores y estudiantes. Las pruebas de Internet desde su ubicación a sitios de borde de Microsoft mostraron un mayores que el 5% la pérdida de paquetes durante las horas de clase. El haber decidido obtener una conexión dedicada a Office 365 con ExpressRoute con un provisioning excesivo ancho de banda, por lo que pueden evitar la congestión de la red para Office 365 especialmente para Skype para el tráfico en tiempo real en línea de negocio. Se conectan a la nube de Microsoft a través de ExpressRoute en el sitio de Atlanta, Georgia MeetMe.
  
![Sitio de ExpressRoute único.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implementación solo Online - varios sitios en el mismo continente

Si su compañía usa Skype para los servicios en línea de negocio de varias oficinas en la misma región o continente y opta por implementar ExpressRoute de Azure, se recomienda para conectar el sitio principal a través de ExpressRoute y, a continuación, de forma opcional agregar adicionales ExpressRoute interconexión para otras ubicaciones que no cumplan los objetivos de rendimiento de red recomendada.
  
En el siguiente ejemplo, Contoso es una empresa de servicios de viajes de Estados Unidos que se encuentra en Nueva York, pero tiene otras oficinas de los Estados Unidos. Sus oficinas están entre granjas conectados a través de una WAN que usa MPLS para conectarse a Office 365. Configura inicialmente una conexión ExpressRoute desde su enrutador de Internet en Hoboken, Nueva Jersey en el sitio de Nueva York MeetMe. 
  
Con esta configuración, el tráfico de red de la mayoría de los sitios a Microsoft Network (sitio de Nueva York perimetral) puede cumplir los Skype para los objetivos de rendimiento de red en conexión de negocio cliente descritos en requisitos de rendimiento de la red [desde un Skype para clientes empresariales a Microsoft de la red perimetral](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Sin embargo, se trata de latencia entre las oficinas de costa oeste de Contoso a Nueva York a través de 50 ms. unidireccional. Además, Honolulu es el segundo mayor office para Contoso, latencia de Honolulu a Nueva York supera 80 ms unidireccional. Para garantizar la calidad de medios buena para los usuarios de dichas oficinas, Contoso decidió agregar un costa oeste ExpressRoute conexión entre su sitio de San José y el sitio de Silicon Valley ExpressRoute MeetMe.
  
![Express enrutador múltiples sitios en el mismo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implementación solo Online - varios sitios en diferentes países

Si todos los usuarios son usar Skype para servicios en línea de negocio y sus oficinas se encuentran en varias ubicaciones físicas en varios continentes, si decide implementar ExpressRoute de Azure, debe configurar al menos una conexión de ExpressRoute para cada continente entre sitios principal de cada continente a su [ubicación de interconexión ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)de más cercano. Dependiendo de costos frente a beneficios, puede elegir implementar conexiones de ExpressRoute adicionales de los sitios donde no se cumplen los objetivos de rendimiento de red.
  
En el siguiente ejemplo, Contoso es una empresa de abogados corporativos de gran tamaño con oficinas en las principales ciudades en Norteamérica y Europa. En función de su conexión a Internet y su evaluación de rendimiento de la red interna, Contoso decidió implementar dos conexiones ExpressRoute en Norteamérica y un único circuito ExpressRoute para todas sus oficinas en Europa.
  
![ExpressRoute con varios sitios y continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implementación híbrida

Si tiene un Lync local o Skype para la implementación empresarial y optar por implementar un híbrido Skype para la integración de negocio en línea, se recomienda que, si decide implementar ExpressRoute de Azure, debe tener al menos una conexión de ExpressRoute para cada uno local Lync o Skype para sitio de perímetro empresarial y al menos una conexión de ExpressRoute para cada continente con oficinas. Según la ventaja de frente a costo, para cada continente puede elegir implementar conexiones de ExpressRoute adicionales de oficinas donde no se cumplen los objetivos de rendimiento de red.
  
Si tiene un Skype local para la implementación empresarial, debe seguir la [Guía de implementación y planeación del servidor perimetral](https://technet.microsoft.com/en-us/library/mt346417.aspx). Específicamente, los servidores perimetrales deben ser accesibles desde fuera de la red. Normalmente, esto se logra mediante la asignación de una dirección IP pública enrutable al servidor perimetral, o mediante el uso de traducción de direcciones de red (NAT).
  
En el siguiente ejemplo, Contoso tiene una Skype local existente para la implementación de Enterprise Voice de negocio. Desean migrar usuarios locales a servicios en línea de Office 365. También decidió usar una implementación híbrida de modo que puede seguir usando su infraestructura existente de RTC para todos los usuarios en línea y local. Centro de datos local de Contoso y Skype para los servidores perimetrales de negocio se encuentran en Chicago. Para su implementación, Contoso decidió establecer una conexión de ExpressRoute entre su centro de datos de Chicago y el ExpressRoute de Chicago. También agrega una conexión de ExpressRoute para servir mejor a su office Honolulu de costa oeste.
  
![ExpressRoute híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implementación en línea con la edición de conector en la nube

Skype para Business Edition de conector de nube en línea es un híbrido que ofrece que consta de un conjunto de empaquetado máquinas virtuales (VM) que implementan la conectividad de RTC local. Mediante la implementación de un mínimo Skype para la topología de servidor empresarial en un entorno virtualizado, podrá enviar y recibir llamadas con landlines y teléfonos móviles a través de la infraestructura de voz de RTC local existente.
  
Si decide implementar ExpressRoute de Azure y la nube conector Edition, se recomienda para que configurar al menos una conexión de ruta Express para cada continente entre el sitio principal de cada continente de TI más cercano [ExpressRoute interconexión ubicación](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Según la ventaja de frente a costo, para cada continente puede elegir implementar conexiones de ExpressRoute adicionales de los sitios donde no se cumplen los objetivos de rendimiento de red.
  
Si tiene un Skype local para la implementación empresarial, debe seguir la [Guía de planeación de Skype para Business Edition de conector en la nube](https://technet.microsoft.com/EN-US/library/mt605227.aspx). En concreto, el servidor perimetral de acceso y / servicios perimetrales de V deben asignarse direcciones IP públicas y está accesible desde los centros de datos de Office 365.
  
En el siguiente ejemplo, Contoso es una empresa de contabilidad Europea con presencia en unos principales países europeos y ciudades. Cuando inician sesión copia de seguridad de Skype para empresarial en línea para todas sus necesidades de colaboración, decidió poner un conector en la nube para cada país que tienen una ubicación física para seguir usando su infraestructura de RTC y los contratos de transporte que ya existen. En función de las pruebas de todos sus sitios y la red perimetral de Microsoft, determina que una sola conexión ExpressRoute en Londres ayudará a cumplir el Skype para los objetivos de rendimiento de red en conexión de negocio cliente que se describen en [rendimiento de la red requisitos de un Skype para clientes empresariales a Microsoft de la red perimetral](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Conector de nube ExpressRoute uno.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A continuación es otra opción de implementación para Contoso. En este caso, decidió configurar una conexión de ExpressRoute en cada sitio donde se implementa un conector en la nube. 
  
![Conector de nube ExpressRoute dos.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 