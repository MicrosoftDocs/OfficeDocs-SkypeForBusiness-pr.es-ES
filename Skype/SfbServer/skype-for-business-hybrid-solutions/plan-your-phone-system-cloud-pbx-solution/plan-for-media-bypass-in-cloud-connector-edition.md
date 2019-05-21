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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lea este tema para revisar las consideraciones de planeación para implementar elementos multimedia con la versión 2,0 y posteriores de Cloud Connector Edition. Para obtener información sobre la implementación de omisión de medios, consulte implementar los medios omitidos en Cloud Connector Edition.
ms.openlocfilehash: 00f700880e26f12da3aa6c2d791e4f15bfe9a90b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287030"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Plan para la omisión de medios en Cloud Connector Edition
 
Lea este tema para revisar las consideraciones de planeación para implementar elementos multimedia con la versión 2,0 y posteriores de Cloud Connector Edition. Para obtener información sobre la implementación de omisión de medios, consulte [implementar los medios omitidos en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
La omisión de elementos multimedia permite a un cliente enviar archivos directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente Cloud Connector Edition de la ruta multimedia.
  
La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la posibilidad de la pérdida de paquetes y la cantidad de puntos de errores potenciales. La eliminación del procesamiento de multimedia para las llamadas omitidas reduce la carga en el conector de nube, lo que permite una mayor cantidad de llamadas simultáneas y puede mejorar la escalabilidad. 
  
 Si se libera el conector de nube del procesamiento de multimedia, puede reducir el número de dispositivos de conector de nube que necesita una infraestructura, por lo que debe habilitar la omisión de elementos multimedia siempre que sea posible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Cómo afecta la omisión de medios a las rutas de señalización y medios

Si bien la señalización toma la misma ruta con o sin omisión de medios, el flujo de medios actúa de forma diferente. Los siguientes diagramas muestran las rutas de señalización y medios en las topologías con omisión de medios y sin ella.   
  
Por ejemplo, en la siguiente topología, que no emplea la omisión de medios, un cliente de Skype empresarial coloca una llamada RTC a un número externo, la señalización de SIP va a Office 365 y, después, Office 365 dirige el tráfico de señalización de acuerdo con la voz del usuario final. políticas. Para los usuarios de conector de nube, la Directiva de voz dirige el tráfico al servidor perimetral del conector de nube, que a su vez enruta el tráfico de señalización a un controlador de borde de sesión (SBC) o puerta de enlace de la sesión RTC a través del servidor de mediación del conector de nube. Los medios fluyen desde el cliente de Skype empresarial al servidor de mediación del conector de nube y, a continuación, a la SBC o la puerta de enlace, tal como se muestra en el siguiente diagrama:
  
**Rutas de señalización y medios sin omisión de medios**

![señalización sin omisión de medios](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Una llamada entrante RTC utiliza la misma ruta de señalización en la dirección contraria. En el caso de los usuarios internos, los medios seguirán fluyendo en última instancia entre el cliente de Skype empresarial y el servidor de mediación del conector de nube y, a continuación, la SBC o la puerta de enlace.
  
En la siguiente topología, que emplea la omisión de medios, la señalización toma la misma ruta, pero multimedia fluye directamente entre el cliente de Skype empresarial y la SBC o la puerta de enlace, tal y como se muestra en el siguiente diagrama:
  
**Rutas de señalización y medios con omisión de medios**

![señalización con omisión de medios](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Escenario centralizado de varios sitios y omisión de medios  

La omisión de elementos multimedia también es útil cuando desea proporcionar servicios de telefonía a varios sitios con un solo dispositivo de conector de nube. Como el conector de nube no puede enrutar llamadas según números de origen o destino, la mayoría de las empresas implementan una SBC o una puerta de enlace detrás del conector de nube para tomar decisiones de enrutamiento. La omisión de medios en este escenario elimina el salto entre el cliente y el SBC central o la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Aplicación de varios sitios**

![Ejemplo de Cloud Connector multisitio](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. El tráfico SIP fluye desde el usuario de Zurich a Office 365.
    
2. El tráfico se dirige después al dispositivo de conector de nube de Amsterdam según se especifica en la política de enrutamiento de voz de usuario.
    
3. El dispositivo de conector de nube en Amsterdam envía el tráfico SIP a la puerta de enlace central de Amsterdam.
    
4. La puerta de enlace central de Amsterdam toma las decisiones de enrutamiento apropiadas y, a continuación, envía el tráfico a una SBC o a una puerta de enlace en Zurich, mientras que los medios fluyen directamente entre el cliente de Skype empresarial y la SBC o la puerta de enlace en Amsterdam.
    
   Este enfoque permite atender a más usuarios por cada una implementación del conector de nube donde el conector de nube está centralizado. Aunque el conector de nube se elimina de la ruta multimedia, en un escenario centralizado de varios sitios puede seguir recorriendo la red WAN dos veces como se requiera para transmitir por el SBC o la puerta de enlace centralizada.
  
Si un cliente se encuentra fuera de la red corporativa que realiza una llamada saliente, el tráfico de medios fluye a través de los servidores de media y periferia del conector en la nube y el vínculo WAN entre Zurich y Amsterdam, tal y como se muestra en el siguiente diagrama:
  
![Ejemplo 2 de Cloud Connector multisitio](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes compatibles con la omisión de medios

En la primera versión de la omisión de elementos multimedia, el único cliente compatible es el cliente de Skype para empresas 2016, que forma parte de Office 365 ProPlus, versión 16.0.7870.2020 o posterior. Los clientes pueden usar cualquier canal: actual, diferido o primera versión de canal diferido. 
  
> [!NOTE]
> Si utiliza una solución VPN cliente junto con el cliente de Skype Empresarial, la omisión de medios solo será compatible con una configuración VPN de túnel dividido. 
  
Para obtener más información sobre los canales de versión, vea [información general sobre los canales de actualización de Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Para la versión de lanzamiento actual de los clientes de canales diferentes, consulte la [información de lanzamiento para las actualizaciones de Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Consideraciones sobre la capacidad de Cloud Connector con la omisión de medios

Sin omisión de medios, y según el hardware: un dispositivo del conector de nube puede controlar desde 50 hasta 500 llamadas simultáneas que requieren medios para viajar a través de un servidor de mediación. Para obtener más información, consulte [plan para Skype empresarial Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Con la omisión de medios habilitado, los clientes internos en la versión compatible no usa el Servidor de mediación, de modo que el número de clientes internos puede aumentar considerablemente.  
  
Como se indicó anteriormente, los clientes externos o los clientes no compatibles usarán los servidores perimetrales y de media del conector de nube para los medios. Al calcular cuántos dispositivos de conector de nube se deben colocar en un sitio, debe considerar el tráfico de usuarios externos y usuarios en clientes no admitidos.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector admite el modo Omitir siempre

El conector en la nube admite siempre el modo de omisión. En entornos locales, existen dos opciones: Omitir siempre y Use Site and Region Information (Usar la información del sitio y la región).
  
"Omitir siempre" significa que la omisión de medios se intentará en todas las llamadas RTC con los clientes internos como punto de origen o de destino. Para determinar si el cliente es interno o externo, se utiliza un sitio web en la máquina virtual del servidor de mediación. Si el cliente puede llegar al sitio, se tiene en cuenta la omisión interna y de medios. Si el cliente no puede llegar al sitio (por ejemplo, el cliente está en una red doméstica), no se utiliza la omisión de medios.  
  
Omitir siempre requiere una conectividad sin obstrucciones entre los usuarios y las puertas de enlace RTC en un sitio RTC.  
  
Para obtener más información, consulte [plan para Skype empresarial Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Por ejemplo, en el siguiente diagrama, los usuarios de Europa deben estar conectados correctamente a los tres controladores de borde de sesión (SBCs) en Amsterdam, mientras que los usuarios de la sudoeste de Estados Unidos deben estar bien conectados a los dos SBCs de Seattle. Estar bien conectados significa que están situados en los mismos sitios de red que los SBC o las puertas de enlace, o por los vínculos WAN que tengan un ancho de banda adecuado.
  
![Capacidad de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un usuario de Zúrich viaja a la oficina de Seattle y quiere usar la red interna para proporcionar tráfico de medios entre el usuario que esté viajando y las puertas de enlace de Europa (frente a ir a través de Internet), debe asegurarse de que la oficina de Seattle y la de Ámsterdam en las que están situados los SBC o las puertas de enlace de Europa se califiquen como bien conectados. 
  
## <a name="codecs-used-in-media-bypass"></a>Códecs usados en la omisión de medios

Con la omisión de medios habilitada, el tráfico de los medios entre un cliente y un SBC o una puerta de enlace usará el códec G.711.  
  
## <a name="see-also"></a>Vea también

[Implementación de omisión de medios en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
