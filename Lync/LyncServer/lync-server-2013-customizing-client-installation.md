---
title: 'Lync Server 2013: personalizar la instalación del cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd099f5d57174eb02733abd70bb99a91679a1328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="318f9-102">Personalizar la instalación del cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="318f9-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="318f9-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="318f9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="318f9-104">Los administradores de empresa pueden personalizar la instalación de Office 2013 basada en Windows Installer (. msi) con los métodos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="318f9-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="318f9-105">Puesto que ninguna herramienta única ofrece todas las opciones de personalización, es probable que use una combinación de estos métodos en su implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="318f9-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="318f9-106">Como mínimo, puede usar las herramientas descritas en las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="318f9-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="318f9-107">[Usar la herramienta de personalización de Office (Oct) en Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) para personalizar las opciones de configuración y las características de Lync y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="318f9-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="318f9-108">[Uso de config. XML para realizar tareas de instalación en Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="318f9-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="318f9-109">[Usar las opciones de la línea de comandos de configuración de Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) para especificar el archivo config. XML que se debe usar durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="318f9-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="318f9-110">[Configuración de directivas de inicio de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) mediante el complemento de MMC editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="318f9-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="318f9-111">Es posible que quiera configurar más opciones a medida que implemente el conjunto de aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="318f9-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="318f9-112">En los temas de esta sección se ofrece información general sobre estas herramientas de personalización y se describen las consideraciones específicas de Lync.</span><span class="sxs-lookup"><span data-stu-id="318f9-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="318f9-113">También se incluyen vínculos a la ayuda detallada de Office sobre estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="318f9-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

