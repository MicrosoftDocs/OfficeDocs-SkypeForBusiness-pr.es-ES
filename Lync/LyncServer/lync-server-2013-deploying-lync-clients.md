---
title: 'Lync Server 2013: implementación de clientes de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbbecc50ed88ac9b3237277ba1c991f8c1fcba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="f0213-102">Implementar clientes de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0213-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f0213-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f0213-104">Lync 2013 presenta un enfoque diferente para la implementación de clientes.</span><span class="sxs-lookup"><span data-stu-id="f0213-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="f0213-105">En una salida de versiones anteriores, Lync 2013 ya no tiene su propio instalador.</span><span class="sxs-lookup"><span data-stu-id="f0213-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="f0213-106">En su lugar, Lync se incluye con el programa de instalación de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="f0213-107">Para implementar Lync 2013 para los usuarios, puede usar los métodos de instalación y las herramientas de personalización de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="f0213-108">**Office 2013 Windows Installer** es un paquete de instalación basado en Windows Installer que consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="f0213-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="f0213-109">Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo.</span><span class="sxs-lookup"><span data-stu-id="f0213-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="f0213-110">La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f0213-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="f0213-111">En los temas de esta sección se describe cómo usar y personalizar Office 2013 Windows Installer para implementar Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="f0213-112">**Office 2013 hacer clic y ejecutar** es un programa de instalación que transmite los archivos de instalación de Office al usuario desde el portal de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0213-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="f0213-113">Los administradores pueden personalizar la instalación con la Herramienta de implementación de Office para Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f0213-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="f0213-114">Dado que Office 2013 hacer clic y ejecutar se usa principalmente en el entorno de Microsoft Office 365, este método de instalación no se describe detalladamente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f0213-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="f0213-115">Encontrará información detallada sobre el uso y la personalización de la instalación de hacer clic y ejecutar en la documentación del kit de recursos de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="f0213-116">Los administradores también pueden descargar el programa de Office 2013 hacer clic y ejecutar y los archivos de origen del idioma a una ubicación local, lo cual es útil cuando desea minimizar la demanda de la red o impedir que los usuarios instalen software de Internet debido a requisitos de seguridad corporativas.</span><span class="sxs-lookup"><span data-stu-id="f0213-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="f0213-117">Los temas de esta sección se centran en cómo implementar clientes con el instalador de Office 2013 basado en MSI.</span><span class="sxs-lookup"><span data-stu-id="f0213-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="f0213-118">La referencia principal debe ser la documentación del kit de recursos de Office 2013, que describe detalladamente cómo preparar su infraestructura, personalizar la instalación e implementar Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="f0213-119">Sin embargo, debería usar la documentación de Office junto con los temas de esta sección, que destacan las consideraciones de implementación específicas de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f0213-120">El complemento de reunión en línea para Lync 2013, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f0213-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="f0213-121">El programa de instalación de Office 2013 no desinstala versiones anteriores de Lync u Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="f0213-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="f0213-122">El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</span><span class="sxs-lookup"><span data-stu-id="f0213-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0213-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f0213-123">In This Section</span></span>

  - [<span data-ttu-id="f0213-124">Personalizar la instalación del cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="f0213-125">Personalizar el comportamiento de Lync y la interfaz de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="f0213-126">Personalizar el complemento de reunión en línea en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="f0213-127">Configuración de la página de participación en reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="f0213-128">Configuración de las versiones de cliente compatibles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="f0213-129">Configuración del modo de privacidad de presencia mejorada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0213-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

