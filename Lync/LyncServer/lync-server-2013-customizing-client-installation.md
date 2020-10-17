---
title: 'Lync Server 2013: personalización de la instalación del cliente'
description: 'Lync Server 2013: personalización de la instalación del cliente.'
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
ms.openlocfilehash: 8dd1942c298ccbc8b6a2950baf4f24cc2f797a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561146"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="5ba39-103">Personalización de la instalación del cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba39-103">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba39-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5ba39-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5ba39-105">Los administradores de la empresa pueden personalizar la instalación de Office 2013 basada en Windows Installer (. msi) mediante los métodos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="5ba39-105">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="5ba39-106">Debido a que ninguna herramienta única proporciona todas las opciones de personalización, es probable que use una combinación de estos métodos en su implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5ba39-106">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="5ba39-107">Como mínimo, puede usar las herramientas que se describen en las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="5ba39-107">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="5ba39-108">[Uso de la herramienta de personalización de Office (Oct) en Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) para personalizar las opciones de instalación y las características de Lync y otros programas de Office.</span><span class="sxs-lookup"><span data-stu-id="5ba39-108">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="5ba39-109">[Uso de Config.xml para realizar tareas de instalación en Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) para especificar la ruta de acceso del punto de instalación de red y realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="5ba39-109">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="5ba39-110">[Uso de opciones de línea de comandos del programa de instalación en Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) para especificar el archivo de Config.xml que se va a usar durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="5ba39-110">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="5ba39-111">[Configuración de directivas de arranque de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) mediante el complemento MMC del editor de objetos de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="5ba39-111">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="5ba39-112">Probablemente habrá otras opciones que querrá configurar al implementar el conjunto de productos de Office.</span><span class="sxs-lookup"><span data-stu-id="5ba39-112">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="5ba39-113">En los temas de esta sección se ofrece información general sobre estas herramientas de personalización y se describen las consideraciones específicas de Lync.</span><span class="sxs-lookup"><span data-stu-id="5ba39-113">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="5ba39-114">Se incluyen vínculos a la ayuda detallada de Office para cada herramienta.</span><span class="sxs-lookup"><span data-stu-id="5ba39-114">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

