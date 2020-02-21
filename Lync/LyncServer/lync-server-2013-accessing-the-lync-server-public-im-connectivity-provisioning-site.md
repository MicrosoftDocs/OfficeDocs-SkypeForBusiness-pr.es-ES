---
title: Acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44692fd6267e23c98ecef1ca227cbde5289a44b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Lync Server desde Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2019-03-22_

El proceso de aprovisionamiento de la conectividad de Lync y Skype ha cambiado, en comparación con los métodos anteriores de aprovisionamiento de PIC. Este proceso de aprovisionamiento puede tardar hasta treinta días en completarse. Le recomendamos que primero inicie este proceso, antes de completar los pasos restantes de este documento. Una vez completado el proceso de aprovisionamiento de Lync-Skype para su cuenta, la cuenta se activa y los usuarios elegibles están habilitados para la conectividad de mensajería instantánea pública.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Para aprovisionar la conectividad de Lync y Skype, necesita la siguiente información:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Número de contrato de Microsoft</p></li>
<li><p>Nombre de dominio completo (FQDN) del servicio perimetral de acceso</p></li>
<li><p>Dominio (s) del Protocolo de inicio de sesión (SIP)</p></li>
<li><p>Todos los FQDN adicionales del servicio perimetral de acceso</p></li>
<li><p>Información de contacto</p></li>
</ol></td>
</tr>
</tbody>
</table>

A partir de abril de 2019, detendremos la recopilación y la retención de la información de contacto para los clientes aprovisionados para la Federación de Skype mediante el sitio web pic.lync.com. Se está realizando este cambio para asegurarse de que el sistema de aprovisionamiento de pic.lync.com cumple con las directivas de privacidad de Microsoft. 

Una vez que este cambio se produzca, ya no podremos proporcionar actualizaciones de correo electrónico en los cambios pendientes de aprovisionamiento. Los cambios de aprovisionamiento de PIC se completan normalmente en un plazo de 24-48 horas tras su entrada. Si sigue experimentando problemas de Federación de Skype de 48 horas después de enviar una solicitud de aprovisionamiento, comuníquese con el soporte técnico de Microsoft para investigar el problema.

> [!IMPORTANT]
> Como parte de este cambio, toda la información de contacto especificada anteriormente se purgará de nuestro sistema a finales de abril de 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Para iniciar el proceso de aprovisionamiento para la conectividad entre Lync y Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Inicie sesión en el sitio Web <strong>https://pic.lync.com</strong>, y use su Microsoft Windows Live ID.</p></li>
<li><p>Seleccione el tipo de contrato de licencia de Microsoft.</p></li>
<li><p>Active la casilla, comprobando que ha leído y aceptado los derechos de uso del producto para Lync Server.</p></li>
<li><p>En la página <strong>iniciar una solicitud de aprovisionamiento</strong> , haga clic en el vínculo correspondiente para iniciar una solicitud de aprovisionamiento:</p></li>
<li><p>En la página <strong>especificar información de aprovisionamiento</strong> , escriba el <strong>FQDN del servicio perimetral de acceso</strong>. Por ejemplo, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Después del 1 de julio de 2017, Microsoft requerirá además que los clientes tengan el registro SRV de DNS de Federación implementado para que la conectividad de mensajería instantánea pública siga funcionando.

</li>
<li><p>Escriba al menos uno de los nombres de dominio SIP y, a continuación, haga clic en <strong>Agregar</strong>.</p>



> [!IMPORTANT]
> Se requiere al menos un servidor perimetral de acceso y un dominio SIP para completar el proceso de aprovisionamiento. El dominio SIP y el servidor perimetral de acceso deben estar activos, en funcionamiento y accesibles en la red.

</li>
<li><p>En la lista de <strong>proveedores de servicios públicos de mensajería instantánea</strong>, seleccione <strong>Skype</strong> y haga clic en <strong>siguiente</strong> para agregar información de contacto y enviar la solicitud de aprovisionamiento.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Después de enviar la solicitud de aprovisionamiento, la cuenta puede tardar hasta 30 días en activarse y los usuarios pueden habilitar la conectividad de mensajería instantánea pública.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitación de la Federación y la conectividad de mensajería instantánea pública (PIC)

