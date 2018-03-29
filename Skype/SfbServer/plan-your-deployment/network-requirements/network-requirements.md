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
description: 'Resumen: Revisar las consideraciones de componente de red a continuación antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: 3d3fd2141da93a9b0b866fe44e2ed8dee6942f3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-network-requirements-for-skype-for-business-2015"></a>Planificar los requisitos de red para Skype Empresarial 2015
 
**Resumen:** Revisar las consideraciones de componente de red a continuación antes de implementar Skype para Business Server 2015.
  
La información de estos temas también se describe en el white paper [Planificación de redes, supervisión y solución de problemas con Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) con detalles adicionales y profundidad. Mientras que el contenido se refiere explícitamente a Lync 2010 y Lync 2013, las consideraciones de Skype para Business Server 2015 no se modifican.
  
Del mismo modo, si trata de su red wi-fi, así como acceso por cable, las notas del producto [Entrega Lync 2013 real-time Communications en Wi-Fi](http://www.microsoft.com/en-us/download/details.aspx?id=36494) es una buena referencia y es igualmente aplicable a Skype para Business Server 2015.
  
Rendimiento de la red y las necesidades se vinculan directamente a la carga de tráfico que se colocan en ellos. Al planear sus implementaciones de servidor y de red le recomendamos utilizar el [Skype para la herramienta de planeación de Business Server 2015](../../management-tools/planning-tool/planning-tool.md), el [Skype para Calculadora de planeación de capacidad de Business Server 2015](../../management-tools/capacity-planning-calculator.md)y el [Skype para Business Server 2015 Herramienta de carga y rendimiento](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

El adaptador de red de cada servidor en el Skype para la topología de servidores de negocios debe admitir al menos 1 gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor en el Skype para la topología de servidores de negocios con una baja latencia y alto ancho de banda red local (LAN). El tamaño de la LAN depende del tamaño de la topología: 
  
- En las topologías de Standard Edition, deben ser servidores en una red compatible con Ethernet de 1 Gbps o equivalente.
    
- En las topologías de Enterprise Edition, la mayoría de los servidores deben estar en una red que admite más de 1 Gbps, especialmente cuando se admiten audio y vídeo (A / V) conferencias y uso compartido de aplicaciones.
    
Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.
  
## <a name="audiovideo-network-requirements"></a>Requisitos de red para el audio y vídeo
<a name="AV_req"> </a>

Requisitos de red para audio y vídeo (A / V) en un Skype para Business Server implementación incluyen los siguientes:
  
- Si va a implementar un solo servidor perimetral o un grupo de borde utilizando Equilibrio de carga de DNS, puede configurar el servidor de seguridad _externo_ para realizar la traducción de direcciones de red (NAT). No puede configurar el servidor de seguridad _interno_ para llevar a cabo NAT. Para obtener información detallada, vea [determinar el servidor de seguridad y requisitos de intervalo de puerto k 50](http://technet.microsoft.com/library/3b849dc7-175d-40d1-820d-80e6ade6d332.aspx).
    
    > [!IMPORTANT]
    > Si tiene un grupo de servidores de borde y utiliza un equilibrador de carga de hardware, debe utilizar direcciones IP públicas en los servidores perimetrales y no puede utilizar NAT para los servidores o el grupo en el dispositivo compatible con NAT (por ejemplo, un dispositivo firewall o interruptor de LAN. Para obtener más información, vea [Resumen de puerto - escala borde consolidado con equilibradores de carga Hardware](http://technet.microsoft.com/library/91213b1e-f875-464b-83e8-fe3a351595a4.aspx). 
  
- Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente. 
    
- Si usa el protocolo de seguridad de Internet (IPsec), recomendamos deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, vea [Excepciones de IPsec](http://technet.microsoft.com/library/241f1eca-6f2f-44de-90b1-2cb659cbe27c.aspx).
    
Para proporcionar una calidad óptima de los medios, siga este procedimiento:
  
- Aprovisione los vínculos de red para admitir un rendimiento de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo (en caso de estar habilitados) durante los períodos de uso máximo. Una sesión bidireccional de audio o de vídeo usa dos secuencias, por lo que una conexión de audio o de vídeo necesitará 130 Kbps para cubrir cada secuencia. Vídeo utilizará asimismo total de 1000 Kbps para realizar una conexión ascendente y descendente. 
    
- Para afrontar los picos inesperados de tráfico y un mayor uso con el tiempo, Skype para extremos de media Business Server puede adaptarse a diferentes condiciones de red y compatibilidad con tres veces el rendimiento de audio y vídeo manteniendo una calidad aceptable. Pero, no se puede dar por sentado que esta capacidad de adaptación enmascarará el problema cuando una red esté mal aprovisionada. En una red aprovisionado bajo, se reduce la capacidad de la Skype para extremos de media Business Server tratar dinámicamente con condiciones de red variables (por ejemplo, pérdida de paquetes alta temporal).
    
- En el caso de los vínculos de red en los que el aprovisionamiento resulta muy costoso y difícil, puede que se vea obligado a considerar un aprovisionamiento para un volumen de tráfico menor. En este escenario, permiten la elasticidad de la Skype para extremos de media Business Server absorber la diferencia entre el volumen de tráfico y del nivel de tráfico pico, a costa de cierta disminución en la calidad de voz. También habrá una disminución en el margen que normalmente está disponible para absorber los picos de tráfico repentinos.
    
- En el caso de los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN de muy poca calidad), considere la posibilidad de deshabilitar el vídeo para algunos usuarios.
    
- Aprovisione la red para asegurar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) con carga máxima. La latencia es el deterioro de una red Skype para componentes de media Business Server no se puede reducir, y es importante encontrar y eliminar los puntos débiles.
    
- Para los servidores que están ejecutando un software antivirus, incluir todos los servidores que están ejecutando Skype para Business Server en la lista de excepciones para proporcionar un rendimiento óptimo y una calidad de audio. 
    
## <a name="conferencing-network-requirements"></a>Requisitos de red de la conferencia
<a name="Conf_req"> </a>

El ancho de banda que se utiliza para descargar el contenido de la conferencia desde el servidor de servicios de Internet Information Server (IIS) depende del tamaño del contenido. Puede optar por supervisar el uso real y ajustar la planeación del ancho de banda según convenga.
  
## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia
<a name="Conf_req"> </a>

Una parte importante del diseño de la red es asegurarse de que la red puede controlar el tráfico de medios generado por Skype para Business Server. Esta sección le ayudará a planear dicho tráfico multimedia. 
  
### <a name="media-traffic-network-usage"></a>Uso de red de tráfico de medios
<a name="Net_req"> </a>

El uso del ancho de banda de tráfico multimedia puede resultar difícil de calcular por la cantidad de variables distintas, como el uso de códecs, la resolución y los niveles de actividad. El uso del ancho de banda es una función del códec usado y la actividad de la secuencia, y ambos pueden variar entre escenarios. La tabla siguiente enumeran los códecs de audio que se utiliza normalmente en Skype para escenarios de Business Server.
  
**Ancho de banda de códec de audio**

|**Códec de audio**|**Escenario**|**Velocidad de bits (KBPS) de carga de audio**|**Carga de audio de ancho de banda y sólo encabezado IP (Kbps)**|**Carga de audio de ancho de banda, el encabezado IP, UDP, RTP y SRTP (Kbps)**|**Carga de audio de ancho de banda, IP header, UDP, RTP, SRTP y corrección de errores (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ancha de RTAudio  <br/> |Punto a punto  <br/> |29,0  <br/> |45,0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda estrecha de RTAudio  <br/> |Punto a punto, RTC  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferencia  <br/> |64,0  <br/> |80,0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 estéreo  <br/> |Punto a punto, conferencias  <br/> |128.0  <br/> |144,0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |RTC, conferencias  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferencia  <br/> |16,0  <br/> |32,0  <br/> |47.6  <br/> |63.6  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |36,0  <br/> |52.0  <br/> |64,0  <br/> |100.0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |26.0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |20.0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Banda ancha o estrecha de SEDA  <br/> |Punto a punto  <br/> |13.0  <br/> |29,0  <br/> |41.0  <br/> |54,0  <br/> |
   
Las cantidades del ancho de banda de la tabla anterior se basan en los paquetes de 20 ms (50 paquetes por segundo) y para los códecs Siren y G.722 se incluyen las sobrecargas adicionales del protocolo de transporte seguro en tiempo real (SRTP) de los escenarios de conferencia y asumen que la secuencia está 100 % activa. La corrección de error de reenvío (FEC) se utiliza de forma dinámica cuando existe una pérdida de paquetes en el vínculo para ayudar a mantener la calidad de la secuencia de audio. 
  
La versión estéreo del códec G.722 se utiliza en los sistemas basados en el sistema de la Sala de reuniones de Lync, que utiliza un micrófono estéreo o un par de micrófonos mono para permitir que los oyentes puedan distinguir mejor a varios hablantes en la sala de reuniones.
  
**Ancho de banda de resolución de vídeo**

|**Códec de vídeo**|**Resolución y relación de aspecto**|**Velocidad de bits de vídeo máxima de la carga (Kbps)**|**Carga de vídeo mínima velocidad de bits (Kbps)**|
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
   
Para el vídeo, el códec predeterminado es el estándar de codificación de vídeo avanzado H.264/MPEG-4 Parte 10, junto con sus extensiones de codificación de vídeo escalable. Para mantener la compatibilidad con clientes heredados, el códec RTVideo todavía se utiliza para llamadas de peer-to-peer entre Skype para Business Server y los clientes heredados. En sesiones de conferencia con ambos Skype para Business Server y los clientes heredados el Skype para Business Server extremo puede codificar el vídeo mediante los códecs de vídeo y enviar el bitstream H.264 para el Skype para clientes Business Server y el bitstream RTVideo heredado de los clientes.
  
El ancho de banda necesario depende de la resolución, la calidad, la velocidad de fotogramas y los movimientos o cambios de la imagen. Para cada resolución existen dos secuencias de bits interesantes:
  
- **Velocidad de bits máxima carga** Se trata de la velocidad de bits que se va a utilizar para la resolución a la velocidad máxima de un extremo. Es el valor que permite la máxima calidad de vídeo y de sonido.
    
- **Velocidad de bits mínima carga** Se trata de la velocidad de bits por debajo del cual un Skype para extremo Business Server cambiará a la siguiente resolución más baja. Para garantizar una determinada resolución, la velocidad de bits de carga de vídeo disponible no tiene que ser menor que esta velocidad de bits mínima para dicha resolución. Este valor le ayuda a comprender el valor mínimo posible en los casos en los que la velocidad de bits máxima no está disponible o no resulta práctica. Para algunos usuarios, esta baja velocidad de bits de vídeo puede considerarse una experiencia de vídeo no aceptable, por lo que aconsejamos precaución al considerar estas velocidades de bits mínimas de vídeo. Tenga en cuenta que en las escenas de vídeo estáticas o invariables, la velocidad de bits real puede descender temporalmente por debajo de la velocidad de bits mínima.
    
Skype para Business Server admite numerosas resoluciones. Esto permite Skype para Business Server ajustar el ancho de banda de red diferentes y la recepción de las capacidades del cliente. La proporción predeterminada de Skype para Business Server es 16:9. La relación de aspecto 4:3 heredado sigue siendo compatible con cámaras Web que no permite la captura en la relación de aspecto 16:9.
  
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
    
- Cada participante que activa el usuario envíe la secuencia de vídeo enviará una o más secuencias de vídeo. Skype para Business Server tiene la capacidad de enviar hasta cinco secuencias de vídeo para optimizar la calidad de vídeo para todos los clientes de recepción. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la CPU, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de vídeo. El caso más común es el de H.264 y una secuencia de vídeo de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de vídeo diferente) se envían para acomodar diferentes solicitudes de receptor. 
    
Además del ancho de banda necesario para el tráfico del protocolo de transporte seguro en tiempo real (RTP) para los medios de audio o vídeo, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar de estadísticas y del control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda de la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo usado para RTCP y difieren entre las secuencias de audio y vídeo por las diferencias en los datos de control. 
  
**Ancho de banda RTCP**

|**Media**|**RTCP máximo ancho de banda (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vídeo (solo se envía/recibe H.264 o RTVideo)  <br/> |10  <br/> |
|Vídeo (se envía/recibe H.264 y RTVideo)  <br/> |15  <br/> |
   
Para la planeación de la capacidad, las dos estadísticas siguientes son de interés:
  
- **Ancho de banda máximo sin FEC** El ancho de banda máximo que consumirá una secuencia. Esto incluye la actividad normal de la secuencia y el códec típico que se utiliza en el escenario sin FEC. Esto es el ancho de banda cuando la secuencia está en el 100% de actividad y no hay ninguna pérdida de paquetes desencadenar el uso de FEC. Esto es útil para calcular cuánto ancho de banda debe asignarse para permitir que el códec que se utilizará en un escenario determinado. FEC no debe ser un requisito en una red administrada.
    
- **Ancho de banda máximo con FEC** El ancho de banda máximo que consume una secuencia. Esto incluye la actividad normal de la secuencia y el códec típico que se utiliza en el escenario con FEC. Esto es el ancho de banda cuando la secuencia está en el 100% de actividad y se activa el uso de FEC para mejorar la calidad de pérdida de paquetes. Esto es útil para calcular cuánto ancho de banda debe asignarse para permitir que el códec que se utiliza en una situación determinada y permitir el uso de FEC para preservar la calidad en condiciones de pérdida de paquetes.
    
Las tablas siguientes enumeran también un valor de ancho de banda adicional, **ancho de banda típico**. Esto es el ancho de banda promedio que consume una secuencia. Esto incluye la actividad normal de la secuencia y el códec típico que se utiliza en el escenario. Este ancho de banda puede utilizarse para aproximar cuánto ancho de banda consumida por el tráfico de medios en un momento determinado, pero no debe utilizarse para planear la capacidad, ya que las llamadas individuales superará este valor cuando el nivel de actividad es mayor que el promedio. El ancho de banda de la secuencia de vídeo típicas en las tablas siguientes se basa en una combinación de diferentes resoluciones de vídeo como observados en los datos de los clientes medidos y las instalaciones más pequeñas son propensas a tener números reales que difieren de los datos de la tabla. Por ejemplo, en la mayoría de usuarios utilizaría el vídeo predeterminado de sesiones de peer-to-peer fotorrealismo de la ventana mientras que un porcentaje de usuarios podría aumentar o maximizar el Skype para aplicación Business Server permitir una mejor resolución de vídeo.
  
En las siguientes tablas se proporcionan los valores para los distintos escenarios.
  
**Planificación para la sesiones de Peer-to-Peer de la capacidad de audio y vídeo**

|**Media**|**Códec**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda máximo de secuencia sin FEC**|**Ancho de banda máximo de secuencia con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda ancha de RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Banda ancha SILK  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal al llamar a Skype para extremos de Business Server  <br/> |H.264  <br/> |460  <br/> |4010 (para una resolución máxima de 1920 x 1080)  <br/> |Ya incluido  <br/> |
|Vídeo principal al llamar a extremos de Lync 2010 o Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para una resolución máxima de 1920 x 720)  <br/> |Ya incluido  <br/> |
|Vídeo panorámica al llamar a Skype para extremos de Business Server  <br/> |H.264  <br/> |190  <br/> |2010 (para una resolución máxima de 1920 x 288)  <br/> |Ya incluido  <br/> |
|Vídeo panorámica al llamar a extremos de Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para una resolución máxima de 1920 x 144)  <br/> |Ya incluido  <br/> |
   
**Planificación de conferencias de la capacidad de audio y vídeo**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda máximo de secuencia sin FEC**|**Ancho de banda máximo de secuencia con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52,6  <br/> |68.6  <br/> |
|Recepción principal de vídeo  <br/> |H.264 y RTVideo¹  <br/> |260  <br/> |8015  <br/> |No aplicable  <br/> |
|Envío principal de vídeo  <br/> |H.264 y RTVideo  <br/> |270  <br/> |8015  <br/> |No aplicable  <br/> |
|Recepción de vídeo panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2010 (para una resolución máxima de 1920 x 288)  <br/> |No aplicable  <br/> |
|Envío de vídeo panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2515 ²  <br/> |No aplicable  <br/> |
   
1. Además, se envía el RT Video a H.264 cuando los clientes de Lync 2010 están conectados a la conferencia.
  
2. Si hay varias secuencias, dinámicamente comparten el ancho de banda asignado.
  
Para el vídeo principal, el ancho de banda de secuencia típico es el ancho de banda agregado sobre todas las secuencias de vídeo recibidas, mientras que la secuencia máxima es el ancho de banda sobre todas las secuencias de vídeo enviadas. Aun con varias secuencias de vídeo, el ancho de banda típico para vídeo es más pequeño que en el escenario punto a punto, ya que muchas conferencias de vídeo utilizan el uso compartido de contenidos, que hace que las ventanas de vídeo sean más pequeñas y, por lo tanto, las resoluciones de vídeo son inferiores. El ancho de banda máximo de carga de vídeo agregada compatible es de 8000 Kbps para las secuencias de envío y de recepción que se utilizarían (por ejemplo, si hay dos secuencias de vídeo entrantes de 1920 x 1080 p). Los valores máximos se ven con poca frecuencia en las implementaciones reales.
  
Al crear una conferencia con varios participantes que utiliza la característica de vista de la galería, utilización de ancho de banda aumenta inicialmente como combinación de participantes, después disminuye a medida que se eliminan las resoluciones para que quepan en el máximo. 
  
||**2 participantes**|**3 participantes**|**4 participantes**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluciones máx. recibidas** <br/> |1920 x 1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640 x 360 320 x 240  <br/> |640 x 360 320 x 240  <br/> |
|**Velocidad de bits media total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocidad de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |
   
El ancho de banda de secuencia típico para los vídeos panorámicos se basa en los dispositivos que solo transmiten en secuencias un vídeo panorámico de hasta 960 x 144. Tenga en cuenta que el ancho de banda de secuencia típico puede aumentar al utilizar dispositivos con un vídeo panorámico de 1920 x 288. 
  
**Capacidad de audio Planning for PSTN**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda máximo de secuencia sin FEC**|**Ancho de banda máximo de secuencia con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (Esto incluye a los participantes PSTN en conferencias)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |
   
Las cifras de ancho de banda de red de estas tablas representan solamente tráfico unidireccional; incluyen 5 Kpbs para sobrecarga de tráfico RTPC de cada secuencia. 
  
## <a name="managing-quality-of-service"></a>Administración de la Calidad de servicio (QoS)
<a name="man_QOS"> </a>

La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en las redes en las que el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.
  
> [!NOTE]
> Como regla general, la QoS se aplica solamente a las sesiones de comunicación de la red interna. Al implementar la QoS necesita configurar los servidores y los enrutadores para que admitan el marcado de paquetes de un modo especial que puede que no se admita en Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no existe ninguna garantía de que se configure de la misma manera que configuró el servicio. Si utiliza MPLS tendrá que colaborar junto con su proveedor de MPLS. 
  
Skype para Business Server no requiere QoS, pero es muy recomendable. Si experimenta problemas de pérdida de paquetes en la red las soluciones disponibles son para agregar más ancho de banda o para implementar QoS. Si no puede agregar más ancho de banda, la implementación de la QoS puede ser la única solución al problema.
  
Skype para Business Server ofrece soporte completo para QoS: que significa que las organizaciones que ya están utilizando QoS pueden fácilmente integrar Skype para Business Server en su infraestructura de red existente. Para ello, es necesario llevar a cabo los siguientes pasos:
  
- [Habilitar QoS para dispositivos que no son Windows](http://technet.microsoft.com/library/26f793df-aef8-4028-9e3b-6c2c37ea61b9.aspx). De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede utilizar Skype para Business Server para habilitar y deshabilitar QoS para dispositivos, normalmente no puede utilizar el producto para cambiar los códigos DSCP utilizados por estos dispositivos.
    
- [Configuración de intervalos de puertos para conferencias, aplicación y los servidores de mediación](http://technet.microsoft.com/library/4d6eaa5d-0127-453f-be6a-e55384772d83.aspx). Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo. Utilizando Skype para Business Server no habilitar o deshabilitar QoS estableciendo un valor de la propiedad en True o en False. En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos y al crear y aplicar posteriormente una directiva de grupo. Si más tarde decide no utilizar QoS puede "Deshabilitar" QoS mediante la eliminación de los objetos de directiva de grupo apropiados.
    
- [Configuración de intervalos de puertos para los servidores de borde](http://technet.microsoft.com/library/6f0ae442-6624-4e3f-849a-5b9e387fb8cf.aspx). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.
    
- [Configuración de intervalos de puertos para los clientes de Microsoft Lync](http://technet.microsoft.com/library/287d5cea-7ada-461c-9b4a-9da2af315e71.aspx). Estos intervalos de puertos solo se aplican a equipos cliente y, por lo general, no son los mismos que los intervalos de puertos configurados en los servidores.
    
- [Configuración de una calidad de servicio directiva para conferencias, aplicación y los servidores de mediación](http://technet.microsoft.com/library/8adcbbc5-c9f5-476d-ab7f-72e61859cacf.aspx). Estas directivas determinan los códigos DSCP que se aplican a diferentes tipos de paquetes.
    
- [Configurar una calidad de servicio directiva de su / servidores de borde de V](http://technet.microsoft.com/library/119ee1f5-45b9-40ba-98e5-c694dd2fc5c2.aspx). Esto sólo debe hacerse para el lado interno de sus servidores perimetrales. Eso es porque QoS está diseñado para su uso en la red interna y no en Internet.
    
- [Configuración de calidad de Peer-to-Peer de las políticas de servicio para los clientes que se ejecutan en Windows 7 o Windows 8](http://technet.microsoft.com/library/efff2b98-b3fb-4183-a4f0-329a9105ce2c.aspx). Tenga en cuenta que Skype para Business Server no admite QoS para otros sistemas operativos de Windows, como Windows Vista o Windows XP.
    
- [Configuración de calidad de servicio en dispositivos de Microsoft Lync Phone Edition](http://technet.microsoft.com/library/a6eb2620-a512-4ab6-bdfd-eb76be43bbfe.aspx). De forma predeterminada, QoS está habilitado para dispositivos Phone Edition de Lync. Pero, tal vez desee cambiar el valor predeterminado de DSCP a fin de garantizar que todos los paquetes de audio de la organización usen el mismo código DSCP.
    
> [!NOTE]
> Si está utilizando Windows Server 2012 o Windows Server R2 de 2012 podría estar interesado en el nuevo conjunto de cmdlets de Windows PowerShell para la administración de QoS en esa plataforma. Para obtener más información, consulte [Red QoS Cmdlets de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379). 
  
QoS se debatirán en el white paper [Planificación de redes, supervisión y solución de problemas con Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) con detalles adicionales y profundidad. Mientras que el contenido se refiere explícitamente a Lync 2010 y Lync 2013, las consideraciones de Skype para Business Server 2015 no se modifican.
  
## <a name="see-also"></a>Vea también
<a name="man_QOS"> </a>

#### 

[Plan de negocios para IPv6 en Skype](ipv6.md)
  
[Requisitos de Skype para el negocio de equilibrio de carga](load-balancing.md)
  
[Requisitos de DNS para Skype para Business Server 2015](dns.md)
  
[Requisitos de protocolo y puerto para servidores](ports-and-protocols.md)

