---
title: 'Lync Server 2013: habilitar la conectividad de Lync y Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2b950b8ff778ee48014dc951d89baafab59510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Habilitar la conectividad entre Lync y Skype en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-16_

Una vez que haya enviado la solicitud de aprovisionamiento, puede centrarse en el entorno de Lync Server y en las tareas administrativas necesarias para configurar la conectividad de Lync y Skype. En esta sección, se supone que el administrador de Lync Server ha implementado Lync Server y ha configurado el acceso externo. Para obtener más información sobre cómo configurar el acceso externo para Lync Server, consulte [Planning for external User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Para preparar el entorno de Lync Server para la conectividad de Lync y Skype, el administrador de Lync Server debe completar las tres tareas siguientes:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configurar la Federación y el PIC

La Federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Lync de la organización. Public Instant Messaging Connectivity (PIC) es una clase de Federación y debe configurarse para permitir que los usuarios de Lync se comuniquen con los usuarios de Skype. La Federación y el PIC se configuran mediante el panel de control de Lync Server, que se muestra a continuación.

![Mostrar PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Mostrar PIC")

<div>


> [!IMPORTANT]  
> La Federación de PIC ya no es compatible con Live Communication Server 2005 SP1 o con Office Communications Server 2007. Las plataformas compatibles para la Federación de PIC incluyen Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurar al menos una directiva para admitir el acceso de usuarios federados

Mediante el panel de control de Lync Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de Skype pueden colaborar con los usuarios internos de Lync Server.

![Directivas](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Directivas")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Configurar la configuración del proveedor de PIC de Skype para Lync

Mediante el shell de administración de Lync Server, un administrador debe configurar la Directiva de cliente Lync para mostrar Skype como un proveedor de PIC adicional.

<div>


> [!NOTE]  
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en la mensajería instantánea o las conferencias de audio o vídeo de su organización hasta que también configure al menos una directiva (paso 2, anteriormente en este procedimiento) para que admita la conectividad de mensajería instantánea pública.



</div>

1.  Para configurar la Federación y PIC, consulte "habilitar o deshabilitar la Federación y la conectividad [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)de mensajería instantánea pública" en.

2.  Para configurar al menos una directiva para admitir el acceso de usuarios federados, vea "configuración de directivas para controlar el acceso [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)de usuarios públicos" en.

**Para editar un proveedor existente de Messenger o PIC de Skype y configurarlo para Skype empresarial**

1.  En un servidor front-end de Lync Server, abra el shell de administración de Lync Server.

2.  Ejecute los dos comandos siguientes:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Si todavía no tiene un proveedor PIC en el entorno y está creando un nuevo proveedor PIC, no es necesario que ejecute el cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Agregado en Lync Server 2013 CU5 &amp; Lync Desktop Client en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" Dominios que no son de Microsoft para identificarlos y enrutarlos a Skype (el formato de: User (contoso. com) @msn. com). Esta nueva configuración permitirá el formato automático de la dirección del usuario en el cuadro de diálogo "agregar contacto de Skype" con la NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios en el NameDecorationExcludedDomainList ( Actualmente, podemos admitir msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  Desde un cliente de Lync, ahora puede seleccionar Skype como proveedor de PIC y agregar un cliente de Skype especificando su cuenta Microsoft. Además, un usuario de Skype que haya combinado y haya iniciado sesión con su cuenta Microsoft puede enviar una solicitud de contacto a los usuarios de Lync. Para obtener más información acerca de las cuentas de Microsoft, vea [¿Qué es una cuenta de Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obtener más información sobre cómo agregar clientes a Lync, consulte [uso de la conectividad de Lync y Skype en Lync Server 2013 como usuario final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Agregar contacto de Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Agregar contacto de Skype")

4.  Para obtener información detallada sobre cómo modificar proveedores hospedados, vea "crear o editar proveedores federados de SIP [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" en.

Esto completa las tareas administrativas que deben realizarse en el servidor. Ya está configurado para la conectividad entre Lync y Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

