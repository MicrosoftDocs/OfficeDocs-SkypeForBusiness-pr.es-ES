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
ms.openlocfilehash: c530387fa9f504120ff3a8f38128eeb07b04e615
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527647"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Uso de las opciones de la línea de comandos del programa de instalación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. Normalmente, en vez de usar las opciones de línea de comandos del programa de instalación, utilizará la Herramienta de personalización de Office y el archivo Config.xml para la configuración de productos y personalización de características.

La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.

### <a name="office-setup-command-line-options"></a>Opciones de línea de comandos del programa de instalación de Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción de línea de comandos del programa de instalación</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>Especifica el archivo Config.xml que usa el programa de instalación durante la instalación. Use la opción/config para especificar el archivo de Config.xml que ha personalizado para las instalaciones de Lync 2013, por ejemplo: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Se utiliza con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y hacer cambios en una instalación de Office existente. Por ejemplo, puede usar la opción /modify para agregar o quitar características de Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Ejecuta el programa de instalación desde el equipo del usuario para reparar Lync.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Ejecuta el programa de instalación para quitar Lync desde el equipo del usuario.</p></td>
</tr>
</tbody>
</table>


Para obtener más información sobre el uso de las opciones de la línea de comandos del programa de instalación, consulte <https://go.microsoft.com/fwlink/p/?linkid=267515> .

</div>

<span> </span>

</div>

</div>

</div>

