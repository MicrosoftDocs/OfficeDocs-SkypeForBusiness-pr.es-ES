---
title: "Lync Server 2013: Configurar directivas para controlar el acceso de usuarios públicos"
TOCTitle: Configurar directivas para controlar el acceso de usuarios públicos
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48274354
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La conectividad de mensajería instantánea pública permite a los usuarios de la organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores de servicios de mensajería instantánea pública, como la red Windows Live de servicios de Internet, Yahoo\! y AOL. Se configuran una o más directivas de acceso de usuario externas para controlar si los usuarios públicos pueden colaborar con usuarios de Lync Server internos. La conectividad de mensajería instantánea pública es una característica agregada que depende de la configuración de su implementación y usuarios. También depende del aprovisionamiento del servicio en el proveedor de mensajería instantánea público. Para obtener información acerca de cómo aprovisionar su implementación para usar los proveedores públicos, vea la guía “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” (Guía de aprovisionamiento para la conectividad de mensajería instantánea pública para Microsoft Lync Server, Office Communications Server y Live Communications Server): <http://go.microsoft.com/fwlink/?linkid=269821>

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>


Para obtener acceso al sitio de aprovisionamiento para la conectividad de mensajería pública para Microsoft Lync Server, use el siguiente vínculo: <http://go.microsoft.com/fwlink/?linkid=212638>

Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios públicos. Para obtener detalles acerca de los tipos de directivas que puede configurar, vea [Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) en la documentación de implementación o en la documentación de planeación. La configuración de directiva de Lync Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva de Lync Server es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

En el caso de las invitaciones de mensajería instantánea, la respuesta depende del software cliente. Se acepta la solicitud a menos que los remitentes externos queden explícitamente bloqueados por una regla configurada por el usuario (es decir, la configuración de las listas **Permitir** y **Bloquear** del cliente del usuario). Además, las invitaciones de mensajería instantánea se pueden bloquear si un usuario opta por bloquear todos los mensajes instantáneos de los usuarios que no estén en su lista **Permitir**.


> [!NOTE]
> Puede configurar directivas para controlar el acceso de usuarios públicos, incluso aunque no haya habilitado una federación para la organización. Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización. Para obtener más información acerca de cómo habilitar la federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación referente a la implementación o a las operaciones. Además, si especifica una directiva de usuario para controlar el acceso de usuarios públicos, la directiva solo se aplica a usuarios habilitados para Lync Server y configurados para usar la directiva. Para obtener más información acerca de cómo especificar usuarios públicos que puedan iniciar la sesión en Lync Server, vea <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</A> en la documentación referente a la implementación o a las operaciones.



Use el procedimiento que se describe a continuación para configurar una directiva que admita el acceso de usuarios de uno o varios proveedores de mensajería instantánea pública.

## Para configurar una directiva de acceso externo para permitir el acceso de usuarios públicos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo**, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios públicos, haga clic en la directiva global, en **Editar** y en **Mostrar detalles**.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **EnablePublicUsers** para una directiva de usuario que permita comunicaciones para usuarios públicos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles**.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios públicos para la directiva, active la casilla **Habilitar comunicaciones con usuarios públicos**.
    
      - Para deshabilitar el acceso de usuarios públicos para la directiva, desactive la casilla **Habilitar comunicaciones con usuarios públicos**.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios públicos, también debe permitir la federación en su organización. Para obtener detalles, vea [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios públicos que desee que puedan colaborar con usuarios públicos. Para obtener detalles, vea [Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md).

## Vea también

#### Tareas

[Crear o editar proveedores federados de SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  

#### Otros recursos

[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

