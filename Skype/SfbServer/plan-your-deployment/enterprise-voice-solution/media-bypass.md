---
title: Plan de omisión de multimedia en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Decisiones necesarias para la planificación de la omisión de medios en la voz empresarial de Skype empresarial Server. Incluye interoperación con el control de admisión de llamadas (CAC).
ms.openlocfilehash: aed78aa12f593f834bc2c694fec87d5d31e6e47b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802710"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Plan de omisión de multimedia en Skype empresarial

Decisiones necesarias para la planificación de la omisión de medios en la voz empresarial de Skype empresarial Server. Incluye interoperación con el control de admisión de llamadas (CAC).

La omisión de elementos multimedia hace referencia a quitar el servidor de mediación de la ruta multimedia siempre que sea posible para las llamadas cuya señalización atraviese el servidor de mediación.

La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la conversión innecesaria, la posibilidad de la pérdida de paquetes y la cantidad de puntos de errores potenciales. La escalabilidad puede mejorarse, ya que la eliminación del procesamiento de medios para llamadas omitidas reduce la carga en el servidor de mediación. Esta reducción de carga complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.

 Cuando un sitio de sucursal sin un servidor de mediación se conecta a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios disminuye el requisito de ancho de banda permitiendo que los medios de un cliente de un sitio de sucursal fluyan directamente a su puerta de enlace local sin en primer lugar, debe transmitirse a través del vínculo WAN a un servidor de mediación del sitio central y viceversa.

Al aliviar el servidor de mediación del procesamiento multimedia, la omisión de medios también puede reducir el número de servidores de mediación que requiere una infraestructura de telefonía IP empresarial. Como regla general, habilita la omisión de medios siempre que sea posible.

La siguiente figura muestra las rutas de señalización y los medios básicos en las topologías con omisión de medios y sin ella.

**Rutas de señalización y medios con omisión de medios y sin ella**

