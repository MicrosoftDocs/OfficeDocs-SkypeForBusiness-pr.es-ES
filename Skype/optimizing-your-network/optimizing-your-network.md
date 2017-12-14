---
title: "Optimizar la red para Skype Empresarial Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
description: "Los siguientes requisitos son realmente importantes para garantizar el mantenimiento a largo plazo y el éxito de todos los Skype empresarial Online características configurar para su organización. Sabemos que algunos usuarios están muy técnicos: este documento es para usted, pero hay algunas de las que no están. Si necesita ayuda para configurar Skype empresarial Online, debe leer este documento para familiarizarse con las cosas que debe tener en cuenta. Le también dará cosas a hablar sobre cuando se trabaja con el Centro de Microsoft FastTrack, su Microsoft Services y equipos de cuenta o con Microsoft partners para averiguar cómo se Puede cumple estos requisitos."
---

# Optimizar la red para Skype Empresarial Online

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](b363bdca-b00d-4150-96c3-ec7eab5a8a43.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43). 
  
Los siguientes requisitos son realmente importantes para garantizar el mantenimiento a largo plazo y el éxito de todos los Skype empresarial Online características configurar para su organización. Sabemos que algunos usuarios están muy técnicos: este documento es para usted, pero hay algunas de las que no están. Si necesita ayuda para configurar Skype empresarial Online, debe leer este documento para familiarizarse con las cosas que debe tener en cuenta. Le también dará cosas a hablar sobre cuando se trabaja con el [Centro de Microsoft FastTrack](https://fasttrack.microsoft.com/office), su Microsoft Services y equipos de cuenta o con [Microsoft partners](https://partnercenter.microsoft.com/en-us/pcv/search) para averiguar cómo se Puede cumple estos requisitos.
  
## Introducción rápida

Skype Empresarial le permite conectarse con compañeros de trabajo o socios comerciales de su empresa o de todo el mundo.
  
Con Skype Empresarial, puede:
  
- Iniciar conversaciones mediante mensajería instantánea, llamadas de voz y videollamadas.
    
- Ver cuándo sus contactos están disponibles en línea, en una reunión o en una presentación.
    
- Establecer una seguridad de categoría industrial para sus reuniones.
    
- Realizar difusiones en línea a un gran público.
    
-  Presentar su pantalla durante las reuniones o conceder el control a otros.
    
- Usar Skype Empresarial en otros programas de Office para chatear, llamar o unirse a una reunión con un clic.
    
## ¿Por qué es todo esto tan importante?

La calidad de los elementos multimedia en tiempo real (audio, vídeo y uso compartido de aplicaciones) sobre IP queda afectada considerablemente por la calidad de la conectividad de la red de un extremo a otro. Para obtener una calidad multimedia óptima en Skype Empresarial Online, es importante asegurarse de que haya una conexión de alta calidad entre la red de su compañía y Skype Empresarial Online. La mejor forma de lograrla es configurar la red interna y la conectividad con la nube de acuerdo con la capacidad de su red. De esta forma, podrá adaptarse al volumen de tráfico pico de Skype Empresarial Online de todas las conexiones.
  
Trabajar con un [asociados de Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), puede conectar una gran variedad de aplicaciones de Office 365 incluidos Skype empresarial Online en la nube a su red y voz en tiempo real y capacidades de comunicaciones de vídeo de Skype para Empresa requiere servicios de red deben estar configurados específicamente para admitir estas cargas de trabajo en tiempo real de Office 365. Esto incluye una red que tiene suficiente ancho de banda para llevar el volumen de tráfico necesario y ser compatible con la calidad de servicio (QoS) para ofrecer una experiencia de clase empresarial para sus usuarios.
  
Junto con esta información, hay otros recursos que pueden ayudarle a planificar e implementar correctamente los servicios y las características de Skype Empresarial Online, y para garantizar que los servicios de red cumplan los requisitos:
  
- [Flujo de llamadas con ExpressRoute](call-flow-using-expressroute.md)
    
- [ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)
    
## Implementar la calidad de servicio (QoS) para Skype Empresarial

Antes de pasar a Skype empresarial Online, debe tener un vistazo a la capacidad de la red para controlar el audio, vídeo y uso compartido de tráfico de la sesión. Como con otros servicios de Office 365, Microsoft está disponible para descargar [Skype para Business Calculadora de ancho de banda](https://www.microsoft.com/en-us/download/details.aspx?id=19011) que se utiliza para determinar el tráfico de red necesarios para cada uno de los sitios de la empresa. Debe realizar modelado de uso, incluidos modelar flujos de medios de tráfico de comunicación en tiempo real y la cantidad de Skype para el tráfico de la empresa por ubicación de la compañía, calcular el volumen de tráfico y analizar la repercusión de que el tráfico de la red general. Una vez que haya terminado, análisis de datos debe proporcionar recomendaciones de dónde debe mejorarse y recomendamos tamaños de cola para proporcionar una experiencia del usuario final excelente su red.
  
Skype para el tráfico en tiempo real de empresa es sensible a la pérdida de paquetes, retraso y la vibración que se producen frecuentemente en las redes. También se debe implementar la calidad de servicio (QoS) - a veces denominado clase de servicio - en WAN externo administrado, administradas LAN internas y redes Wi-Fi enterprise. Esto le ayudará a prioridades correctamente Skype para el tráfico en tiempo real de empresa como audio y vídeo a través de otro tráfico de tiempo no real en redes locales e WAN, crear una mejor experiencia para los usuarios finales.
  
Se debe implementar Skype para el audio de la empresa en el EF (acelerado reenvío: 46 DSCP) cola y Skype para vídeo de empresa se deben implementar en la AF41 (seguro reenvío: 34 DSCP) cola. Esto es cierto incluso para el tráfico de punto a punto y conferencias, independientemente de si se implementan sistema telefónico en Office 365 u otras características de telefonía.
  
Mientras QoS existente directivas pueden estar en lugar ya en la LAN y WAN para otros productos de telefonía IP, Skype empresarial permite a los usuarios para ser móviles y de ubicación al utilizar el servicio. Por este motivo, las directivas de QoS deben marcarse LAN, WAN y redes inalámbricas para Asegúrese de que todos los Skype para el tráfico de la empresa que se tiene prioridad a través de redes administradas.
  
Para ayudarle a establecer el tamaño de la red, descargue la [Calculadora de ancho de banda de Skype Empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Para obtener más información sobre la calidad de los elementos multimedia y la QoS, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
Para obtener más información sobre cómo configurar y administrar QoS, vea [Administración de calidad de servicio](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## Omisión de servidores proxy y dispositivos de optimización de la WAN

Todos los incluidos Skype empresarial Online de Office 365 se cifra y no suele ser capaz de inspeccionar dispositivos de proxy. Por estas razones, se recomienda omitiendo dispositivos proxy para Office 365 tráfico de red según se define como conexiones que los usuarios realizan a [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx)y URL de Office 365. Dado que dispositivos proxy es probable que presentan retraso en tiempo real Skype empresarial Online secuencias de multimedia, le recomendamos encarecidamente omitiendo dispositivos proxy como mínimo para que el tráfico.
  
Microsoft recomienda que se excluyan las URL de Office 365 que usen archivos PAC para enviar tráfico de Office 365 a un firewall. 
  
Los siguientes recursos también pueden ser útiles:
  
- [Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](http://technet.microsoft.com/library/1492cb94-bd62-43e6-b8d0-2a61ed88ebae%28Office.14%29.aspx)
    
- [Red y planificación de migración para Office 365](http://technet.microsoft.com/library/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132%28Office.14%29.aspx)
    
- [Generador proxy de PAC de Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Uso del controlador de optimización de WAN o dispositivos de tráfico/inspección con Office 365](https://aka.ms/kb2690045)
    
- [Enrutamiento con ExpressRoute para Office 365](http://technet.microsoft.com/library/e1da26c6-2d39-4379-af6f-4da213218408%28Office.14%29.aspx)
    
## Omisión del cifrado doble

Para proporcionar a los usuarios la mejor posible de audio y vídeo experiencia, debe implementar una solución que impide Skype para multimedia de empresa (audio y vídeo) atraviesa un túnel de red privada Virtual (VPN). Todos los Skype para el tráfico de la empresa está cifrado con seguridad de capa de transporte (TLS) y las cargas de trabajo de medios están encriptados con el protocolo de tiempo Real seguro (SRTP). Señalización se cifra con TLS y las cargas de trabajo de medios están encriptados con SRTP. Para enviar que este tráfico a través del túnel VPN agrega una capa adicional de cifrado y saltos de red adicional entre el cliente y Office 365, que pueden dar lugar a una sesión de degradado porque aumenta vibración, la pérdida de paquetes y latencia.
  
Una opción para evitar que Skype para el tráfico de empresa recorrer el túnel VPN es túnel dividido. Para implementar túnel dividido, los clientes deben consultar con su proveedor de VPN en los detalles de cómo hacerlo en su software.
  
> [!NOTE]
> Esto solo se requiere para las cargas de trabajo de multimedia de Skype Empresarial y no se aplica a otros servicios de Office 365. 
  
Recursos adicionales:
  
- [Permitir que los elementos multimedia de Lync omitan un túnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Más información sobre el acceso directo, el túnel dividido y el túnel forzado](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Habilitar el acceso directo](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## Asegúrese de que los puertos y los protocolos adecuados estén abiertos.

Los clientes deben garantizar el acceso a las URL y las direcciones IP requeridas para el servicio de Office 365. Para ver un listado completo de todas las direcciones IP y las URL de Skype Empresarial Online, consulte [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx).
  
Los clientes de Skype Empresarial usan varios puertos y protocolos. La dirección y el flujo del tráfico de red de una sesión de Skype Empresarial variará en función del tipo de interacciones (punto a punto o varios participantes) y del uso de contenido compartido y de voz/vídeo. Deberá revisar y abrir la lista de puertos y protocolos, prestando especial atención a los puertos de origen y de destino. Por ejemplo, el tráfico de audio solo usa 20 puertos (50000-50019 TCP/UDP) en el lado del cliente, pero el puerto de destino podría estar en cualquier parte de un intervalo de 10.000 puertos (50000-59999 TCP/UDP) en el lado del servicio. Esto también incluye la apertura de TCP 443 y UDP 3478 en el firewall.
  
También podría ser necesaria una configuración de red adicional para dar soporte a Skype Empresarial Online.
  
Puede ejecutar la prueba FastTrack Cloudapp desde los equipos cliente para comprobar que todo se haya configurado correctamente:
  
- **Para Norteamérica:**
    
  - [Office 365 Fast Track Network Analysis (Norteamérica)](http://na1-fasttrack.cloudapp.net/)
    
  - [https://137.117.72.96](https://137.117.72.96)
    
- **Para EMEA:**
    
  - [Office 365 Fast Track Network Analysis (EMEA)](http://em1-fasttrack.cloudapp.net/)
    
  - [https://137.116.212.202](https://137.116.212.202)
    
- **Para APAC:**
    
  - [Office 365 Fast Track Network Analysis (Asia Pacífico)](http://ap1-fasttrack.cloudapp.net)
    
  - [https://168.63.169.67](https://168.63.169.67)
    
También puede ver, [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## Usar teléfonos y dispositivos optimizados para Skype Empresarial

En una sesión multimedia en tiempo real, los dispositivos multimedia que usan los participantes, como los auriculares y las cámaras web, afectan de forma importante a la calidad global del audio y el vídeo. Los dispositivos de audio y vídeo de menor calidad o que utilizan controladores incorrectos generan, respectivamente, sonido e imágenes de calidad reducida. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.
  
Teléfonos y dispositivos hacen una gran diferencia en la calidad de audio y vídeo para los usuarios finales. La Skype para el programa de certificación de empresa es una evolución del programa "Lync Compatible" y valida que el dispositivo cumple los estándares de Microsoft para audio y vídeo. Hay un número de teléfonos IP, USB dispositivos de audio y vídeo, equipos y dispositivos de espacio que se han probado y calificado por Microsoft de la reunión. Debería revisar la lista de dispositivos que están optimizados para Skype para la empresa y trabajo proporcionar distintos dispositivos para satisfacer las necesidades de diversos y preferencias personales de los usuarios finales de su organización.
  
Vea los siguientes documentos para ver más información sobre los dispositivos compatibles y certificados:
  
- [Obtener teléfonos con Skype Empresarial Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Teléfonos y dispositivos para Skype Empresarial](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catálogo de soluciones para periféricos personales](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Teléfonos y dispositivos autorizados para Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.
  
Para obtener una imagen clara de uso de la experiencia de audio y vídeo de un usuario la Skype empresarial **Herramientas** > **Opciones** > **Dispositivo de Audio** o **Vídeo** para realizar cambios en el dispositivo en uso y personalizar su configuración. También puede comprobar la calidad del audio de una llamada, haga clic en **Comprobar calidad de llamada**. Si hacen clic en **Comprobar calidad de llamada**, a continuación, puede informar de la calidad y problemas con la llamada de prueba.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

