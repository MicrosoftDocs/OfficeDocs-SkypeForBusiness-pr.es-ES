---
title: 'Lync Server 2013: Requisitos de software para herramientas administrativas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Requisitos de software para herramientas administrativas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

En este tema se describe el software necesario para instalar y usar las herramientas administrativas 2013 de Lync Server, además de los requisitos del sistema operativo.

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

La edición de 64 bits de Microsoft .NET Framework 4,5 es necesaria para Lync Server 2013.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Para ejecutar cualquier componente de Microsoft Lync Server 2013 se necesita Windows PowerShell 3,0. Para obtener más información, consulte [instalar Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer versión 4,5

Lync Server 2013 usa la tecnología Windows Installer para instalar, desinstalar y mantener diversos roles de servidor. Windows Installer versión 4,5 está disponible como un componente redistribuible para el sistema operativo Windows Server. Windows Installer 4,5 se incluye con Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2, lo que significa que no necesita descargar la utilidad de ningún equipo que ejecute Lync Server 2013. (Lync Server 2013 solo se puede instalar en equipos que ejecuten Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2).

Sin embargo, si desea instalar el shell de administración de Lync Server o el generador de topología de Lync Server en una estación de trabajo de administrador, es posible que tenga que descargar Windows Installer 4,5. Esa utilidad se suministra con Windows 7 y Windows 2008 R2, pero no con las versiones anteriores del sistema operativo Windows. Puede descargar Windows Installer 4,5 desde el centro de descarga de Microsoft <http://go.microsoft.com/fwlink/p/?linkid=197395>en.

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Complemento del explorador Microsoft Silverlight 5

El panel de control de Lync Server 2013 es una herramienta basada en Web y requiere que instale la última versión del complemento del explorador Microsoft Silverlight 5. Al iniciar el panel de control de Lync Server 2013, si este software no está instalado o si se ha instalado una versión anterior, Lync Server 2013 panel de control le pedirá que instale la versión requerida.

</div>

<div>

## <a name="see-also"></a>Vea también


[Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

