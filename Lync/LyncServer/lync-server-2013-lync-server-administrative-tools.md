---
title: 'Lync Server 2013: herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a7567fa467f8e152f4b6a61b06600a127607d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Herramientas administrativas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En este tema se describen las herramientas administrativas para Lync Server 2013.

Las herramientas administrativas se instalan de forma predeterminada en cada servidor de Lync Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Para conocer los procedimientos para instalar las herramientas administrativas, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md). Para ver los procedimientos para abrir las herramientas para realizar tareas de administración, consulte [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

Asegúrese de revisar los requisitos de la infraestructura, el sistema operativo, el software y los derechos de administrador antes de instalar o usar las herramientas administrativas de Lync Server. Para obtener más información acerca de los requisitos de infraestructura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [soporte y requisitos de servidor adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Los derechos de usuario y los permisos necesarios para instalar y usar las herramientas se describen en [derechos de administrador y permisos necesarios para la instalación y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Las herramientas de administración son las siguientes:

  - **El asistente**   para la implementación de Lync Server usa para implementar Lync Server e instalar todas las herramientas administrativas.

  - **El generador**   de topologías de Lync Server se usa para definir componentes en la implementación.

  - ****   Uso del panel de control de Lync Server para la administración continua de la implementación mediante una interfaz basada en Web.

  - **El shell**   de administración de Lync Server se usa para la administración continua de la implementación mediante la línea de comandos.

  - **Herramienta de registro de Lync Server**   Úsela para solucionar problemas de la implementación.

  - **El servicio**   de registro centralizado recopila los registros y los archivos de seguimiento de un equipo, grupo de servidores, sitio o global. Seleccione y defina escenarios que contengan proveedores, marcas y niveles de seguimiento. El registro se recopila, agrega y muestra herramientas como, por ejemplo, cualquier herramienta basada en texto o Snooper. exe.

Para administrar la implementación, puede usar principalmente el generador de topologías y el panel de control de Lync Server.

<div>

## <a name="deployment-wizard"></a>Asistente para implementación

Debe usar el Asistente para la implementación de Lync Server que se incluye en los medios de instalación para instalar todas las herramientas administrativas en un equipo en el que todavía no ha instalado Lync Server. Durante el proceso de instalación de herramientas administrativas, el Asistente para la implementación de Lync Server se instala localmente junto con el resto de las herramientas, de modo que puede usarla más adelante para instalar archivos para componentes adicionales o para quitar archivos de componentes que no desea en el automático.

Para obtener más información sobre cómo ejecutar el Asistente para la implementación de Lync Server por primera vez desde los medios de instalación de Lync Server, vea [install Lync server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Topology Builder

Para obtener más información sobre las tareas de implementación que puede realizar con el generador de topologías, consulte la documentación de implementación de cada rol de servidor.

</div>

<div>

## <a name="lync-server-control-panel"></a>Panel de Control de Lync Server

Puede usar el panel de control de Lync Server 2013 para realizar la mayoría de las tareas administrativas necesarias para administrar y mantener Lync Server 2013. El panel de control de Lync Server le proporciona una interfaz gráfica de usuario (GUI) para administrar la configuración de los servidores que ejecutan Lync Server, además de los usuarios, clientes y dispositivos de su organización. El shell de administración de Lync Server usa el panel de control de Lync Server como mecanismo subyacente para realizar la configuración de Lync Server.

El panel de control de Lync Server se instala automáticamente en cada servidor front-end de Lync Server o servidor Standard Edition. En esta versión, se administran de forma remota los servidores perimetrales. También puede instalar el panel de control de Lync Server en otro equipo, como una consola de administración desde la que desea administrar Lync Server de forma centralizada. Para obtener más información, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Para establecer la configuración mediante el panel de control de Lync Server, debe haber iniciado sesión con una cuenta asignada al rol CsAdministrator. Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, vea <A href="lync-server-2013-planning-for-role-based-access-control.md">planeación del control de acceso basado en roles en Lync server 2013</A>.</P>
> <LI>
> <P>Para establecer la configuración mediante el panel de control de Lync Server, también debe usar un equipo con una resolución de pantalla mínima de 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Shell de administración de Communications Server

En Lync Server, el shell de administración de Lync Server proporciona un nuevo método para la administración y la administración. El shell de administración de Lync Server es una interfaz de administración eficaz, integrada en la interfaz de línea de comandos de Windows PowerShell, que incluye un conjunto completo de cmdlets específicos de Lync Server. Con el shell de administración de Lync Server, obtiene un amplio conjunto de controles de configuración y automatización. El generador de topologías y el panel de control de Lync Server implementan subconjuntos de estos cmdlets para admitir la administración de Lync Server. El shell de administración de Lync Server incluye cmdlets para todas las tareas de administración de Lync Server y puede usar los cmdlets individualmente para administrar la implementación. Para obtener más información, consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) o la ayuda de la línea de comandos para cada cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Herramienta de registro

La herramienta de registro de Lync Server facilita la solución de problemas al capturar el registro y la información de seguimiento del producto mientras se ejecuta el producto. Puede usar la herramienta para ejecutar sesiones de depuración en cualquier rol de servidor de Lync Server. Para obtener más información sobre la herramienta de registro, vea la documentación de la herramienta de registro de Lync [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)Server 2010 en la biblioteca de TechNet en.

<div>


> [!IMPORTANT]  
> El servicio de registro centralizado se recomienda para todas las colecciones de registro a través de la herramienta de registro de Lync Server en todas las circunstancias. La herramienta de registro de Lync Server seguirá funcionando, pero interferirá o se representará en su mayoría imefectivas si el servicio de registro centralizado ya se está ejecutando. Solo debe usar el servicio de registro centralizado o la herramienta de registro de Lync Server, pero nunca ambos al mismo tiempo. Para obtener más información sobre el servicio de registro centralizado y por qué debe usarlo de forma exclusiva, consulte <A href="lync-server-2013-using-the-centralized-logging-service.md">uso del servicio de registro centralizado en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Requisitos de software de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Permisos y derechos de administrador necesarios para la instalación y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Requisitos para publicar una topología en Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Instalación de las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Solución de problemas del Panel de control de Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Uso del servicio de registro centralizado en Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Consulta también


[Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

