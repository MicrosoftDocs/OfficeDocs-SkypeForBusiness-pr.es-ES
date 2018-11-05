---
title: Preparación e instalación del Analizador de procedimientos recomendados
TOCTitle: Preparación e instalación del Analizador de procedimientos recomendados
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48275281
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparación e instalación del Analizador de procedimientos recomendados

 

_**Última modificación del tema:** 2016-12-08_

Para realizar las tareas que se describen en este tema debe haber iniciado sesión como miembro del grupo Administradores.

## Requisitos del sistema para la instalación del Analizador de procedimientos recomendados

Para ejecutar Lync Server 2013, Analizador de procedimientos recomendados para examinar su entorno, el equipo debe tener una versión de 64 bits de uno de los siguientes sistemas operativos:

  - Sistema operativo Windows Server 2008 R2 Standard con Service Pack 1 (SP1)

  - Sistema operativo Windows Server 2008 R2 Enterprise con SP1

  - Sistema operativo Windows Server 2008 R2 Datacenter con SP1

  - Sistema operativo Windows Server 2012 Datacenter

  - Sistema operativo Windows Server 2012 Standard

  - Sistema operativo Windows Server 2012 Enterprise

  - Sistema operativo Windows Server 2012 R2 Datacenter

  - Sistema operativo Windows Server 2012 R2 Standard

  - Sistema operativo Windows Server 2012 R2 Enterprise

  - Sistema operativo Windows 8

  - Sistema operativo Windows 7

El equipo también debe ejecutar lo siguiente:

  - Microsoft .NET Framework 4.5. Para Lync Server 2013, debe instalar manualmente la versión de 64 bits de Microsoft .NET Framework 4.5 en el servidor antes de instalar Lync Server 2013.

  - Lync Server 2013, Componentes principales.

  - Paquete de compatibilidad con versiones anteriores de WMI. Para información, vea [Instalar paquete de compatibilidad con versiones anteriores de WMI](install-wmi-backward-compatibility-package.md) en la documentación de migración.

  - Windows PowerShell 3.0. Para más información, vea [Instalar Windows PowerShell 3.0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) en la documentación de implementación.

Puede instalar el Analizador de procedimientos recomendados en equipos con un sistema operativo compatible que no ejecute Lync Server 2013, Componentes principales o Paquete de compatibilidad con versiones anteriores de WMI, pero puede usar el Analizador de procedimientos recomendados en esos equipos solo para ver informes, no para ejecutar exámenes.

## Selección de un equipo para la instalación

Recomendamos instalar Lync Server 2013, Analizador de procedimientos recomendados en un equipo dedicado a la administración de Lync Server 2013. Puede instalar la herramienta en un servidor que ejecuta Lync Server 2013 o en un equipo administrativo que ejecuta las herramientas administrativas de Lync Server 2013. Si instala la herramienta en un servidor que ejecuta Lync Server, le recomendamos que use la herramienta para examinar solo ese servidor.

## Instalación del Analizador de procedimientos recomendados

Puede descargar el Analizador de procedimientos recomendados para Lync Server 2013 en [http://go.microsoft.com/fwlink/?linkid=266539\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=266539%26clcid=0xc0a).

Para instalar el Analizador de procedimientos recomendados, inicie el archivo RtcBPA.msi de Microsoft Installer en el equipo donde desea instalar la herramienta y luego siga las instrucciones que aparecen en pantalla. La ubicación predeterminada para la instalación de los archivos de programa es *\<unidad del sistema\>*\\Archivos de programa\\Lync Server 2013\\BPA.

