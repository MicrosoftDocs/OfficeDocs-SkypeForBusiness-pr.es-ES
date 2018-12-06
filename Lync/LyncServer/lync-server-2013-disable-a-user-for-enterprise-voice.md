---
title: Deshabilitar a un usuario para Enterprise Voice en Lync Server 2013
TOCTitle: Deshabilitar a un usuario para Enterprise Voice en Lync Server 2013
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49889065
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deshabilitar a un usuario para Enterprise Voice en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Use el procedimiento siguiente para deshabilitar Telefonía IP empresarial en una cuenta de usuario que está habilitada para Lync Server 2013.

## Para deshabilitar una cuenta de usuario para Telefonía IP empresarial

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar** .

5.  En la tabla, haga clic en la cuenta de usuario que desee habilitar para Telefonía IP empresarial.

6.  En el menú **Editar** , haga clic en **Mostrar detalles** .

7.  En la página **Editar usuario de Lync Server** , en **Telefonía** , haga clic en cualquier opción excepto **Telefonía IP empresarial** .
    

    > [!NOTE]
    > Para impedir que un usuario haga llamadas de audio o vídeo con Lync, en <STRONG>Telefonía</STRONG>, haga clic en <STRONG>Audio y vídeo deshabilitados</STRONG>.



8.  Haga clic en **Confirmar** .

El usuario ahora no puede usar la función Telefonía IP empresarial.

## Vea también

#### Tareas

[Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  

#### Otros recursos

[Administración de Enterprise Voice para usuarios](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md)

