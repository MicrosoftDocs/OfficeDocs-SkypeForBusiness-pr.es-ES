---
title: "Lync Server 2013 : Conf. logicielle requise pour les outils d’administration"
TOCTitle: Requisitos de software para herramientas administrativas
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48274817
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de software para herramientas administrativas en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describe el software necesario para instalar y usar las herramientas administrativas de Lync Server 2013 además de los requisitos de sistema operativo.

## Microsoft .NET Framework 4.5

La edición de 64 bits de Microsoft .NET Framework 4.5 es necesaria para Lync Server 2013.

## Windows PowerShell 3.0

Windows PowerShell 3.0 es necesario para ejecutar cualquier componente de Microsoft Lync Server 2013. Para obtener más información, consulte [Instalar Windows PowerShell 3.0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Windows Installer versión 4.5

Lync Server 2013 usa la tecnología de Windows Installer para instalar, desinstalar y mantener diversos roles de servidor. Windows Installer versión 4.5 está disponible como un componente redistribuible para el sistema operativo Windows Server. Windows Installer 4.5 incluye Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2, es decir que no es necesario que descargue la utilidad en ningún equipo que ejecute Lync Server 2013. ( Lync Server 2013 solo puede instalarse en equipos que ejecuten Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2.)

No obstante, si quiere instalar el Generador de topologías de Shell de administración de Lync Server o Lync Server en la estación de trabajo de un administrador, es posible que tenga que descargar Windows Installer 4.5. Esta utilidad incluye Windows 7 y Windows 2008 R2, pero ninguna versión anterior del sistema operativo de Windows. Puede descargar Windows Installer 4.5 del Centro de descargas de Microsoft en <http://go.microsoft.com/fwlink/p/?linkid=197395>.

## Complemento de explorador Microsoft Silverlight 5

Panel de control de Lync Server 2013 es una herramienta basada en web y requiere que instale la versión más reciente del complemento de explorador Microsoft Silverlight 5. Cuando inicia Panel de control de Lync Server 2013, si este software no está instalado o si hay instalada una versión anterior, Panel de control de Lync Server 2013 solicita la instalación de la versión requerida.

## Vea también

#### Conceptos

[Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Otros recursos

[Requisitos de infraestructura de herramientas administrativas de Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

