---
title: 'Lync Server 2013: Instalar las herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1115d5848806f95d35a158f36b7689967cec5d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Instalar las herramientas administrativas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En este tema se describe cómo instalar las herramientas administrativas que necesita usar para implementar y administrar Lync Server 2013. Las herramientas administrativas se instalan de forma predeterminada en todos los servidores que ejecutan Lync Server 2013. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Le recomendamos encarecidamente que instale las herramientas administrativas en un equipo del mismo dominio o bosque que la implementación de Lync Server 2013 que está creando porque, de esta manera, tendrá que asegurarse de que los pasos de preparación de los servicios de dominio de Active Directory ya están completado, que le permite usar las herramientas administrativas en ese equipo más tarde para publicar su topología.

Asegúrese de revisar los requisitos de los derechos de infraestructura, sistema operativo, software y administrador antes de instalar o usar las herramientas administrativas de Lync Server 2013. Para obtener más información sobre los requisitos de infraestructura, consulte [requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server 2013, consulte [compatibilidad del sistema operativo de servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [Requisitos y compatibilidad de servidor adicionales en Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md). Para obtener más información sobre los derechos de usuario y los permisos necesarios para instalar y usar las herramientas, consulte [derechos y permisos de administrador necesarios para la configuración y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Si su organización requiere que encuentre Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo Configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Para instalar las herramientas administrativas 2013 de Lync Server

1.  Inicie sesión como administrador local (requisito mínimo) en el equipo en el que desea instalar las herramientas administrativas. Si ha iniciado sesión como un usuario estándar en los sistemas operativos Windows Vista o Windows 7, y el control de cuentas de usuario (UAC) está habilitado, se le solicitará el administrador local o un nombre de usuario y una contraseña de dominio equivalente.

2.  Busque los medios de instalación en el equipo y, a continuación, \\haga\\doble\\clic en Setup AMD64 Setup. exe.

3.  Si se le pide que instale el paquete distribuible de Microsoft Visual C++ 2008, haga clic en **sí**.

4.  En la página **Ubicación de instalación de Microsoft Lync Server 2013** , haga clic en **Aceptar**. Cambie esta ruta de acceso a otra ubicación o unidad si necesita tener los archivos instalados en otra ubicación.
    
    <div>
    

    > [!IMPORTANT]  
    > Si su organización requiere que encuentre Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también en esta unidad.

    
    </div>

5.  En la página contrato de licencia para el **usuario final** , revise los términos **** de licencia, haga clic en Acepto y, después, haga clic en **Aceptar**. Este paso es necesario para poder continuar.

6.  En la página **Microsoft Lync Server 2013: Asistente para la implementación** , haga clic en **instalar herramientas del administrador**.

7.  Cuando la instalación finalice correctamente, haga clic en **salir**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

