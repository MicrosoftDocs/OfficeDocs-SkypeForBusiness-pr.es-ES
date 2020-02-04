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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Shell de administración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-09-20_

<div>


> [!NOTE]  
> La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com. Al hacer clic en los vínculos siguientes te llevará a la nueva página de docs.microsoft.com. El contenido ahora está abierto y disponible para las contribuciones de la comunidad a través de GitHub. ¿Está interesado en colaborar? Consulte el archivo Léame en el repositorio aquí:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 presentó un gran conjunto de características nuevas y mejoradas en comparación con lo que estaba disponible en Microsoft Office Communications Server 2007 R2. Una mejora es la manera en la que administra su implementación. Por ejemplo, hay una nueva interfaz de usuario, llamada panel de control de Lync Server, que representa un gran turno desde donde se usan la mayoría de los usuarios con Microsoft Management Console. La otra mejora importante de la capacidad de administración es la inclusión de Windows PowerShell.

Windows PowerShell le permite administrar aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Windows PowerShell se presentó por primera vez como una versión descargable para el sistema operativo Windows en 2006, y se incorporó como la interfaz de línea de comandos para la capacidad de administración de Microsoft Exchange Server 2007. A partir de ese punto, continuará creciendo y se ha incorporado a la mayoría de los productos de servidor de Microsoft, el más reciente de ellos es Microsoft Lync Server 2013. Lync Server 2010 ha introducido cmdlets específicos de producto de 550 que puede usar para administrar todos los aspectos de su implementación.

Las secciones siguientes contienen una lista de los cmdlets y sus descripciones. Esta información también se encuentra disponible directamente en la línea de comandos. Simplemente escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:

    Get-Help <cmdlet name> -Full

Por ejemplo, para obtener ayuda en el símbolo del sistema sobre el cmdlet **New-CsVoicePolicy**, escriba lo siguiente:

    Get-Help New-CsVoicePolicy -Full

Cosas que debe saber sobre Windows PowerShell en Lync Server 2013:

  - Para ejecutar los cmdlets de Lync Server, abra el shell de administración de Lync Server.
    
    <div>
    

    > [!WARNING]  
    > Si abre una ventana de Windows PowerShell en lugar del shell de administración de Lync Server, de forma predeterminada, no podrá ejecutar los cmdlets de Lync Server. Para ejecutar los cmdlets de Lync Server desde Windows PowerShell, en primer lugar escriba lo siguiente en el símbolo del sistema de Windows PowerShell:<BR>Importación: módulo de Lync

    
    </div>

  - El shell de administración de Lync Server se instala automáticamente en todos los servidores front-end de Lync Server Enterprise Edition o en el servidor Standard Edition.

  - La información nueva y actualizada, los scripts de ejemplo y la ayuda para comenzar y aprender más acerca de los cmdlets de Windows PowerShell y Microsoft Lync Server 2013 está disponible en [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)el blog de Windows PowerShell de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

