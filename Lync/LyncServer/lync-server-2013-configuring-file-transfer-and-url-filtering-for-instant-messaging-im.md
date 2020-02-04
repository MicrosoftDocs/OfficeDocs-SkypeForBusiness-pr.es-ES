---
title: Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi)
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
ms.openlocfilehash: e6c5a6053118b14b68c49a7fdaa6f444aca7ad23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La herramienta filtro inteligente de mensajes instantáneos ayuda a proteger la implementación de Lync Server 2013 contra la propagación de las formas más comunes de virus con una degradación mínima para la experiencia del usuario. Use el filtro inteligente de mi para configurar filtros para bloquear mensajes instantáneos no solicitados o potencialmente dañinos de puntos de conexión desconocidos fuera del firewall de la empresa. Para configurar filtros, especifique los criterios que se van a usar para determinar qué se debe bloquear, por ejemplo, los mensajes instantáneos que contengan hipervínculos con determinados prefijos y archivos con extensiones específicas.

El filtro inteligente de mensajes instantáneos proporciona lo siguiente:

  - Filtrado de URL mejorado.

  - Filtrado mejorado de transferencia de archivos.

La configuración del filtro inteligente de mensajes instantáneos incluye lo siguiente:

  - Configuración del filtrado de URL.

  - Configuración del filtrado de transferencia de archivos.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Cómo se aplican las opciones de filtrado a los mensajes instantáneos

Antes de implementar la herramienta inteligente de filtro de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado a medida que los mensajes se dirigen desde un servidor de Lync Server 2013 a otro. La manera en que se aplican estas opciones de filtrado es coherente, independientemente de si los servidores se encuentran en una sola organización o en los límites de la organización. Esta coherencia se aplica a la forma en que el aviso personalizado y los mensajes de advertencia se insertan en mensajes y se envían por servidores.

<div>


> [!NOTE]
> El filtro de mensajes instantáneos aumenta la cantidad de recursos de CPU necesarios para procesar las direcciones URL en un mensaje. Este aumento en la demanda de la CPU también afecta al rendimiento de Lync Server.



</div>

Si usa la página **filtro de URL** en el grupo **presencia y mi** en el panel de control de Lync Server, puede bloquear algunos o todos los hipervínculos o configurar una advertencia. La advertencia se inserta al principio de un mensaje instantáneo que contiene un hipervínculo cuando se elige la opción **Enviar mensaje de advertencia**en el **Prefijo de hipervínculo** .

Cuando un mensaje instantáneo viaja de un servidor a otro, se aplican las siguientes directrices generales:

  - Si un servidor bloquea un mensaje instantáneo (porque ha seleccionado la casilla de verificación **bloquear direcciones URL con extensión de archivo** en la página **filtro de URL** o porque ha elegido la opción **bloquear hipervínculos del hipervínculo**), se devolverá un mensaje de error al cliente. **** Los siguientes servidores no reciben este mensaje instantáneo.

  - Si un servidor (Servidor1) agrega una advertencia a un mensaje instantáneo que contiene un hipervínculo activo, un servidor posterior (servidor2) que reciba este mensaje instantáneo aún puede tomar una acción diferente según este hipervínculo activo presente en el mensaje instantáneo y bloquear la envía mensajes instantáneos o agrega una advertencia. Si server2 está configurado únicamente para agregar una advertencia para esta dirección URL, se quitará la advertencia anterior agregada por server1 y se agregará la advertencia configurada en server2 al principio del mensaje instantáneo.

<div>


> [!NOTE]
> Si ejecuta Lync Server 2013 en un entorno mixto, Live Communications Server 2005 con SP1 es la versión mínima requerida para usar la aplicación de filtro inteligente de mensajes instantáneos. El filtro inteligente de mensajes instantáneos no es compatible con Live Communications Server 2005 sin SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtrado de URL

Las direcciones URL se filtran según su prefijo de hipervínculo. Los siguientes ejemplos son prefijos válidos:

  - www\*.

  - FTP.

  - Protocolo

Si no configura el filtro de mensajes instantáneos para realizar el filtrado de URL, todas las direcciones URL incluidas en los mensajes instantáneos se pasan sin modificar a través del servidor. Si configura el filtro de mensaje instantáneo para que realice el filtrado de URL, las direcciones URL de los mensajes instantáneos se filtran de acuerdo con las opciones que seleccione en el cuadro de diálogo Editar filtro de **URL** o **nuevo filtro de URL** .

  - **Habilitar filtro**   de URL esta opción habilita el filtrado de URL para la implementación global o para el sitio que seleccione.

  - **Bloquear direcciones URL con extensión**   de archivo el filtro de mensaje instantáneo bloquea cualquier dirección URL activa de la intranet o de Internet que contenga un archivo con una extensión enumerada en **extensiones de tipo de archivo que se bloquean** en el cuadro de diálogo **Editar filtro de archivos** . Cuando se bloquea una dirección URL, se muestra un mensaje de error al remitente. Cuando se selecciona, esta opción tiene prioridad sobre todas las demás opciones de filtrado para cualquier extensión de archivo definida en **extensiones de tipo de archivo que se bloquee**.
    
    <div>
    

    > [!IMPORTANT]
    > El filtrado de extensiones de archivo está limitado a los nombres de archivo estándar. Es posible que el filtrado no funcione con las extensiones de archivo incrustadas en otros nombres.

    
    </div>

