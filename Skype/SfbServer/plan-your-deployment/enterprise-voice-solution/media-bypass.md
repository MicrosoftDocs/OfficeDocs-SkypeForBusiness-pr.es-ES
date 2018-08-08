---
title: Planear el desvío de medios en Skype para la empresa
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Las decisiones necesarias para la planeación para los medios de omisión de Skype Business Server Enterprise Voice. Incluye interoperación con el control de admisión de llamadas (CAC).
ms.openlocfilehash: a6e7cd2a37af67415962a4f0a2e0c390160f66f3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020860"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planear el desvío de medios en Skype para la empresa
 
Las decisiones necesarias para la planeación para los medios de omisión de Skype Business Server Enterprise Voice. Incluye interoperación con el control de admisión de llamadas (CAC).
  
Desvío de medios hace referencia a quitar el servidor de mediación de la ruta de acceso de medios siempre que sea posible para las llamadas con señalización que atraviese el servidor de mediación.
  
La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la conversión innecesaria, la posibilidad de la pérdida de paquetes y la cantidad de puntos de errores potenciales. Puede mejorar la escalabilidad debido a que la eliminación de medios de procesamiento para las llamadas omitidas reduce la carga en el servidor de mediación. Esta reducción de carga complementa la capacidad del servidor de mediación para controlar varias puertas de enlace. 
  
 Cuando una sucursal sin un servidor de mediación está conectada a un sitio central por uno o más vínculos WAN con ancho de banda restringido, el desvío de medios reduce el requisito de ancho de banda permitiendo medios desde un cliente en un sitio de sucursal a flujo directamente a su puerta de enlace local sin en primer lugar tener que fluyen a través de la WAN vincular a un servidor de mediación en el sitio central y realizar una copia.
  
Al evitar al procesamiento de medios en el servidor de mediación, el desvío de medios puede reducir también el número de servidores de mediación que necesita una infraestructura de Enterprise Voice. Como regla general, habilita la omisión de medios siempre que sea posible.
  
La siguiente figura muestra las rutas de señalización y los medios básicos en las topologías con omisión de medios y sin ella.
  
**Rutas de señalización y medios con omisión de medios y sin ella**

![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)
  
Desvío de medios es útil cuando desea minimizar el número de servidores de mediación implementados. Normalmente, un grupo de servidores de mediación se implementará en un sitio central y controlará las puertas de enlace en sitios de sucursal. Habilitar la omisión de medios permite que las llamadas de la red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Skype para rutas de llamadas salientes de Business Server y las directivas de Enterprise Voice debe estar correctamente configurado para que las llamadas de RTC de clientes en un sitio de sucursal se enrutan a la puerta de enlace apropiada.
  
Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si necesitas habilitar la omisión de medios para una subred inalámbrica, te recomendamos evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta una contrapartida respecto a la recuperación de la pérdida de paquetes que también necesitas tener en cuenta. RTAudio, un códec disponible para llamadas que no omiten el servidor de mediación, es más apropiado para la gestión de la pérdida de paquetes.
  
## <a name="planning-your-media-bypass-deployment"></a>Planear la implementación de desvío de medios

Una vez la estructura de Enterprise Voice, planear el desvío de medios es sencillo.
  
- Si tienes una topología centralizada sin vínculos WAN a sitios de sucursal, puedes habilitar la omisión de medios global porque no se necesita control de ajustes.
    
- Si tienes una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determina los aspectos siguientes:
    
  - Si los componentes del mismo nivel del servidor de mediación pueden asumir las capacidades que se requieren para la omisión de medios.
    
  - Los sitios de cada región de red que están bien conectados.
    
  - La combinación de la omisión de medios y el servicio de control de admisión de llamadas que es apropiada para la red.
    
Al habilitar la omisión de medios, se genera automáticamente un identificador de omisión único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región a través de vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de omisión únicos.
  
Cuando un usuario realiza una llamada a la RTC, el servidor de mediación se compara el identificador de desvío de la subred del cliente con el identificador de desvío de la subred de puerta de enlace. Si los dos identificadores de omisión coinciden, se usará la omisión de medios para la llamada. Si el desvío de identificadores no coinciden, debe flujo multimedia para la llamada a través del servidor de mediación.
  
