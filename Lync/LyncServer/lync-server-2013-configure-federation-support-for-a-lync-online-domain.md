---
title: 'Lync Server 2013: configurar la compatibilidad con la Federación para un dominio de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27780806e064aae82aa36cee96d9fafcdba2eddb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525977"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Para federar con un cliente de Microsoft Lync Online 2010, es necesario completar los siguientes pasos:

  - Configure la compatibilidad para el dominio del cliente de Lync Online 2010 (por ejemplo, contoso.onmicrosoft.com). Como se especifica en la sección [requisitos previos para federar con un cliente de Lync Online en Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de esta documentación, debe haber habilitado la Federación de su organización. Para ello, se debe especificar el método que se usará para controlar el acceso por dominios federados. Si configuró su organización para que use detección, es opcional agregar el dominio a la lista permitida de su organización. Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Lync Online a la lista de dominios permitidos. Puede Agregar un nombre de dominio mediante el panel de control de Lync Server o mediante la ejecución del cmdlet **New-CSAllowedDomain** . Para obtener información detallada sobre cómo usar el panel de control de Lync Server, incluida la habilitación de la detección de dominios, vea [Manage SIP Federated Providers for your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) en la documentación de operaciones. Para obtener información detallada sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, consulte [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) en la documentación de operaciones.
    
    <div>
    

    > [!NOTE]  
    > Un cliente de Lync Online puede tener varios dominios. Si desea federarse con más de uno de los dominios, debe configurar la compatibilidad para cada dominio con el que desee admitir la Federación, y el administrador del cliente de Lync Online debe habilitar la Federación para cada uno de los dominios que se va a federar.

    
    </div>

  - Configure la compatibilidad para el proveedor de hospedaje del dominio de cliente de Lync Online 2010 con el que quiera federar. Use el procedimiento de esta sección para configurar la compatibilidad para el proveedor de hospedaje.
    
    <div>
    

    > [!NOTE]  
    > Este paso solo es necesario para la Federación con un dominio de un cliente de Lync Online, no para la Federación con ningún dominio implementado localmente en la ubicación de un socio federado.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>Para configurar compatibilidad para un proveedor de hospedaje

1.  En un servidor front-end, inicie el shell de administración de Lync Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet de **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor existente con dicho valor de Identity.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, usted tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **VerificationLevel** indica de qué manera se comprueban (y si se comprueban) los mensajes enviados desde un proveedor de hospedaje para asegurar que se enviaron realmente desde dicho proveedor.
    
      - **Enabled** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.
    
      - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server. Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server.
    
    Para obtener información detallada sobre cómo usar este cmdlet, vea [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

