---
title: 'Lync Server 2013: implementación de clientes de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fa0bae9909015ca8cefe52cc09dabbe7a4419b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="a5318-102">Implementar clientes de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5318-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a5318-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a5318-104">Lync 2013 presenta un enfoque diferente para la implementación de clientes.</span><span class="sxs-lookup"><span data-stu-id="a5318-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="a5318-105">En una salida de versiones anteriores, Lync 2013 ya no tiene su propio instalador.</span><span class="sxs-lookup"><span data-stu-id="a5318-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="a5318-106">En su lugar, Lync se incluye con el programa de instalación de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="a5318-107">Para implementar Lync 2013 para sus usuarios, puede usar los métodos de instalación y las herramientas de personalización de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="a5318-108">**Office 2013 Windows Installer** es un paquete de instalación basado en Windows Installer que consta de varios archivos MSI.</span><span class="sxs-lookup"><span data-stu-id="a5318-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="a5318-109">Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo.</span><span class="sxs-lookup"><span data-stu-id="a5318-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="a5318-110">La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a5318-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="a5318-111">En los temas de esta sección se describe cómo usar y personalizar el Office 2013 Windows Installer para implementar Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="a5318-112">**Office 2013 hacer clic y ejecutar** es un programa de instalación que transmite los archivos de instalación de Office al usuario desde el portal de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5318-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="a5318-113">Los administradores pueden personalizar la instalación utilizando la herramienta de implementación de Office para Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="a5318-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="a5318-114">Como Office 2013 hacer clic y ejecutar se usa principalmente en el entorno de Microsoft Office 365, este método de instalación no se describe en detalle en esta sección.</span><span class="sxs-lookup"><span data-stu-id="a5318-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="a5318-115">Encontrará información detallada sobre cómo usar y personalizar la instalación de hacer clic y ejecutar en la documentación del kit de recursos de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="a5318-116">Los administradores también pueden descargar los archivos de origen de idioma y programa de hacer clic y ejecutar de Office 2013 en una ubicación local, lo que resulta útil cuando se desea minimizar la demanda en la red o impedir que los usuarios instalen software desde Internet debido a requisitos de seguridad corporativos.</span><span class="sxs-lookup"><span data-stu-id="a5318-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="a5318-117">Los temas de esta sección se centran en cómo implementar clientes mediante el instalador basado en MSI de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="a5318-118">La referencia principal debe ser la documentación del kit de recursos de Office 2013, que describe detalladamente cómo preparar la infraestructura, personalizar la instalación e implementar Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="a5318-119">Sin embargo, debe usar la documentación de Office junto con los temas de esta sección, que indican las consideraciones de implementación específicas de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="a5318-120">El complemento para reunión en línea para Lync 2013, que admite la administración de reuniones desde el cliente de colaboración y mensajería de Outlook, se instala automáticamente con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a5318-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="a5318-121">El programa de instalación de Office 2013 no desinstala versiones anteriores de Lync u Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="a5318-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="a5318-122">El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</span><span class="sxs-lookup"><span data-stu-id="a5318-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5318-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a5318-123">In This Section</span></span>

  - [<span data-ttu-id="a5318-124">Personalización de la instalación del cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="a5318-125">Personalización del comportamiento de Lync y la interfaz de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="a5318-126">Personalización del complemento para reunión en línea en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="a5318-127">Configuración de la página de participación en la reunión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="a5318-128">Configuración de versiones de cliente admitidas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="a5318-129">Configurar el modo de privacidad de presencia mejorada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5318-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

