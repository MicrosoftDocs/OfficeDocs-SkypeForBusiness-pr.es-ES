---
title: Plan para la omisión de medios en Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lea este tema para revisar las consideraciones de planificación a la hora de implementar la omisión de medios con la versión 2.0 de Cloud Connector Edition y las versiones posteriores. Para obtener información acerca de cómo implementar los medios de derivación, consulte implementar medios de derivación en nube conector Edition.
ms.openlocfilehash: bf659b7ea7b872a09e8c8ce2358c04cde2ba11d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Plan para la omisión de medios en Cloud Connector Edition
 
Lea este tema para revisar las consideraciones de planificación a la hora de implementar la omisión de medios con la versión 2.0 de Cloud Connector Edition y las versiones posteriores. Para obtener información acerca de cómo implementar los medios de derivación, consulte [implementar medios de derivación en nube conector Edition](deploy-media-bypass-in-cloud-connector.md).
  
Omisión de medios permite que un cliente envíe medios directamente en el próximo salto de red pública de telefónica conmutada (PSTN), un gateway o un controlador de borde de sesión (SBC) y eliminar el componente de edición de conector de nube desde la ruta de acceso de medios.
  
La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la posibilidad de la pérdida de paquetes y la cantidad de puntos de errores potenciales. Eliminación de medios de procesamiento de llamadas omitidas reduce la carga en el conector de la nube, lo que permite a un mayor número de llamadas simultáneas, y mejora la escalabilidad. 
  
 Liberar nube de conector de las tareas de procesamiento de medios puede reducir el número de aparatos de nube conector que requiere una infraestructura, por lo que se debe habilitar la omisión de medios, siempre que sea posible.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Cómo afecta la omisión de medios a las rutas de señalización y medios

Si bien la señalización toma la misma ruta con o sin omisión de medios, el flujo de medios actúa de forma diferente. Los siguientes diagramas muestran las rutas de señalización y medios en las topologías con omisión de medios y sin ella.  
  
Por ejemplo, en la topología siguiente: que omitir la no emplear medios — un Skype para empresa cliente realiza una llamada PSTN a un número externo, la señalización SIP va a Office 365 y Office 365, a continuación, dirige el tráfico de señalización según la voz del usuario final Directiva. Para los usuarios del conector de la nube, la directiva de voz dirige el tráfico de señalización para el servidor perimetral de conector de nube, que enruta el tráfico de señalización a un controlador de borde de sesión (SBC) PSTN o puerta de enlace a través del servidor de mediación de conector de nube. Media fluye desde el Skype para Business client en el servidor de mediación de nube conector y, a continuación, al SBC o puerta de enlace, tal como se muestra en el siguiente diagrama:
  
**Medios y vías de señalización sin medios de derivación**

