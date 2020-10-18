---
title: 'Lync Server 2013: instalar las herramientas administrativas de Lync Server'
description: 'Lync Server 2013: instalar las herramientas administrativas de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1ad96299197c3339d06c4f094784edc632e6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574176"
---
# <a name="install-lync-server-2013-administrative-tools"></a>Instalación de las herramientas administrativas de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En este tema se describe cómo instalar las herramientas administrativas que necesita usar para implementar y administrar Lync Server 2013. Las herramientas administrativas se instalan de forma predeterminada en todos los servidores que ejecutan Lync Server 2013. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Se recomienda instalar las herramientas administrativas en un equipo que se encuentre en el mismo dominio o bosque que la implementación de Lync Server 2013 que está creando porque, al hacerlo, se asegura de que ya se hayan completado los pasos de preparación de los servicios de dominio de Active Directory, lo que le permite usar las herramientas administrativas en ese equipo más adelante para publicar la topología.

Asegúrese de revisar los requisitos de la infraestructura, el sistema operativo, el software y los derechos de administrador antes de instalar o usar las herramientas administrativas de Lync Server 2013. Para obtener más información acerca de los requisitos de infraestructura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server 2013, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [compatibilidad con servidores y requisitos adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Para obtener más información sobre los derechos de usuario y los permisos necesarios para instalar y usar las herramientas, consulte [derechos de administrador y permisos necesarios para la instalación y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Si su organización necesita que ubique Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, debe cambiar la ruta de acceso a la ubicación de instalación de los archivos de Lync Server en el cuadro de diálogo de instalación. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, también se implementará el resto de los archivos de Lync Server 2013 en esta unidad.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Para instalar las herramientas administrativas de Lync Server 2013

1.  Inicie sesión como administrador local (requisito mínimo) en el equipo donde desee instalar las herramientas administrativas. Si ha iniciado la sesión como usuario estándar en los sistemas operativos Windows Vista o Windows 7 y está habilitado el control de cuenta de usuarios (UAC), se le pedirá que indique el administrador local o un nombre de usuario equivalente del dominio y una contraseña.

2.  Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \\ configuración \\ AMD64 \\Setup.exe.

3.  Si se le pide que instale Microsoft Visual C++ 2008 distribuible, haga clic en **Sí**.

4.  En la página **Ubicación de instalación de Microsoft Lync Server 2013** , haga clic en **Aceptar**. Cambie esta ruta de acceso a otra ubicación o unidad si necesita que los archivos se instalen en una ubicación diferente.
    
    <div>
    

    > [!IMPORTANT]  
    > Si su organización requiere Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.

    
    </div>

5.  En la página **Contrato de licencia para el usuario final**, revise los términos de la licencia, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar**. Este paso es necesario para poder continuar

6.  En la página **Microsoft Lync Server 2013 – Asistente para la implementación** , haga clic en **instalar herramientas del administrador**.

7.  Cuando finalice la instalación correctamente, haga clic en **Salir**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

