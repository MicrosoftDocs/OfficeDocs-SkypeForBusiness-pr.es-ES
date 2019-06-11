---
title: Acceder al aprovisionamiento de la conectividad de mensajería instantánea pública para Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6e028afcd3a9affc6c316b7cb373e124e6d5b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Acceder al aprovisionamiento de la conectividad de mensajería instantánea pública para Lync Server desde Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2019-03-22_

El proceso de aprovisionamiento para Lync-conectividad de Skype ha cambiado en comparación con los métodos de aprovisionamiento PIC anteriores. Este proceso de aprovisionamiento puede demorar hasta 30 días en completarse. Recomendamos que inicie este proceso antes de continuar con el resto de los pasos que aparecen en este documento. Una vez completado el proceso de aprovisionamiento de Lync-Skype para su cuenta, la cuenta se activará y los usuarios elegibles estarán habilitados para conectividad de mensajería instantánea pública.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Para aprovisionar la conectividad de Skype con Lync, necesita la siguiente información:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Número del contrato de Microsoft</p></li>
<li><p>Nombre de dominio completo (FQDN) del servicio perimetral de acceso</p></li>
<li><p>Dominio(s) del Protocolo de inicio de sesión (SIP)</p></li>
<li><p>Todos los FQDN del servicio perimetral de acceso adicionales</p></li>
<li><p>Información de contacto</p></li>
</ol></td>
</tr>
</tbody>
</table>

A partir del 2019 de abril, detendremos la recopilación y la retención de la información de contacto de los clientes que estén aprovisionados para la Federación de Skype a través del sitio web de pic.lync.com. Este cambio se está efectuando para garantizar que el sistema de provisioning de pic.lync.com cumpla con las directivas de privacidad de Microsoft. 

Una vez que este cambio se produzca en vivo, ya no podremos proporcionar actualizaciones de correo electrónico en los cambios pendientes de aprovisionamiento. Los cambios de aprovisionamiento PIC suelen completarse en 24-48 horas después de haberlos introducido. Si sigue experimentando problemas de Federación de Skype 48 horas después de enviar una solicitud de aprovisionamiento, comuníquese con el servicio de soporte técnico de Microsoft para investigar más.

> [!IMPORTANT]
> Como parte de este cambio, toda la información de contacto introducida previamente se purgará de nuestro sistema antes de que finalice el abril de 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Para iniciar el proceso de aprovisionamiento de la conectividad de Skype en Lync:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Inicie sesión en el sitio Web <strong>https://pic.lync.com</strong>, usando su Microsoft Windows Live ID.</p></li>
<li><p>Seleccione el tipo de contrato de licencia de Microsoft.</p></li>
<li><p>Active la casilla comprobar que ha leído y que acepta los derechos de uso del producto para Lync Server.</p></li>
<li><p>En la página <strong>iniciar una solicitud de aprovisionamiento</strong> , haga clic en el vínculo correspondiente para iniciar una solicitud de aprovisionamiento:</p></li>
<li><p>En la página <strong>especificar información de aprovisionamiento</strong> , escriba el <strong>FQDN del servicio perimetral de Access</strong>. Por ejemplo, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Después del 1 de julio de 2017, Microsoft necesitará además que los clientes tengan el registro SRV de DNS de Federación implementado para que la conectividad de mensajería instantánea pública siga funcionando.

</li>
<li><p>Escriba al menos uno de los nombres de dominio SIP y, a continuación, haga clic en <strong>Agregar</strong>.</p>



> [!IMPORTANT]
> Se necesita al menos un servidor perimetral de acceso y un dominio SIP para completar el proceso de aprovisionamiento. El dominio SIP y el servidor perimetral de acceso necesitan estar activos, funcionar y ser accesibles en la red.

</li>
<li><p>En la lista de <strong>proveedores de servicios de mensajería instantánea pública</strong>, seleccione <strong>Skype</strong> y haga clic en <strong>siguiente</strong> para agregar información de contacto y enviar la solicitud de aprovisionamiento.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Una vez que se ha enviado la solicitud de aprovisionamiento, la cuenta puede tardar hasta 30 días en activarse y los usuarios deben habilitar la conectividad de mensajería instantánea pública.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitar la federación y la conectividad de mensajería instantánea pública (PIC)

