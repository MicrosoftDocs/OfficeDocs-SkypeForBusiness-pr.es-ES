---
title: 'Lync Server 2013: personalización de la instalación del cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da27eed81ea63db059a23baad511471cbe31cfe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="5429b-102">Personalización de la instalación del cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5429b-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5429b-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5429b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5429b-104">Los administradores de la empresa pueden personalizar la instalación de Office 2013 basada en Windows Installer (. msi) mediante los métodos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="5429b-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="5429b-105">Debido a que ninguna herramienta única proporciona todas las opciones de personalización, es probable que use una combinación de estos métodos en su implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5429b-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="5429b-106">Como mínimo, puede usar las herramientas que se describen en las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="5429b-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="5429b-107">[Uso de la herramienta de personalización de Office (Oct) en Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) para personalizar las opciones de instalación y las características de Lync y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="5429b-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="5429b-108">[Uso de config. XML para realizar tareas de instalación en Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="5429b-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="5429b-109">[Uso de las opciones de la línea de comandos del programa de instalación en Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) para especificar el archivo config. XML que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="5429b-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="5429b-110">[Configuración de directivas de arranque de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) mediante el complemento MMC del editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="5429b-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="5429b-111">Probablemente habrá otras opciones que querrá configurar al implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="5429b-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="5429b-112">En los temas de esta sección se ofrece información general sobre estas herramientas de personalización y se describen las consideraciones específicas de Lync.</span><span class="sxs-lookup"><span data-stu-id="5429b-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="5429b-113">Se incluyen vínculos a la ayuda detallada de Office para cada herramienta.</span><span class="sxs-lookup"><span data-stu-id="5429b-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