Cuando un usuario recibe una llamada desde la RTC, el cliente del usuario compara su identificador de desvío a la de la puerta de enlace de RTC. Si los dos omitir la coincidencia de los identificadores, se transmite directamente desde la puerta de enlace para el cliente, sin pasar por el servidor de mediación.
  
Sólo Lync 2010 o más reciente los clientes y dispositivos admiten interacciones de desvío de medios con un servidor de mediación.
  
> [!IMPORTANT]
> Además de habilitar la omisión de medios de manera global, necesitas habilitar la omisión de medios en cada tronco RTC de forma individual. Si la omisión se habilita globalmente, pero no se habilita en un determinado tronco RTC, no se invocará la omisión de medios en ninguna de las llamadas en las que intervenga ese tronco RTC. Asimismo, si la omisión de medios se define en **Usar información de región y sitio**, todas las subredes que se pueden redirigir necesitan asociarse con los sitios en los que se ubican. Si en un sitio hay subredes que se pueden redirigir en las que no se desea habilitar la omisión, dichas subredes necesitan agruparse en un sitio nuevo antes de habilitar la omisión de medios. Esta acción asegurará que las subredes que no se pueden redirigir tengan asignado un identificador de omisión diferente. 
  
## <a name="media-bypass-modes"></a>Modos de omisión de medios

Necesitas configurar la omisión de medios de forma global y para cada tronco RTC individual. Al habilitar la omisión de medios globalmente, tienes dos opciones: **Omitir siempre** y **Usar información de sitio y región**. 
  
Como el propio nombre sugiere, **Omitir siempre** significa que se intentará realizar la omisión de todas las llamadas de RTC. **Omitir siempre** se usa en implementaciones en las que no hay necesidad de habilitar el servicio de control de admisión de llamadas ni de especificar información detallada de configuración con respecto a cuándo intentar la omisión de medios. Además, **Omitir siempre** se usa cuando existe plena conectividad entre los clientes y las puertas de enlace RTC. En esta configuración, todas las subredes se asignan únicamente a un solo identificador de omisión, que el sistema calcula.
  
Con **Usar información de sitio y región**, se usa el identificador de omisión asociado a la configuración del sitio y de la región para tomar la decisión de omisión. Esta configuración proporciona la flexibilidad de configurar la omisión de medios para las topologías más comunes, ya que proporciona un control más preciso cuando se produce la omisión, además de admitir interacciones con el servicio de control de admisión de llamadas (CAC). El sistema intenta facilitarte la tarea asignando automáticamente identificadores de omisión de la manera siguiente.
  
- El sistema asigna automáticamente un único identificador de omisión a cada región.
    
- Cualquier sitio conectado a una región por un vínculo WAN sin restricciones de ancho de banda hereda el mismo identificador de omisión de la región.
    
- A un sitio asociado a la región por un vínculo WAN con un ancho de banda restringido se le asigna un identificador de omisión distinto al de la región.
    
- Las subredes asociadas a cada sitio heredan el identificador de omisión del sitio.
    
## <a name="media-bypass-and-call-admission-control"></a>Omisión de medios y servicio de control de admisión de llamadas

El servicio de control de admisión de llamadas (CAC) y la omisión de medios funcionan conjuntamente para administrar el control del ancho de banda para medios telefónicos. La omisión de medios facilita el flujo de medios a través de vínculos con buenas conexiones; el CAC administra el tráfico en vínculos con restricciones de ancho de banda. Como la omisión de medios y el CAC son mutuamente exclusivos, deberás tener en cuenta a cada uno de ellos al realizar la planificación del otro. Se admiten las siguientes combinaciones:
  
