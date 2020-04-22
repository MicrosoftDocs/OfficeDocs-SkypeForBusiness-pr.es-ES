---
title: Planeación del desvío de medios en Cloud Connector Edition
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
description: Lea este tema para revisar las consideraciones de planeación para implementar la omisión de medios con Cloud Connector Edition, versión 2,0 y posteriores. Para obtener información sobre la implementación de la omisión de medios, vea deploy media bypass in Cloud Connector Edition.
ms.openlocfilehash: f9da5df4815c731b479f5d2333f26546be0daf4c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778786"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planeación del desvío de medios en Cloud Connector Edition
 
Lea este tema para revisar las consideraciones de planeación para implementar la omisión de medios con Cloud Connector Edition, versión 2,0 y posteriores. Para obtener información sobre la implementación de la omisión de medios, vea [deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente de Cloud Connector Edition de la ruta de medios.
  
La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la posibilidad de pérdida de paquetes y el número de puntos de posibles errores. La eliminación del procesamiento de medios para llamadas por omisión reduce la carga en Cloud Connector, lo que permite un mayor número de llamadas simultáneas y puede mejorar la escalabilidad. 
  
 La posibilidad de liberar Cloud Connector de las tareas de procesamiento de medios puede reducir el número de dispositivos de Cloud Connector que necesita una infraestructura, por lo que debe habilitar la omisión de medios siempre que sea posible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Cómo afecta la omisión de medios a las rutas de señalización y medios

Mientras que la señalización toma la misma ruta de acceso con o sin omisión de medios, el flujo de medios será diferente. En los siguientes diagramas se muestran los medios y las rutas de señalización en topologías con desvío de medios y sin ellos. 
  
Por ejemplo, en la siguiente topología, que no emplea la omisión de medios, un cliente de Skype empresarial realiza una llamada RTC a un número externo, la señalización SIP va a Office 365 y Office 365, a continuación, dirige el tráfico de señalización de acuerdo con la Directiva de voz del usuario final. Para los usuarios de Cloud Connector, la Directiva de voz dirige el tráfico de señalización al servidor perimetral de Cloud Connector, que luego enruta el tráfico de señalización a un controlador de borde de sesión (SBC) o una puerta de enlace de sesión RTC a través del servidor de mediación de Cloud Connector. Los medios fluyen desde el cliente de Skype empresarial al servidor de mediación de Cloud Connector y, a continuación, a la SBC o la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Rutas de señalización y medios sin desvío de medios**

![señalización sin desvío de medios](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Una llamada entrante de la RTC usa la misma ruta de señalización en la dirección inversa. Para los usuarios internos, los medios seguirán en última instancia entre el cliente de Skype empresarial y el servidor de mediación de Cloud Connector y, a continuación, la SBC o la puerta de enlace.
  
En la siguiente topología, que emplea la omisión de medios, la señalización toma la misma ruta de acceso, pero los medios se transmiten directamente entre el cliente de Skype empresarial y la SBC o la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Rutas de señalización y medios con desvío de medios**

![señalización con desvío de medios](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Escenario de varios sitios y omisión de medios

La omisión de medios también es útil cuando se desea proporcionar servicios de telefonía a varios sitios con un solo dispositivo de Cloud Connector. Dado que Cloud Connector no puede enrutar llamadas en función de números de origen o de destino, la mayoría de las empresas implementan un SBC o una puerta de enlace detrás de Cloud Connector para tomar decisiones de enrutamiento. La omisión de medios en este escenario elimina el salto entre el cliente y el SBC o la puerta de enlace centrales, tal como se muestra en el siguiente diagrama:
  
**Aplicación de varios sitios**

![Ejemplo de multisitio de Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. El tráfico SIP fluye desde el usuario de Zurich a Office 365.
    
2. A continuación, el tráfico se dirige al dispositivo de Cloud Connector en Amsterdam como se especifica en la Directiva de enrutamiento de voz de usuario.
    
3. El dispositivo de Cloud Connector en Amsterdam envía el tráfico SIP a la puerta de enlace central en Amsterdam.
    
4. La puerta de enlace central de Amsterdam toma las decisiones de enrutamiento adecuadas y, a continuación, envía el tráfico a un SBC o una puerta de enlace en Zurich, mientras que los medios fluyen directamente entre el cliente de Skype empresarial y SBC o la puerta de enlace en Amsterdam.
    
   Este enfoque permite atender a más usuarios por una implementación de Cloud Connector en la que Cloud Connector está centralizado. Aunque Cloud Connector se elimina de la ruta de medios, en un escenario de varios sitios centralizados puede seguir recorriendo la WAN dos veces como sea necesario para fluir por el SBC o la puerta de enlace centralizada.
  
Si un cliente está fuera de la red corporativa que realiza una llamada saliente, el tráfico multimedia fluye a través de los servidores perimetrales y de mediación de Cloud Connector y el vínculo WAN entre Zurich y Amsterdam, tal como se muestra en el siguiente diagrama:
  
![Ejemplo 2 de multisitio de Cloud Connector](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes admitidos para el desvío de medios

Con la primera versión de la omisión de medios, el único cliente compatible es el cliente de Skype empresarial 2016 Windows que forma parte de Microsoft 365 apps for Enterprise, versión 16.0.7870.2020 o superior. Los clientes pueden usar cualquier canal: actual, aplazada o primera versión aplazada. 
  
> [!NOTE]
> Si usa una solución de VPN de cliente en combinación con el cliente de Skype empresarial, la omisión de medios solo se admite con una configuración de túnel dividido de VPN. 
  
Para obtener más información sobre los canales de la versión, consulte [información general sobre los canales de actualización para las aplicaciones de Microsoft 365 para empresas](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Para la versión de lanzamiento actual de los clientes en distintos canales, vea la [información sobre la versión de las actualizaciones de las aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Consideraciones de capacidad de Cloud Connector con desvío de medios

Sin omisión de medios, y según el hardware, un dispositivo de Cloud Connector puede controlar de 50 a 500 llamadas simultáneas que requieren medios para viajar a través de un servidor de mediación. Para obtener más información, consulte [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Con la omisión de medios habilitada, los clientes internos en la versión compatible no usan el servidor de mediación, por lo que el número de clientes internos puede aumentar considerablemente. 
  
Como se indicó anteriormente, los clientes externos o los clientes no admitidos usarán los servidores perimetrales y de mediación de Cloud Connector para los medios. Al calcular cuántos equipos de Cloud Connector deben colocarse en un sitio, debe tener en cuenta el tráfico de usuarios externos y de usuarios en clientes no admitidos.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector admite el modo de omisión siempre

Cloud Connector solo admite el modo Omitir siempre. En entornos locales, hay dos opciones: omitir siempre y usar la información de sitio y región.
  
Omitir siempre significa que la omisión de medios se intentará en todas las llamadas RTC con clientes internos como un punto de origen o de destino. Para determinar si el cliente es interno o externo, se utiliza un sitio web en la máquina virtual del servidor de mediación. Si el cliente puede llegar al sitio, se considera que se usa la omisión interna y de medios. Si el cliente no puede llegar al sitio (por ejemplo, el cliente está en una red doméstica), no se usa la omisión de medios. 
  
Omitir siempre requiere una conectividad sin obstáculos entre los usuarios y las puertas de enlace RTC en un sitio RTC. 
  
Para obtener más información, consulte [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Por ejemplo, en el siguiente diagrama, los usuarios de Europa deben estar bien conectados a los tres controladores de borde de sesión (SBCs) en Amsterdam, mientras que los usuarios de oeste de EE. UU. deben estar bien conectados a los dos SBC de Seattle. Conectado significa que se encuentran en los mismos sitios de red que los SBC o las puertas de enlace, o bien en vínculos WAN con un ancho de banda adecuado.
  
![Capacidad de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un usuario de Zurich se desplaza a la oficina de Seattle y desea usar la red interna para entregar el tráfico de medios entre el usuario que viaja y las puertas de enlace en Europa (en lugar de pasar por Internet), debe asegurarse de que la oficina de Seattle y la oficina de Amsterdam en la que se encuentran las puertas de enlace o SBC europeos están calificadas como bien conectadas. 
  
## <a name="codecs-used-in-media-bypass"></a>Códecs usados en la omisión de medios

Con la omisión de medios habilitada, el tráfico de medios entre un cliente y un SBC o una puerta de enlace usa el códec G. 711. 
  
## <a name="see-also"></a>Vea también

[Implementación de la omisión de medios en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