Una vez que haya enviado la solicitud de aprovisionamiento, puede centrarse en el entorno de Lync Server y en las tareas administrativas necesarias para configurar la conectividad de Lync y Skype. En esta sección, damos por hecho que el administrador de Lync Server ha implementado Lync Server y ha configurado el acceso externo. Para obtener más información sobre cómo configurar el acceso externo para Lync Server, consulte "planear el acceso de [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) usuarios externos" en e "implementar el acceso [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)externo de usuarios" en.

Para preparar el entorno de Lync Server para la conectividad de Skype Lync, el administrador de Lync Server debe completar las tres tareas siguientes:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Configurar la federación y la PIC

La Federación es necesaria para que los usuarios de Skype puedan comunicarse con los usuarios de Lync de su organización. La conectividad de mensajería instantánea pública (PIC) es una clase de Federación y debe estar configurada para permitir que los usuarios de Lync se comuniquen con usuarios de Skype. La Federación y el PIC se configuran mediante el panel de control de Lync Server, que se muestra a continuación.

<div>


> [!IMPORTANT]
> La federación de PIC ya no es compatible con Live Communication Server 2005 SP1 ni con Office Communications Server 2007. Las plataformas compatibles con la Federación de PIC incluyen Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Configurar al menos una directiva para permitir el acceso de usuarios federados

Con el panel de control de Lync Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de Skype pueden colaborar con usuarios internos de Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Configurar la configuración del proveedor PIC de Skype para Lync

Con el shell de administración de Lync Server, un administrador debe configurar la Directiva de cliente de Lync para mostrar Skype como proveedor de PIC adicional.

<div>


> [!NOTE]
> Los usuarios de los proveedores del servicio de conectividad de mensajería instantánea pública (PIC) no pueden participar en sesiones de mensajería instantánea ni en conferencias dentro de su organización hasta que no configure también al menos una directiva (paso 2, la tarea anterior a esta) para admitir la conectividad de la mensajería instantánea pública. <BR>Para configurar la Federación y el PIC, consulte "habilitar o deshabilitar la Federación y la <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>conectividad de mensajería instantánea pública" en.<BR>Para configurar al menos una directiva para admitir el acceso de usuarios federados, consulte "configurar directivas para controlar el acceso de <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>usuarios públicos" en.



</div>

1.  Desde un servidor front-end de Lync Server, abra el shell de administración de Lync Server.

2.  Ejecute estos dos comandos:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Si todavía no tiene un proveedor PIC en su entorno y está creando un nuevo proveedor PIC, no necesita ejecutar el cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Agregado en el cliente de escritorio &amp; de lync Server 2013 CU5 en el SP1 de Office 2013, la NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" Dominios que no son de Microsoft para identificar y enrutarlos a Skype (el formato de: usuario (contoso. com) @msn. com). Esta nueva configuración permitirá la conversión automática del formato de la dirección que los usuarios introduzcan en el cuadro de diálogo “Agregar contacto de Skype” con NameDecorationRoutingDomain (que se necesita establecer en msn.com) si no contiene los dominios en NameDecorationExcludedDomainList (actualmente, se admite msn.com, live.com, Hotmail.com y outlook.com).

        
        </div>

3.  Desde un cliente de Lync, ahora puede seleccionar Skype como proveedor PIC y agregar un cliente de Skype especificando su cuenta Microsoft. Además, un usuario de Skype que ha fusionado y ha iniciado sesión con su cuenta de Microsoft puede enviar una solicitud de contacto a los usuarios de Lync. Para obtener más información sobre las cuentas de Microsoft, vea [¿Qué es una cuenta de Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obtener más información sobre cómo agregar clientes a Lync, consulte [usar Lync: conectividad de Skype en Lync Server 2013 como usuario final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Para obtener información detallada sobre cómo modificar proveedores hospedados, vea "crear o editar proveedores federados de SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)alojados" en.

Estas son todas las tareas administrativas que se necesitan llevar a cabo en el servidor. Ya está configurado para Lync: conectividad de Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Recursos adicionales

[Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guía de aprovisionamiento para la conectividad entre Lync y Skype en Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

