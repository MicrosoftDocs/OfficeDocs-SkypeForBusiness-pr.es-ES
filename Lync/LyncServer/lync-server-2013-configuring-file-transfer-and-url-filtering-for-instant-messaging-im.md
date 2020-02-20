---
title: Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 311472459958a60708e89a4eace22e5ace1325cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La herramienta filtro inteligente de mensajería instantánea ayuda a proteger la implementación de Lync Server 2013 frente a la propagación de las formas más comunes de virus con una degradación mínima para la experiencia del usuario. Use el filtro inteligente de mensajería instantánea para configurar filtros que bloqueen los mensajes instantáneos no solicitados o potencialmente dañinos procedentes de extremos desconocidos más allá del firewall corporativo. Los filtros se configuran al especificar los criterios que se van a usar para determinar lo que se va a bloquear, como mensajes instantáneos que contienen hipervínculos con prefijos determinados y archivos con extensiones específicas.

El filtro inteligente de mensajería instantánea ofrece lo siguiente:

  - Filtrado mejorado de direcciones URL.

  - Filtrado mejorado de transferencias de archivos.

La configuración del filtro inteligente de mensajería instantánea incluye lo siguiente:

  - Configuración de filtrado de direcciones URL.

  - Configuración de filtrado de transferencias de archivos.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Cómo se aplican las opciones de filtrado a los mensajes instantáneos

Antes de implementar la herramienta de filtro inteligente de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado a medida que los mensajes se redirigen desde un servidor de Lync Server 2013 a otro. Estas opciones de filtrado se aplican de manera coherente, independientemente de si los servidores se encuentran en una sola organización o en varias organizaciones. Esta coherencia se aplica a la forma en que se insertan los avisos y advertencias personalizados en los mensajes y se envían a través de los servidores.

<div>


> [!NOTE]
> El filtro de mensajes instantáneos aumenta la cantidad de recursos de CPU necesarios para procesar las direcciones URL de un mensaje. Este aumento de la demanda de la CPU también afecta al rendimiento de Lync Server.



</div>

Mediante el uso de la página **filtro de URL** en el grupo de **presencia y mensajería instantánea** del panel de control de Lync Server, puede bloquear algunos o todos los hipervínculos o configurar una advertencia. La advertencia se introduce al comienzo de un mensaje instantáneo que contiene un hipervínculo al seleccionar la opción **Prefijo de hipervínculo****Enviar mensaje de advertencia**.

Cuando un mensaje instantáneo pasa de un servidor a otro, se aplican las siguientes pautas generales:

  - Si un servidor bloquea un mensaje instantáneo (porque ha activado la casilla **Bloquear direcciones URL con extensión de archivo** de la página **Filtro para direcciones URL** o porque ha seleccionado la opción **Prefijo de hipervínculo****Bloquear hipervínculos**), el cliente recibe un mensaje de error. Los servidores subsiguientes no reciben este mensaje instantáneo.

  - Si un servidor (Server1) agrega una advertencia a un mensaje instantáneo que tiene un hipervínculo activo, un servidor subsiguiente (Server2) que reciba este mensaje instantáneo podrá emprender otra acción basándose en este hipervínculo activo presente en el mensaje instantáneo, y bloquear el mensaje o agregar una advertencia. Si Server2 está configurado de modo que solo agregue una advertencia para esta dirección URL, se quitará la advertencia anterior agregada por Server1 y se agregará al comienzo del mensaje instantáneo la advertencia configurada en Server2.

<div>


> [!NOTE]
> Si ejecuta Lync Server 2013 en un entorno mixto, Live Communications Server 2005 con SP1 es la versión mínima necesaria para usar la aplicación de filtro inteligente de mensajería instantánea. El filtro inteligente de mensajería instantánea no se puede usar en Live Communications Server 2005 sin SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtrado para direcciones URL

Las direcciones URL se filtran en función de su prefijo de hipervínculo. A continuación se muestran ejemplos de prefijos válidos:

  - www\*.

  - Protocolo.

  - http

Si no se configura el filtro de mensajería instantánea para que realice algún filtrado de direcciones URL, todas las direcciones URL que aparezcan en mensajes instantáneos pasarán a través del servidor sin sufrir modificaciones. Si configura el filtro de mensajería instantánea para que realice un filtrado de direcciones URL, las URL de los mensajes instantáneos se filtrarán de acuerdo con las opciones que seleccione en el cuadro de diálogo **Editar filtro para direcciones URL** o **Nuevo filtro para direcciones URL**.

  - **Habilitar filtro**   de dirección URL esta opción permite el filtrado de direcciones URL para la implementación global o para el sitio que seleccione.

  - **Bloquear direcciones URL con extensión**   de archivo el filtro de mensaje instantáneo bloquea cualquier dirección URL de intranet o Internet activa que contenga un archivo con una extensión enumerada en **extensiones de tipo de archivo que se bloqueen** en el cuadro de diálogo **Editar filtro de archivo** . Cuando se bloquea una dirección URL, el remitente recibe un mensaje de error. Al seleccionar dicha opción, esta tiene prioridad sobre todas las demás opciones de filtrado para cualquier extensión de archivo definida en **Extensiones de tipo de archivo a bloquear**.
    
    <div>
    

    > [!IMPORTANT]
    > El filtrado de las extensiones de archivo se limita a los nombres de archivo estándar. Puede que el filtrado no funcione con las extensiones de archivo insertadas en otros nombres.

    
    </div>

