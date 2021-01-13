---
title: Planear la omisión de medios en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Decisiones necesarias para planear la omisión de medios en Skype Empresarial Server Telefonía IP empresarial. Incluye interoperación con el servicio de control de admisión de llamadas (CAC).
ms.openlocfilehash: a6d49b8abaa75e555f3de4c44b890e18b6de664a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825380"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planear la omisión de medios en Skype Empresarial

Decisiones necesarias para planear la omisión de medios en Skype Empresarial Server Telefonía IP empresarial. Incluye interoperación con el servicio de control de admisión de llamadas (CAC).

El desvío de medios consiste en quitar el servidor de mediación de la ruta de acceso a medios siempre que sea posible, en las llamadas cuya señalización atraviese el servidor de mediación.

El desvío de medios puede mejorar la calidad de la voz al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y el número de puntos de errores potenciales. Se puede mejorar la escalabilidad, ya que, al eliminar el procesamiento de medios de las llamadas desviadas, se reduce la carga del servidor de mediación. Esta reducción de la carga complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.

 Cuando un sitio de sucursal sin un servidor de mediación está conectado a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios reduce el requisito de ancho de banda al permitir que los medios de un cliente en un sitio de sucursal fluyan directamente a su puerta de enlace local sin tener que fluir primero a través del vínculo WAN a un servidor de mediación en el sitio central y hacia atrás.

Al evitar el procesamiento de medios en el servidor de mediación, la omisión de medios también puede reducir el número de servidores de mediación que requiere una infraestructura Telefonía IP empresarial medios. Por regla general, se recomienda habilitar el desvío de medios siempre que sea posible.

La siguiente ilustración muestra las rutas de señalización y los medios básicos en las topologías con desvío de medios y sin él.

**Rutas de señalización y medios con desvío de medios y sin él**

