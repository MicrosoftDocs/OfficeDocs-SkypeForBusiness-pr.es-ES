---
title: "Lync Server 2013: Configurar directivas para control de acceso de usuarios remotos"
TOCTitle: Configurar directivas para el control del acceso de usuarios remotos
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48275999
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios externos admitidos pueden colaborar con usuarios internos de Lync Server. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario. Las directivas de sitio invalidan la directiva global y las directivas de usuario invalidan las directivas de sitio y globales. Para obtener más información acerca de los tipos de directivas que puede configurar, consulte [Administración de la federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). La configuración de directiva de Lync Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva de Lync Server es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


> [!NOTE]
> Puede configurar directivas para controlar el acceso de usuarios remotos, incluso aunque no se haya habilitado el acceso de usuarios remotos en su organización. Sin embargo, las directivas que se configuran solo son efectivas cuando se habilita el acceso de usuarios remotos en su organización. Para obtener más información sobre cómo habilitar el acceso de usuarios remotos, consulte <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</A>. Además, si especifica una directiva de usuarios para controlar el acceso de usuarios remotos, la directiva se aplica solo a los usuarios que están habilitados en Lync Server y configurados para usar la directiva. Para obtener más información sobre cómo especificar usuarios que puedan iniciar sesión en Lync Server desde ubicaciones remotas, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</A>.



Use el procedimiento siguiente para configurar cada directiva de acceso externo que desea usar para controlar el acceso de usuarios remotos.


> [!NOTE]
> Este procedimiento describe cómo se configura una directiva solo para habilitar comunicaciones con usuarios remotos, pero cada directiva que se configura para permitir el acceso de usuarios remotos puede también configurar el acceso de usuarios federados y usuarios públicos. Para obtener información sobre cómo configurar directivas para permitir usuarios federados, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</A>. Para obtener información sobre cómo configurar directivas para permitir usuarios públicos, consulte <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</A>.



## Para configurar una directiva de acceso de usuarios externos para permitir el acceso de usuarios remotos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo** .

4.  En la página **Directiva de acceso externo** , siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios remotos, haga clic en la directiva global, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles** .
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio** . En **Seleccionar un sitio** , haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar** .
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario** . En **Nueva directiva de acceso externo** , cree un nombre único en el campo **Nombre** que indique los aspectos que cubre la directiva de usuario (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permita comunicaciones a usuarios remotos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles** .

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción** .

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios remotos de la directiva, active la casilla **Habilitar comunicaciones con usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos de la directiva, desactive la casilla **Habilitar comunicaciones con usuarios remotos** .

7.  Haga clic en **Confirmar** .

Para habilitar el acceso de usuarios remotos, también debe permitir el acceso de usuarios remotos en su organización. Para obtener más información, consulte [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación sobre implementación o sobre operaciones.

Si se trata de una directiva de usuario, también debe aplicar la directiva a usuarios a los que quiera permitir conectarse de forma remota. Para obtener más información, consulte [Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) en la documentación referente a la implementación o a las operaciones.