Una vez que haya enviado la solicitud de aprovisionamiento, puede centrarse en el entorno de Lync Server y en las tareas administrativas necesarias para configurar la conectividad de Lync y Skype. En esta sección, se supone que el administrador de Lync Server ha implementado Lync Server y ha configurado el acceso externo. Para obtener más información sobre cómo configurar el acceso externo para Lync Server, consulte "planeación para el [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) acceso de usuarios externos" en e "implementar [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)el acceso de usuarios externos" en.

Para preparar el entorno de Lync Server para la conectividad de Lync y Skype, el administrador de Lync Server debe completar las tres tareas siguientes:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configurar la Federación y el PIC

La Federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Lync de la organización. Public Instant Messaging Connectivity (PIC) es una clase de Federación y debe configurarse para permitir que los usuarios de Lync se comuniquen con los usuarios de Skype. La Federación y el PIC se configuran mediante el panel de control de Lync Server, que se muestra a continuación.

<div>


> [!IMPORTANT]
> La Federación de PIC ya no es compatible con Live Communication Server 2005 SP1 o con Office Communications Server 2007. Las plataformas compatibles para la Federación de PIC incluyen Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurar al menos una directiva para admitir el acceso de usuarios federados

Mediante el panel de control de Lync Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de Skype pueden colaborar con los usuarios internos de Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Configurar la configuración del proveedor de PIC de Skype para Lync

Mediante el shell de administración de Lync Server, un administrador debe configurar la Directiva de cliente Lync para mostrar Skype como un proveedor de PIC adicional.

<div>


> [!NOTE]
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en mensajería instantánea o conferencias en su organización hasta que también configure al menos una directiva (paso 2, anteriormente en este procedimiento) para que admita la conectividad de mensajería instantánea pública.<BR>Para configurar la Federación y PIC, consulte "habilitar o deshabilitar la Federación y la conectividad <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>de mensajería instantánea pública" en.<BR>Para configurar al menos una directiva para admitir el acceso de usuarios federados, vea "configuración de directivas para controlar el acceso <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>de usuarios públicos" en.



</div>

1.  En un servidor front-end de Lync Server, abra el shell de administración de Lync Server.

2.  Ejecute los dos comandos siguientes:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Si todavía no tiene un proveedor PIC en el entorno y está creando un nuevo proveedor PIC, no es necesario que ejecute el cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Agregado en Lync Server 2013 CU5 &amp; Lync Desktop Client en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" Dominios que no son de Microsoft para identificarlos y enrutarlos a Skype (el formato de: User (contoso. com) @msn. com). Esta nueva configuración permitirá el formato automático de la dirección del usuario en el cuadro de diálogo "agregar contacto de Skype" con la NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios en el NameDecorationExcludedDomainList ( Actualmente, podemos admitir msn.com, live.com, Hotmail.com, outlook.com).

        
        </div>

3.  Desde un cliente de Lync, ahora puede seleccionar Skype como proveedor de PIC y agregar un cliente de Skype especificando su cuenta Microsoft. Además, un usuario de Skype que haya combinado y haya iniciado sesión con su cuenta Microsoft puede enviar una solicitud de contacto a los usuarios de Lync. Para obtener más información acerca de las cuentas de Microsoft, vea [¿Qué es una cuenta de Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obtener más información sobre cómo agregar clientes a Lync, consulte [uso de la conectividad de Lync y Skype en Lync Server 2013 como usuario final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Para obtener información detallada sobre cómo modificar proveedores hospedados, vea "crear o editar proveedores federados de SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" en.

Esto completa las tareas administrativas que deben realizarse en el servidor. Ya está configurado para la conectividad entre Lync y Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Recursos adicionales

[Usar la conectividad de Lync y Skype en Lync Server 2013 como un usuario final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guía de aprovisionamiento para Lync-conectividad de Skype en Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