![Aplicación de la conexión de omisión de medios de CAC de voz](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados. En general, un grupo de servidores de mediación se implementa en un sitio central y controla puertas de enlace en los sitios de sucursal. Habilitar el desvío de medios permite que las llamadas de red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las rutas de llamadas salientes y las directivas de Telefonía IP empresarial de Skype Empresarial Server deben configurarse correctamente para que las llamadas RTC de los clientes de una sucursal se enrutar a la puerta de enlace adecuada.

Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si debe habilitarse el desvío de medios para una subred inalámbrica, se recomienda evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta unas contrapartidas respecto a la recuperación de pérdida de paquetes que también deben tenerse en cuenta. RTAudio, un códec disponible para llamadas que no desvían el servidor de mediación, es más apropiado para ocuparse de la pérdida de paquetes.

## <a name="planning-your-media-bypass-deployment"></a>Planear la implementación de la omisión de medios

Una vez que Telefonía IP empresarial estructura de medios, la planeación de la omisión de medios es sencilla.

- Si tiene una topología centralizada sin vínculos WAN a redes de sucursal, puede habilitar un desvío de medios global porque no se necesita control ajustado.

- Si tiene una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determine los aspectos siguientes:

  - Si los homólogos del servidor de mediación pueden asumir las capacidades que se requieren para el desvío de medios.

  - Los sitios de cada región de redes que están bien conectados.

  - La combinación de desvío de medios y control de admisión de llamadas que es apropiada para la red.

Al habilitar el desvío de medios, se genera automáticamente un identificador de desvío único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región mediante vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de desvío únicos.

Cuando un usuario realiza una llamada a la RTC, el servidor de mediación compara el identificador de omisión de la subred de cliente con el identificador de omisión de la subred de puerta de enlace. Si los dos identificadores de desvío coinciden, se usará el desvío de medios para la llamada. Si los IDs de omisión no coinciden, los medios de la llamada deben fluir a través del servidor de mediación.

Cuando un usuario recibe una llamada de la RTC, el cliente del usuario compara su identificador de omisión con el de la puerta de enlace RTC. Si los dos omisión de los IDs coinciden, los medios fluyen directamente desde la puerta de enlace al cliente, omitiendo el servidor de mediación.

Solo los clientes y dispositivos lync 2010 o más recientes admiten interacciones de omisión de medios con un servidor de mediación.

> [!IMPORTANT]
> Además de habilitar el desvío de medios de manera global, debe habilitarse en cada tronco RTC. Si el desvío se habilita globalmente pero no se habilita en un determinado tronco RTC, no se invocará el desvío de medios en ninguna de las llamadas en las que intervenga ese tronco RTC. Asimismo, si el desvío de medios se define en **Usar información de región y sitio**, todas las subredes enrutables deben asociarse con los sitios en los que se ubican. Si en un sitio hay subredes enrutables en las que no se desea habilitar el desvío, dichas subredes deben agruparse en un sitio nuevo antes de habilitar el desvío de medios. Esta acción asegurará que las subredes no enrutables tengan asignado un identificador de desvío diferente.

## <a name="media-bypass-modes"></a>Modos de omisión de medios

Debe configurar el desvío de medios de forma global y para cada tronco RTC individual. Al habilitar el desvío de medios globalmente, tiene dos opciones: **Desviar siempre** y **Usar información de sitio y región**.

Como el propio nombre sugiere, **Desviar siempre** significa que se intentará realizar el desvío de todas las llamadas de RTC. **Desviar siempre** se usa en implementaciones en las que no hay necesidad de habilitar el control de admisión de llamadas ni de especificar información detallada de configuración con respecto a cuándo intentar el desvío de medios. Además, **Desviar siempre** se usa cuando existe plena conectividad entre clientes y puertas de enlace de RTC. En esta configuración, todas las subredes se asignan únicamente a un solo identificador de desvío, que el sistema calcula.

Con **Usar información de sitio y región**, se usa el identificador de desvío asociado a la configuración del sitio y la región para tomar la decisión de desvío. Esta configuración proporciona la flexibilidad de configurar el desvío para las topologías más comunes, ya que proporciona un control más preciso cuando se produce el desvío, además de admitir interacciones con el control de admisión de llamadas (CAC). El sistema intenta facilitarle la tarea asignando automáticamente identificadores de desvío de la manera siguiente.

- El sistema asigna automáticamente un único identificador de desvío a cada región.

- Cualquier sitio conectado a una región por un vínculo WAN sin restricciones de ancho de banda hereda el mismo identificador de desvío de la región.

- A un sitio asociado a la región por un vínculo WAN con un ancho de banda restringido se le asigna un identificador de desvío distinto al de la región.

- Las subredes asociadas a cada sitio heredan el identificador de desvío del sitio.

## <a name="media-bypass-and-call-admission-control"></a>Desvío de medios y control de admisión de llamadas

La omisión de medios y el control de admisión de llamadas (CAC) funcionan conjuntamente para administrar el control de ancho de banda para los medios de llamadas. La omisión de medios facilita el flujo de medios a través de vínculos bien conectados; El CAC administra el tráfico en vínculos con restricciones de ancho de banda. Dado que la omisión de medios y el CAC son mutuamente excluyentes, debe tener en cuenta uno al planear el otro. Se admiten las siguientes combinaciones:

- El CAC y la omisión de medios están habilitados. La omisión de medios debe establecerse **en Usar información de sitio y región.** Esta información de sitio y región es la misma que la que se usa para cac.

    Si habilita el CAC, no puede seleccionar **Omitir** siempre y viceversa, porque las dos configuraciones son mutuamente excluyentes. Es decir, solo uno de los dos se aplicará a cualquier llamada RTC determinada. En primer lugar, se realiza una comprobación para determinar si la omisión de medios se aplica a la llamada. Si es así, no se usa el CAC. Esto tiene sentido, porque si una llamada es apta para la omisión, es por definición mediante una conexión en la que no se necesita cac. Si no se puede aplicar la omisión a la llamada (es decir, si los ID de omisión del cliente y la puerta de enlace no coinciden), se aplica el CAC a la llamada.

- EL CAC no está habilitado y la omisión de medios está establecida en **Omitir siempre.**

    En esta configuración, las subredes de cliente y tronco se asignan a un solo identificador de omisión, que calcula el sistema.

- EL CAC no está habilitado y la omisión de medios está **establecida en Usar información de sitio y región.**

    Cuando **la opción Usar información de sitio** y región está habilitada, la determinación de omisión funciona básicamente de la misma manera, independientemente de si el CAC está habilitado o no. Es decir, para cualquier llamada RTC determinada, la subred del cliente se asigna a un sitio determinado y se extrae el identificador de omisión de esa subred. De forma similar, la subred de la puerta de enlace se asigna a un sitio determinado y se extrae el identificador de omisión de esa subred. Solo si los dos id. de omisión son idénticos, se omitirá la llamada. Si no son idénticas, no se producirá la omisión de medios.

    Aunque el CAC está deshabilitado globalmente, la directiva de ancho de banda debe definirse para cada sitio y vínculo si desea usar la configuración de sitio y región para controlar la decisión de omisión. El valor real de la restricción de ancho de banda o su modalidad no importa. El objetivo final es hacer que el sistema calcule automáticamente diferentes IDs de omisión para asociar con diferentes configuraciones regionales que no están bien conectadas. Definir una restricción de ancho de banda por definición significa que un vínculo no está bien conectado.

- El CAC está habilitado y la omisión de medios no está habilitada. Esto solo se aplicaría cuando todas las puertas de enlace IP-PBXs no estén bien conectadas o no cumplan otros requisitos para la omisión de medios. Para obtener más información sobre los requisitos para la omisión de medios, consulte [Requisitos para la omisión de medios.](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx)

## <a name="technical-requirements"></a>Requisitos técnicos

Para cada llamada a la RTC, el servidor de mediación determina si los medios del punto de conexión de origen de Skype Empresarial se pueden enviar directamente a un servidor de mediación del mismo nivel sin atravesar el servidor de mediación. El componente del mismo nivel puede ser una puerta de enlace RTC, un sistema IP-PBX o un controlador SBC en un proveedor de servicios de telefonía por Internet (ITSP) asociado con el tronco entre el servidor de mediación hacia el que se ha enrutado la llamada.

Puede emplearse el desvío de medios cuando se reúnen los siguientes requisitos:

- Un servidor de mediación del mismo nivel debe admitir las capacidades necesarias para la omisión de medios, siendo la más importante la capacidad de controlar varias respuestas bifurcadas (conocidas como "diálogos iniciales"). Póngase en contacto con el fabricante de su puerta de enlace, sistema PBX o ITSP para obtener el valor del número máximo de diálogos iniciales que la puerta de enlace, el sistema PBX o el SBC puede aceptar.

- El sistema del mismo nivel del servidor de mediación debe aceptar el tráfico de medios directamente desde los puntos de conexión de Skype Empresarial. Muchos ITSP permiten que su SBC reciba tráfico solo desde el servidor de mediación. Póngase en contacto con su ITSP para determinar si su SBC acepta tráfico de medios directamente desde los puntos de conexión de Skype Empresarial.

- Los clientes de Skype Empresarial y un servidor de mediación del mismo nivel deben estar bien conectados, lo que significa que se encuentran en la misma región de red o en sitios de red que se conectan a la región a través de vínculos WAN que no tienen restricciones de ancho de banda


