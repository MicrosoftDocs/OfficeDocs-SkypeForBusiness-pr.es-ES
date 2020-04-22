---
title: 'Lync Server 2013: información general sobre el entorno híbrido de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b39c94b08da65e546fdf3ad01d42ada636ff371d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Información general sobre el entorno híbrido de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-28_

El entorno híbrido de Lync Server 2013 hace referencia a una implementación en la que hay algunos usuarios hospedados en Lync Server 2013 local y otros usuarios hospedados en Lync Online, pero los usuarios comparten el mismo dominio, como user@contoso.com.

<div>

## <a name="about-this-guide"></a>Acerca de esta guía

En esta guía se describen las tareas necesarias para configurar el entorno de Lync Server 2013 para la interoperabilidad con Lync Online y, a continuación, mover a los usuarios de la implementación local para usar Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Requisitos previos

Tendrá que tener instaladas las siguientes aplicaciones y utilidades para completar las tareas de configuración de una implementación de híbrido. Los programas de instalación para estos archivos se incluyen en los medios de instalación proporcionados para su implementación, así como en los vínculos incluidos en la lista siguiente.

  - [Servicios de federación de Active Directory (ADFS) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Herramienta de sincronización de directorios de Microsoft 9,1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Instalar Windows PowerShell para el inicio de sesión único con AD FS](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - El Asistente para el inicio de sesión de Microsoft Online Services (msoidcli-7.0. msi) se incluye en la configuración de escritorio de Office 365, que se puede obtener en la página de descargas a la que se vincula desde el centro de administración de Microsoft 365.

</div>

<div>

## <a name="administrator-credentials"></a>Credenciales de administrador

Cuando se le pida que proporcione sus credenciales de administrador, use el nombre de usuario y la contraseña de la cuenta de administrador de la organización de Office 365. También usará estas credenciales para configurar los servicios de Federación de Active Directory (AD FS) 2,0, la sincronización de directorios, el inicio de sesión único, la Federación y el traslado de usuarios a Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Conectarse a Lync Online PowerShell

Los administradores ahora pueden usar Windows PowerShell para administrar Lync Online y sus cuentas de usuario de Lync Online. Para ello, primero debe descargar e instalar el módulo Lync Online Connector desde el centro de descarga de Microsoft (https://go.microsoft.com/fwlink/?LinkId=294688). Para obtener más información sobre cómo descargar, instalar y usar el módulo Lync Online Connector y para obtener información detallada sobre cómo usar Windows PowerShell para administrar Lync Online, consulte [using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

