---
title: 'Lync Server 2013: Herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Herramientas administrativas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En este tema se describen las herramientas administrativas para Lync Server 2013.

Las herramientas administrativas se instalan de forma predeterminada en cada servidor de Lync Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Para obtener información sobre los procedimientos para instalar las herramientas administrativas, consulte [instalar herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md). Para obtener información sobre los procedimientos para abrir las herramientas para realizar tareas de administración, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

Asegúrese de revisar los requisitos de los derechos de infraestructura, sistema operativo, software y administrador antes de instalar o usar las herramientas administrativas de Lync Server. Para obtener más información sobre los requisitos de infraestructura, consulte [requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server, consulte [compatibilidad del sistema operativo servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [ Requisitos y compatibilidad de servidor adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Los derechos de usuario y los permisos necesarios para instalar y usar las herramientas se describen en [derechos de administrador y permisos necesarios para la configuración y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Las herramientas administrativas son las siguientes:

  - **Asistente para la implementación de Lync Server**   se usa para implementar Lync Server e instalar todas las herramientas administrativas.

  - **El generador**   de topología de Lync Server se usa para definir componentes en la implementación.

  - ****   Uso del panel de control de Lync Server para la administración continua de la implementación mediante una interfaz basada en Web.

  - **Shell de administración de Lync Server**   para la administración continua de la implementación mediante la línea de comandos.

  - **Herramienta de registro de Lync Server**   use esta solución para solucionar problemas en la implementación.

  - **El servicio**   de registro centralizado recopila registros y rastrea archivos de un equipo, grupo, sitio o global. Seleccione y defina escenarios que contengan proveedores, marcas y niveles de seguimiento. El registro se recopila, se agrega y se muestra con herramientas como, por ejemplo, cualquier herramienta de texto o Snoop. exe.

Para administrar la implementación, puede usar principalmente el generador de topología y el panel de control de Lync Server.

<div>

## <a name="deployment-wizard"></a>Asistente para la implementación

Debe usar el Asistente para la implementación de Lync Server incluido en el medio de instalación para instalar todas las herramientas administrativas en un equipo en el que no haya instalado ya Lync Server. Durante el proceso de instalación de herramientas administrativas, el Asistente para la implementación de Lync Server se instala localmente junto con el resto de las herramientas para que pueda usarla más adelante para instalar archivos de componentes adicionales o para quitar archivos de componentes que no desee en el sistema.

Para obtener más información sobre cómo ejecutar el Asistente para la implementación de Lync Server por primera vez desde los medios de instalación de Lync Server, consulte [instalar las herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Generador de topologías

Para obtener más información sobre las tareas de implementación que puede realizar con el generador de topologías, consulte la documentación de implementación de cada rol de servidor.

</div>

<div>

## <a name="lync-server-control-panel"></a>Panel de control de Lync Server

Puede usar el panel de control de Lync Server 2013 para realizar la mayoría de las tareas administrativas necesarias para administrar y mantener Lync Server 2013. El panel de control de Lync Server le proporciona una interfaz gráfica de usuario (GUI) para administrar la configuración de los servidores que ejecutan Lync Server, además de los usuarios, los clientes y los dispositivos de su organización. El shell de administración de Lync Server usa el panel de control de Lync Server como mecanismo subyacente para realizar la configuración de Lync Server.

El panel de control de Lync Server se instala automáticamente en todos los servidores front-end de Lync Server o el servidor Standard Edition. En esta versión, se administran servidores perimetrales de forma remota. También puede instalar el panel de control de Lync Server en otro equipo, como una consola de administración desde la que desee administrar Lync Server de forma centralizada. Para obtener información detallada, consulte [instalar herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Para configurar la configuración con el panel de control de Lync Server, debe haber iniciado sesión con una cuenta asignada al rol CsAdministrator. Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync server 2013</A>.</P>
> <LI>
> <P>Para configurar la configuración con el panel de control de Lync Server, también debe usar un equipo con una resolución de pantalla mínima de 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Shell de administración de Communications Server

En Lync Server, el shell de administración de Lync Server proporciona un nuevo método de administración y administración. El shell de administración de Lync Server es una eficaz interfaz de administración, creada en la interfaz de línea de comandos de Windows PowerShell, que incluye un conjunto completo de cmdlets específicos de Lync Server. Con el shell de administración de Lync Server, obtiene un conjunto completo de controles de configuración y automatización. El generador de topología y el panel de control de Lync Server implementan subconjuntos de estos cmdlets para admitir la administración de Lync Server. El shell de administración de Lync Server incluye cmdlets para todas las tareas de administración de Lync Server, y puede usar los cmdlets individualmente para administrar la implementación. Para obtener más información, consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) o la ayuda de la línea de comandos para cada cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Herramienta de registro

La herramienta de registro de Lync Server facilita la solución de problemas al capturar el registro y la información de seguimiento del producto mientras se ejecuta el producto. Puede usar la herramienta para ejecutar sesiones de depuración en cualquier rol de servidor de Lync Server. Para obtener más información sobre la herramienta de registro, consulte la documentación de la herramienta de registro de Lync [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Server 2010 en la biblioteca de TechNet en.

<div>


> [!IMPORTANT]  
> El servicio de registro centralizado se recomienda para todas las colecciones de registro en la herramienta de registro de Lync Server en todas las circunstancias. La herramienta de registro de Lync Server seguirá funcionando, pero interferirá o se representará principalmente ineficaz si el servicio de registro centralizado ya se está ejecutando. Debe usar solo el servicio de registro centralizado o la herramienta de registro de Lync Server, pero nunca ambos a la vez. Para obtener más información sobre el servicio de registro centralizado y por qué debería usarlo exclusivamente, consulte <A href="lync-server-2013-using-the-centralized-logging-service.md">usar el servicio de registro centralizado en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Requisitos de software para herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Requisitos para publicar una topología en Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Solución de problemas del panel de control de Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Usar el servicio de registro centralizado en Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

