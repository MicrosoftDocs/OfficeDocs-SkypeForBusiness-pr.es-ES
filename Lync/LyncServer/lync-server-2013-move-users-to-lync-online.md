---
title: 'Lync Server 2013: mover usuarios a Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dcc72c0f9934aebf28838cfd79899e1ce7aa2bc
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Mover usuarios a Lync Online en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-29_

Antes de iniciar la migración de usuarios a Lync Online, debe hacer una copia de seguridad de los datos de usuario asociados con las cuentas que se van a mover. No todos los datos de usuario se mueven con la cuenta de usuario. Para obtener más información, vea [requisitos de copia de seguridad y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migrar la configuración del usuario a Lync Online

La configuración de usuario se mueve con la cuenta de usuario. Algunas configuraciones locales no se mueven con la cuenta de usuario.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Mover usuarios piloto a Lync Online

Antes de empezar a mover usuarios a Lync Online, es posible que desee mover algunos usuarios piloto para confirmar que el entorno está configurado correctamente. A continuación, puede comprobar que las características y servicios de Lync funcionan como se esperaba antes de intentar mover otros usuarios.

Para mover un usuario local a su inquilino de Lync Online, ejecute los siguientes cmdlets en el shell de administración de Lync Server, con las credenciales de administrador de la organización de Microsoft 365 u Office 365. Reemplace "username@contoso.com" por la información del usuario que desea mover.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL del grupo en el que se está ejecutando el servicio de migración hospedado, en el siguiente formato: https:// \< grupo de FQDN \> /HostedMigration/hostedmigrationService.SVC.

Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del panel de control de Lync Online para la cuenta de la organización de Microsoft 365 u Office 365.

**Para determinar la dirección URL del servicio de migración hospedado de la organización**

1.  Inicie sesión en su organización de Microsoft 365 u Office 365 como administrador.

2.  Abra el **centro de administración de Lync**.

3.  Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**. Una dirección URL de ejemplo tiene un aspecto similar al siguiente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Reemplace **webdir** en la dirección URL con **admin**, lo que dará como resultado lo siguiente:
    
    `https://admin0a.online.lync.com`

5.  Anexe la cadena siguiente a la dirección URL: **/HostedMigration/hostedmigrationservice.SVC**.
    
    La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser similar a la siguiente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Mover usuarios a Lync Online

Puede mover varios usuarios mediante el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) con el parámetro – filter para seleccionar los usuarios con una propiedad específica asignada a las cuentas de usuario, como RegistrarPool. A continuación, puede canalizar los usuarios devueltos al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , como se muestra en el ejemplo siguiente.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

También puede usar el parámetro – OU para recuperar todos los usuarios de la unidad organizativa especificada, como se muestra en el ejemplo siguiente.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Compruebe las características y configuración de usuario de Lync Online

Puede comprobar que el usuario se ha movido con éxito de las siguientes maneras:

  - Vea el estado del usuario en el Panel de Control de Lync Online. El indicador visual de los usuarios locales y los usuarios en línea es diferente.

  - Ejecute el siguiente cmdlet:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

