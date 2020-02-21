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
ms.openlocfilehash: a0f9968b6154b281126430b87b7ae4ac98aa4b0a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="16eb0-102">Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16eb0-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16eb0-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="16eb0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="16eb0-104">La herramienta filtro inteligente de mensajería instantánea ayuda a proteger la implementación de Lync Server 2013 frente a la propagación de las formas más comunes de virus con una degradación mínima para la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="16eb0-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="16eb0-105">Use el filtro inteligente de mensajería instantánea para configurar filtros que bloqueen los mensajes instantáneos no solicitados o potencialmente dañinos procedentes de extremos desconocidos más allá del firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="16eb0-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="16eb0-106">Los filtros se configuran al especificar los criterios que se van a usar para determinar lo que se va a bloquear, como mensajes instantáneos que contienen hipervínculos con prefijos determinados y archivos con extensiones específicas.</span><span class="sxs-lookup"><span data-stu-id="16eb0-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="16eb0-107">El filtro inteligente de mensajería instantánea ofrece lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16eb0-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="16eb0-108">Filtrado mejorado de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="16eb0-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="16eb0-109">Filtrado mejorado de transferencias de archivos.</span><span class="sxs-lookup"><span data-stu-id="16eb0-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="16eb0-110">La configuración del filtro inteligente de mensajería instantánea incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16eb0-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="16eb0-111">Configuración de filtrado de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="16eb0-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="16eb0-112">Configuración de filtrado de transferencias de archivos.</span><span class="sxs-lookup"><span data-stu-id="16eb0-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="16eb0-113">Cómo se aplican las opciones de filtrado a los mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="16eb0-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="16eb0-114">Antes de implementar la herramienta de filtro inteligente de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado a medida que los mensajes se redirigen desde un servidor de Lync Server 2013 a otro.</span><span class="sxs-lookup"><span data-stu-id="16eb0-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="16eb0-115">Estas opciones de filtrado se aplican de manera coherente, independientemente de si los servidores se encuentran en una sola organización o en varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="16eb0-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="16eb0-116">Esta coherencia se aplica a la forma en que se insertan los avisos y advertencias personalizados en los mensajes y se envían a través de los servidores.</span><span class="sxs-lookup"><span data-stu-id="16eb0-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="16eb0-117">El filtro de mensajes instantáneos aumenta la cantidad de recursos de CPU necesarios para procesar las direcciones URL de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="16eb0-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="16eb0-118">Este aumento de la demanda de la CPU también afecta al rendimiento de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16eb0-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="16eb0-119">Mediante el uso de la página **filtro de URL** en el grupo de **presencia y mensajería instantánea** del panel de control de Lync Server, puede bloquear algunos o todos los hipervínculos o configurar una advertencia.</span><span class="sxs-lookup"><span data-stu-id="16eb0-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="16eb0-120">La advertencia se introduce al comienzo de un mensaje instantáneo que contiene un hipervínculo al seleccionar la opción **Prefijo de hipervínculo\*\*\*\*Enviar mensaje de advertencia**.</span><span class="sxs-lookup"><span data-stu-id="16eb0-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="16eb0-121">Cuando un mensaje instantáneo pasa de un servidor a otro, se aplican las siguientes pautas generales:</span><span class="sxs-lookup"><span data-stu-id="16eb0-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="16eb0-p105">Si un servidor bloquea un mensaje instantáneo (porque ha activado la casilla **Bloquear direcciones URL con extensión de archivo** de la página **Filtro para direcciones URL** o porque ha seleccionado la opción **Prefijo de hipervínculo\*\*\*\*Bloquear hipervínculos**), el cliente recibe un mensaje de error. Los servidores subsiguientes no reciben este mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="16eb0-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="16eb0-p106">Si un servidor (Server1) agrega una advertencia a un mensaje instantáneo que tiene un hipervínculo activo, un servidor subsiguiente (Server2) que reciba este mensaje instantáneo podrá emprender otra acción basándose en este hipervínculo activo presente en el mensaje instantáneo, y bloquear el mensaje o agregar una advertencia. Si Server2 está configurado de modo que solo agregue una advertencia para esta dirección URL, se quitará la advertencia anterior agregada por Server1 y se agregará al comienzo del mensaje instantáneo la advertencia configurada en Server2.</span><span class="sxs-lookup"><span data-stu-id="16eb0-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="16eb0-126">Si ejecuta Lync Server 2013 en un entorno mixto, Live Communications Server 2005 con SP1 es la versión mínima necesaria para usar la aplicación de filtro inteligente de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="16eb0-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="16eb0-127">El filtro inteligente de mensajería instantánea no se puede usar en Live Communications Server 2005 sin SP1.</span><span class="sxs-lookup"><span data-stu-id="16eb0-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="16eb0-128">Filtrado para direcciones URL</span><span class="sxs-lookup"><span data-stu-id="16eb0-128">URL Filtering</span></span>