- Tanto el CAC como la omisión de medios están habilitados. La omisión de medios necesita estar configurada con **Usar información de sitio y región**. La información de sitio y región es la misma que la usada para el CAC.
    
    Si habilita el CAC, no puede seleccionar **Siempre el desvío**y viceversa, debido a que las dos configuraciones son mutuamente excluyentes. Es decir, sólo uno de los dos se aplicará a cualquier llamada de RTC determinado. En primer lugar, se realiza una comprobación para determinar si el desvío de medios se aplica a la llamada. Si lo hace, no se usa el CAC. Esto tiene sentido, porque si tiene derecho para el desvío de una llamada, es por definición utilizando una conexión donde CAC no es necesario. Si el desvío de no se puede aplicar a la llamada (es decir, si el desvío del cliente y la puerta de enlace no coinciden los identificadores), a continuación, se aplica el CAC a la llamada.
    
- CAC no habilitado y la omisión de medios configurada con **Omitir siempre**.
    
    En esta configuración, las subredes tanto del tronco como del cliente están asignadas a un solo identificador de omisión, y el sistema lo calcula.
    
- CAC no habilitado y la omisión de medios configurada con **Usar información de sitio y región**.
    
    Cuando **Usar información de sitio y región** está habilitado, la determinación de omisión funciona básicamente del mismo modo, independientemente de si el CAC está habilitado o no. Es decir, para cualquier llamada de RTC determinada, la subred del cliente está asignada a un sitio concreto y se extrae el identificador de desvío para esa subred. De forma similar, subred de la puerta de enlace se asigna a un sitio determinado, y se extrae el identificador de desvío para esa subred. La omisión de la llamada solo se producirá si los dos identificadores de omisión son idénticos. Si no es así, la omisión de medios no tendrá lugar.
    
    Incluso aunque el CAC esté deshabilitado globalmente, es necesario definir la directiva de ancho de banda para cada uno de los sitios y vínculos si deseas usar una configuración de sitio y región para controlar la decisión de omisión. El valor real de la restricción de ancho de banda o su modalidad no importa. El objetivo final es hacer que el sistema calcule automáticamente diferentes identificadores de omisión para asociarse con diferentes configuraciones regionales que no tienen una buena conexión. La definición de una restricción de ancho de banda significa por definición que un vínculo no tiene una buena conexión.
    
- El CAC está habilitado y la omisión de medios no está habilitada. Esto se aplica únicamente cuando todas las puertas de enlace y las IP-PBX presentan una conexión deficiente o no reúnen otros requisitos para la omisión de medios. Para obtener información detallada acerca de los requisitos para el desvío de medios, consulte [requisitos para el desvío de medios](http://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).
    
## <a name="technical-requirements"></a>Requisitos técnicos

Para cada llamada a la RTC, el servidor de mediación determina si se pueden enviar medios desde la Skype de extremo de negocio de origen directamente a un elemento del mismo nivel de servidor de mediación sin cruzar el servidor de mediación. El componente del mismo nivel puede ser una puerta de enlace RTC, una IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet (ITSP) asociado con el tronco entre el servidor de mediación hacia el que se ha redirigido la llamada.
  
Puede emplearse la omisión de medios cuando se reúnen los siguientes requisitos:
  
- Un par de servidor de mediación debe admitir las capacidades necesarias para el desvío de medios, el más importantes que se va a la capacidad para manejar varias respuestas bifurcadas (conocidas como "de diálogos iniciales"). Ponte en contacto con el fabricante de tu puerta de enlace o PBX, o con tu ITSP, para obtener el valor de la cantidad máxima de diálogos iniciales que la puerta de enlace, la PBX o el SBC pueden aceptar.
    
- El par de servidor de mediación debe aceptar el tráfico de medios directamente desde Skype para los extremos de negocio. Muchas ITSPs permitir que sus SBC recibir tráfico sólo desde el servidor de mediación. Póngase en contacto con el protocolo para determinar si su SBC acepta el tráfico de medios directamente desde Skype para los extremos de negocio.
    
- Skype para clientes empresariales y un servidor de mediación par debe estar bien conectado, lo que significa que se encuentran ya sea en la misma región de red o en la red de sitios que se conectan a la región a través de WAN vínculos que no tienen restricciones de ancho de banda
    

