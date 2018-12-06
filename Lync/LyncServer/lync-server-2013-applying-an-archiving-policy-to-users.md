---
title: Aplicación de una directiva de archivado a los usuarios
TOCTitle: Aplicación de una directiva de archivado a los usuarios
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48275455
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aplicación de una directiva de archivado a los usuarios

 

_**Última modificación del tema:** 2013-02-23_

Si ha habilitado un usuario para Lync Server 2013 y ha creado una o varias directivas de archivado para los usuarios hospedados en Lync Server 2013, puede implementar la compatibilidad de archivado para determinados usuarios aplicando las directivas adecuadas a dichos usuarios o grupos de usuarios. Por ejemplo, si crea una directiva que permita archivar comunicaciones internas, puede usarla en al menos un usuario o grupo de usuarios para permitir el archivado de las comunicaciones de Lync Server 2013 del usuario.


> [!NOTE]
> Si ha habilitado la integración con Microsoft Exchange en su implementación, las directivas de conservación local de Exchange controlan si el archivado está habilitado para los usuarios hospedados en Exchange 2013 y que tienen sus buzones en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación de implementación.<BR>Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener información más detallada, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores</A> en la documentación de operaciones.



Use el procedimiento descrito en este tema para usar una directiva de usuario de archivado creada previamente en una o varias cuentas de usuario o grupos de usuarios.

## Para aplicar una directiva de archivado a un usuario o grupo de usuarios

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la directiva de usuario de archivado que quiera usar.
    

    > [!NOTE]
    > En configuración <STRONG>&lt;Automática&gt;</STRONG>, aplique la configuración de la instalación del servidor predeterminada. El servidor aplica automáticamente esta configuración.



6.  Haga clic en **Confirmar**.

## Asignar una directiva de archivado por usuario mediante cmdlets de Shell de administración de Lync Server

Las directivas de archivado por usuario también se pueden asignar usando Windows PowerShell de Lync Server y el cmdlet **Grant-CsArchivingPolicy**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignar una directiva de archivado por usuario a un solo usuario

  - Con el siguiente comando se asigna la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## Asignar una directiva de archivado por usuario a varios usuarios

  - Con este comando se asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas hospedadas en el grupo de registradores atl-cs-001.litwareinc.com. Para obtener información sobre el parámetro Filter empleado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## Quitar la asignación de una directiva de archivado por usuario

  - Con el siguiente comando se quita la asignación de cualquier directiva de archivado por usuario que Ken Myer haya tenido asignada previamente. Tras ello, la administración de Ken Myer recaerá en la directiva global o, si existe, en la directiva de sitio local. Una directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy).

## Vea también

#### Otros recursos

[Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md)

