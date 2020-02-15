---
title: 'Lync Server 2013: actualización desde la versión de evaluación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Actualización de la versión de evaluación de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Si ha instalado la versión de evaluación de Microsoft Lync Server 2013, tendrá que actualizar esa instalación a una copia con licencia del software; Esto se debe a que la versión de evaluación expira a los 180 días después de su instalación. Sin embargo, no tendrá que desinstalar completamente la versión de evaluación y, a continuación, instalar la versión con licencia. En su lugar, después de obtener una clave de licencia válida, puede actualizar la versión de evaluación de Lync Server 2013 llevando a cabo el siguiente procedimiento en cada equipo que actúe como servidor front-end de Lync Server, director o servidor perimetral. Tenga en cuenta que no es necesario actualizar los equipos que llevan a cabo otras funciones de servidor, como un servidor de supervisión o un servidor de archivado.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Actualización de la versión de evaluación de Microsoft Lync Server 2013

Para actualizar un equipo desde la versión de evaluación de Lync Server 2013 a la versión con licencia del software:

**Actualización de la versión de evaluación de Microsoft Lync Server 2013**

1.  Inicie sesión en el equipo como administrador local.

2.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Shell de administración de Lync Server**.

3.  En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Tenga en cuenta que puede que tenga que especificar la ruta completa del archivo server.msi. Este archivo puede encontrarse en la carpeta Setup de los archivos de instalación de medios de volumen de Lync Server.

4.  Cuando termine de ejecutarse la instalación, escriba lo siguiente desde el símbolo del sistema y, a continuación, pulse ENTRAR:
    
        Enable-CsComputer

5.  Repita este procedimiento en cualquier otro servidor front-end, director o servidor perimetral que ejecute una copia de evaluación de Lync Server. Este procedimiento también debe realizarse en cualquier servidor de sucursal que se haya implementado mediante los archivos de instalación de medios de Lync Server.

Si no está seguro de si la versión de evaluación de Lync Server se está ejecutando en un equipo determinado, puede comprobar si ejecuta el siguiente comando desde el shell de administración de Lync Server:

    Get-CsServerVersion

El cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analizará el equipo local y devolverá una de las siguientes opciones:

  - Que la clave de licencia por volumen de Lync Server se ha instalado en el equipo, lo que significa que no es necesaria ninguna actualización.

  - Que se ha instalado la clave de licencia de evaluación de Lync Server, lo que significa que el equipo debe actualizarse.

  - Que no es necesaria ninguna clave de licencia por volumen en el equipo. La actualización de la versión de evaluación a la versión con licencia solo es necesaria en los servidores front-end, directores y servidores perimetrales.

</div>

</div>

<span> </span>

</div>

</div>

</div>

