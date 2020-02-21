---
title: 'Lync Server 2013: usar las opciones de la línea de comandos del programa de instalación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c181c16e5480d1dc7659ed3778faf738eed70949
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="e3fe9-102">Uso de las opciones de la línea de comandos del programa de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3fe9-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3fe9-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e3fe9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e3fe9-p101">La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. Normalmente, en vez de usar las opciones de línea de comandos del programa de instalación, utilizará la Herramienta de personalización de Office y el archivo Config.xml para la configuración de productos y personalización de características.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="e3fe9-106">La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="e3fe9-107">Opciones de línea de comandos del programa de instalación de Office</span><span class="sxs-lookup"><span data-stu-id="e3fe9-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3fe9-108">Opción de línea de comandos del programa de instalación</span><span class="sxs-lookup"><span data-stu-id="e3fe9-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="e3fe9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3fe9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3fe9-110">/admin</span><span class="sxs-lookup"><span data-stu-id="e3fe9-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="e3fe9-111">Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</span><span class="sxs-lookup"><span data-stu-id="e3fe9-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3fe9-112">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="e3fe9-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="e3fe9-p102">Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3fe9-115">/config [path]</span><span class="sxs-lookup"><span data-stu-id="e3fe9-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="e3fe9-116">Especifica el archivo Config.xml que usa el programa de instalación durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="e3fe9-117">Use la opción/config para especificar el archivo config. XML que ha personalizado para las instalaciones de Lync 2013, por ejemplo:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="e3fe9-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3fe9-118">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="e3fe9-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="e3fe9-p104">Se utiliza con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y hacer cambios en una instalación de Office existente. Por ejemplo, puede usar la opción /modify para agregar o quitar características de Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-p104">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation. For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3fe9-121">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="e3fe9-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="e3fe9-122">Ejecuta el programa de instalación desde el equipo del usuario para reparar Lync.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3fe9-123">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="e3fe9-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="e3fe9-124">Ejecuta el programa de instalación para quitar Lync desde el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3fe9-125">Para obtener más información sobre el uso de las opciones de la <https://go.microsoft.com/fwlink/p/?linkid=267515>línea de comandos del programa de instalación, consulte.</span><span class="sxs-lookup"><span data-stu-id="e3fe9-125">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

