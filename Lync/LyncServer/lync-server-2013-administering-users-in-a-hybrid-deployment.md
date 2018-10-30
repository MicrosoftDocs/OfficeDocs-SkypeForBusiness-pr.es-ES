---
title: 'Lync Server 2013: Administrar usuarios en una implementación híbrida'
TOCTitle: Administrar usuarios en una implementación híbrida
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48275533
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar usuarios en una implementación híbrida de Lync Server 2013

 

_**Última modificación del tema:** 2014-05-29_

Puede administrar las directivas y configuraciones de usuario para los usuarios migrados a Lync Online mediante las características de administración de usuarios disponibles en el portal en línea de Microsoft Office 365. Debe iniciar sesión con una cuenta de administrador de inquilinos para realizar tareas administrativas.

## Mover a usuarios localmente

> [!IMPORTANT]  
> Esta sección solo se aplica a usuarios creados y habilitados para Lync local y posteriormente movidos de una implementación local a Lync Online. Si quiere mover a usuarios creados en Lync Online (y que nunca han sido habilitados para Lync en una implementación local) vea <a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Mover usuarios de Lync Online a Lync local en Lync Server 2013</a>.



  - Ejecute los siguientes cmdlets para volver a mover un usuario de Lync Online a Lync local:
    
    ```
    $cred=Get-Credential
    ```
    ```
    Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
    ```
    

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL al grupo donde se ejecuta el servicio de migración hospedado, con el siguiente formato:

*Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc* . Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.

**Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365**

1.  Inicie sesión en el inquilino de Office 365 como administrador.

2.  Abra el **Centro de administración de Lync** .

3.  Con el **Centro de administración de Lync** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:
    
    `https://admin0a.online.lync.com`

5.  Anexe la cadena siguiente a la URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser como la siguiente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

