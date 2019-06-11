---
title: 'Lync Server 2013: Compatibilidad de servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b264abefb1234892df355fee123dd6ce68b4dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Compatibilidad de servicios de dominio de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Lync Server 2013 usa el almacén de administración central para almacenar los datos de configuración de servidores y servicios, en lugar de depender de los servicios de dominio de Active Directory para esta información, como en el pasado. Lync Server 2013 sigue almacenando lo siguiente en AD DS:

  - **Extensiones de esquema**
    
      - Extensiones de objetos de usuario
    
      - Extensiones de Lync Server 2010 y las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores compatibles

  - **Datos** (almacenado en el esquema extendido de Lync Server 2013 y en las clases existentes)
    
      - URI de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto para aplicaciones (por ejemplo, la aplicación de grupo de respuesta y la aplicación de operador de conferencia)
    
      - Datos publicados para la compatibilidad con versiones anteriores
    
      - Un punto de control de servicio (SCP) para el almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En esta sección se describen los requisitos de compatibilidad de AD DS para Lync Server 2013. Para obtener más información sobre la compatibilidad de topología, consulte [topologías de Active Directory admitidas en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación de soporte técnico.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Sistemas operativos de controlador de dominio compatibles

Lync Server 2013 admite controladores de dominio que ejecutan los siguientes sistemas operativos:

  - Sistema operativo Windows Server 2012 R2

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 R2

  - Sistema operativo Windows Server 2008

  - Windows Server 2008 Enterprise 32 bits

  - Las versiones de 32 o 64 bits del sistema operativo Windows Server 2003 R2

  - Las versiones de 32 o 64 bits del sistema operativo Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Nivel funcional de bosque y dominio

Debe elevar todos los dominios en los que implementa Lync Server 2013 a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.

Todos los bosques en los que implemente Lync Server 2013 deben elevarse al nivel funcional de bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o al menos Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Compatibilidad con controladores de dominio de solo lectura

Lync Server 2013 admite implementaciones de servicios de dominio de Active Directory que incluyen controladores de dominio de solo lectura o servidores de catálogo global de solo lectura, siempre que haya controladores de dominio de escritura disponibles.

</div>

<div>

## <a name="domain-names"></a>Nombres de dominio

Lync Server no es compatible con los dominios con etiqueta única. Por ejemplo, un bosque con un dominio raíz denominado **contoso. local** es compatible, pero no se admite un dominio raíz denominado **local** . Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)de etiqueta única" en.

<div>


> [!NOTE]  
> Lync Server no permite cambiar el nombre de los dominios. Si necesita cambiar el nombre de un dominio donde se ha implementado Lync Server, primero debe desinstalar Lync Server, después cambiar el nombre del dominio y, a continuación, volver a instalar Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Entornos AD DS bloqueados

En un entorno de AD DS bloqueado, los usuarios y los objetos de equipos a menudo se colocan en unidades organizativas (OU) específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y habilitar el uso de objetos de directiva de grupo (GPO) para aplicar directivas de seguridad. Lync Server 2013 se puede implementar en un entorno de Active Directory bloqueado. Para obtener más información sobre lo que se necesita para implementar Lync Server en un entorno bloqueado, consulte preparar los servicios de dominio de Active Directory bloqueados en [Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación de implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

