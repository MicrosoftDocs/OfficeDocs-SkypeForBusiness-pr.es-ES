---
title: Optimizar su red
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Los siguientes requisitos son realmente importantes para garantizar el estado y el funcionamiento correcto a largo plazo de todas las características de Skype Empresarial Online que configure para su organización. Sabemos que algunos de nuestros usuarios son muy técnicos (y este documento es para ellos), pero hay algunos que no lo son tanto. Si necesita ayuda para configurar Skype Empresarial Online, lea este documento para familiarizarse con todo lo que debe tener en cuenta. También encontrará temas de los que podrá hablar cuando trabaje con el Centro de FastTrack de Microsoft, los equipos de servicios y cuentas de Microsoft, o los socios de Microsoft para averiguar cómo cumplir los requisitos.
ms.openlocfilehash: ece99899400d8fca063f9b28c868ba94d4f72b99
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100686"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Optimizar la red para Skype Empresarial Online

[] Los siguientes requisitos son realmente importantes para garantizar el estado y el funcionamiento correcto a largo plazo de todas las características de Skype Empresarial Online que configure para su organización. Sabemos que algunos de nuestros usuarios son muy técnicos (y este documento es para ellos), pero hay algunos que no lo son tanto. Si necesita ayuda para configurar Skype Empresarial Online, lea este documento para familiarizarse con todo lo que debe tener en cuenta. También encontrará temas de los que podrá hablar cuando trabaje con el [Centro de FastTrack de Microsoft](https://fasttrack.microsoft.com/office), los equipos de servicios y cuentas de Microsoft, o los [socios de Microsoft](https://partnercenter.microsoft.com/pcv/search) para averiguar cómo cumplir los requisitos.

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

Trabajando con un partner de [Microsoft,](https://partnercenter.microsoft.com/pcv/search)puede conectar una variedad de aplicaciones de Microsoft 365 u Office 365, como Skype Empresarial Online en la nube, a su red y las capacidades de comunicaciones de voz y vídeo en tiempo real para Skype Empresarial requieren que los servicios de red estén configurados específicamente para admitir estas cargas de trabajo en tiempo real de Microsoft 365 y Office 365. Esto incluye una red que tenga un ancho de banda suficiente para transferir el volumen necesario de tráfico y que sea capaz de admitir una calidad de servicio (QoS), y así poder ofrecer a sus usuarios una experiencia de categoría empresarial.

Junto con esta información, hay otros recursos que pueden ayudarle a planificar e implementar correctamente los servicios y las características de Skype Empresarial Online, y para garantizar que los servicios de red cumplan los requisitos:

- [Flujo de llamadas con ExpressRoute](call-flow-using-expressroute.md)

- [ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)

- [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Implementar la calidad de servicio (QoS) para Skype Empresarial

Antes de pasar a Skype Empresarial Online, deberá comprobar la capacidad de su red para gestionar el tráfico de audio, vídeo y sesiones compartidas. Al igual que con otros servicios de Microsoft 365 y Office 365, Microsoft tiene disponible para descargar la Calculadora de ancho de banda de [Skype](https://www.microsoft.com/download/details.aspx?id=19011) Empresarial que se usa para determinar el tráfico de red necesario para cada uno de los sitios de su empresa. Deberá realizar el modelado de uso, que incluye el modelado de los flujos de multimedia del tráfico de comunicación en tiempo real y la cantidad de tráfico de Skype Empresarial por cada ubicación de la compañía, el cálculo del volumen de tráfico y el análisis del impacto que tiene el tráfico en la red general. Una vez que haya realizado esto, el análisis de estos datos debería proporcionar recomendaciones de lo que se debe mejorar en su red y recomendará los tamaños de cola para ofrecer una excelente experiencia del usuario final.

El tráfico en tiempo real de Skype Empresarial es sensible a la pérdida de paquetes, los retrasos y la vibración, que suelen ocurrir en las redes congestionadas. La calidad de servicio (QoS), que en ocasiones se denomina Clase de servicio, también se debe implementar en las WAN externas administradas, las LAN internas administradas y las redes WiFi de la empresa. De esta manera se dará prioridad adecuadamente al tráfico en tiempo real de Skype Empresarial, tal como el audio y el vídeo sobre el tráfico que no ocurre en tiempo real en redes locales y sobre la WAN, lo que crea una mejor experiencia para los usuarios finales.

El audio de Skype Empresarial debe implementarse en la cola de EF (desvío rápido - DSCP 46) y el vídeo de Skype Empresarial debe implementarse en la cola de AF41 (desvío garantizado - DSCP 34). Esto es así incluso para el tráfico de punto a punto y conferencia, independientemente de si se están implementando sistema telefónico en Microsoft 365 u Office 365 u otras características de telefonía.

Aunque es posible que ya haya directivas de QoS en la LAN y la WAN para otros productos de telefonía IP, Skype Empresarial permite que sus usuarios puedan utilizar dispositivos móviles e ir de una ubicación a otra mientras usan el servicio. Debido a esto, las directivas de QoS deben estar marcadas en la LAN, la WAN y las redes inalámbricas para asegurarse de que todo el tráfico de Skype Empresarial tenga prioridad en las redes administradas.

Para ayudarle a establecer el tamaño de la red, descargue la [Calculadora de ancho de banda de Skype Empresarial](https://www.microsoft.com/download/details.aspx?id=19011).

Para obtener más información sobre la calidad de los elementos multimedia y la QoS, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md).

Para obtener más información sobre la configuración y la administración de la QoS, consulte [Administración de la calidad de servicio](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md).

## <a name="bypass-proxies-and-wan-optimization-devices"></a>Omisión de servidores proxy y dispositivos de optimización de la WAN

Todos los dispositivos proxy de Microsoft 365 u Office 365, incluido Skype Empresarial Online, están cifrados y normalmente no se pueden inspeccionar con dispositivos proxy. Por estos motivos, se recomienda omitir los dispositivos proxy para todo el tráfico de red de Microsoft 365 y Office 365 definido como conexiones que los usuarios hacen a direcciones URL e intervalos de direcciones IP de [Office 365.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Since proxy devices will likely introduce delay in real-time Skype for Business Online media streams we strongly recommend bypassing proxy devices at a minimum for that traffic.

Microsoft recomienda excluir direcciones URL de Microsoft 365 y Office 365 con archivos PAC para enviar tráfico de Microsoft 365 y Office 365 a un firewall.

Los siguientes recursos también pueden ser útiles:

- [Ajuste del rendimiento de Microsoft 365 u Office 365 con líneas base e historial de rendimiento](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [Planificación de red y migración para Microsoft 365 u Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Generador proxy de PAC de Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [Usar el controlador de optimización WAN o los dispositivos de tráfico e inspección con Microsoft 365 u Office 365](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [Enrutamiento con ExpressRoute para Microsoft 365 u Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>Omisión del cifrado doble

Para proporcionar a los usuarios la mejor experiencia de audio y vídeo posible, debe implementar una solución que impida que los medios de Skype Empresarial (audio y vídeo) pasen por un túnel de red privada virtual (VPN). Todo el tráfico de Skype Empresarial se cifra con seguridad de capa de transporte (TLS) y las cargas de trabajo multimedia se cifran con protocolo seguro en tiempo real (SRTP). La señalización se cifra con TLS y las cargas de trabajo multimedia se cifran con SRTP. Enviar este tráfico a través del túnel VPN agrega una capa adicional de cifrado y saltos de red adicionales entre el cliente y Microsoft 365 u Office 365, lo que puede provocar una sesión degradada porque aumenta la vibración, la pérdida de paquetes y la latencia.

Una opción para impedir que el tráfico de Skype Empresarial pase por el túnel VPN sería el túnel dividido. Para implementar el túnel dividido, los clientes deben consultar al proveedor de VPN las instrucciones específicas para hacerlo con su software.

> [!NOTE]
> Esto solo es necesario para las cargas de trabajo multimedia de Skype Empresarial y no es aplicable a otros servicios de Microsoft 365 u Office 365.

Recursos adicionales:

- [Permitir que los elementos multimedia de Lync omitan un túnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [Más información sobre el acceso directo, el túnel dividido y el túnel forzado](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- [Habilitar el acceso directo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Asegúrese de que los puertos y los protocolos adecuados estén abiertos.

Los clientes deben garantizar la capacidad de acceso de las direcciones URL y IP necesarias para el servicio de Microsoft 365 u Office 365. Para ver un listado completo de todas las direcciones IP y las URL de Skype Empresarial Online, consulte [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).

Los clientes de Skype Empresarial usan varios puertos y protocolos. La dirección y el flujo del tráfico de red de una sesión de Skype Empresarial variará en función del tipo de interacciones (punto a punto o varios participantes) y del uso de contenido compartido y de voz/vídeo. Deberá revisar y abrir la lista de puertos y protocolos, prestando especial atención a los puertos de origen y de destino. Por ejemplo, el tráfico de audio solo usa 20 puertos (50000-50019 TCP/UDP) en el lado del cliente, pero el puerto de destino podría estar en cualquier parte de un intervalo de 10.000 puertos (50000-59999 TCP/UDP) en el lado del servicio. Esto también incluye la apertura de TCP 443 y UDP 3478 en el firewall.

También podría ser necesaria una configuración de red adicional para dar soporte a Skype Empresarial Online.


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Usar teléfonos y dispositivos optimizados para Skype Empresarial

En una sesión multimedia en tiempo real, los dispositivos multimedia que usan los participantes, como los auriculares y las cámaras web, afectan de forma importante a la calidad global del audio y el vídeo. Los dispositivos o dispositivos de menor calidad con controladores de dispositivo incorrectos producirán una calidad de sonido general más baja para el audio y una calidad de imagen inferior para el vídeo. Por otra parte, los dispositivos certificados o de buena calidad, contribuyen a la anulación del eco, el filtrado del ruido, la reducción de la latencia y una mejor resolución del vídeo.

Los teléfonos y los dispositivos tienen un impacto importante en la calidad del audio y vídeo para los usuarios finales. El programa de certificación de Skype Empresarial es una evolución del programa "Compatible con Lync" y se asegura de que el dispositivo cumpla las normas de Microsoft para audio y vídeo. Microsoft ha probado y autorizado toda una serie de teléfonos IP, dispositivos de audio y vídeo USB, equipos y dispositivos para salas de reuniones. Revise la lista de dispositivos optimizados para Skype Empresarial y asegúrese de proporcionar los distintos dispositivos para cumplir las diferentes necesidades y preferencias personales de sus usuarios finales en su organización.

Vea los siguientes documentos para ver más información sobre los dispositivos compatibles y certificados:  

- [Obtener teléfonos con Skype Empresarial Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [Teléfonos y dispositivos para Skype Empresarial](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [Catálogo de soluciones para periféricos personales](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Teléfonos y dispositivos autorizados para Microsoft Lync](../../SfbPartnerCertification/lync-cert/ip-phones.md)

El entorno y el área que rodea el lugar donde los usuarios se reúnen y utilizan dispositivos de audio y vídeo es otro gran factor a tener en cuenta para la calidad de sonido e imagen. Si los usuarios llaman desde un entorno ruidoso, se generará un audio con ecos, apagado y difuminado. Los usuarios en un entorno oscuro o con poca luz generarán vídeo con poca luminosidad y claridad de imagen. Otra cuestión determinante en la calidad de la imagen y el sonido que recibirán los participantes es la ubicación del micrófono y el dispositivo de vídeo en entornos como salas de conferencias.

Para obtener una imagen más clara de la experiencia de audio y vídeo de un usuario, use la aplicación de Skype Empresarial Herramientas Opciones de dispositivo de audio o dispositivo de vídeo para realizar cambios en el dispositivo en uso y personalizar su  >    >   configuración.  También puede comprobar la calidad de audio de una llamada haciendo clic en **Comprobar calidad de llamada.** Si hacen clic **en Comprobar calidad de** llamada, pueden informar de la calidad y los problemas encontrados con la llamada de prueba.

![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>Temas relacionados

[ExpressRoute y QoS en Skype Empresarial Online](expressroute-and-qos-in-skype-for-business-online.md)