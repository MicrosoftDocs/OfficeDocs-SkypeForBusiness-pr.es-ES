---
title: 'Lync Server 2013: instalación de Windows PowerShell 3,0'
description: 'Lync Server 2013: instalación de Windows PowerShell 3,0.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4605231f4e73f6aada4fb34de895cdeb883d82b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550656"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Instalación de Windows PowerShell 3,0 para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-27_

Para implementar Lync Server 2013 correctamente, necesitará Windows PowerShell 3,0 en cada equipo que forme parte de la topología de Lync Server.

Ahora, para sistemas que ejecutan Windows Server 2012 o Windows Server 2012 R2, no es necesario que haga nada aquí y puede continuar con la siguiente fase de la implementación, ya que PowerShell 3,0 se incluye con esos sistemas operativos.

<div>


> [!IMPORTANT]  
> Pero para los sistemas que ejecutan Windows Server 2008 R2 SP1, tendrá que instalar PowerShell 3,0 como requisito previo antes de instalar Lync Server 2013, o no funcionará nada. Para instalar PowerShell 3,0, vea <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Se trata de un vínculo directo a la página de descarga de PowerShell 3,0, junto con información relacionada con la instalación correcta.



</div>

Una vez que haya realizado la instalación, o si solo quiere comprobar y está seguro antes de continuar con la implementación de Lync Server, la confirmación de que PowerShell 3,0 está en un servidor es bastante sencillo si hace lo siguiente:

1.  En el servidor que desea comprobar, elija **Inicio**, **todos los programas**, **accesorios**, **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.

2.  En la consola de Windows PowerShell, escriba el siguiente comando en el símbolo del sistema y, a continuación, presione ENTRAR:
    
        Get-Host | Select-Object Version

3.  Si Windows PowerShell 3,0 está instalado, verá un resultado similar al siguiente:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

