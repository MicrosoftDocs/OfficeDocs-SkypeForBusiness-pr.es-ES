---
title: 'Lync Server 2013: compatibilidad con los servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f427486756895f1bff5330075f4c323f944afd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529637"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Compatibilidad de servicios de dominio de Active Directory en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Lync Server 2013 usa el almacén de administración central para almacenar los datos de configuración de servidores y servicios, en lugar de depender de los servicios de dominio de Active Directory para esta información, como en el pasado. Lync Server 2013 sigue almacenando lo siguiente en AD DS:

  - **Extensiones de esquema**
    
      - Extensiones de objetos de usuario
    
      - Extensiones para Lync Server 2010 y las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores con versiones anteriores admitidas

  - **Datos** (almacenados en el esquema extendido de Lync Server 2013 y en las clases existentes)
    
      - URI de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto de aplicaciones (por ejemplo, la aplicación grupo de respuesta y la aplicación operador de conferencia)
    
      - Datos publicados para lograr compatibilidad con versiones anteriores
    
      - Un punto de control de servicio (SCP) para el almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En esta sección se describen los requisitos de compatibilidad de AD DS para Lync Server 2013. Para obtener más información sobre la compatibilidad de la topología, consulte [topologías admitidas de Active Directory en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación sobre compatibilidad.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Sistemas operativos admitidos con los controladores de dominio

Lync Server 2013 admite controladores de dominio que ejecutan los siguientes sistemas operativos:

  - Sistema operativo Windows Server 2012 R2

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 R2

  - Sistema operativo Windows Server 2008

  - Windows Server 2008 Enterprise 32 bits

  - Las versiones de 32 y 64 bits del sistema operativo Window Server 2003 R2

  - Las versiones de 32 bits o de 64 bits del sistema operativo Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Nivel funcional de bosque y dominio

Debe elevar todos los dominios en los que implemente Lync Server 2013 a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.

Todos los bosques en los que implemente Lync Server 2013 deben elevarse a un nivel funcional del bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Compatibilidad con los controladores de dominio de solo lectura

Lync Server 2013 admite implementaciones de servicios de dominio de Active Directory que incluyen controladores de dominio de solo lectura o servidores de catálogo global de solo lectura, siempre que haya controladores de dominio de escritura disponibles.

</div>

<div>

## <a name="domain-names"></a>Nombres de dominio

Lync Server no admite dominios con una sola etiqueta. Por ejemplo, se admitiría un bosque con un dominio raíz denominado **contoso.local**, pero no un dominio raíz denominado **local**. Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS de etiqueta única" en [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .

<div>


> [!NOTE]  
> Lync Server no admite el cambio de nombre de dominios. Si necesita cambiar el nombre de un dominio en el que se ha implementado Lync Server, primero debe desinstalar Lync Server, luego cambiar el nombre del dominio y, a continuación, volver a instalar Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Entornos de AD DS bloqueados

En entorno de AD DS bloqueado, los objetos de usuario y equipo se colocan a menudo en unidades organizativas (OU) específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y para permitir al uso de objetos de directivas de grupo (GPO) para la aplicación de directivas de seguridad. Lync Server 2013 se puede implementar en un entorno de Active Directory bloqueado. Para obtener más información sobre lo que se necesita para implementar Lync Server en un entorno bloqueado, consulte [preparación de servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación sobre implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

