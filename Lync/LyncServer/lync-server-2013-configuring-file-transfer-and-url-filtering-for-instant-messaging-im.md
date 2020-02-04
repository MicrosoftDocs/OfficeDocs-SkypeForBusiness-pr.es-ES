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

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="9597c-102">Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9597c-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9597c-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9597c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9597c-104">La herramienta filtro inteligente de mensajes instantáneos ayuda a proteger la implementación de Lync Server 2013 contra la propagación de las formas más comunes de virus con una degradación mínima para la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="9597c-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="9597c-105">Use el filtro inteligente de mi para configurar filtros para bloquear mensajes instantáneos no solicitados o potencialmente dañinos de puntos de conexión desconocidos fuera del firewall de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9597c-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="9597c-106">Para configurar filtros, especifique los criterios que se van a usar para determinar qué se debe bloquear, por ejemplo, los mensajes instantáneos que contengan hipervínculos con determinados prefijos y archivos con extensiones específicas.</span><span class="sxs-lookup"><span data-stu-id="9597c-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="9597c-107">El filtro inteligente de mensajes instantáneos proporciona lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9597c-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="9597c-108">Filtrado de URL mejorado.</span><span class="sxs-lookup"><span data-stu-id="9597c-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="9597c-109">Filtrado mejorado de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="9597c-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="9597c-110">La configuración del filtro inteligente de mensajes instantáneos incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9597c-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="9597c-111">Configuración del filtrado de URL.</span><span class="sxs-lookup"><span data-stu-id="9597c-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="9597c-112">Configuración del filtrado de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="9597c-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="9597c-113">Cómo se aplican las opciones de filtrado a los mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="9597c-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="9597c-114">Antes de implementar la herramienta inteligente de filtro de mensajes de mensajería instantánea, debe comprender cómo se aplican las opciones de filtrado a medida que los mensajes se dirigen desde un servidor de Lync Server 2013 a otro.</span><span class="sxs-lookup"><span data-stu-id="9597c-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="9597c-115">La manera en que se aplican estas opciones de filtrado es coherente, independientemente de si los servidores se encuentran en una sola organización o en los límites de la organización.</span><span class="sxs-lookup"><span data-stu-id="9597c-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="9597c-116">Esta coherencia se aplica a la forma en que el aviso personalizado y los mensajes de advertencia se insertan en mensajes y se envían por servidores.</span><span class="sxs-lookup"><span data-stu-id="9597c-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9597c-117">El filtro de mensajes instantáneos aumenta la cantidad de recursos de CPU necesarios para procesar las direcciones URL en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="9597c-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="9597c-118">Este aumento en la demanda de la CPU también afecta al rendimiento de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9597c-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="9597c-119">Si usa la página **filtro de URL** en el grupo **presencia y mi** en el panel de control de Lync Server, puede bloquear algunos o todos los hipervínculos o configurar una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9597c-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="9597c-120">La advertencia se inserta al principio de un mensaje instantáneo que contiene un hipervínculo cuando se elige la opción **Enviar mensaje de advertencia**en el **Prefijo de hipervínculo** .</span><span class="sxs-lookup"><span data-stu-id="9597c-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="9597c-121">Cuando un mensaje instantáneo viaja de un servidor a otro, se aplican las siguientes directrices generales:</span><span class="sxs-lookup"><span data-stu-id="9597c-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="9597c-122">Si un servidor bloquea un mensaje instantáneo (porque ha seleccionado la casilla de verificación **bloquear direcciones URL con extensión de archivo** en la página **filtro de URL** o porque ha elegido la opción **bloquear hipervínculos del hipervínculo**), se devolverá un mensaje de error al cliente. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9597c-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="9597c-123">Los siguientes servidores no reciben este mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="9597c-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="9597c-124">Si un servidor (Servidor1) agrega una advertencia a un mensaje instantáneo que contiene un hipervínculo activo, un servidor posterior (servidor2) que reciba este mensaje instantáneo aún puede tomar una acción diferente según este hipervínculo activo presente en el mensaje instantáneo y bloquear la envía mensajes instantáneos o agrega una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9597c-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="9597c-125">Si server2 está configurado únicamente para agregar una advertencia para esta dirección URL, se quitará la advertencia anterior agregada por server1 y se agregará la advertencia configurada en server2 al principio del mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="9597c-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9597c-126">Si ejecuta Lync Server 2013 en un entorno mixto, Live Communications Server 2005 con SP1 es la versión mínima requerida para usar la aplicación de filtro inteligente de mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="9597c-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="9597c-127">El filtro inteligente de mensajes instantáneos no es compatible con Live Communications Server 2005 sin SP1.</span><span class="sxs-lookup"><span data-stu-id="9597c-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="9597c-128">Filtrado de URL</span><span class="sxs-lookup"><span data-stu-id="9597c-128">URL Filtering</span></span>