Para configurar la forma en la que se administran los hipervínculos en las conversaciones de mensajes instantáneos, seleccione una de las siguientes opciones en **Prefijo de hipervínculo**:

  - **No filtrar**   direcciones URL en los mensajes se envían a través del servidor. Al seleccionar esta opción se muestra el cuadro **Permitir mensaje**. En el cuadro **Permitir mensaje**, especifique el aviso que desea insertar al comienzo de cada mensaje instantáneo que contenga hipervínculos. Este aviso no puede tener más de 65.535 caracteres.

  - **Bloquear hipervínculos**   la entrega de mensajes instantáneos que contienen hipervínculos activos se bloquea en Lync Server y se muestra un mensaje de error al remitente.

  - **Enviar mensaje**   de advertencia Lync Server permite hipervínculos activos en mensajes instantáneos, pero incluye una advertencia. Al seleccionar esta opción, se muestra el cuadro **Mensaje de advertencia**. En el cuadro **Mensaje de advertencia**, debe escribir la advertencia que desea incluir en los mensajes instantáneos que contengan hipervínculos válidos. Por ejemplo, esta advertencia podría indicar los posibles riesgos de hacer clic en vínculos desconocidos o hacer referencia a directivas y requisitos relevantes para la organización. La advertencia no puede tener más de 65.535 caracteres.

Si selecciona **Bloquear hipervínculos** o **Enviar mensaje de advertencia**, puede definir las siguientes opciones:

  - **Excluir hipervínculos**   de Intranet local el filtro de mensajes instantáneos bloquea solo direcciones URL de Internet. Las direcciones URL de ubicaciones que se encuentran en la intranet pasan por el servidor sin sufrir modificaciones. Sin embargo, las direcciones URL de intranet que los servidores individuales que ejecutan Lync Server dependen de qué tipos de sitios web locales se consideran parte de su zona de intranet. Para comprobar la configuración de la zona Intranet de un servidor, consulte el procedimiento "para configurar la intranet en Internet Explorer" en [modificar el filtro de direcciones URL predeterminadas en Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtre estos prefijos**   de hipervínculos para elegir los prefijos que desea bloquear, haga clic en **seleccionar**y, a continuación, en **seleccionar prefijo de hipervínculo**, agregue los prefijos a la lista **prefijos de hipervínculos** .
    
    Todos los prefijos, salvo **href**, deben terminar con un punto, un signo de dos puntos o un asterisco seguido de un punto. Los prefijos válidos pueden contener cualquier carácter del conjunto de caracteres de dirección URL válido\*excepto el asterisco (). El conjunto de caracteres válidos de dirección \# \*URL es: +/0123456789\_ \` = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtrado para transferencia de archivos

El filtro para transferencia afecta tanto a los mensajes instantáneos como a las conferencias. En el caso de las conferencias, esta configuración afecta a la característica de documentos en el cliente de Office Live Meeting 2007 y a las características de reproducción multimedia.

<div>


> [!NOTE]
> Lync Server también ofrece opciones de configuración de transferencia de archivos. Esta opción del lado servidor se ofrece además de los controles de cliente disponibles en Lync Server.



</div>

Puede filtrar transferencias de archivos durante conversaciones de mensajes instantáneos, cuando use la característica de documentos en el cliente de Office Live Meeting 2007, así como las características de reproducción multimedia para todos los tipos de archivo. Puede definir las opciones siguientes para controlar las transferencias de archivos:

  - **Habilitar filtro**   de archivos esta opción habilita el filtrado de archivos para la implementación global o para el sitio que seleccione.
    
    Al activar el filtro de archivo, puede seleccionar una de las opciones siguientes en **Transferencia de archivos**:
    
      - **Bloquear tipos**   de archivo específicos especifica qué solicitudes de transferencia de archivos se filtran por el servidor mediante la especificación de una lista de extensiones de archivo que se van a bloquear. Las entradas de la lista pueden contener todos los caracteres estándar, pero no el carácter\*comodín (). En el cliente de Office Live Meeting 2007, la característica de documentos está habilitada, pero no se podrán cargar ni descargar los archivos que tengan estas extensiones. Si activa la casilla **Bloquear direcciones URL con extensión de archivo** en la configuración de un filtro de direcciones URL de la ficha **Filtro para direcciones URL**, el filtro para direcciones URL usa la misma lista para bloquear hipervínculos activos que contengan cualquiera de esas extensiones de archivo. Para seleccionar los tipos de archivo que desea bloquear, haga clic en **Seleccionar** y, en **Seleccionar tipo de archivo**, agregue las extensiones de tipo de archivo a la lista **Extensiones de tipo de archivo seleccionadas**.
    
      - **Bloquear todo**   el servidor elimina todos los mensajes instantáneos que contengan solicitudes de transferencia de archivos y devuelve un mensaje de error al remitente de la solicitud. Se deshabilita la característica de documentos en el cliente de Office Live Meeting 2007.

<div>


> [!IMPORTANT]
> El filtrado de las extensiones de archivo se limita a los nombres de archivo estándar. Puede que el filtrado no funcione con las extensiones de archivo insertadas en otros nombres.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificar el filtro de direcciones URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de la configuración de mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

