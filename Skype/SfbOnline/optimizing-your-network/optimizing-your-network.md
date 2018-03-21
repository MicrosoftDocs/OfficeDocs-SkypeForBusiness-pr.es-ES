---
title: Optimizar la red
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "Los siguientes requisitos son realmente importantes para garantizar el estado y el funcionamiento correcto a largo plazo de todas las características de Skype Empresarial Online que configure para su organización. Sabemos que algunos de nuestros usuarios son muy técnicos (y este documento es para ellos), pero hay algunos que no lo son tanto. Si necesita ayuda para configurar Skype Empresarial Online, lea este documento para familiarizarse con todo lo que debe tener en cuenta. También encontrará temas de los que podrá hablar cuando trabaje con el Centro de FastTrack de Microsoft, los equipos de servicios y cuentas de Microsoft, o los socios de Microsoft para averiguar cómo cumplir los requisitos."
ms.openlocfilehash: f5328705e79a44828a9787f35c0526f4b2e0ea35
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Optimizar la red para Skype Empresarial Online

[] Los siguientes requisitos son realmente importantes para garantizar el estado y el funcionamiento correcto a largo plazo de todas las características de Skype Empresarial Online que configure para su organización. Sabemos que algunos de nuestros usuarios son muy técnicos (y este documento es para ellos), pero hay algunos que no lo son tanto. Si necesita ayuda para configurar Skype Empresarial Online, lea este documento para familiarizarse con todo lo que debe tener en cuenta. También encontrará temas de los que podrá hablar cuando trabaje con el [Centro de FastTrack de Microsoft](https://fasttrack.microsoft.com/office), los equipos de servicios y cuentas de Microsoft, o los [socios de Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search) para averiguar cómo cumplir los requisitos.
  
## <a name="a-quick-overview"></a>Introducción rápida

Skype Empresarial le permite conectarse con compañeros de trabajo o socios comerciales de su empresa o de todo el mundo.
  
Con Skype Empresarial, puede:
  
- Iniciar conversaciones mediante mensajería instantánea, llamadas de voz y videollamadas.
    
- Ver cuándo sus contactos están disponibles en línea, en una reunión o en una presentación.
    
- Establecer una seguridad de categoría industrial para sus reuniones.
    
- Realizar difusiones en línea a un gran público.
    
- Presentar su pantalla durante las reuniones o conceder el control a otros.
    
- Usar Skype Empresarial en otros programas de Office para chatear, llamar o unirse a una reunión con un clic.
    
## <a name="why-is-this-all-so-important"></a>¿Por qué es todo esto tan importante?

La calidad de los elementos multimedia en tiempo real (audio, vídeo y uso compartido de aplicaciones) sobre IP queda afectada considerablemente por la calidad de la conectividad de la red de un extremo a otro. Para obtener una calidad multimedia óptima en Skype Empresarial Online, es importante asegurarse de que haya una conexión de alta calidad entre la red de su compañía y Skype Empresarial Online. La mejor forma de lograrla es configurar la red interna y la conectividad con la nube de acuerdo con la capacidad de su red. De esta forma, podrá adaptarse al volumen de tráfico pico de Skype Empresarial Online de todas las conexiones.
  
Trabajar con un [socio de Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), puede conectar una variedad de aplicaciones de Office 365, incluyendo Skype para los negocios en línea en la nube a su red y voz en tiempo real y capacidades de comunicaciones de vídeo de Skype para empresas requieren red servicios deben configurarse específicamente para admitir estas cargas de trabajo en tiempo real de Office 365. Esto incluye una red que tenga un ancho de banda suficiente para transferir el volumen necesario de tráfico y que sea capaz de admitir una calidad de servicio (QoS), y así poder ofrecer a sus usuarios una experiencia de categoría empresarial.
  
Junto con esta información, hay otros recursos que pueden ayudarle a planificar e implementar correctamente los servicios y las características de Skype Empresarial Online, y para garantizar que los servicios de red cumplan los requisitos:
  
- [Flujo de llamadas con ExpressRoute](call-flow-using-expressroute.md)
    
- [ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Implementar la calidad de servicio (QoS) para Skype Empresarial

Antes de pasar a Skype Empresarial Online, deberá comprobar la capacidad de su red para gestionar el tráfico de audio, vídeo y sesiones compartidas. Al igual que ocurre con otros servicios de Office 365, Microsoft tiene disponible para la descarga la [Calculadora de ancho de banda de Skype Empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=19011), que se usa para determinar el tráfico de red requerido para cada uno de los sitios de su compañía. Deberá realizar el modelado de uso, que incluye el modelado de los flujos de multimedia del tráfico de comunicación en tiempo real y la cantidad de tráfico de Skype Empresarial por cada ubicación de la compañía, el cálculo del volumen de tráfico y el análisis del impacto que tiene el tráfico en la red general. Una vez que haya realizado esto, el análisis de estos datos debería proporcionar recomendaciones de lo que se debe mejorar en su red y recomendará los tamaños de cola para ofrecer una excelente experiencia del usuario final.
  
El tráfico en tiempo real de Skype Empresarial es sensible a la pérdida de paquetes, los retrasos y la vibración, que suelen ocurrir en las redes congestionadas. La calidad de servicio (QoS), que en ocasiones se denomina Clase de servicio, también se debe implementar en las WAN externas administradas, las LAN internas administradas y las redes WiFi de la empresa. De esta manera se dará prioridad adecuadamente al tráfico en tiempo real de Skype Empresarial, tal como el audio y el vídeo sobre el tráfico que no ocurre en tiempo real en redes locales y sobre la WAN, lo que crea una mejor experiencia para los usuarios finales.
  
El audio de Skype Empresarial debe implementarse en la cola de EF (desvío rápido - DSCP 46) y el vídeo de Skype Empresarial debe implementarse en la cola de AF41 (desvío garantizado - DSCP 34). Esto es así incluso para el tráfico de punto a punto y de conferencias, independientemente de si se han implementado PBX en la nube u otras características de telefonía.
  
Aunque es posible que ya haya directivas de QoS en la LAN y la WAN para otros productos de telefonía IP, Skype Empresarial permite que sus usuarios puedan utilizar dispositivos móviles e ir de una ubicación a otra mientras usan el servicio. Debido a esto, las directivas de QoS deben estar marcadas en la LAN, la WAN y las redes inalámbricas para asegurarse de que todo el tráfico de Skype Empresarial tenga prioridad en las redes administradas.
  
Para ayudarle a establecer el tamaño de la red, descargue la [Calculadora de ancho de banda de Skype Empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Para obtener más información sobre la calidad de los elementos multimedia y la QoS, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md).
  
Para obtener más información sobre la configuración y la administración de la QoS, consulte [Administración de la calidad de servicio](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a>Omisión de servidores proxy y dispositivos de optimización de la WAN

All Office 365 including Skype for Business Online is encrypted and is typically not able to be inspected by proxy devices. For these reasons we recommend bypassing proxy devices for all Office 365 network traffic as defined as connections your users make to [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Since proxy devices will likely introduce delay in real-time Skype for Business Online media streams we strongly recommend bypassing proxy devices at a minimum for that traffic.
  
Microsoft recomienda que se excluyan las URL de Office 365 que usen archivos PAC para enviar tráfico de Office 365 a un firewall.
  
Los siguientes recursos también pueden ser útiles:
  
- [Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Red y planificación de migración para Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Generador proxy de PAC de Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Uso del controlador de optimización de WAN o dispositivos de tráfico/inspección con Office 365](https://aka.ms/kb2690045)
    
- [Enrutamiento con ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a>Omisión del cifrado doble

Para proporcionar a los usuarios la mejor experiencia posible de audio y vídeo, deberá implementar una solución que impida que los elementos multimedia de Skype Empresarial (audio y vídeo) pasen por un túnel de red privada virtual (VPN). Todo el tráfico de Skype Empresarial está cifrado con Seguridad de la capa de transporte (TLS) y las cargas de trabajo multimedia están cifradas con el protocolo seguro en tiempo real (SRTP). La señalización está cifrada con TLS y las cargas de trabajo multimedia están cifradas con SRTP. El envío de este tráfico por el túnel VPN agrega una capa adicional de cifrado y la red adicional salta entre el cliente y Office 365. Esto provocaría que ambos tuvieran una reducción en la calidad de la sesión porque aumentarían la latencia, la pérdida de paquetes y la vibración.
  
Una opción para impedir que el tráfico de Skype Empresarial pase por el túnel VPN sería el túnel dividido. Para implementar el túnel dividido, los clientes deben consultar al proveedor de VPN las instrucciones específicas para hacerlo con su software.
  
> [!NOTE]
> Esto solo se requiere para las cargas de trabajo de multimedia de Skype Empresarial y no se aplica a otros servicios de Office 365. 
  
Recursos adicionales:
  
- [Permitir que los elementos multimedia de Lync omitan un túnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Más información sobre el acceso directo, el túnel dividido y el túnel forzado](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Habilitar el acceso directo](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Asegúrese de que los puertos y los protocolos adecuados estén abiertos.

Los clientes deben garantizar el acceso a las URL y las direcciones IP requeridas para el servicio de Office 365. Para ver un listado completo de todas las direcciones IP y las URL de Skype Empresarial Online, consulte [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
Los clientes de Skype Empresarial usan varios puertos y protocolos. La dirección y el flujo del tráfico de red de una sesión de Skype Empresarial variará en función del tipo de interacciones (punto a punto o varios participantes) y del uso de contenido compartido y de voz/vídeo. Deberá revisar y abrir la lista de puertos y protocolos, prestando especial atención a los puertos de origen y de destino. Por ejemplo, el tráfico de audio solo usa 20 puertos (50000-50019 TCP/UDP) en el lado del cliente, pero el puerto de destino podría estar en cualquier parte de un intervalo de 10.000 puertos (50000-59999 TCP/UDP) en el lado del servicio. Esto también incluye la apertura de TCP 443 y UDP 3478 en el firewall.
  
También podría ser necesaria una configuración de red adicional para dar soporte a Skype Empresarial Online.
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Usar teléfonos y dispositivos optimizados para Skype Empresarial

En una sesión multimedia en tiempo real, los dispositivos multimedia que usan los participantes, como los auriculares y las cámaras web, afectan de forma importante a la calidad global del audio y el vídeo. Dispositivos de menor calidad o con los controladores de dispositivo incorrectos producirá más baja la calidad del sonido de calidad de imagen inferior y audio para vídeo. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Los teléfonos y los dispositivos tienen un impacto importante en la calidad del audio y vídeo para los usuarios finales. El programa de certificación de Skype Empresarial es una evolución del programa "Compatible con Lync" y se asegura de que el dispositivo cumpla las normas de Microsoft para audio y vídeo. Microsoft ha probado y autorizado toda una serie de teléfonos IP, dispositivos de audio y vídeo USB, equipos y dispositivos para salas de reuniones. Revise la lista de dispositivos optimizados para Skype Empresarial y asegúrese de proporcionar los distintos dispositivos para cumplir las diferentes necesidades y preferencias personales de sus usuarios finales en su organización.
  
Vea los siguientes documentos para ver más información sobre los dispositivos compatibles y certificados:  
  
- [Obtener teléfonos con Skype Empresarial Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Teléfonos y dispositivos para Skype Empresarial](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catálogo de soluciones para periféricos personales](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Teléfonos y dispositivos autorizados para Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen clara sobre el uso de audio y vídeo de experiencia del usuario la Skype para **Herramientas**de la aplicación empresarial > **Opciones** > **Dispositivo de sonido** o **Dispositivo de vídeo** para realizar cambios en el dispositivo en uso y personalizar su configuración. También puede comprobar la calidad de audio de una llamada haciendo clic en **Comprobar calidad de llamar**. Si hacen clic en **Comprobar calidad de llamar**, a continuación, puede informar la calidad y los problemas encontrados en la llamada de la prueba.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a>See also 

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)
  

