---
title: 'Lync Server 2013: Mover usuarios a Lync Online'
TOCTitle: Mover usuarios a Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48275547
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover usuarios a Lync Online en Lync Server 2013

 

_**Última modificación del tema:** 2014-05-29_

Antes de iniciar la migración de los usuarios a Lync Online, hay que hacer una copia de seguridad de los datos de usuario asociados con las cuentas que se van a mover, porque no todos los datos de usuario se mueven con la cuenta de usuario. Para obtener información, vea [Requisitos de copia de seguridad y restauración: datos](lync-server-2013-backup-and-restoration-requirements-data.md).

## Migrar la configuración del usuario a Lync Online

La configuración de usuario se mueve con la cuenta de usuario. Algunos valores de configuración locales no se mueven con la cuenta de usuario.

## Mover los usuarios piloto a Lync Online

Antes de empezar a mover usuarios a Lync Online, le recomendamos que mueva unos cuantos usuarios piloto para confirmar que el entorno está correctamente configurado. Después puede verificar que las características y los servicios de Lync funcionan del modo esperado antes de intentar mover más usuarios.

Para mover un usuario local a su inquilino de Skype Empresarial Online, ejecute los siguientes cmdlets en el Shell de administración de Lync Server con las credenciales de administrador de su inquilino de Microsoft Office 365. Sustituya “username@contoso.com” por la información del usuario que quiera mover.

```
$creds=Get-Credential
```
```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** tiene que ser la URL del grupo en el que se está ejecutando el servicio de migración hospedada y tiene que tener el siguiente formato: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc* .

Para determinar la URL del servicio de migración hospedada, consulte la URL del Panel de control de Lync Online de su cuenta de inquilino de Office 365.

**Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365**

1.  Inicie sesión en el inquilino de Office 365 como administrador.

2.  Abra el **Centro de administración de Lync** .

3.  Con el **Centro de administración de Lync** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:
    
    `https://admin0a.online.lync.com`

5.  Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedada.svc**.
    
    La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser como la siguiente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

## Mover usuarios a Lync Online

Puede mover varios usuarios con el cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) con el parámetro –Filter para seleccionar a los usuarios con una propiedad concreta.asignada a las cuentas de usuario como, por ejemplo, RegistrarPool. Después puede canalizar los usuarios devueltos al cmdlet [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser), tal como se muestra en el ejemplo siguiente.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

También puede usar el parámetro –OU para recuperar todos los usuarios del OU especificado, tal como se muestra en el ejemplo siguiente.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

## Compruebe las características y configuración de usuario de Lync Online

Puede comprobar que el usuario se ha movido correctamente de las siguientes maneras:

  - Vea el estado del usuario en el Panel de Control de Lync Online. El indicador visual de los usuarios locales y los usuarios en línea es diferente.

  - Ejecute el siguiente cmdlet:
    
        Get-CsUser -Identity