![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

La omisión de elementos multimedia es útil cuando desea minimizar el número de servidores de mediación implementados. Normalmente, un grupo de servidores de mediación se implementará en un sitio central y controlará las puertas de enlace en los sitios de sucursales. Habilitar la omisión de medios permite que las llamadas de la red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las rutas de llamadas salientes de Skype empresarial Server y las directivas de voz empresarial deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.

Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si necesitas habilitar la omisión de medios para una subred inalámbrica, te recomendamos evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta una contrapartida respecto a la recuperación de la pérdida de paquetes que también necesitas tener en cuenta. RTAudio, un códec disponible para llamadas que no omiten el servidor de mediación, es más apropiado para la gestión de la pérdida de paquetes.

## <a name="planning-your-media-bypass-deployment"></a>Planear la implementación de omisión de medios

Una vez que la estructura de telefonía empresarial está en vigor, la planeación de la omisión de elementos multimedia es sencilla.

- Si tienes una topología centralizada sin vínculos WAN a sitios de sucursal, puedes habilitar la omisión de medios global porque no se necesita control de ajustes.

- Si tienes una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determina los aspectos siguientes:

  - Si los componentes del mismo nivel del servidor de mediación pueden asumir las capacidades que se requieren para la omisión de medios.

  - Los sitios de cada región de red que están bien conectados.

  - La combinación de la omisión de medios y el servicio de control de admisión de llamadas que es apropiada para la red.

Al habilitar la omisión de medios, se genera automáticamente un identificador de omisión único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región a través de vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de omisión únicos.

Cuando un usuario realiza una llamada a la RTC, el servidor de mediación compara el identificador de omisión de la subred del cliente con el identificador de omisión de la subred de la puerta de enlace. Si los dos identificadores de omisión coinciden, se usará la omisión de medios para la llamada. Si los identificadores de omisión no coinciden, el medio para la llamada debe fluir por el servidor de mediación.

Cuando un usuario recibe una llamada de la RTC, el cliente del usuario compara su identificador de omisión con el de la puerta de enlace PSTN. Si los dos identificadores de omisión coinciden, los medios fluyen directamente de la puerta de enlace al cliente, omitiendo el servidor de mediación.

Solo los clientes y dispositivos de Lync 2010 o versiones posteriores admiten interacciones de omisión de contenido multimedia con un servidor de mediación.

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

    Si habilita CAC, no puede seleccionar **omitir siempre**y viceversa, porque las dos configuraciones se excluyen mutuamente. Es decir, solo una de las dos se aplicará a una llamada RTC. En primer lugar, se realiza una comprobación para determinar si se aplica la omisión de elementos multimedia a la llamada. Si es así, no se utiliza CAC. Esto tiene sentido, ya que si una llamada es apta para la omisión, se realiza por definición mediante una conexión en la que no es necesario CAC. Si no se puede aplicar el omisión a la llamada (es decir, si los identificadores de omisión del cliente y el gateway no coinciden), se aplica CAC a la llamada.

- CAC no habilitado y la omisión de medios configurada con **Omitir siempre**.

    En esta configuración, las subredes tanto del tronco como del cliente están asignadas a un solo identificador de omisión, y el sistema lo calcula.

- CAC no habilitado y la omisión de medios configurada con **Usar información de sitio y región**.

    Cuando **Usar información de sitio y región** está habilitado, la determinación de omisión funciona básicamente del mismo modo, independientemente de si el CAC está habilitado o no. Es decir, para cualquier llamada RTC, la subred del cliente se asigna a un sitio en particular y se extrae el identificador de derivación de esa subred. De forma similar, la subred de la puerta de enlace se asigna a un sitio en particular y se extrae el identificador de derivación de esa subred. La omisión de la llamada solo se producirá si los dos identificadores de omisión son idénticos. Si no es así, la omisión de medios no tendrá lugar.

    Incluso aunque el CAC esté deshabilitado globalmente, es necesario definir la directiva de ancho de banda para cada uno de los sitios y vínculos si deseas usar una configuración de sitio y región para controlar la decisión de omisión. El valor real de la restricción de ancho de banda o su modalidad no importa. El objetivo final es hacer que el sistema calcule automáticamente diferentes identificadores de omisión para asociarse con diferentes configuraciones regionales que no tienen una buena conexión. La definición de una restricción de ancho de banda significa por definición que un vínculo no tiene una buena conexión.

- El CAC está habilitado y la omisión de medios no está habilitada. Esto se aplica únicamente cuando todas las puertas de enlace y las IP-PBX presentan una conexión deficiente o no reúnen otros requisitos para la omisión de medios. Para obtener más información sobre los requisitos para la omisión de medios, mira [Requirements for Media Bypass](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).

## <a name="technical-requirements"></a>Requisitos técnicos

Para cada llamada a la RTC, el servidor de mediación determina si los medios del extremo de origen de Skype empresarial se pueden enviar directamente a un servidor de mediación del mismo nivel sin atravesar el servidor de mediación. El componente del mismo nivel puede ser una puerta de enlace RTC, una IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet (ITSP) asociado con el tronco entre el servidor de mediación hacia el que se ha redirigido la llamada.

Puede emplearse la omisión de medios cuando se reúnen los siguientes requisitos:

- Un servidor de mediación debe admitir las capacidades necesarias para la omisión de elementos multimedia, la más importante es la capacidad de controlar varias respuestas bifurcadas (conocidas como "cuadros de diálogo temprano"). Ponte en contacto con el fabricante de tu puerta de enlace o PBX, o con tu ITSP, para obtener el valor de la cantidad máxima de diálogos iniciales que la puerta de enlace, la PBX o el SBC pueden aceptar.

- El servidor de mediación del mismo nivel debe aceptar el tráfico de medios directamente desde los puntos de conexión de Skype empresarial. Muchas ITSPs permiten que su SBC reciba únicamente el tráfico del servidor de mediación. Póngase en contacto con su ITSP para determinar si su SBC acepta tráfico de medios directamente desde los puntos de conexión de Skype empresarial.

- Los clientes de Skype empresarial y un servidor de mediación deben estar conectados correctamente, lo que significa que se encuentran en la misma región de red o en sitios de red que se conectan a la región a través de vínculos WAN que no tienen restricciones de ancho de banda


