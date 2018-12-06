---
title: "Lync Server 2013: Acceder a aprovisionam. conectividad de MI pública para Lync Server"
TOCTitle: Acceder al aprovisionamiento de la conectividad de mensajería instantánea pública para Lync Server
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn440174(v=OCS.15)
ms:contentKeyID: 59602840
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Acceder al aprovisionamiento de la conectividad de mensajería instantánea pública para Lync Server desde Lync Server 2013

 

_**Última modificación del tema:** 2017-03-09_

El proceso de aprovisionamiento para la conectividad entre Lync y Skype ha cambiado y ya no es como los métodos anteriores de aprovisionamiento de PIC. Este proceso puede tardar hasta treinta días en completarse. Le recomendamos que inicie este proceso antes de completar el resto de los pasos que aparecen en este documento. Una vez terminado el proceso de aprovisionamiento para Lync y Skype de su cuenta, esta se activará y los usuarios válidos se habilitarán para la conectividad de mensajería instantánea pública.

### Para aprovisionar la conectividad entre Lync y Skype, necesita esta información:

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
<li><p>FQDN de servicios perimetrales de acceso adicionales</p></li>
<li><p>Información de contacto</p></li>
</ol></td>
</tr>
<tr class="even">
<td><ol>
<li><p>Número del contrato de Microsoft</p></li>
<li><p>Nombre de dominio completo (FQDN) del servicio perimetral de acceso</p></li>
<li><p>Dominio(s) del Protocolo de inicio de sesión (SIP)</p></li>
<li><p>FQDN de servicios perimetrales de acceso adicionales</p></li>
<li><p>Información de contacto</p></li>
</ol></td>
</tr>
</tbody>
</table>


### Para iniciar el proceso de aprovisionamiento para la conectividad entre Lync y Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Inicie sesión en el sitio web, <strong>https://pic.lync.com</strong>, con su Microsoft Windows Live ID.</p></li>
<li><p>Seleccione el tipo de contrato de licencia de Microsoft.</p></li>
<li><p>Active la casilla para confirmar que ha leído y acepta los derechos de uso del producto de Lync Server.</p></li>
<li><p>En la página <strong>Iniciar una solicitud de aprovisionamiento</strong>, haga clic en el vínculo adecuado para iniciar la solicitud de aprovisionamiento:</p></li>
<li><p>En la página <strong>Especificar información del aprovisionamiento</strong>, inserte el <strong>FQDN del servicio Access Edge</strong>. Por ejemplo, <strong>accessedge.contoso.com</strong>.</p></li>
<li><p>Inserte al menos un dominio SIP y haga clic en <strong>Agregar</strong>.</p>
<div>

> [!IMPORTANT]  
> Se debe indicar, por lo menos, un servidor perimetral de acceso y un dominio SIP para completar el proceso de aprovisionamiento. El dominio SIP y el servidor perimetral de acceso deben estar activos, funcionar y ser accesibles en la red.


</div></li>
<li><p>En la lista de <strong>proveedores de servicio de mensajería instantánea públicos</strong>, seleccione <strong>Skype,</strong> y haga clic en <strong>Siguiente</strong> para añadir información de contacto y enviar la solicitud de aprovisionamiento.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><ol>
<li><p>Inicie sesión en el sitio web, <strong>https://pic.lync.com</strong>, con su Microsoft Windows Live ID.</p></li>
<li><p>Seleccione el tipo de contrato de licencia de Microsoft.</p></li>
<li><p>Active la casilla para confirmar que ha leído y acepta los derechos de uso del producto de Lync Server.</p></li>
<li><p>En la página <strong>Iniciar una solicitud de aprovisionamiento</strong>, haga clic en el vínculo adecuado para iniciar la solicitud de aprovisionamiento:</p></li>
<li><p>En la página <strong>Especificar información del aprovisionamiento</strong>, inserte el <strong>FQDN del servicio Access Edge</strong>. Por ejemplo, <strong>accessedge.contoso.com</strong>.</p></li>
<li><p>Inserte al menos un dominio SIP y haga clic en <strong>Agregar</strong>.</p>
<div>

> [!IMPORTANT]  
> Se debe indicar, por lo menos, un servidor perimetral de acceso y un dominio SIP para completar el proceso de aprovisionamiento. El dominio SIP y el servidor perimetral de acceso deben estar activos, funcionar y ser accesibles en la red.


