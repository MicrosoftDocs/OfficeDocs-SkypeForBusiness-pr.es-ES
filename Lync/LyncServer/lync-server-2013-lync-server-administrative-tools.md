---
title: 'Lync Server 2013: Herramientas administrativas de Lync Server'
TOCTitle: Herramientas administrativas de Lync Server
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48276210
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Herramientas administrativas de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describen las herramientas administrativas para Lync Server 2013.

Las herramientas administrativas se instalan de forma predeterminada en cada servidor de Lync Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Para conocer los procedimientos para instalar las herramientas administrativas, consulte [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md). Para conocer los procedimientos para abrir las herramientas y realizar tareas de administración, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

Asegúrese de revisar los requisitos de infraestructura, sistema operativo, software y derechos de administrador antes de instalar o usar las herramientas administrativas de Lync Server. Para obtener información sobre los requisitos de infraestructura, consulte [Requisitos de infraestructura de herramientas administrativas de Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obtener información sobre los requisitos de sistema operativo y software para instalar las herramientas administrativas de Lync Server consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md) y [Compatibilidad y requisitos para un servidor adicional en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Los permisos y derechos de usuario requeridos para instalar y usar las herramientas se describen en [Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Las herramientas de administración son las siguientes:

  - **Asistente para la implementación de Lync Server**   Use para implementar Lync Server y para instalar todas las herramientas administrativas.

  - **Lync ServerGenerador de topologías**   Use para definir componentes en su implementación.

  - **Panel de control de Lync Server**   Use para administración continuada de su implementación mediante una interfaz basada en web.

  - **Shell de administración de Lync Server**   Use para administración continuada de su implementación mediante la línea de comandos.

  - **Lync ServerHerramienta de registro de**   Use para solucionar problemas en su implementación.

  - **Servicio de registro centralizado**   Recopile registros y haga un seguimiento de los archivos de un equipo, grupo de servidores, sitio o a escala global. Seleccione y defina escenarios que contengan niveles de seguimiento, proveedores y etiquetas. Los registros se recopilan, agregan y muestran con herramientas como pueden ser cualquier herramienta basada en texto o Snooper.exe.

Puede administrar su implementación en primer lugar mediante Generador de topologías y Panel de control de Lync Server.

## Asistente para implementación

Debe usar la Asistente para la implementación de Lync Server que se incluye en los medios de instalación para instalar todas las herramientas administrativas en un equipo en el que aún no se haya instalado Lync Server. Durante el proceso de instalación de herramientas administrativas, la Asistente para la implementación de Lync Server se instala localmente junto con las otras herramientas para poder instalar luego los archivos para componentes adicionales o eliminar los archivos para los componentes que no desea tener en el equipo.

Para obtener más información sobre cómo ejecutar la Asistente para la implementación de Lync Server por primera vez desde los medios de instalación de Lync Server, vea [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

## Generador de topologías

Para obtener más información sobre tareas de implementación que puede realizar mediante Generador de topologías, consulte la documentación sobre implementación de cada función de servidor.

## Panel de control de Lync Server

Puede usar Panel de control de Lync Server 2013 para realizar la mayoría de las tareas necesarias para la administración y el mantenimiento de Lync Server 2013. Panel de control de Lync Server le ofrece una interfaz gráfica de usuario (GUI) que le permite administrar la configuración de los servidores donde se ejecuta Lync Server, además de los usuarios, clientes y dispositivos de su organización. Shell de administración de Lync Server utiliza Panel de control de Lync Server como mecanismo subyacente para la configuración de Lync Server.

Panel de control de Lync Server se instala automáticamente en cada servidor front-end o servidor Standard Edition Lync Server. En esta versión, se administran de forma remota los servidores perimetrales. También puede instalar Panel de control de Lync Server en otro equipo, como una consola de administración desde la que desea administrar centralmente Lync Server. Para más información, consulte [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

> [!IMPORTANT]  
> <ul>
> <li><p>Para establecer la configuración mediante Panel de control de Lync Server, debe haber iniciado sesión con una cuenta que tenga asignado el rol CsAdministrator. Para más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a>.</p></li>
> <li><p>Para configurar los valores con Panel de control de Lync Server, deberá utilizar también un equipo con una resolución de pantalla mínima de 1024 x 768.</p></li>
> </ul>


## Shell de administración de Communications Server

En Lync Server, el Shell de administración de Lync Server brinda un nuevo método de administración y gestión. Shell de administración de Lync Server es una eficaz interfaz de administración, integrada en la Interfaz de la línea de comandos Windows PowerShell, que incluye un conjunto exhaustivo de cmdlets específicos de Lync Server. Con el Shell de administración de Lync Server, puede controlar con mayor facilidad la administración y automatización. Generador de topologías y Panel de control de Lync Server implementan subconjuntos de estos cmdlets para admitir la administración de Lync Server. El Shell de administración de Lync Server incluye cmdlets para todas las tareas de administración de Lync Server, y puede usar los cmdlets individualmente para administrar su implementación. Para más información, vea la documentación del [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md) o la ayuda de línea de comandos para cada cmdlet.

## Herramienta de registro

La Herramienta de registro de Lync Server facilita la solución de problemas al capturar y seguir la información del producto mientras se está ejecutando el producto. Puede usar la herramienta para ejecutar sesiones de depuración en cualquier función de servidor de Lync Server. Para más información sobre la Herramienta de registro, consulte la documentación de la Herramienta de registro de Lync Server 2010 en la Biblioteca de TechNet en <http://go.microsoft.com/fwlink/?linkid=199265>.

> [!IMPORTANT]  
> Le recomendamos usar en todos los casos el Servicio de registro centralizado para todas las labores de recopilación de registros en vez de la herramienta de registro de Lync Server. La herramienta de registro de Lync Server seguirá funcionando, pero interferirá o será ineficiente si el Servicio de registro centralizado ya se está ejecutando. Use solo el Servicio de registro centralizado o la herramienta de registro de Lync Server, pero nunca simultáneamente. Para más información sobre el Servicio de registro centralizado y los motivos por los que debe usarse exclusivamente, consulte <a href="lync-server-2013-using-the-centralized-logging-service.md">Uso del servicio de registro centralizado de Lync Server 2013</a>.



## En esta sección

  - [Requisitos de infraestructura de herramientas administrativas de Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Requisitos de software para herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Requisitos para publicar una topología en Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Solución de problemas del Panel de control de Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Uso del servicio de registro centralizado de Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

## Vea también

#### Otros recursos

[Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md)

