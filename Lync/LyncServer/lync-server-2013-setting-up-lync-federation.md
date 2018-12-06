---
title: 'Lync Server 2013: Configuración de federación de Lync'
TOCTitle: Configuración de federación de Lync
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48274939
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de federación de Lync en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Si ya ha implementado los servidores perimetrales, la adición de las características de los escenarios federados será sencilla. Si no ha configurado los servidores perimetrales, debe hacerlo primero. Para obtener más información, vea: [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación sobre planeación y [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.


> [!NOTE]
> Si va a configurar cualquier combinación de federación XMPP, federación de Lync o conectividad de mensajería instantánea pública, puede implementarlas simultáneamente o una cada vez. Si configura las opciones mediante el generador de topologías y el Shell de administración de Lync Server, y después ejecuta el asistente para la implementación en el servidor perimetral tras la configuración de las opciones de uno, dos o todos los tipos de federación, puede reducir el número de pasos necesarios.



## Configuración de la federación de Lync en el Generador de topologías y en el Asistente para la implementación

1.  En un servidor front-end, abra el Generador de topologías. Expanda los Grupos de servidores perimetrales y, a continuación, haga clic con el botón secundario en Servidor perimetral o Grupo de servidores perimetrales. Seleccione Editar propiedades.

2.  En Editar propiedades en General, seleccione Habilitar federación para este grupo de servidores perimetrales (Puerto 5061). Haga clic en Aceptar.

3.  Haga clic en Acción, seleccione Topología y, finalmente, Publicar. Cuando se le solicite en Publicar la topología, seleccione Siguiente. Una vez completado el proceso de publicación, haga clic en Finalizar.

4.  En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.

5.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.
    
    > [!IMPORTANT]  
    > Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.
    


## Configuración de la federación con socios

1.  Para configurar correctamente una federación con otro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 o Office Communicator 2007, seleccione el tipo de federación de la tabla siguiente y defina los registros DNS SRV, el host DNS (A o AAAA para IPv6) y configure las directivas aplicables al tipo de federación:
    
    
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
    <td><p>Configure el registro SRV con el formato _sipfederationtls._tcp.&lt;nombre del domino externo&gt;, donde el valor del puerto del registro SRV es TCP 5061 y el <strong>Host que ofrece este servicio</strong> está definido como sip. &lt;external domain name&gt; – FQDN de su Servidor perimetral de acceso. Vea <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar DNS para admitir servidores perimetrales en Lync Server 2013</a> para obtener detalles sobre la creación del registro SRV.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>En las versiones anteriores, este tipo de federación se conocía como <strong>Federación abierta mejorada</strong>. La creación del registro SRV es obligatoria para este tipo de federación y permite que otros socios puedan detectar su federación.</p></td>
    </tr>
    <tr class="even">
    <td><p>Dominio de socio permitido</p></td>
    <td><p>Configure el registro SRV con el formato _sipfederationtls._tcp.&lt;nombre del domino externo&gt;, donde el valor del puerto del registro SRV es TCP 5061 y el <strong>Host que ofrece este servicio</strong> está definido como sip. &lt;external domain name&gt; – FQDN de su Servidor perimetral de acceso. Vea <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar DNS para admitir servidores perimetrales en Lync Server 2013</a> para obtener detalles sobre la creación del registro SRV.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>En las versiones anteriores, este tipo de federación se conocía como <strong>Federación abierta mejorada</strong>. La creación del registro SRV es opcional para este tipo de federación y permite que otros socios puedan detectar su federación. Por ello, se trata de una <strong>Federación abierta mejorada</strong> o de un <strong>Dominio de socio detectado</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Servidor de socio permitido</p></td>
    <td><p>Configure el nombre de dominio SIP y el FQDN del Servidor perimetral del socio como un socio de federación en las directivas.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Este tipo de federación es la definición de una relación unilateral y no permite la detección de otros socios de federación. Cada socio de federación está configurado específicamente. En versiones anteriores, esto se conocía como <strong>Federación directa</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p>Proveedor de hospedaje y proveedor de MI pública</p></td>
    <td><p>No son necesarios requisitos de DNS específicos para este tipo de federación.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Crear o editar proveedores federados de SIP hospedados en Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Este tipo de federación define los servicios y proveedores de hospedaje que desea configurar para sus usuarios. Suele usarse para la configuración de proveedores de MI pública como, por ejemplo, Windows Live Messenger, Yahoo! y AOL, así como para el hospedaje de proveedores como, por ejemplo, Lync Online y Office 365.</p>
    
    > [!IMPORTANT]  
	> <ul>
    > <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
    > <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
    > <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
    > </ul>
	
	</td>
    </tr>
    </tbody>
    </table>


2.  Defina y configure los hosts DNS necesarios (A o AAAA para IPv6) así como los registros DNS SRV.

3.  Defina y configure las directivas desde el Panel de control de Lync Server o utilizando el Shell de administración de Lync Server y los cmdlets pertinentes. Para obtener más detalles sobre los cmdlets de Shell de administración de Lync Server, vea [Cmdlets de federación y acceso externo en Lync Server 2013](https://docs.microsoft.com/en-us/powershell/module/skype/)
    

    > [!NOTE]
    > El sistema Lync Room (LRS) no muestra el botón Unirse en las reuniones enviadas por organizadores en socios federados de Lync. Para que aparezca el vínculo para unirse a la reunión en LRS, la organización que envía la reunión debe activar TNEF mediante el cmdlet:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Observe que no es específico de LRS. Outlook y Lync tampoco muestran los vínculos Unirse si las propiedades MAPI no se transportan, pero, en el caso de Outlook, el usuario puede abrir la invitación a la reunión y hacer clic en la dirección URL de la reunión. Cuando se establece TNEFEnabled en True, Exchange 2013 no quita las propiedades MAPI, incluida OnlineMeetingExternalLink, y el botón Unirse se muestra en el aviso.



## Vea también

#### Otros recursos

[Planeación de la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Administración de la federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)

