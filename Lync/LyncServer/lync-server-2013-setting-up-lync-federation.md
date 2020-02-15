---
title: 'Lync Server 2013: configuración de la Federación de Lync'
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
ms.openlocfilehash: 1972155fa48cd8bc96ee0ec4602bd4b08b2a7b17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configuración de la Federación de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-27_

Si ya ha implementado los servidores perimetrales, la adición de las características de los escenarios federados será sencilla. Si no ha configurado los servidores perimetrales, debe hacerlo primero. Para obtener más información, consulte: [planeación del acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación e [implementación de acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.

<div>


> [!NOTE]  
> Si va a configurar cualquier combinación de federación XMPP, federación de Lync o conectividad de mensajería instantánea pública, puede implementarlas simultáneamente o una cada vez. Si configura las opciones mediante el generador de topologías y el shell de administración de Lync Server, y después ejecuta el asistente para la implementación en el servidor perimetral tras la configuración de las opciones de uno, dos o todos los tipos de federación, puede reducir el número de pasos necesarios.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configuración de la federación de Lync en el Generador de topologías y en el Asistente para la implementación

1.  En un servidor front-end, abra el Generador de topologías. Expanda los Grupos de servidores perimetrales y, a continuación, haga clic con el botón secundario en Servidor perimetral o Grupo de servidores perimetrales. Seleccione Editar propiedades.

2.  En Editar propiedades en General, seleccione Habilitar federación para este grupo de servidores perimetrales (Puerto 5061). Haga clic en Aceptar.

3.  Haga clic en Acción, seleccione Topología y, finalmente, Publicar. Cuando se le solicite en Publicar la topología, seleccione Siguiente. Una vez completado el proceso de publicación, haga clic en Finalizar.

4.  En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.

5.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.
    
    <div>
    

    > [!IMPORTANT]  
    > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configuración de la federación con socios

1.  Para configurar correctamente una federación con otro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 u Office Communicator 2007, seleccione el tipo de Federación de la tabla siguiente y defina los registros DNS SRV, el host DNS (A o AAAA para IPv6) y configure las directivas aplicables al tipo de Federación:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Tipo de federación</th>
    <th>Registros DNS</th>
    <th>Definición de directiva</th>
    <th>Notas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Dominio de socio detectado</p></td>
    <td><p>Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor de puerto para el registro SRV es TCP 5061 y el <strong>host que ofrece este servicio</strong> se define como SIP. &lt;nombre&gt; de dominio externo: el FQDN del servicio perimetral de acceso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>En las versiones anteriores, este tipo de federación se conocía como <strong>Federación abierta mejorada</strong>. La creación del registro SRV es obligatoria para este tipo de federación y permite que otros socios puedan detectar su federación.</p></td>
    </tr>
    <tr class="even">
    <td><p>Dominio de socio permitido</p></td>
    <td><p>Configure el registro SRV del formato _sipfederationtls. _tcp. &lt;nombre&gt;de dominio externo donde el valor de puerto para el registro SRV es TCP 5061 y el <strong>host que ofrece este servicio</strong> se define como SIP. &lt;nombre&gt; de dominio externo: el FQDN del servicio perimetral de acceso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</a> para obtener más información sobre cómo crear el registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Las versiones anteriores hacían referencia a este tipo de Federación como <strong>Federación mejorada</strong>. La creación del registro SRV es opcional para este tipo de federación y permite que otros socios puedan detectar su federación. Por ello, se trata de una <strong>Federación abierta mejorada</strong> o de un <strong>Dominio de socio detectado</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Servidor de socio permitido</p></td>
    <td><p>Configure el nombre de dominio SIP y el FQDN del servidor perimetral de asociados como asociado de Federación en las directivas</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Este tipo de federación es la definición de una relación unilateral y no permite la detección de otros socios de federación. Cada socio de federación está configurado específicamente. En versiones anteriores, esto se conocía como <strong>Federación directa</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p>Proveedor de hospedaje y proveedor de MI pública</p></td>
    <td><p>No son necesarios requisitos de DNS específicos para este tipo de federación.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creación o edición de proveedores federados de SIP hospedados Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Este tipo de federación define los servicios y proveedores de hospedaje que desea configurar para sus usuarios. Suele usarse para la configuración de proveedores de MI pública como, por ejemplo, Windows Live Messenger, Yahoo! y AOL, así como a los proveedores de hospedaje, como Lync Online y Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
    > <LI>
    > <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
    > <LI>
    > <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Defina y configure los hosts DNS necesarios (A o AAAA para IPv6) así como los registros DNS SRV.

3.  Definir y configurar las directivas mediante el panel de control de Lync Server o mediante el shell de administración de Lync Server y los cmdlets adecuados. Para obtener más información sobre los cmdlets del shell de administración de Lync Server, consulte [cmdlets de Federación y de acceso externo en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) no muestra el botón de Unión para las reuniones enviadas por los organizadores en socios federados de Lync. Para que un vínculo para unirse a una reunión aparezca en LRS, la organización de envío debe habilitar la TNEF mediante el siguiente cmdlet:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Tenga en cuenta que esto no es específico de LRS. Outlook y Lync tampoco mostrarán vínculos de combinación en este caso, ya que las propiedades MAPI no se transportan, pero en el caso de Outlook, el usuario puede abrir la invitación a la reunión y hacer clic en la dirección URL de la reunión. Cuando TNEFEnabled se establece en true, Exchange 2013 no quita las propiedades MAPI, incluidas OnlineMeetingExternalLink, y el botón unirse se muestra en el aviso.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Administración de la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