<span data-ttu-id="16eb0-p108">Las direcciones URL se filtran en función de su prefijo de hipervínculo. A continuación se muestran ejemplos de prefijos válidos:</span><span class="sxs-lookup"><span data-stu-id="16eb0-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="16eb0-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="16eb0-131">www\*.</span></span>

  - <span data-ttu-id="16eb0-132">Protocolo.</span><span class="sxs-lookup"><span data-stu-id="16eb0-132">ftp.</span></span>

  - <span data-ttu-id="16eb0-133">http</span><span class="sxs-lookup"><span data-stu-id="16eb0-133">http:</span></span>

<span data-ttu-id="16eb0-p109">Si no se configura el filtro de mensajería instantánea para que realice algún filtrado de direcciones URL, todas las direcciones URL que aparezcan en mensajes instantáneos pasarán a través del servidor sin sufrir modificaciones. Si configura el filtro de mensajería instantánea para que realice un filtrado de direcciones URL, las URL de los mensajes instantáneos se filtrarán de acuerdo con las opciones que seleccione en el cuadro de diálogo **Editar filtro para direcciones URL** o **Nuevo filtro para direcciones URL**.</span><span class="sxs-lookup"><span data-stu-id="16eb0-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="16eb0-136">**Habilitar filtro**   de dirección URL esta opción permite el filtrado de direcciones URL para la implementación global o para el sitio que seleccione.</span><span class="sxs-lookup"><span data-stu-id="16eb0-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="16eb0-137">**Bloquear direcciones URL con extensión**   de archivo el filtro de mensaje instantáneo bloquea cualquier dirección URL de intranet o Internet activa que contenga un archivo con una extensión enumerada en **extensiones de tipo de archivo que se bloqueen** en el cuadro de diálogo **Editar filtro de archivo** .</span><span class="sxs-lookup"><span data-stu-id="16eb0-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="16eb0-138">Cuando se bloquea una dirección URL, el remitente recibe un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="16eb0-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="16eb0-139">Al seleccionar dicha opción, esta tiene prioridad sobre todas las demás opciones de filtrado para cualquier extensión de archivo definida en **Extensiones de tipo de archivo a bloquear**.</span><span class="sxs-lookup"><span data-stu-id="16eb0-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="16eb0-140">El filtrado de las extensiones de archivo se limita a los nombres de archivo estándar.</span><span class="sxs-lookup"><span data-stu-id="16eb0-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="16eb0-141">Puede que el filtrado no funcione con las extensiones de archivo insertadas en otros nombres.</span><span class="sxs-lookup"><span data-stu-id="16eb0-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="16eb0-142">Para configurar la forma en la que se administran los hipervínculos en las conversaciones de mensajes instantáneos, seleccione una de las siguientes opciones en **Prefijo de hipervínculo**:</span><span class="sxs-lookup"><span data-stu-id="16eb0-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="16eb0-143">**No filtrar**   direcciones URL en los mensajes se envían a través del servidor.</span><span class="sxs-lookup"><span data-stu-id="16eb0-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="16eb0-144">Al seleccionar esta opción se muestra el cuadro **Permitir mensaje**.</span><span class="sxs-lookup"><span data-stu-id="16eb0-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="16eb0-145">En el cuadro **Permitir mensaje**, especifique el aviso que desea insertar al comienzo de cada mensaje instantáneo que contenga hipervínculos.</span><span class="sxs-lookup"><span data-stu-id="16eb0-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="16eb0-146">Este aviso no puede tener más de 65.535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="16eb0-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="16eb0-147">**Bloquear hipervínculos**   la entrega de mensajes instantáneos que contienen hipervínculos activos se bloquea en Lync Server y se muestra un mensaje de error al remitente.</span><span class="sxs-lookup"><span data-stu-id="16eb0-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="16eb0-148">**Enviar mensaje**   de advertencia Lync Server permite hipervínculos activos en mensajes instantáneos, pero incluye una advertencia.</span><span class="sxs-lookup"><span data-stu-id="16eb0-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="16eb0-149">Al seleccionar esta opción, se muestra el cuadro **Mensaje de advertencia**.</span><span class="sxs-lookup"><span data-stu-id="16eb0-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="16eb0-150">En el cuadro **Mensaje de advertencia**, debe escribir la advertencia que desea incluir en los mensajes instantáneos que contengan hipervínculos válidos.</span><span class="sxs-lookup"><span data-stu-id="16eb0-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="16eb0-151">Por ejemplo, esta advertencia podría indicar los posibles riesgos de hacer clic en vínculos desconocidos o hacer referencia a directivas y requisitos relevantes para la organización.</span><span class="sxs-lookup"><span data-stu-id="16eb0-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="16eb0-152">La advertencia no puede tener más de 65.535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="16eb0-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="16eb0-153">Si selecciona **Bloquear hipervínculos** o **Enviar mensaje de advertencia**, puede definir las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="16eb0-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="16eb0-154">**Excluir hipervínculos**   de Intranet local el filtro de mensajes instantáneos bloquea solo direcciones URL de Internet.</span><span class="sxs-lookup"><span data-stu-id="16eb0-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="16eb0-155">Las direcciones URL de ubicaciones que se encuentran en la intranet pasan por el servidor sin sufrir modificaciones.</span><span class="sxs-lookup"><span data-stu-id="16eb0-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="16eb0-156">Sin embargo, las direcciones URL de intranet que los servidores individuales que ejecutan Lync Server dependen de qué tipos de sitios web locales se consideran parte de su zona de intranet.</span><span class="sxs-lookup"><span data-stu-id="16eb0-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="16eb0-157">Para comprobar la configuración de la zona Intranet de un servidor, consulte el procedimiento "para configurar la intranet en Internet Explorer" en [modificar el filtro de direcciones URL predeterminadas en Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="16eb0-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="16eb0-158">**Filtre estos prefijos**   de hipervínculos para elegir los prefijos que desea bloquear, haga clic en **seleccionar**y, a continuación, en **seleccionar prefijo de hipervínculo**, agregue los prefijos a la lista **prefijos de hipervínculos** .</span><span class="sxs-lookup"><span data-stu-id="16eb0-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="16eb0-159">Todos los prefijos, salvo **href**, deben terminar con un punto, un signo de dos puntos o un asterisco seguido de un punto.</span><span class="sxs-lookup"><span data-stu-id="16eb0-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="16eb0-160">Los prefijos válidos pueden contener cualquier carácter del conjunto de caracteres de dirección URL válido\*excepto el asterisco ().</span><span class="sxs-lookup"><span data-stu-id="16eb0-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="16eb0-161">El conjunto de caracteres válidos de dirección \# \*URL es: +/0123456789\_ \` = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="16eb0-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="16eb0-162">Filtrado para transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="16eb0-162">File Transfer Filtering</span></span>

<span data-ttu-id="16eb0-p116">El filtro para transferencia afecta tanto a los mensajes instantáneos como a las conferencias. En el caso de las conferencias, esta configuración afecta a la característica de documentos en el cliente de Office Live Meeting 2007 y a las características de reproducción multimedia.</span><span class="sxs-lookup"><span data-stu-id="16eb0-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="16eb0-165">Lync Server también ofrece opciones de configuración de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="16eb0-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="16eb0-166">Esta opción del lado servidor se ofrece además de los controles de cliente disponibles en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16eb0-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="16eb0-p118">Puede filtrar transferencias de archivos durante conversaciones de mensajes instantáneos, cuando use la característica de documentos en el cliente de Office Live Meeting 2007, así como las características de reproducción multimedia para todos los tipos de archivo. Puede definir las opciones siguientes para controlar las transferencias de archivos:</span><span class="sxs-lookup"><span data-stu-id="16eb0-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="16eb0-169">**Habilitar filtro**   de archivos esta opción habilita el filtrado de archivos para la implementación global o para el sitio que seleccione.</span><span class="sxs-lookup"><span data-stu-id="16eb0-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="16eb0-170">Al activar el filtro de archivo, puede seleccionar una de las opciones siguientes en **Transferencia de archivos**:</span><span class="sxs-lookup"><span data-stu-id="16eb0-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="16eb0-171">**Bloquear tipos**   de archivo específicos especifica qué solicitudes de transferencia de archivos se filtran por el servidor mediante la especificación de una lista de extensiones de archivo que se van a bloquear.</span><span class="sxs-lookup"><span data-stu-id="16eb0-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="16eb0-172">Las entradas de la lista pueden contener todos los caracteres estándar, pero no el carácter\*comodín ().</span><span class="sxs-lookup"><span data-stu-id="16eb0-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="16eb0-173">En el cliente de Office Live Meeting 2007, la característica de documentos está habilitada, pero no se podrán cargar ni descargar los archivos que tengan estas extensiones.</span><span class="sxs-lookup"><span data-stu-id="16eb0-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="16eb0-174">Si activa la casilla **Bloquear direcciones URL con extensión de archivo** en la configuración de un filtro de direcciones URL de la ficha **Filtro para direcciones URL**, el filtro para direcciones URL usa la misma lista para bloquear hipervínculos activos que contengan cualquiera de esas extensiones de archivo.</span><span class="sxs-lookup"><span data-stu-id="16eb0-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="16eb0-175">Para seleccionar los tipos de archivo que desea bloquear, haga clic en **Seleccionar** y, en **Seleccionar tipo de archivo**, agregue las extensiones de tipo de archivo a la lista **Extensiones de tipo de archivo seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="16eb0-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="16eb0-176">**Bloquear todo**   el servidor elimina todos los mensajes instantáneos que contengan solicitudes de transferencia de archivos y devuelve un mensaje de error al remitente de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="16eb0-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="16eb0-177">Se deshabilita la característica de documentos en el cliente de Office Live Meeting 2007.</span><span class="sxs-lookup"><span data-stu-id="16eb0-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="16eb0-p121">El filtrado de las extensiones de archivo se limita a los nombres de archivo estándar. Puede que el filtrado no funcione con las extensiones de archivo insertadas en otros nombres.</span><span class="sxs-lookup"><span data-stu-id="16eb0-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16eb0-180">En esta sección</span><span class="sxs-lookup"><span data-stu-id="16eb0-180">In This Section</span></span>

  - [<span data-ttu-id="16eb0-181">Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16eb0-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="16eb0-182">Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="16eb0-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="16eb0-183">Modificar el filtro de direcciones URL predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16eb0-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="16eb0-184">Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="16eb0-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16eb0-185">Consulta también</span><span class="sxs-lookup"><span data-stu-id="16eb0-185">See Also</span></span>


[<span data-ttu-id="16eb0-186">Administración de la configuración de mensajería instantánea y presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16eb0-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

