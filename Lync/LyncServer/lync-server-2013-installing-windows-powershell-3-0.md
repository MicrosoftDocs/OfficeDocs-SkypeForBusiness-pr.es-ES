---
title: 'Lync Server 2013: Instalar Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Instalar Windows PowerShell 3.0 para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-27_

Para implementar Lync Server 2013 correctamente, necesitará Windows PowerShell 3,0 en cada equipo que forme parte de la topología de Lync Server.

Ahora, para sistemas con Windows Server 2012 o Windows Server 2012 R2, no tiene que hacer nada aquí, y puede continuar con la siguiente fase de implementación, porque PowerShell 3,0 se incluye con esos sistemas operativos.

<div>


> [!IMPORTANT]  
> Pero para los sistemas que ejecutan Windows Server 2008 R2 SP1, tendrá que instalar PowerShell 3,0 como requisito previo antes de instalar Lync Server 2013, o lo que no funcionará. Para instalar PowerShell 3,0, vea <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Este es un vínculo directo a la página de descarga de PowerShell 3,0, junto con información relacionada con la instalación correcta.



</div>

Una vez que haya realizado la instalación, o si solo desea comprobar la implementación de Lync Server y asegurarse de que no va a hacerlo, es muy sencillo que confirme que PowerShell 3,0 está en un servidor:

1.  En el servidor que desea comprobar, elija **Inicio**, haga clic en **todos los programas**, en **accesorios**, en **Windows PowerShell**y, por último, en **Windows PowerShell**.

2.  En la consola de Windows PowerShell, escriba el siguiente comando en el símbolo del sistema y, a continuación, presione ENTRAR:
    
        Get-Host | Select-Object Version

3.  Si Windows PowerShell 3,0 está instalado, verá el resultado que tiene el siguiente aspecto:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