</div></li>
<li><p>En la lista de <strong>proveedores de servicio de mensajería instantánea públicos</strong>, seleccione <strong>Skype,</strong> y haga clic en <strong>Siguiente</strong> para añadir información de contacto y enviar la solicitud de aprovisionamiento.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Una vez enviada la solicitud de aprovisionamiento, pueden pasar hasta 30 días hasta que se active la cuenta y se habilite a los usuarios para la conectividad de mensajería instantánea pública.

## Habilitar la federación y la conectividad de mensajería instantánea pública (PIC)

Después de enviar la solicitud de aprovisionamiento, se puede centrar en el entorno de Lync Server y en las tareas administrativas necesarias para configurar la conectividad entre Lync y Skype. En esta sección, presuponemos que el administrador de Lync Server ha implementado Lync Server y ha configurado el acceso externo. Para información adicional sobre cómo configurar el acceso externo en Lync Server, vea "Planeación del acceso de usuarios externos" en [http://go.microsoft.com/fwlink/p/?LinkID=273772](http://go.microsoft.com/fwlink/p/?linkid=273772) e "Implementación del acceso de usuarios externos" en [http://go.microsoft.com/fwlink/p/?LinkID=27378](http://go.microsoft.com/fwlink/p/?linkid=27378).

Para preparar el entorno de Lync Server para la conectividad entre Lync y Skype, el administrador de Lync Server debe completar las tres tareas siguientes:

## 1\. Configurar la federación y la PIC

La federación es necesaria para permitir a los usuarios de Skype que se comuniquen con los usuarios de Lync de su organización. Public Instant Messaging Connectivity (PIC), que es un tipo de federación, se debe configurar para que los usuarios de Lync se puedan comunicar con los usuarios de Skype. La federación y la PIC se configuran usando el panel de control de Lync Server, que verá abajo.

> [!IMPORTANT]  
> La federación PIC ya no es compatible con Live Communication Server 2005 SP1 ni con Office Communications Server 2007. Las plataformas compatibles para la federación PIC incluyen Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2.



## 2\. Configurar al menos una directiva para permitir el acceso de usuarios federados

Los administradores tienen que configurar una o varias directivas de acceso de usuarios externos desde el panel de control de Lync Server para controlar si los usuarios de Skype pueden colaborar con usuarios internos de Lync Server.

## 3\. Establecer la configuración del proveedor de PIC para Lync

En el Shell de administración de Lync Server, los administradores pueden configurar la directiva de cliente de Lync para mostrar Skype como un proveedor de PIC adicional.


> [!NOTE]
> Los usuarios de los proveedores del servicio de conectividad de mensajería instantánea pública (PIC) no pueden participar en sesiones de mensajería instantánea ni en conferencias dentro de su organización hasta que usted no configure también al menos una directiva (paso 2, la tarea anterior a esta) para admitir la conectividad de mensajería instantánea pública.<BR>Para configurar la federación y la PIC, vea "Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública" en <A href="http://go.microsoft.com/fwlink/p/?linkid=306063">http://go.microsoft.com/fwlink/p/?LinkId=306063</A>.<BR>Para configurar al menos una directiva para admitir el acceso de usuarios federados, vea "Configuración de directivas para controlar el acceso de usuarios públicos" en <A href="http://go.microsoft.com/fwlink/p/?linkid=306064">http://go.microsoft.com/fwlink/p/?LinkId=306064</A>.



1.  Desde un servidor front-end de Lync Server, abra el Shell de administración de Lync Server.

2.  Ejecute estos dos comandos:
    
      - Remove-CsPublicProvider -Identity Messenger
    
      - New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger\_16x16.png" -VerificationLevel 2 -Enabled 1

3.  Desde un cliente de Lync, ahora puede seleccionar Skype como el proveedor de PIC y agregar un cliente de Skype especificando su cuenta Microsoft. Además, un usuario de Skype que haya combinado e iniciado sesión con su cuenta Microsoft, puede enviar solicitudes de contacto a usuarios de Lync. Para obtener más información sobre las cuentas Microsoft, consulte [¿Qué es una cuenta Microsoft?](https://support.skype.com/es/faq/fa12059/what-is-a-microsoft-account). Para obtener más información sobre cómo añadir clientes a Lync, consulte [Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Para información detallada sobre cómo modificar proveedores hospedados, vea "Creación o edición de proveedores federados de SIP hospedados" en [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).

Estas son todas las tareas administrativas que se deben llevar a cabo en el servidor. Ahora ya está todo configurado para la conectividad entre Lync y Skype.

## Recursos adicionales

[Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Provisioning guide for Lync-Skype connectivity in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

