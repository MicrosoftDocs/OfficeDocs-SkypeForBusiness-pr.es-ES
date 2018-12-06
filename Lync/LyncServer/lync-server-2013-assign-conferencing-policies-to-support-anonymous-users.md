---
title: "Lync Server 2013: Asignar directivas de conferencia para admitir usuarios anónimos"
TOCTitle: Asignar directivas de conferencia para admitir usuarios anónimos
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48275493
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

De forma predeterminada, ningún usuario puede invitar a usuarios anónimos a participar en una reunión. Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencia que admita la participación de usuarios anónimos y aplicar dicha directiva a usuarios específicos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir usuarios anónimos, consulte [Creación o modificación de una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) y [Administración de la federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Use el procedimiento descrito en esta sección para aplicar una directiva de conferencia creada anteriormente a uno o varios usuarios o grupos de usuarios.


> [!NOTE]
> Además de configurar y aplicar una directiva apara permitir a los usuarios invitar a usuarios anónimos, también debe habilitar la compatibilidad con usuarios anónimos para la organización. Para obtener información detallada, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</A>.



## Para configurar una directiva de usuario para la participación anónima en las reuniones

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, siga uno de estos procedimientos:
    
    1.  Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario** . Cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **Habilitaranónimos** para una directiva de usuario que permita las comunicaciones con usuarios anónimos).
    
    2.  Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles**.

4.  En el cuadro de diálogo **Directivas de conferencia**, active la casilla **Permitir a los participantes invitar a usuarios anónimos**.

5.  Haga clic en **Confirmar**.

6.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.

7.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.

8.  En **Editar usuario de Lync Server** en **Directiva de conferencia** , seleccione la directiva de usuario con la configuración de acceso de usuarios anónimos que desea aplicar a este usuario.
    

    > [!NOTE]
    > La configuración <STRONG>&lt;Automática&gt;</STRONG> aplica la configuración de la instalación del servidor predeterminada y el servidor la aplica automáticamente.



Para permitir a los usuarios invitar a usuarios anónimos a conferencias, también tiene que habilitar la compatibilidad con usuarios anónimos en la organización. Para obtener más información, consulte [Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) en la documentación referente a la implementación o a las operaciones.

