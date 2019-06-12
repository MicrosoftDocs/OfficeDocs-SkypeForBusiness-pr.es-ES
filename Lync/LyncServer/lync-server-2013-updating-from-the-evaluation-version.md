---
title: 'Lync Server 2013: actualización desde la versión de evaluación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Actualización de la versión de evaluación de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Si ha instalado la versión de evaluación de Microsoft Lync Server 2013, tendrá que actualizar esa instalación en una copia con licencia del software; Esto se debe a que la versión de evaluación vence el 180 días después de su instalación. Sin embargo, no tendrá que desinstalar completamente la versión de evaluación y, a continuación, instalar la versión con licencia. En su lugar, después de haber obtenido una clave de licencia válida, puede actualizar la versión de evaluación de Lync Server 2013 llevando a cabo el siguiente procedimiento en cada equipo que actúe como servidor perimetral, director o servidor de Lync Server. Tenga en cuenta que no es necesario actualizar equipos que lleven a cabo otras funciones de servidor, como un servidor de supervisión o un servidor de archivado.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Actualización desde la versión de evaluación de Microsoft Lync Server 2013

Para actualizar un equipo desde la versión de evaluación de Lync Server 2013 a la versión con licencia del software:

**Actualización desde la versión de evaluación de Microsoft Lync Server 2013**

1.  Inicie sesión en el equipo como administrador local.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Tenga en cuenta que es posible que tenga que especificar la ruta de acceso completa del servidor de archivos. msi. Este archivo puede encontrarse en la carpeta Setup de los archivos de instalación de medios de volumen de Lync Server.

4.  Cuando finalice la instalación, escriba lo siguiente en el símbolo del sistema y, a continuación, presione ENTRAR:
    
        Enable-CsComputer

5.  Repita este procedimiento en cualquier otro servidor front-end, director o servidor perimetral que ejecute una copia de evaluación de Lync Server. Este procedimiento también se debe realizar en los servidores de sucursal que se hayan implementado con los archivos de instalación de Lync Server media.

Si no está seguro de si la versión de evaluación de Lync Server se está ejecutando en un equipo determinado, puede comprobar si ejecuta el siguiente comando desde el shell de administración de Lync Server:

    Get-CsServerVersion

El cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analizará el equipo local y devolverá una de las siguientes opciones:

  - La clave de licencia por volumen de Lync Server se ha instalado en el equipo, lo que significa que no es necesaria ninguna actualización.

  - La clave de licencia de evaluación de Lync Server se ha instalado, lo que significa que debe actualizarse el equipo.

  - Que no se requiere ninguna clave de licencia por volumen en el equipo. La actualización de la versión de evaluación a la versión con licencia solo es necesaria en servidores front-end, directores y servidores perimetrales.

</div>

</div>

<span> </span>

</div>

</div>

</div>

