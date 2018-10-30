---
title: "Aplicar una directiva de chat persistente a un usuario o grupo de usuarios"
TOCTitle: Aplicar una directiva de chat persistente a un usuario o grupo de usuarios
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48275833
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aplicar una directiva de chat persistente a un usuario o grupo de usuarios en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Si un usuario se ha habilitado para Lync Server 2013, puede aplicar las políticas apropiadas para que usuarios específicos las habiliten o deshabiliten para Servidor de chat persistente.


> [!NOTE]
> Para configurar y usar el Servidor de chat persistente, primero debe usar el Generador de topologías a fin de agregar la compatibilidad del Servidor de chat persistente con la topología y, luego, publicar la topología. Para más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.<BR>Para establecer las opciones de configuración del Servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013</A> en la documentación sobre implementación.



Utilice el procedimiento de este tema para aplicar una directiva de usuario de Chat persistente creada anteriormente a una o más cuentas de usuario o grupos de usuarios.

## Para aplicar una directiva de usuario de Chat persistente a una cuenta de usuario

1.  En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el Panel de control de Lync Server o abra la ventana del explorador y, después, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para abrir el Panel de control de Lync Server, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles** .

5.  En **Editar usuario de Lync Server**, en **Directiva de Chat persistente**, seleccione la directiva de usuario de Chat persistente que desea aplicar.
    

    > [!NOTE]
    > La configuración <STRONG>&lt;Automático&gt;</STRONG> se aplica a la directiva efectiva predeterminada. Esta configuración se aplica automáticamente por el servidor.



6.  Haga clic en **Confirmar** .

