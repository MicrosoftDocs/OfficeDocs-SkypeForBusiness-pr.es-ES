---
title: Combinar cmdlets de Skype empresarial online con otros cmdlets de Windows PowerShell en
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d0dd6070eb3c69b23f03e56bf542025c221b15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinar cmdlets de Skype empresarial online con otros cmdlets de Windows PowerShell en

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-05_

Al conectarse a Skype empresarial online mediante Windows PowerShell, aproximadamente 40 cmdlets de Skype empresarial online estarán disponibles para su uso. Sin embargo, no está limitado a usar solo esos cmdlets de 40 al administrar Skype empresarial online. Además de los cmdlets de Skype empresarial online, también puede usar otros cmdlets de Windows PowerShell que estén instalados en su equipo. (Al instalar Windows PowerShell 3,0, también se instalan cientos de cmdlets básicos de Windows PowerShell). Sus comandos pueden combinar y asociar los cmdlets de Skype empresarial online y cualquier otro cmdlet disponible en su equipo.

Aunque un curso completo en Windows PowerShell 3,0 va más allá del ámbito de este artículo, aquí se muestran algunos ejemplos que muestran por qué es posible que desee combinar y asociar cmdlets. En primer lugar, ninguno de los cmdlets de Skype empresarial online incluye un comando imprimir, y este comando no se puede encontrar en la consola de Windows PowerShell. ¿Cómo se obtiene una copia impresa de la información que un cmdlet ha recuperado? Una es recuperar la información y, a continuación, enviar esa información al cmdlet **out-Printer** :

    Get-CsTenant | Out-Printer

Como no se incluyen parámetros adicionales, toda la información devuelta por **el cmdlet out-Printer** se imprimirá en la impresora predeterminada.

Del mismo modo, ninguno de los cmdlets de Skype empresarial online incluye un parámetro que le permite guardar datos en un archivo. Pero eso es correcto: este comando usa el cmdlet **out-File** para guardar la información devuelta en el archivo de texto\\C\\: registra arrendatarios. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Y este comando usa el cmdlet **Select-Object** para limitar los datos que se devuelven y se muestran en pantalla. En este ejemplo, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) recupera información de todos los usuarios de Skype empresarial online y, a continuación, el cmdlet **Select-Object** se usa para limitar los datos mostrados al valor de identidad del usuario y a su Directiva de archivado:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Como habrá cientos de cmdlets disponibles para su uso en el equipo, es posible que tenga problemas para determinar qué cmdlets son los cmdlets de Skype empresarial online y cuáles no. Para obtener una lista de los cmdlets de Skype empresarial online (y solo de Skype empresarial online), primero debe determinar el nombre del módulo temporal de Windows PowerShell que contiene todos los cmdlets de Skype empresarial online. Para ello, ejecute este comando desde el símbolo del sistema de Windows PowerShell:

    Get-Module

Aparecerá información similar a la siguiente en la pantalla:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

El módulo con el script de ModuleType es el módulo que contiene los cmdlets de Skype empresarial online. Para obtener una lista de esos cmdlets, ejecute el cmdlet **get-command** y use el nombre del módulo de script como el nombre del módulo:

    Get-Command -Module tmp_5astd3uh.m5v

Es posible tener varios módulos con un valor de ModuleType igual a script. En ese caso, puede ejecutar el comando siguiente para averiguar qué módulo incluye el cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

El módulo devuelto para el cmdlet **Get-CsTenant** será el módulo que contiene todos los cmdlets de Skype empresarial online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Vea también


[Una introducción a Windows PowerShell y Skype Empresarial Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

