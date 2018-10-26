---
title: "Lync Server 2013: Requisitos de sistema para servidores que ejecuten Lync Server 2013"
TOCTitle: Requisitos del sistema para servidores que ejecuten Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48275741
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos del sistema para servidores que ejecuten Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_


> [!NOTE]
> Para más información sobre los requisitos de hardware, vea <A href="lync-server-2013-server-hardware-platforms.md">Plataformas de hardware de servidor para Lync Server 2013</A>.



Los servidores Standard Edition y Enterprise Edition comparten los mismos requisitos de software

Los servidores que ejecutan Lync Server 2013, Enterprise Edition están pensados para usarse en organizaciones grandes como implementación organizativa principal. El servidor Enterprise Edition está diseñado para escalar aproximadamente a 80.000 usuarios hospedados por grupo de servidores. Los servidores que ejecutan Lync Server 2013, Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas de la implementación principal de la organización. Un par de servidores de Standard Edition puede dar soporte hasta a 5.000 usuarios. Para más información sobre las diferencias entre los servidores Standard Edition y los servidores Enterprise Edition, vea [Introducción general a la implementación para Lync Server 2013](lync-server-2013-deployment-overview.md) .

## Instalación del sistema operativo

> [!IMPORTANT]  
> Lync Server 2013 solamente está disponible en una edición de 64 bits, lo que requiere hardware de 64 bits y una edición de 64 bits del sistema operativo Windows Server. Esta versión no está disponible en una edición de 32 bits de Lync Server 2013.



El servidor Standard Edition y el Enterprise Edition pueden usar cualquiera de las siguientes opciones:

  - Windows Server 2008 R2 SP1 o un Pack Service posterior

  - Windows Server 2012

  - Windows Server 2012 R2

Instale el software del sistema operativo en el servidor front-end del servidor Standard Edition o Enterprise Edition. Aplique todas las actualizaciones para dotar al sistema operativo de la actualización más reciente y del nivel de actualización necesario que sea coherente con los estándares de su organización. Para más información sobre los requisitos del sistema operativo, vea [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.


> [!NOTE]
> Para que Lync Server 2013 funcione en Windows Server 2012 R2, puede que tenga que cambiar el valor de una clave de registro en Windows Server. Este cambio puede ser necesario para que los certificados funcionen correctamente y para los clientes que se registren en Aplicaciones de sucursal con funciones de supervivencia. Para obtener más información, vea <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.



## Software adicional para Lync Server 2013

Además de las actualizaciones necesarias para el sistema operativo, Lync Server 2013 requiere roles de sistema operativo, características y software para poder funcionar. Para obtener más información acerca del software adicional que debe instalarse antes de publicar la topología e instalar Lync Server 2013, consulte [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md) la documentación sobre planificación.

## Software adicional necesario para todos los roles de servidor

Asegúrese también de que estén instalados Interfaz de la línea de comandos Windows PowerShell 3.0 y Microsoft .NET Framework 4.5 en todos los roles del servidor.

Además, Interfaz de la línea de comandos Windows PowerShell 3.0 y Microsoft .NET Framework 4.5 son necesarios en cualquier equipo donde ejecute las herramientas administrativas de Lync Server.

## Windows PowerShell 3.0

Lync Server 2013 requiere que instale Windows PowerShell 3.0 en todos los equipos que participarán en la topología de Lync Server. Para más información sobre cómo instalar Windows PowerShell 3.0, consulte [Instalar Windows PowerShell 3.0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).


> [!NOTE]
> En Windows Server&nbsp;2008&nbsp;R2 con SP1, no se puede instalar Interfaz de la línea de comandos Windows PowerShell 3.0 antes de instalar Microsoft .NET Framework 4.5.



## Microsoft .NET Framework 4.5

Cuando instale Microsoft .NET Framework 4.5 en servidores que ejecutarán Lync Server 2013 en Windows Server 2012 o Windows Server 2012 R2, será necesario que realice un paso adicional. Tras la instalación de NET Framework 4.5, use el Administrador de servidores para instalar la Activación HTTP.

**Para instalar la Activación HTTP .NET 4.5 en Windows Server 2012 o Windows Server 2012 R2**

1.  En el menú **Inicio**, haga clic en **Programas**, en **Herramientas administrativas** y, después, en **Administrador de servidores**.

2.  Una vez esté en Administrador de servidores, en **Resumen de características**, elija **Agregar características**.

3.  Expanda **.NET Framework 4.5**.

4.  Seleccione **Activación WCF** si no está seleccionada. Después, seleccione **Activación HTTP**.

5.  Haga clic en **Siguiente** y siga las indicaciones para completar la instalación.