![señalización sin omisión de medios](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Una llamada entrante RTC utiliza la misma ruta de señalización en la dirección contraria. Para los usuarios internos, medios todavía finalmente fluirá entre el Skype para Business client y el servidor de mediación de nube conector y, a continuación, el SBC o puerta de enlace.
  
En la siguiente topología: que omitir la media del empleo: señalización toma la misma ruta, pero media fluye directamente entre el Skype para Business client y el SBC o puerta de enlace, como se muestra en el siguiente diagrama:
  
**Medios y vías de señalización con medios de derivación**

![señalización con omisión de medios](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Escenario centralizado de varios sitios y omisión de medios

Omisión de medios también es útil cuando desea proporcionar servicios de telefonía varios sitios utilizando un solo dispositivo conector de nube. Como conector de nube no se pueden enrutar llamadas basadas en los números de origen o de destino, la mayoría de las empresas implementación una SBC o detrás de la nube de conector de puerta de enlace para tomar decisiones de enrutamiento. La omisión de medios en este escenario elimina el salto entre el cliente y el SBC central o la puerta de enlace, como se muestra en el siguiente diagrama:
  
**Aplicación de múltiples sitios**

![Ejemplo de Cloud Connector multisitio](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Fluye el tráfico SIP del usuario en Zurich a Office 365.
    
2. A continuación, enruta el tráfico al dispositivo conector de nube en Amsterdam como se especifica en la directiva de enrutamiento de voz de usuario.
    
3. El dispositivo conector de nube en Amsterdam envía el tráfico SIP a la puerta de enlace central en Amsterdam.
    
4. La puerta de enlace central en Amsterdam toma las decisiones de enrutamiento apropiadas y, a continuación, envía el tráfico a un SBC o puerta de enlace en Zurich, mientras que los flujos de medios directamente entre el Skype para Business client y SBC o puerta de enlace en Amsterdam.
    
 Este enfoque permite sirviendo a más usuarios por una implementación del conector de la nube donde se centraliza la nube de conector. Aunque el conector de la nube se eliminan de la ruta de acceso de medios, en un escenario de múltiples sitios centralizado media puede aún atravesar la WAN dos veces, según sea necesario para fluir a través de puerta de enlace o SBC centralizado.
  
Si un cliente está fuera de la red corporativa, colocando una llamada saliente, fluye el tráfico multimedia a través de los servidores perimetrales y de mediación de un vínculo WAN y conector de nube entre Zurich y Amsterdam, tal como se muestra en el siguiente diagrama:
  
![Ejemplo 2 de Cloud Connector multisitio](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes compatibles con la omisión de medios

Con la primera versión de omisión de medios, el cliente sólo admitido es el Skype para cliente de Windows de 2016 de negocio que forma parte de Office 365 ProPlus, versión 16.0.7870.2020 o superior. Los clientes pueden usar cualquier canal: actual, diferido o primera versión de canal diferido. 
  
> [!NOTE]
> Si utiliza una solución VPN cliente junto con el cliente de Skype Empresarial, la omisión de medios solo será compatible con una configuración VPN de túnel dividido. 
  
Para obtener más información acerca de los canales de lanzamiento, vea [información general acerca de los canales de actualización para Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Para la versión actual de los clientes en canales diferentes, vea [Actualizar versiones de canal de cliente de Office 365](https://technet.microsoft.com/en-us/office/mt465751.aspx). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Consideraciones sobre la capacidad de Cloud Connector con la omisión de medios

Sin omitir la media y dependiendo del hardware, puede controlar un dispositivo conector de nube de 50 a 500 llamadas simultáneas que requieren los medios para viajar a través de un servidor de mediación. Para obtener más información, consulte [Plan de Skype para conector de nube Business Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Con la omisión de medios habilitado, los clientes internos en la versión compatible no usa el Servidor de mediación, de modo que el número de clientes internos puede aumentar considerablemente. 
  
Como se mencionó anteriormente, clientes externos o no compatible utilizará los servidores de mediación y borde de conector de nube para medios. Al calcular cuántos dispositivos de nube conector deben colocarse en un sitio, debe tener en cuenta el tráfico de los usuarios externos y usuarios en clientes no compatibles.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector admite el modo Omitir siempre

Nube conector admite sólo el modo omitir siempre. En entornos locales, existen dos opciones: Omitir siempre y Use Site and Region Information (Usar la información del sitio y la región).
  
«Omitir siempre» significa que la omisión de medios se intentará en todas las llamadas RTC con los clientes internos como punto de origen o de destino. Para determinar si el cliente es interno o externo, se utiliza un sitio web en la máquina virtual del servidor de mediación. Si el cliente puede llegar al sitio, se tiene en cuenta la omisión interna y de medios. Si el cliente no puede llegar al sitio (por ejemplo, el cliente está en una red doméstica), no se utiliza la omisión de medios.  
  
Para usar Omitir siempre, hace falta que la conectividad esté despejada entre los usuarios y las puertas de enlace RTC dentro de un sitio RTC.  
  
Para obtener más información, consulte [Plan de Skype para conector de nube Business Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Por ejemplo, en el diagrama siguiente, los usuarios de Europa deben estar conectados correctamente a los tres controladores de borde de sesión (SBCs) en Amsterdam mientras los usuarios nos West deben estar bien conectados a los dos SBCs en Seattle. Estar bien conectados significa que están situados en los mismos sitios de red que los SBC o las puertas de enlace, o por los vínculos WAN que tengan un ancho de banda adecuado.
  
![Capacidad de Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Si un usuario de Zúrich viaja a la oficina de Seattle y quiere usar la red interna para proporcionar tráfico de medios entre el usuario que esté viajando y las puertas de enlace de Europa (frente a ir a través de Internet), debe asegurarse de que la oficina de Seattle y la de Ámsterdam en las que están situados los SBC o las puertas de enlace de Europa se califiquen como bien conectados. 
  
## <a name="codecs-used-in-media-bypass"></a>Códecs usados en la omisión de medios

Con la omisión de medios habilitada, el tráfico de los medios entre un cliente y un SBC o una puerta de enlace usará el códec G.711. 
  
## <a name="see-also"></a>Vea también

#### 

[Implementar la omisión de medios en nube conector Edition](deploy-media-bypass-in-cloud-connector.md)

