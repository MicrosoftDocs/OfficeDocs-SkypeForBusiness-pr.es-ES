---
title: "Configurar transferencia de archivos y filtrado de URL para MI en Lync Server 2013"
TOCTitle: "Conf. du transf. de fich. et du filtr. des URL pour mess. inst. dans LS 2013"
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48274467
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la transferencia de archivos y el filtrado de direcciones URL para la mensajería instantánea (MI) en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

La herramienta Filtro inteligente de mensajería instantánea ayuda a proteger la implementación de Lync Server 2013 contra la propagación de las formas más comunes de virus con una degradación mínima de la experiencia por parte de los usuarios. Use el filtro inteligente de mensajería instantánea para configurar filtros que bloqueen los mensajes instantáneos no solicitados o potencialmente dañinos procedentes de extremos desconocidos más allá del firewall corporativo. Los filtros se configuran al especificar los criterios que se van a usar para determinar lo que se va a bloquear, como mensajes instantáneos que contienen hipervínculos con prefijos determinados y archivos con extensiones específicas.

El filtro inteligente de mensajería instantánea ofrece lo siguiente:

  - Filtrado mejorado de direcciones URL.

  - Filtrado mejorado de transferencias de archivos.

La configuración del filtro inteligente de mensajería instantánea incluye lo siguiente:

  - Configuración de filtrado de direcciones URL.

  - Configuración de filtrado de transferencias de archivos.

## Cómo se aplican las opciones de filtrado a los mensajes instantáneos

Antes de implementar la herramienta Filtro inteligente de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado cuando se enrutan los mensajes de un servidor Lync Server 2013 a otro. Estas opciones de filtrado se aplican de manera coherente, independientemente de si los servidores se encuentran en una sola organización o en varias organizaciones. Esta coherencia se aplica a la forma en que se insertan los avisos y advertencias personalizados en los mensajes y se envían a través de los servidores.


> [!NOTE]
> El filtro de mensajes instantáneos aumenta la cantidad de recursos de CPU necesarios para procesar las direcciones URL de un mensaje. Este aumento de la demanda de CPU afecta asimismo al rendimiento de Lync Server.



Al usar la página **Filtro para direcciones URL** del grupo **Mensajería instantánea y presencia** en Panel de control de Lync Server, puede bloquear algunos hipervínculos o todos ellos, o configurar una advertencia. La advertencia se introduce al comienzo de un mensaje instantáneo que contiene un hipervínculo al seleccionar la opción **Prefijo de hipervínculoEnviar mensaje de advertencia**.

Cuando un mensaje instantáneo pasa de un servidor a otro, se aplican las siguientes pautas generales:

  - Si un servidor bloquea un mensaje instantáneo (porque ha activado la casilla **Bloquear direcciones URL con extensión de archivo** de la página **Filtro para direcciones URL** o porque ha seleccionado la opción **Prefijo de hipervínculoBloquear hipervínculos**), el cliente recibe un mensaje de error. Los servidores subsiguientes no reciben este mensaje instantáneo.

  - Si un servidor (Server1) agrega una advertencia a un mensaje instantáneo que tiene un hipervínculo activo, un servidor subsiguiente (Server2) que reciba este mensaje instantáneo podrá emprender otra acción basándose en este hipervínculo activo presente en el mensaje instantáneo, y bloquear el mensaje o agregar una advertencia. Si Server2 está configurado de modo que solo agregue una advertencia para esta dirección URL, se quitará la advertencia anterior agregada por Server1 y se agregará al comienzo del mensaje instantáneo la advertencia configurada en Server2.


> [!NOTE]
> Si está ejecutando Lync Server 2013 en un entorno mixto, Live Communications Server 2005 con SP1 es la versión mínima necesaria para usar la aplicación Filtro inteligente de mensajería instantánea. El filtro inteligente de mensajería instantánea no se puede usar en Live Communications Server 2005 sin SP1.



## Filtrado para direcciones URL

Las direcciones URL se filtran en función de su prefijo de hipervínculo. A continuación se muestran ejemplos de prefijos válidos:

  - www\*.

  - ftp.

  - http:

Si no se configura el filtro de mensajería instantánea para que realice algún filtrado de direcciones URL, todas las direcciones URL que aparezcan en mensajes instantáneos pasarán a través del servidor sin sufrir modificaciones. Si configura el filtro de mensajería instantánea para que realice un filtrado de direcciones URL, las URL de los mensajes instantáneos se filtrarán de acuerdo con las opciones que seleccione en el cuadro de diálogo **Editar filtro para direcciones URL** o **Nuevo filtro para direcciones URL**.

  - **Habilitar filtro para direcciones URL**   Esta opción permite el filtrado de direcciones URL para toda la implementación o para el sitio que seleccione.

  - **Bloquear direcciones URL con extensión de archivo**  El filtro para mensajería instantánea bloquea cualquier dirección URL activa de la intranet o de Internet que contenga un archivo con una extensión incluida en **Extensiones de tipo de archivo a bloquear** en el cuadro de diálogo **Editar filtro de archivo**. Cuando se bloquea una dirección URL, el remitente recibe un mensaje de error. Al seleccionar dicha opción, esta tiene prioridad sobre todas las demás opciones de filtrado para cualquier extensión de archivo definida en **Extensiones de tipo de archivo a bloquear**.
    
    > [!IMPORTANT]  
    > El filtrado de las extensiones de archivo se limita a los nombres de archivo estándar. Puede que el filtrado no funcione con las extensiones de archivo insertadas en otros nombres.
    


