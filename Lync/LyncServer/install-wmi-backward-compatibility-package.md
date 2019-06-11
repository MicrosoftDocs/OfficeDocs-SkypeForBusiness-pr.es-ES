---
title: Instalar el paquete de compatibilidad con versiones anteriores de WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b61d34ce8809f06156f4d4dca61c39cc4aff0f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Instalar el paquete de compatibilidad con versiones anteriores de WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Si intenta ejecutar el Asistente para la combinación del generador de topología sin instalar el paquete de compatibilidad con versiones anteriores de WMI, verá el siguiente error:

![Mensaje de error de WMI] (images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Mensaje de error de WMI")

Si intenta ejecutar el cmdlet **Merge-CsLegacytopology** sin instalar el paquete de compatibilidad con versiones anteriores de WMI, verá el siguiente error:

![Error del proveedor WMI de Windows PowerShell] (images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Error del proveedor WMI de Windows PowerShell")

Para instalar el paquete de compatibilidad con versiones anteriores de WMI

1.  Desde los medios de instalación, vaya \\a\\configuración\\de\\instalación de AMD64 OCSWMIBC. MS.

2.  Instale OCSWMIBC. MS.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi debe instalarse en el equipo en el que se ejecuta el Asistente para la combinación del generador de topología. Sin embargo, recomendamos instalar OCSWMIBC. msi en todos los servidores front-end de su topología.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi puede instalarse en cualquier equipo del dominio que tenga instalados los componentes principales de Lync Server 2013 y el shell de administración de Lync Server 2013, y tiene acceso a la topología de Office Communications Server 2007 R2 (proveedor WMI a dominio de Active Directory). Servicios (AD DS) y SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

