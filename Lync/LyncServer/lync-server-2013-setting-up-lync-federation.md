---
title: 'Lync Server 2013: Configuración de federación de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configuración de federación de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-27_

Si ya ha implementado el servidor o servidores perimetrales, agregue las características de escenarios federados hacia delante. Si no ha configurado servidores perimetrales, debe hacerlo primero. Para obtener más información, vea: [planificación para el acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación e [implementación de acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.

<div>


> [!NOTE]  
> Si pretende configurar cualquier combinación de Federación de XMPP, Federación de Lync o conectividad de mensajería instantánea pública, puede implementarla de forma simultánea o una por vez. Si configura las opciones mediante el generador de topología y el shell de administración de Lync Server, ejecute el Asistente de implementación en el servidor perimetral después de configurar las opciones para uno, dos o tres tipos de Federación, puede reducir el número de pasos necesarios.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configurar la Federación de Lync en el generador de topología y el Asistente para la implementación

1.  En un servidor front-end, abra Topology Builder. Expanda agrupaciones perimetrales y haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales. Seleccione Editar propiedades.

2.  En propiedades de edición, en general, seleccione Habilitar Federación para este grupo perimetral (puerto 5061). Haga clic en Aceptar.

3.  Haga clic en acción, seleccione topología, seleccione publicar. Cuando se le solicite al publicar la topología, haga clic en siguiente. Una vez finalizada la publicación, haga clic en finalizar.

4.  En el servidor perimetral, abra el Asistente para la implementación de Lync Server. Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server. Vuelva a hacer clic en ejecutar.

5.  En instalación de los componentes de Lync Server, haga clic en siguiente. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en finalizar para completar la implementación.
    
    <div>
    

    > [!IMPORTANT]  
    > Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación. Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único. Por ejemplo, si la implementación incluye un grupo perimetral o un solo servidor perimetral implementado en Nueva York y uno implementado en Londres y habilita la compatibilidad con la Federación en el grupo de servidores perimetrales de Nueva York o en el único servidor de borde, la señal de tráfico para usuarios federados pasará por la Nueva York. Grupo Edge o servidor perimetral único. Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configurar la Federación con socios

1.  Para configurar una Federación correcta con otro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 u Office Communicator 2007, seleccione el tipo de Federación de la tabla siguiente y defina los registros SRV de DNS, el host DNS (A o AAAA para IPv6) y configurar directivas aplicables al tipo de Federación:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Tipo de Federación</th>
    <th>Registros DNS</th>
    <th>Definición de Directiva</th>
    <th>Notas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Dominio de socio descubierto</p></td>
    <td><p>Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor del puerto para el registro SRV es TCP 5061 y el <strong>hospedador que ofrece este servicio</strong> se define como SIP. &lt;nombre&gt; de dominio externo: el FQDN de su servicio perimetral de acceso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Las versiones anteriores hacían referencia a este tipo de Federación como <strong>Federación mejorada abierta</strong>. La creación del registro SRV es necesaria para este tipo de Federación y es permitir que otros socios descubran su Federación.</p></td>
    </tr>
    <tr class="even">
    <td><p>Dominio asociado permitido</p></td>
    <td><p>Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor del puerto para el registro SRV es TCP 5061 y el <strong>hospedador que ofrece este servicio</strong> se define como SIP. &lt;nombre&gt; de dominio externo: el FQDN de su servicio perimetral de acceso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Las versiones anteriores hacían referencia a este tipo de Federación como <strong>Federación mejorada</strong>. La creación del registro SRV es opcional para este tipo de Federación y es permitir que otros socios descubran su Federación. Por supuesto, esta es una <strong>Federación mejorada abierta</strong>o un <strong>dominio de socio descubierto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Servidor asociado permitido</p></td>
    <td><p>Configurar el nombre de dominio SIP y el FQDN del servidor perimetral asociado como un asociado de Federación en las directivas</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Este tipo de Federación es la definición de una relación de uno a uno y no permite la detección de otros socios de Federación. Cada socio de Federación está configurado de forma explícita. En versiones anteriores, esto se conocía como <strong>Federación directa</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Proveedor de hospedaje y proveedor de mensajería instantánea pública</p></td>
    <td><p>No se han definido requisitos DNS específicos para este tipo de Federación</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Crear o editar proveedores federados de SIP hospedados en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Este tipo de Federación define los servicios y proveedores de hospedaje que desea configurar para los usuarios. Los usos típicos incluyen la configuración de proveedores de mensajería instantánea pública, como Windows Live Messenger, Yahoo! y AOL, así como los proveedores de hospedaje, como Lync Online y Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
    > <LI>
    > <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
    > <LI>
    > <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definir y configurar los registros DNS (A o AAAA para IPv6) necesarios y los registros SRV de DNS

3.  Defina y configure las directivas mediante el panel de control de Lync Server o mediante el shell de administración de Lync Server y los cmdlets apropiados. Para obtener más información sobre los cmdlets del shell de administración de Lync Server, consulte [cmdlets de Federación y de acceso externo en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) no muestra el botón unirse a las reuniones enviadas por los organizadores en socios federados de Lync. Para que un vínculo de unirse a una reunión aparezca en LRS, la organización remitente debe habilitar TNEF con el siguiente cmdlet:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Ten en cuenta que esto no es específico de LRS. Outlook y Lync tampoco mostrarán vínculos de combinación en este caso, ya que las propiedades de MAPI no se transportan, pero en el caso de Outlook, el usuario puede abrir la invitación a la reunión y hacer clic en la dirección URL de la reunión. Cuando TNEFEnabled se establece en true, Exchange 2013 no elimina las propiedades de MAPI, incluidas OnlineMeetingExternalLink y el botón unirse en el aviso.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Administración de la federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

