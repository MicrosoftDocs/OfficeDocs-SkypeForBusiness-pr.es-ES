---
title: "Lync Server 2013: Habilitar o deshabilitar la federación y conectividad de MI pública"
TOCTitle: Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48275986
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013

 

_**Última modificación del tema:** 2013-06-24_

Es obligatorio tener compatibilidad para la federación con el fin de que los usuarios que dispongan de una cuenta con un cliente de confianza o con una organización de un socio, incluso dominios y usuarios de proveedores de mensajería instantánea pública que usted admita, puedan colaborar con los usuarios de su organización. La federación también es necesaria para usar un proveedor de servicios hospedados de Exchange para proporcionar correo de voz a usuarios de Telefonía IP empresarial cuyos buzones de correo se ubican en un servicio hospedado de Exchange como Microsoft Exchange Online. Cuando haya establecido una relación de confianza con estos dominios externos, podrá autorizar a los usuarios de tales dominios a tener acceso a la implementación y a participar en las comunicaciones de Lync Server. Esta relación de confianza se denomina federación y no está relacionada ni depende de una relación de confianza con Active Directory.

Para admitir el acceso de usuarios de dominios federados, es preciso que habilite la federación. Si habilita la federación en su organización, deberá especificar también si se van a implementar las opciones siguientes:

  - **Habilitar la detección de dominios de socios** . Si habilita esta opción, Lync Server usará registros del Sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparezcan en la lista de dominios permitidos, y evaluará automáticamente el tráfico entrante de los socios federados detectados, además de restringir o bloquear este tráfico según el nivel de confianza, cantidad de tráfico y configuración del administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener detalles sobre el control del acceso por parte de los dominios federados, consulte [Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Enviar declinación de responsabilidades de archivado a los socios federados**     Se envía un aviso de declinación de responsabilidades a los socios federados indicando que en su implementación está activado el archivado. Si admite el archivado de las comunicaciones externas con los dominios de socios federados, debe habilitar la notificación de declinación de responsabilidad para avisar a los socios que sus mensajes están siendo archivados.

Si más adelante desea impedir, de forma temporal o permanente, el acceso de usuarios de dominios federados, puede deshabilitar la para su organización. Use el procedimiento que aparece en esta sección para habilitar o deshabilitar el acceso de usuarios federados en su organización, así como para especificar las opciones de federación apropiadas para su organización.


> [!NOTE]
> Si se habilita la federación para la organización solo se indica que los servidores que ejecutan el servicio perimetral de acceso admiten el enrutamiento a dominios federados. Los usuarios de dominios federados no pueden participar en la mensajería instantánea o conferencias en su organización hasta que configure asimismo al menos una directiva para admitir el acceso de usuarios federados. Los usuarios de proveedores de servicios de mensajería instantánea pública no podrán participar en la mensajería instantánea ni en conferencias de la organización hasta que configure también al menos una directiva para admitir conectividad de mensajería instantánea pública. Lync Server no puede usar un servicio hospedado de Exchange para proporcionar servicios de contestador automático, Outlook Voice Access (incluido el correo de voz) o servicios de operador automático para usuarios cuyos buzones de correo se ubican en un servicio hospedado de Exchange hasta que configure una directiva de correo de voz hospedada que proporcione información de enrutamiento. Para obtener detalles sobre la configuración de directivas para la comunicación con usuarios de dominios federados en otras organizaciones, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Administrar dominios federados SIP para la organización en Lync Server 2013</A> en la documentación referente a las operaciones. Por otra parte, si desea admitir la comunicación con usuarios de los proveedores de servicios de mensajería instantánea, es preciso que configure directivas para aportar tal compatibilidad, así como para aportar compatibilidad a los proveedores de servicios individuales que desee. Para obtener información detallada, consulte <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Administrar proveedores federados SIP para la organización en Lync Server 2013</A> en la documentación referente a las operaciones. Para más información sobre la creación de una directiva de correo de voz hospedada, consulte <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Administrar directivas de correo de voz hospedado en Lync Server 2013</A> en la documentación referente a la implementación.



## Para habilitar o deshabilitar el acceso de usuarios federados en la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso** .

4.  En la página **Configuración perimetral de acceso** , haga clic en **Global** , en **Editar** y, a continuación en **Mostrar detalles** .

5.  En **Editar configuración perimetral de acceso** , lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios federados en la organización, active la casilla **Habilitar comunicaciones con usuarios federados** .
    
      - Para deshabilitar el acceso de usuarios federados en la organización, desactive la casilla **Habilitar comunicaciones con usuarios federados** .

6.  Si activó la casilla **Habilitar comunicaciones con usuarios federados** , haga lo siguiente:
    
    1.  Si desea admitir la detección automática de dominios de socios, active la casilla **Habilitar detección de dominio de socio** .
    
    2.  Si la organización admite el archivado de comunicaciones externas, active la casilla **Enviar declinación de responsabilidades de archivado a los socios federados** .

7.  Haga clic en **Confirmar** .

Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server 2013, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para más información, consulte [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) en la documentación referente a la implementación o a las operaciones. Para controlar el acceso en dominios federados específicos, consulte [Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación referente a la implementación o a las operaciones.

## Habilitar o deshabilitar la federación y la conectividad de MI con cmdlets de Windows PowerShell

La federación y la conectividad de mensajería instantánea pública también se pueden administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar la federación y la conectividad de MI pública

  - Para habilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## Para deshabilitar la federación y la conectividad de MI pública

  - Para deshabilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

