---
title: Configuración de la integración de Lync Server local con Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a652fea6c54592526047e8d8b35a0bddd0ef1995
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Configuración de la integración de Lync Server 2013 local con Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2018-03-30_

Los clientes que usan las implementaciones locales de Lync Server 2013 pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange online en modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el servidor perimetral en la implementación de Lync Server local completando las siguientes tareas:

  - Configurar un espacio de direcciones SIP compartido

  - Configurar un proveedor de hospedaje en el servidor perimetral

  - Comprobar la replicación del almacén de administración central actualizado

Si Lync Server 2013 está integrado en Exchange Online, un usuario que está intentando iniciar sesión en mensajería instantánea desde OWA se considera un usuario remoto o externo. En este escenario, este usuario debe tener una directiva de acceso externo asignada que tenga la siguiente opción seleccionada:

**Habilitar las comunicaciones con usuarios remotos**

Habilite esta opción si quiere que los usuarios de su organización que estén fuera del firewall, como teletrabajadores y usuarios que viajan, puedan conectarse a Lync Server a través de Internet.

Para obtener más información, vea [administrar la Directiva de acceso externo en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Configurar un espacio de direcciones SIP compartido

Para integrar Lync Server local 2013 con Exchange Online, debe configurar un espacio de direcciones SIP compartido. El mismo espacio de direcciones de dominio SIP es compatible con Lync Server y el servicio Exchange Online.

Con el shell de administración de Lync Server, configure el servidor perimetral para la Federación ejecutando el cmdlet **set-CSAccessEdgeConfiguration** , usando los parámetros que se muestran en el siguiente ejemplo:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers ** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Lync Server y Exchange Online.

Para obtener más información sobre cómo usar el shell de administración de Lync Server, consulte [consola de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar un proveedor de hospedaje en el servidor perimetral

Use el shell de administración de Lync Server para configurar un proveedor de hospedaje en el servidor perimetral. Para ello, ejecute el cmdlet **New-CsHostingProvider** con los parámetros del siguiente ejemplo:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro <STRONG>ProxyFqdn</STRONG> de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".



</div>

  - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online"). Los valores que contienen espacios deben ir entre comillas dobles.

  - **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Debe establecerse en **true**.

  - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Debe establecerse en **true**.

  - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Lync Server. Debe establecerse en **false**.

  - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.

  - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server. Debe establecerse en **false**.

  - **VerificationLevel** indica el nivel de comprobación permitido para los mensajes que se envían al proveedor hospedado y desde él. Especifique **UseSourceVerification**. Esta opción se basa en el nivel de comprobación que está incluido en los mensajes que se envían desde el proveedor de hospedaje. Si no se especifica este nivel, el mensaje se rechazará como no verificable.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Comprobar la replicación del almacén de administración central actualizada

Los cambios que realizó usando los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y generalmente tardan menos de un minuto en replicarse. Puede comprobar el estado de replicación y que se aplicaron los cambios a su servidor perimetral mediante los cmdlets siguientes.

Para comprobar las actualizaciones de replicación en un servidor interno de la implementación de Lync Server, ejecute el siguiente cmdlet:

    Get-CsManagementStoreReplicationStatus

Para comprobar que se han aplicado los cambios, ejecute el siguiente cmdlet en el servidor perimetral:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>Vea también


[Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Integración de la mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

