---
title: Plan para la omisión de medios en Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lea este tema para revisar las consideraciones de planeación para implementar la omisión de medios con Cloud Connector Edition versión 2.0 y versiones posteriores. Para obtener información acerca de la implementación de la omisión de medios, vea Implementar la omisión de medios en Cloud Connector Edition.
ms.openlocfilehash: 568fa13584a44540d8351ea2eb32475c1d276ff7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220260"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Plan para la omisión de medios en Cloud Connector Edition
 
Lea este tema para revisar las consideraciones de planeación para implementar la omisión de medios con Cloud Connector Edition versión 2.0 y versiones posteriores. Para obtener información acerca de la implementación de la omisión de medios, vea [Implementar la omisión de medios en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente Cloud Connector Edition de la ruta de acceso multimedia.
  
La omisión de medios puede mejorar la calidad de voz al reducir la latencia, la posibilidad de pérdida de paquetes y el número de puntos de posibles errores. La eliminación del procesamiento de medios para llamadas omitidas reduce la carga en Cloud Connector, lo que permite un mayor número de llamadas simultáneas y puede mejorar la escalabilidad. 
  
 Liberar Cloud Connector de las tareas de procesamiento de medios puede reducir el número de dispositivos de Cloud Connector que requiere una infraestructura, por lo que debe habilitar la omisión de medios siempre que sea posible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Cómo afecta la omisión de medios a los medios y a las rutas de señalización

Aunque la señalización toma la misma ruta con o sin desvío de medios, el flujo de medios será diferente. En los diagramas siguientes se muestran los medios y las rutas de señalización en topologías con y sin desvío de medios. 
  
Por ejemplo, en la siguiente topología,que no usa la omisión de medios, un cliente de Skype Empresarial realiza una llamada RTC a un número externo, la señalización SIP va a Microsoft 365 u Office 365, que dirige el tráfico de señalización de acuerdo con la directiva de voz del usuario final. Para los usuarios de Cloud Connector, la directiva de voz dirige el tráfico de señalización al servidor perimetral de Cloud Connector, que luego enruta el tráfico de señalización a un controlador de borde de sesión RTC (SBC) o una puerta de enlace a través del servidor de mediación de Cloud Connector. Los medios fluyen desde el cliente de Skype Empresarial al servidor de mediación de Cloud Connector y, a continuación, al SBC o a la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Rutas de señalización y medios sin desvío de medios**

![señalización sin desvío de medios](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Una llamada entrante de la RTC usa la misma ruta de señalización en la dirección inversa. Para los usuarios internos, los medios seguirán fluyendo en última instancia entre el cliente de Skype Empresarial y el servidor de mediación de Cloud Connector y, a continuación, el SBC o la puerta de enlace.
  
En la siguiente topología, que emplea la omisión de medios, la señalización toma la misma ruta, pero los medios fluyen directamente entre el cliente de Skype Empresarial y el SBC o la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Rutas de señalización y medios con desvío de medios**

![señalización con desvío de medios](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Escenario de varios sitios y omisión de medios

La omisión de medios también es útil cuando se desea proporcionar servicios de telefonía a varios sitios mediante un único dispositivo de Cloud Connector. Dado que Cloud Connector no puede enrutar llamadas basadas en números de origen o destino, la mayoría de las empresas implementan un SBC o una puerta de enlace detrás de Cloud Connector para tomar decisiones de enrutamiento. La omisión de medios en este escenario elimina el salto entre el cliente y el SBC central o la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Aplicación de varios sitios**

![Ejemplo de Multisitio de Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. El tráfico SIP fluye desde el usuario deRichrich a Microsoft 365 u Office 365.
    
2. A continuación, el tráfico se enruta al dispositivo de Cloud Connector en Ámsterdam, como se especifica en la directiva de enrutamiento de voz del usuario.
    
3. El dispositivo de Cloud Connector en Ámsterdam envía el tráfico SIP a la puerta de enlace central de Ámsterdam.
    
4. La puerta de enlace central de Ámsterdam toma las decisiones de enrutamiento adecuadas y, a continuación, envía el tráfico a un SBC o una puerta de enlace enRich, mientras que los medios fluyen directamente entre el cliente de Skype Empresarial y el SBC o la puerta de enlace de Ámsterdam.
    
   Este enfoque permite atender a más usuarios por cada implementación de Cloud Connector en la que Cloud Connector está centralizado. Aunque Cloud Connector se elimina de la ruta de acceso multimedia, en un escenario centralizado de varios sitios, los medios aún pueden atravesar la WAN dos veces según sea necesario para fluir a través del SBC centralizado o la puerta de enlace.
  
Si un cliente está fuera de la red corporativa realizando una llamada saliente, el tráfico multimedia fluye a través de los servidores perimetrales y de mediación de Cloud Connector y el vínculo WAN entreRich y Ámsterdam, como se muestra en el siguiente diagrama:
  
![Ejemplo 2 de Cloud Connector Multisite](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes admitidos para la omisión de medios

Con la primera versión de omisión de medios, el único cliente compatible es el cliente de Windows de Skype Empresarial 2016 que forma parte de Aplicaciones de Microsoft 365 para empresas, versión 16.0.7870.2020 o posterior. Los clientes pueden usar cualquier canal: Actual, Diferido o Primera versión diferida. 
  
> [!NOTE]
> Si usa una solución vpn de cliente en combinación con el cliente de Skype Empresarial, la omisión de medios solo se admite con una configuración de túnel dividido de VPN. 
  
Para obtener más información acerca de los canales de lanzamiento, vea Información general sobre los canales de actualización de Aplicaciones de [Microsoft 365 para empresas.](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)
  
Para obtener la versión de lanzamiento actual de los clientes en diferentes canales, consulte Información de la versión de actualizaciones de Aplicaciones de [Microsoft 365 para empresas.](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Consideraciones de capacidad de Cloud Connector con omisión de medios

Sin la omisión de medios(y según el hardware), un dispositivo de Cloud Connector puede administrar de 50 a 500 llamadas simultáneas que requieren medios para desplazarse a través de un servidor de mediación. Para obtener más información, vea [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Con la omisión de medios habilitada, los clientes internos de la versión admitida no usan el servidor de mediación, por lo que el número de clientes internos puede aumentar significativamente. 
  
Como se indicó anteriormente, los clientes externos o los clientes no compatibles usarán los servidores perimetrales y de mediación de Cloud Connector para los medios. Al calcular cuántos dispositivos de Cloud Connector deben colocarse en un sitio, debe tener en cuenta el tráfico de usuarios externos y usuarios en clientes no compatibles.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector admite el modo de omisión siempre

Cloud Connector solo admite el modo Omitir siempre. En entornos locales, hay dos opciones: Omitir siempre y Usar información de sitio y región.
  
Omitir siempre significa que se intenta la omisión de medios para todas las llamadas RTC con clientes internos como origen o punto de destino. Para determinar si el cliente es interno o externo, se usa un sitio web en la máquina virtual del servidor de mediación. Si el cliente puede llegar al sitio, se considera interno y se usa la omisión de medios. Si el cliente no puede acceder al sitio (por ejemplo, el cliente está en una red doméstica), no se usa la omisión de medios. 
  
La omisión siempre requiere conectividad sin obstáculos entre los usuarios y las puertas de enlace RTC dentro de un sitio RTC. 
  
Para obtener más información, vea [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Por ejemplo, en el siguiente diagrama, los usuarios de Europa deben estar bien conectados a los tres controladores de borde de sesión (SBC) en Ámsterdam, mientras que los usuarios de Ee. UU. Oeste deben estar bien conectados a los dos SBC de Seattle. Estar bien conectados significa que se encuentran en los mismos sitios de red que los SBC o puertas de enlace, o a través de vínculos WAN que tienen un ancho de banda adecuado.
  
![Capacidad de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un usuario deRich viaja a la oficina de Seattle y desea usar la red interna para ofrecer tráfico de medios entre el usuario que está de viaje y las puertas de enlace de Europa (en lugar de ir a través de Internet), debe asegurarse de que la oficina de Seattle y la oficina de Ámsterdam donde se encuentran las puertas de enlace o SBC europeos se califican como bien conectadas. 
  
## <a name="codecs-used-in-media-bypass"></a>Códecs usados en la omisión de medios

Con la omisión de medios habilitada, el tráfico multimedia entre un cliente y un SBC o una puerta de enlace usa el códec G.711. 
  
## <a name="see-also"></a>Vea también

[Implementar la omisión de medios en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
