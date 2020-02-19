---
title: 'Lync Server 2013: componentes usados por el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6cf167917dc7d72484eb0fa833a688b0b4e4b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="86f90-102">Componentes usados por el grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86f90-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86f90-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="86f90-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="86f90-104">La aplicación de grupo de respuesta se habilita automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="86f90-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="86f90-105">En esta sección se describen los componentes que admiten la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86f90-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="86f90-106">Componentes del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="86f90-106">Response Group Components</span></span>

<span data-ttu-id="86f90-107">Los siguientes componentes de Microsoft Lync Server 2013 admiten la aplicación grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="86f90-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="86f90-108">\*\*\*\*   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86f90-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="86f90-109">El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86f90-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="86f90-110">**Aplicación de grupo de respuesta**   la aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="86f90-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="86f90-111">Se incluye automáticamente al implementar el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86f90-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="86f90-112">La aplicación de grupo de respuesta enruta y pone en cola las llamadas entrantes a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="86f90-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="86f90-113">**Paquete de idioma**   se requiere un paquete de idioma para admitir el texto a voz y el reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="86f90-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="86f90-114">Estas tecnologías de voz se usan cuando se configuran los mensajes, como el mensaje de bienvenida y otros mensajes, y se responde a las preguntas y respuestas interactivas de respuesta de voz (IVR).</span><span class="sxs-lookup"><span data-stu-id="86f90-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="86f90-115">De forma predeterminada, los 26 paquetes de idioma admitidos se instalan al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86f90-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="86f90-116">**Archivos de audio**   los archivos de audio se usan para los mensajes y la música en espera.</span><span class="sxs-lookup"><span data-stu-id="86f90-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="86f90-117">\*\*\*\*   El grupo de respuesta del almacén de archivos usa el almacén de archivos para almacenar los archivos de audio.</span><span class="sxs-lookup"><span data-stu-id="86f90-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="86f90-118">Varios grupos de grupos de respuesta pueden usar la misma instancia del almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="86f90-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="86f90-119">**Herramienta de configuración**   de grupos de respuesta la herramienta de configuración de grupos de respuesta es una herramienta basada en Web que se usa para crear y configurar grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86f90-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="86f90-120">La herramienta de configuración de grupos de respuesta se incluye al instalar los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="86f90-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="86f90-121">**Panel de control de Microsoft Lync Server 2013**   puede usar el panel de control de Lync Server para instalar y configurar grupos de agentes y colas para grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86f90-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="86f90-122">**Shell de administración de Lync Server**   toda la configuración del grupo de respuesta se puede configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86f90-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="86f90-123">**Microsoft Lync 2013**   : agentes formales (agentes que son necesarios para iniciar sesión en el grupo antes de que puedan aceptar llamadas para el grupo) Use Lync 2013 para iniciar sesión en el grupo y cerrarla.</span><span class="sxs-lookup"><span data-stu-id="86f90-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="86f90-124">Si un grupo de agentes está configurado para los agentes formales, los agentes hacen clic en un elemento de menú en Lync 2013 para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="86f90-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="86f90-125">**Servicios web**servicios web es necesario para la herramienta de configuración de grupos de respuesta, la consola de inicio y de cierre de sesión de los agentes, el panel de control de Lync Server y el servicio Web de cliente del grupo de respuesta.   </span><span class="sxs-lookup"><span data-stu-id="86f90-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="86f90-126">\*\*\*\*   La aplicación grupo de respuesta del servicio Web cliente de grupo de respuesta proporciona un servicio Web de cliente, que puede ser utilizado por aplicaciones de terceros para recuperar información sobre agentes, pertenencia a grupos de agentes, estado de inicio de sesión de agentes, estado de llamadas para grupos y grupos que admiten llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="86f90-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="86f90-127">Lync 2013 y el operador de Lync 2010 usan el servicio Web cliente de grupo de respuesta para recuperar la lista de grupos de respuesta que los agentes pueden usar para realizar llamadas anónimas.</span><span class="sxs-lookup"><span data-stu-id="86f90-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="86f90-128">El servicio web de cliente se incluye al instalar los servicios web.</span><span class="sxs-lookup"><span data-stu-id="86f90-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