<span data-ttu-id="9597c-129">Las direcciones URL se filtran según su prefijo de hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="9597c-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="9597c-130">Los siguientes ejemplos son prefijos válidos:</span><span class="sxs-lookup"><span data-stu-id="9597c-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="9597c-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="9597c-131">www\*.</span></span>

  - <span data-ttu-id="9597c-132">FTP.</span><span class="sxs-lookup"><span data-stu-id="9597c-132">ftp.</span></span>

  - <span data-ttu-id="9597c-133">Protocolo</span><span class="sxs-lookup"><span data-stu-id="9597c-133">http:</span></span>

<span data-ttu-id="9597c-134">Si no configura el filtro de mensajes instantáneos para realizar el filtrado de URL, todas las direcciones URL incluidas en los mensajes instantáneos se pasan sin modificar a través del servidor.</span><span class="sxs-lookup"><span data-stu-id="9597c-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="9597c-135">Si configura el filtro de mensaje instantáneo para que realice el filtrado de URL, las direcciones URL de los mensajes instantáneos se filtran de acuerdo con las opciones que seleccione en el cuadro de diálogo Editar filtro de **URL** o **nuevo filtro de URL** .</span><span class="sxs-lookup"><span data-stu-id="9597c-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="9597c-136">**Habilitar filtro**   de URL esta opción habilita el filtrado de URL para la implementación global o para el sitio que seleccione.</span><span class="sxs-lookup"><span data-stu-id="9597c-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="9597c-137">**Bloquear direcciones URL con extensión**   de archivo el filtro de mensaje instantáneo bloquea cualquier dirección URL activa de la intranet o de Internet que contenga un archivo con una extensión enumerada en **extensiones de tipo de archivo que se bloquean** en el cuadro de diálogo **Editar filtro de archivos** .</span><span class="sxs-lookup"><span data-stu-id="9597c-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="9597c-138">Cuando se bloquea una dirección URL, se muestra un mensaje de error al remitente.</span><span class="sxs-lookup"><span data-stu-id="9597c-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="9597c-139">Cuando se selecciona, esta opción tiene prioridad sobre todas las demás opciones de filtrado para cualquier extensión de archivo definida en **extensiones de tipo de archivo que se bloquee**.</span><span class="sxs-lookup"><span data-stu-id="9597c-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="9597c-140">El filtrado de extensiones de archivo está limitado a los nombres de archivo estándar.</span><span class="sxs-lookup"><span data-stu-id="9597c-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="9597c-141">Es posible que el filtrado no funcione con las extensiones de archivo incrustadas en otros nombres.</span><span class="sxs-lookup"><span data-stu-id="9597c-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="9597c-142">Para configurar cómo se administran los hipervínculos en las conversaciones de mensajes instantáneos, seleccione una de las siguientes opciones en **Prefijo de hipervínculo**:</span><span class="sxs-lookup"><span data-stu-id="9597c-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="9597c-143">**No filtre**   las direcciones URL de los mensajes que se envían a través del servidor.</span><span class="sxs-lookup"><span data-stu-id="9597c-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="9597c-144">Al elegir esta opción, aparece el cuadro de **mensaje permitir** .</span><span class="sxs-lookup"><span data-stu-id="9597c-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="9597c-145">En el cuadro **permitir mensaje** , especifique el aviso que desea insertar al principio de cada mensaje instantáneo que contenga hipervínculos.</span><span class="sxs-lookup"><span data-stu-id="9597c-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="9597c-146">Este aviso no puede contener más de 65535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9597c-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="9597c-147">**Bloquear hipervínculos**   la entrega de mensajes instantáneos que contienen hipervínculos activos está bloqueada por Lync Server y se muestra un mensaje de error al remitente.</span><span class="sxs-lookup"><span data-stu-id="9597c-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="9597c-148">**Enviar mensaje**   de advertencia Lync Server permite hipervínculos activos en mensajes instantáneos, pero incluye una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9597c-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="9597c-149">Al elegir esta opción, aparece el cuadro de **mensaje de advertencia** .</span><span class="sxs-lookup"><span data-stu-id="9597c-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="9597c-150">En el cuadro de **mensaje de advertencia** , debe escribir la advertencia que desea incluir con los mensajes instantáneos que contengan hipervínculos válidos.</span><span class="sxs-lookup"><span data-stu-id="9597c-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="9597c-151">Por ejemplo, esta advertencia podría indicar los peligros potenciales de hacer clic en un vínculo desconocido o puede hacer referencia a las directivas y requisitos relevantes de su organización.</span><span class="sxs-lookup"><span data-stu-id="9597c-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="9597c-152">La advertencia no puede tener más de 65535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9597c-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="9597c-153">Si selecciona **bloquear hipervínculos** o **Enviar mensaje de advertencia**, las siguientes opciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="9597c-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="9597c-154">**Excluir hipervínculos**   de Intranet local el filtro de mensajes instantáneos bloquea solo direcciones URL de Internet.</span><span class="sxs-lookup"><span data-stu-id="9597c-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="9597c-155">Las direcciones URL de ubicaciones dentro de la intranet se pasan sin modificar a través del servidor.</span><span class="sxs-lookup"><span data-stu-id="9597c-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="9597c-156">Sin embargo, las direcciones URL de intranet a las que pasan los servidores individuales que ejecutan Lync Server dependen de qué tipos de sitios web locales se consideran parte de su zona de intranet.</span><span class="sxs-lookup"><span data-stu-id="9597c-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="9597c-157">Para comprobar la configuración de la zona Intranet de un servidor, consulte el procedimiento "para configurar la configuración de la intranet en Internet Explorer" en [modificar el filtro de URL predeterminado en Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="9597c-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="9597c-158">**Filtre estos prefijos**   de hipervínculo para elegir los prefijos que desea bloquear, haga clic en **seleccionar**y, a continuación, en **seleccionar prefijo de hipervínculo**, agregue los prefijos a la lista de **prefijos de hipervínculos** .</span><span class="sxs-lookup"><span data-stu-id="9597c-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="9597c-159">Todos los prefijos excepto **href** deben finalizar con un punto o un signo de dos puntos, o un asterisco seguido de un punto.</span><span class="sxs-lookup"><span data-stu-id="9597c-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="9597c-160">Los prefijos válidos pueden contener cualquier carácter del conjunto de caracteres de dirección URL válidos excepto el asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="9597c-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="9597c-161">El conjunto de caracteres válidos de URL \# \*es: +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="9597c-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="9597c-162">Filtrado de transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="9597c-162">File Transfer Filtering</span></span>

<span data-ttu-id="9597c-163">Filtrar el filtrado de transferencia afecta tanto a los mensajes instantáneos como a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="9597c-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="9597c-164">Para las conferencias, esta configuración afecta a la característica de documentos de las características de reproducción multimedia y cliente de Office Live Meeting 2007.</span><span class="sxs-lookup"><span data-stu-id="9597c-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9597c-165">Lync Server también ofrece opciones de configuración para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="9597c-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="9597c-166">Esta opción del servidor se ofrece además de los controles del cliente disponibles en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9597c-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="9597c-167">Puede filtrar las transferencias de archivos durante las conversaciones de mensajes instantáneos, cuando use la característica de documentos en el cliente de Office Live Meeting 2007 y las características de reproducción multimedia de todos los tipos de archivo.</span><span class="sxs-lookup"><span data-stu-id="9597c-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="9597c-168">Puede establecer las siguientes opciones para controlar las transferencias de archivos:</span><span class="sxs-lookup"><span data-stu-id="9597c-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="9597c-169">**Habilitar filtro**   de archivos esta opción habilita el filtrado de archivos para la implementación global o para el sitio que seleccione.</span><span class="sxs-lookup"><span data-stu-id="9597c-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="9597c-170">Al habilitar el filtro de archivos, puede elegir una de las siguientes opciones en la **transferencia de archivos**:</span><span class="sxs-lookup"><span data-stu-id="9597c-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="9597c-171">**Bloquear tipos**   de archivo específicos especifique las solicitudes de transferencia de archivos filtradas por el servidor especificando una lista de extensiones de archivo para bloquear.</span><span class="sxs-lookup"><span data-stu-id="9597c-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="9597c-172">Las entradas de la lista pueden contener todos los caracteres estándar, pero no el carácter\*comodín ().</span><span class="sxs-lookup"><span data-stu-id="9597c-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="9597c-173">En el cliente de Office Live Meeting 2007 la característica de documentos está habilitada, pero no se puede cargar ni descargar ningún archivo con esta extensión.</span><span class="sxs-lookup"><span data-stu-id="9597c-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="9597c-174">Si selecciona la casilla de verificación **bloquear direcciones URL con extensión de archivo** en la configuración de un filtro de URL que aparece en la pestaña **filtro de URL** , el filtro de dirección URL usa esta misma lista para bloquear los hipervínculos activos que contienen cualquiera de estas extensiones de archivo.</span><span class="sxs-lookup"><span data-stu-id="9597c-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="9597c-175">Para elegir qué tipos de archivo desea bloquear, haga clic en **seleccionar**y, a continuación, en **Seleccionar tipo de archivo**, agregue las extensiones de tipos de archivo a la lista Extensiones de tipos de **archivo seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="9597c-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="9597c-176">**Bloquear todo**   el servidor elimina todos los mensajes instantáneos que contienen solicitudes de transferencia de archivos y devuelve un mensaje de error al remitente de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9597c-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="9597c-177">La característica de documentos del cliente de Office Live Meeting 2007 está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="9597c-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9597c-178">El filtrado de extensiones de archivo está limitado a los nombres de archivo estándar.</span><span class="sxs-lookup"><span data-stu-id="9597c-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="9597c-179">Es posible que el filtrado no funcione con las extensiones de archivo incrustadas en otros nombres.</span><span class="sxs-lookup"><span data-stu-id="9597c-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9597c-180">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9597c-180">In This Section</span></span>

  - [<span data-ttu-id="9597c-181">Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9597c-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="9597c-182">Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="9597c-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="9597c-183">Modificar el filtro de dirección URL predeterminado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9597c-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="9597c-184">Crear un filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="9597c-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9597c-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="9597c-185">See Also</span></span>


[<span data-ttu-id="9597c-186">Administrar la configuración de mensajería instantánea y de presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9597c-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

