---
title: 'Lync Server 2013: Shell de administración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc4ab6a9c32a8b060308526fcdb1f1da403a9e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Shell de administración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-09-20_

<div>


> [!NOTE]  
> La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com. Al hacer clic en los siguientes vínculos, se le llevará a la nueva página de docs.microsoft.com. El contenido se encuentra ahora abierto y disponible para contribuciones de la comunidad a través de GitHub. ¿Está interesado en colaborar? Consulte el archivo Léame en el repositorio aquí:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 introdujo un gran conjunto de características nuevas y mejoradas en comparación con lo que estaba disponible en Microsoft Office Communications Server 2007 R2. Una de las mejoras es la manera de administrar la implementación. Por ejemplo, hay una nueva interfaz de usuario, denominada panel de control de Lync Server, que representa un gran cambio de lo que la mayoría de las personas se usan con Microsoft Management Console. La otra mejora importante de la administración es la inclusión de Windows PowerShell.

Windows PowerShell le permite administrar las aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos de producto y un lenguaje de scripting completo. Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows más tarde en 2006 y se incorporó como la interfaz de línea de comandos para la administración de Microsoft Exchange Server 2007. A partir de ese punto, continuó creciendo y se ha incorporado a la mayoría de los productos de servidor de Microsoft, la más reciente es Microsoft Lync Server 2013. Lync Server 2010 presentaba cerca de 550 cmdlets específicos del producto que puede usar para administrar todos los aspectos de la implementación.

Las secciones siguientes contienen una lista de cmdlets y sus descripciones. Esta información también está disponible directamente desde la línea de comandos. Basta con escribir lo siguiente en el símbolo del sistema del shell de administración de Lync Server:

    Get-Help <cmdlet name> -Full

Por ejemplo, para obtener ayuda en el símbolo del sistema sobre el cmdlet **New-CsVoicePolicy**, escriba lo siguiente:

    Get-Help New-CsVoicePolicy -Full

Aspectos que debe conocer sobre Windows PowerShell en Lync Server 2013:

  - Para ejecutar los cmdlets de Lync Server, abra el shell de administración de Lync Server.
    
    <div>
    

    > [!WARNING]  
    > Si abre una ventana de Windows PowerShell en lugar del shell de administración de Lync Server, de forma predeterminada, no podrá ejecutar los cmdlets de Lync Server. Para ejecutar los cmdlets de Lync Server desde dentro de Windows PowerShell, primero escriba lo siguiente en el símbolo del sistema de Windows PowerShell:<BR>Import-Module Lync

    
    </div>

  - El shell de administración de Lync Server se instala automáticamente en cada servidor front-end de Lync Server Enterprise Edition o servidor Standard Edition.

  - La información nueva y actualizada, los scripts de ejemplo y la ayuda para empezar y aprender más acerca de Windows PowerShell y los cmdlets de 2013 de Microsoft Lync Server están disponibles [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)en el blog de Lync Server Windows PowerShell.

</div>

<span> </span>

</div>

</div>

</div>