Para configurar la forma en la que se administran los hipervínculos en las conversaciones de mensajes instantáneos, seleccione una de las siguientes opciones en **Prefijo de hipervínculo**:

  - **No filtrar**   Las direcciones URL de los mensajes se envían a través del servidor. Al seleccionar esta opción se muestra el cuadro **Permitir mensaje**. En el cuadro **Permitir mensaje**, especifique el aviso que desea insertar al comienzo de cada mensaje instantáneo que contenga hipervínculos. Este aviso no puede tener más de 65.535 caracteres.

  - **Bloquear hipervínculos**   Lync Server bloquea la entrega de mensajes instantáneos que tengan algún hipervínculo activo y el remitente recibe un mensaje de error.

  - **Enviar mensaje de advertencia**   Lync Server permite hipervínculos activos en los mensajes instantáneos, pero incluye una advertencia. Al seleccionar esta opción, se muestra el cuadro **Mensaje de advertencia**. En el cuadro **Mensaje de advertencia**, debe escribir la advertencia que desea incluir en los mensajes instantáneos que contengan hipervínculos válidos. Por ejemplo, esta advertencia podría indicar los posibles riesgos de hacer clic en vínculos desconocidos o hacer referencia a directivas y requisitos relevantes para la organización. La advertencia no puede tener más de 65.535 caracteres.

Si selecciona **Bloquear hipervínculos** o **Enviar mensaje de advertencia**, puede definir las siguientes opciones:

  - **Excluir hipervínculos de intranet locales**   El filtro de mensajes instantáneos solo bloquea las direcciones URL de Internet. Las direcciones URL de ubicaciones que se encuentran en la intranet pasan por el servidor sin sufrir modificaciones. Sin embargo, las direcciones URL de intranet que atraviesen servidores individuales que ejecuten Lync Server dependen de los tipos de sitios web locales que se consideren parte de su zona de intranet. Para comprobar la configuración de zona de intranet de un servidor, consulte el procedimiento "Para establecer la configuración de intranet en Internet Explorer” en [Modificar el filtro para direcciones URL predeterminado](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrar estos prefijos de hipervínculos**   Para seleccionar los prefijos que desea bloquear, haga clic en **Seleccionar** y en **Seleccionar prefijo de hipervínculos** y agregue los prefijos a la lista **Prefijos de hipervínculos**.
    
    Todos los prefijos, salvo **href**, deben terminar con un punto, un signo de dos puntos o un asterisco seguido de un punto. Los prefijos válidos pueden contener cualquier carácter del juego de caracteres válidos para direcciones URL, salvo el asterisco (\*). El juego de caracteres válidos para direcciones URL es: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~

## Filtrado para transferencia de archivos

El filtro para transferencia afecta tanto a los mensajes instantáneos como a las conferencias. En el caso de las conferencias, esta configuración afecta a la característica de documentos en el cliente de Office Live Meeting 2007 y a las características de reproducción multimedia.


> [!NOTE]
> Lync Server ofrece asimismo opciones de configuración para la transferencia de archivos. Esta opción del servidor se ofrece además de los controles del cliente disponibles en Lync Server.



Puede filtrar transferencias de archivos durante conversaciones de mensajes instantáneos, cuando use la característica de documentos en el cliente de Office Live Meeting 2007, así como las características de reproducción multimedia para todos los tipos de archivo. Puede definir las opciones siguientes para controlar las transferencias de archivos:

  - **Habilitar filtro de archivo**   Esta opción permite el filtrado de archivos para toda la implementación o para el sitio que seleccione.
    
    Al activar el filtro de archivo, puede seleccionar una de las opciones siguientes en **Transferencia de archivos**:
    
      - **Bloquear tipos de archivos específicos**   Especifique qué solicitudes de transferencia de archivos filtrará el servidor mediante una lista de las extensiones de archivo que se deben bloquear. Las entradas de la lista pueden contener todos los caracteres estándar, salvo el carácter comodín (\*). En el cliente de Office Live Meeting 2007, la característica de documentos está habilitada, pero no se podrán cargar ni descargar los archivos que tengan estas extensiones. Si activa la casilla **Bloquear direcciones URL con extensión de archivo** en la configuración de un filtro de direcciones URL de la ficha **Filtro para direcciones URL**, el filtro para direcciones URL usa la misma lista para bloquear hipervínculos activos que contengan cualquiera de esas extensiones de archivo. Para seleccionar los tipos de archivo que desea bloquear, haga clic en **Seleccionar** y, en **Seleccionar tipo de archivo**, agregue las extensiones de tipo de archivo a la lista **Extensiones de tipo de archivo seleccionadas**.
    
      - **Bloquear todo**   El servidor quita todos los mensajes instantáneos que incluyan solicitudes de transferencia de archivos y envía un mensaje de error al remitente de la solicitud. Se deshabilita la característica de documentos en el cliente de Office Live Meeting 2007.

> [!IMPORTANT]  
> El filtrado de las extensiones de archivo se limita a los nombres de archivo estándar. Puede que el filtrado no funcione con las extensiones de archivo insertadas en otros nombres.



## En esta sección

  - [Modificar el filtro de transferencia de archivos predeterminado](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Crear un filtro de transferencia de archivos nuevo para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificar el filtro para direcciones URL predeterminado](lync-server-2013-modify-the-default-url-filter.md)

  - [Crear un filtro nuevo para direcciones URL para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

## Vea también

#### Otros recursos

[Administrar la configuración de mensajería instantánea y de presencia en Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)

