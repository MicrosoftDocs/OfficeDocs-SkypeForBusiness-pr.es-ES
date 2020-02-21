---
title: Combinar los cmdlets de Skype empresarial online con otros cmdlets de Windows PowerShell en
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
ms.openlocfilehash: f95d242ec5a1f24f403e59b49e305d9e0a6c84b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinar los cmdlets de Skype empresarial online con otros cmdlets de Windows PowerShell en

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-05_

Al conectarse a Skype empresarial online mediante Windows PowerShell, aproximadamente 40 cmdlets de Skype empresarial online estarán disponibles para su uso. Sin embargo, no está limitado a usar solo esos cmdlets 40 al administrar Skype empresarial online. Además de los cmdlets de Skype empresarial online, también puede usar otros cmdlets de Windows PowerShell que estén instalados en el equipo. (Al instalar Windows PowerShell 3,0, también se instalan cientos de cmdlets de Windows PowerShell principales). Los comandos pueden combinar y hacer coincidir los cmdlets de Skype empresarial online y cualquier otro cmdlet disponible en el equipo.

Aunque un curso completo de Windows PowerShell 3,0 va más allá del ámbito de este artículo, a continuación se muestran algunos ejemplos que muestran por qué es posible que desee combinar y hacer coincidir los cmdlets. En primer lugar, ninguno de los cmdlets de Skype empresarial online incluye un comando Print y no se puede encontrar dicho comando en la consola de Windows PowerShell. ¿Cómo se obtiene una copia impresa de la información recuperada por un cmdlet? Una forma de hacerlo es recuperar la información y enviarla al cmdlet **out-Printer** :

    Get-CsTenant | Out-Printer

Como no se incluye ningún parámetro adicional, toda la información devuelta por **el cmdlet out-Printer** se imprimirá en la impresora predeterminada.

De forma similar, ninguno de los cmdlets de Skype empresarial online incluye un parámetro que permite guardar datos en un archivo. Pero esto es correcto: este comando usa el cmdlet **out-File** para guardar la información devuelta en el archivo de texto\\C\\: logs Tenants. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Y este comando usa el cmdlet **Select-Object** para limitar los datos que se devuelven y que se muestran en la pantalla. En este ejemplo, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) recupera información de todos los usuarios de Skype empresarial online y, a continuación, el cmdlet **Select-Object** se usa para limitar los datos que se muestran al valor de identidad del usuario y a su Directiva de archivado:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Como habrá cientos de cmdlets disponibles para su uso en el equipo, es posible que tenga dificultades para determinar qué cmdlets son los cmdlets de Skype empresarial online y cuáles no. Para obtener una lista de los cmdlets de Skype empresarial online (y solo los cmdlets de Skype empresarial online), primero debe determinar el nombre del módulo temporal de Windows PowerShell que contiene todos los cmdlets de Skype empresarial online. Para ello, ejecute este comando desde el símbolo del sistema de Windows PowerShell:

    Get-Module

La información similar a la siguiente aparecerá en la pantalla:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

El módulo con el script de ModuleType es el módulo que contiene los cmdlets de Skype empresarial online. Para obtener una lista de estos cmdlets, ejecute el cmdlet **get-command** , usando el nombre del módulo de script como el nombre del módulo:

    Get-Command -Module tmp_5astd3uh.m5v

Es posible tener varios módulos con un valor de ModuleType igual a script. En ese caso, puede ejecutar el siguiente comando para averiguar qué módulo incluye el cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

El módulo devuelto para el cmdlet **Get-CsTenant** será el módulo que contiene todos los cmdlets de Skype empresarial online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Consulta también


[Introducción a Windows PowerShell y Skype empresarial online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