Para configurar cómo se administran los hipervínculos en las conversaciones de mensajes instantáneos, seleccione una de las siguientes opciones en **Prefijo de hipervínculo**:

  - **No filtre**   las direcciones URL de los mensajes que se envían a través del servidor. Al elegir esta opción, aparece el cuadro de **mensaje permitir** . En el cuadro **permitir mensaje** , especifique el aviso que desea insertar al principio de cada mensaje instantáneo que contenga hipervínculos. Este aviso no puede contener más de 65535 caracteres.

  - **Bloquear hipervínculos**   la entrega de mensajes instantáneos que contienen hipervínculos activos está bloqueada por Lync Server y se muestra un mensaje de error al remitente.

  - **Enviar mensaje**   de advertencia Lync Server permite hipervínculos activos en mensajes instantáneos, pero incluye una advertencia. Al elegir esta opción, aparece el cuadro de **mensaje de advertencia** . En el cuadro de **mensaje de advertencia** , debe escribir la advertencia que desea incluir con los mensajes instantáneos que contengan hipervínculos válidos. Por ejemplo, esta advertencia podría indicar los peligros potenciales de hacer clic en un vínculo desconocido o puede hacer referencia a las directivas y requisitos relevantes de su organización. La advertencia no puede tener más de 65535 caracteres.

Si selecciona **bloquear hipervínculos** o **Enviar mensaje de advertencia**, las siguientes opciones están disponibles:

  - **Excluir hipervínculos**   de Intranet local el filtro de mensajes instantáneos bloquea solo direcciones URL de Internet. Las direcciones URL de ubicaciones dentro de la intranet se pasan sin modificar a través del servidor. Sin embargo, las direcciones URL de intranet a las que pasan los servidores individuales que ejecutan Lync Server dependen de qué tipos de sitios web locales se consideran parte de su zona de intranet. Para comprobar la configuración de la zona Intranet de un servidor, consulte el procedimiento "para configurar la configuración de la intranet en Internet Explorer" en [modificar el filtro de URL predeterminado en Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtre estos prefijos**   de hipervínculo para elegir los prefijos que desea bloquear, haga clic en **seleccionar**y, a continuación, en **seleccionar prefijo de hipervínculo**, agregue los prefijos a la lista de **prefijos de hipervínculos** .
    
    Todos los prefijos excepto **href** deben finalizar con un punto o un signo de dos puntos, o un asterisco seguido de un punto. Los prefijos válidos pueden contener cualquier carácter del conjunto de caracteres de dirección URL válidos excepto el asterisco (\*). El conjunto de caracteres válidos de URL \# \*es: +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtrado de transferencia de archivos

Filtrar el filtrado de transferencia afecta tanto a los mensajes instantáneos como a las conferencias. Para las conferencias, esta configuración afecta a la característica de documentos de las características de reproducción multimedia y cliente de Office Live Meeting 2007.

<div>


> [!NOTE]
> Lync Server también ofrece opciones de configuración para la transferencia de archivos. Esta opción del servidor se ofrece además de los controles del cliente disponibles en Lync Server.



</div>

Puede filtrar las transferencias de archivos durante las conversaciones de mensajes instantáneos, cuando use la característica de documentos en el cliente de Office Live Meeting 2007 y las características de reproducción multimedia de todos los tipos de archivo. Puede establecer las siguientes opciones para controlar las transferencias de archivos:

  - **Habilitar filtro**   de archivos esta opción habilita el filtrado de archivos para la implementación global o para el sitio que seleccione.
    
    Al habilitar el filtro de archivos, puede elegir una de las siguientes opciones en la **transferencia de archivos**:
    
      - **Bloquear tipos**   de archivo específicos especifique las solicitudes de transferencia de archivos filtradas por el servidor especificando una lista de extensiones de archivo para bloquear. Las entradas de la lista pueden contener todos los caracteres estándar, pero no el carácter\*comodín (). En el cliente de Office Live Meeting 2007 la característica de documentos está habilitada, pero no se puede cargar ni descargar ningún archivo con esta extensión. Si selecciona la casilla de verificación **bloquear direcciones URL con extensión de archivo** en la configuración de un filtro de URL que aparece en la pestaña **filtro de URL** , el filtro de dirección URL usa esta misma lista para bloquear los hipervínculos activos que contienen cualquiera de estas extensiones de archivo. Para elegir qué tipos de archivo desea bloquear, haga clic en **seleccionar**y, a continuación, en **Seleccionar tipo de archivo**, agregue las extensiones de tipos de archivo a la lista Extensiones de tipos de **archivo seleccionados** .
    
      - **Bloquear todo**   el servidor elimina todos los mensajes instantáneos que contienen solicitudes de transferencia de archivos y devuelve un mensaje de error al remitente de la solicitud. La característica de documentos del cliente de Office Live Meeting 2007 está deshabilitada.

<div>


> [!IMPORTANT]
> El filtrado de extensiones de archivo está limitado a los nombres de archivo estándar. Es posible que el filtrado no funcione con las extensiones de archivo incrustadas en otros nombres.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificar el filtro de dirección URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Crear un filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar la configuración de mensajería instantánea y de presencia en Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

