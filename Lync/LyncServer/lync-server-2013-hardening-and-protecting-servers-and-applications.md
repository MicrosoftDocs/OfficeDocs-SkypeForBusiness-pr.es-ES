---
title: 'Lync Server 2013: refuerzo y protección de servidores y aplicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8de372a8ca0ae6ec8c80a147eb74ffb01d0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Protección y protección de servidores y aplicaciones para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

Debe proteger el sistema operativo y las aplicaciones de acuerdo con los procedimientos recomendados correspondientes al componente en cuestión. En esta sección se explica cómo proteger los servidores de aplicaciones y el uso de la directiva de grupo para implementar bloqueos de seguridad.

<div>


> [!NOTE]  
> También puede reforzar y proteger las bases de datos que se usan para la implementación de Microsoft Lync Server 2013. Para obtener más información, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">refuerzo y protección de las bases de datos de Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Proteger los servidores de aplicaciones

En el caso de los servidores de aplicaciones, deben protegerse el sistema operativo y las aplicaciones. Así, un equipo con Windows Server 2008 dedicado a ejecutar Microsoft Internet Security and Acceleration (ISA) Server 2006 se debe proteger tanto desde el punto vista del sistema operativo como de las aplicaciones. Reducir el número de servicios que se ejecutan y ofrecen en un servidor debe ser un objetivo primordial.

</div>

<div>

## <a name="securing-virtual-servers"></a>Proteger los servidores virtuales

Las instantáneas del servidor virtual contienen copias de los discos de datos del servidor y también contienen volcados de datos en memoria, que pueden contener datos criptográficos confidenciales que podrían dar lugar a ataques. Para los servidores de producción implementados mediante la virtualización, debe deshabilitar todas las instantáneas del servidor o administrarlas de manera controlada. Para obtener más información sobre cómo proteger los servidores virtuales Hyper-V, consulte la guía de seguridad de [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)Hyper-v en:.

</div>

<div>

## <a name="group-policy"></a>Directiva de grupo

En Windows Server 2008 y Windows Server 2008 R2, la directiva de grupo permite la administración de la configuración de escritorio basada en directorios. La directiva de grupo puede servir para implementar bloqueos de seguridad, que se logra definiendo la configuración de equipo y usuario de los siguientes elementos en un objeto de la directiva de grupo (GPO):

  - Directivas basadas en el Registro

  - Seguridad

  - Instalación de software

  - Scripts

  - Redirección de carpetas

  - Servicios de instalación remota

Para proporcionar una interfaz de usuario para que el Administrador configure estas opciones, se incluyen plantillas administrativas con versiones de sistema operativo, versiones de Service Pack y algunas aplicaciones, incluido Lync Server 2013.

El archivo Communicator. adm es una plantilla administrativa que se incluye con Lync Server 2013, se instala en el directorio%\\WINDIR\\ % inf y proporciona una interfaz a la configuración de la Directiva de grupo. Cada valor de configuración de Communicator.adm se corresponde con un valor del Registro que afecta al comportamiento de la aplicación.

Se puede obtener acceso a esta configuración desde GPedit.dll, que está disponible en la consola Usuarios y equipos de Active Directory y en la Consola de administración de directivas de grupo (GPMC).

</div>

<div>

## <a name="group-policy-security-settings"></a>Configuración de seguridad de la directiva de grupo

La directiva de grupo contiene una configuración de seguridad para un GPO en Configuración del equipo/Configuración de Windows/Configuración de seguridad si se obtiene acceso desde GPedit.dll. Puede importar plantillas de seguridad para definir la configuración de seguridad del GPO. La guía de seguridad de Windows Server [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 2008 en y el kit de herramientas de administración de cumplimiento [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) de seguridad de Windows Server 2008 R2 incluyen una serie de plantillas de ejemplo que puede modificar para satisfacer sus necesidades.

</div>

<div>

## <a name="best-practices"></a>Procedimientos recomendados

  - Proteja todos los sistemas operativos y aplicaciones del servidor.

  - Proteja las instantáneas de servidor y mejore la seguridad de todos los servidores virtuales.

  - Use la directiva de grupo para implementar bloqueos de seguridad.

</div>

</div>

<span> </span>

</div>

</div>

</div>

