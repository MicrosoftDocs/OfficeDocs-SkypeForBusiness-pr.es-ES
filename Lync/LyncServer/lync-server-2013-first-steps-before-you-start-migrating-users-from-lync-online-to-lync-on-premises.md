---
title: "1ères étapes av. début migration des util. de Lync Online vers Lync local"
TOCTitle: "1ères étapes av. début migration des util. de Lync Online vers Lync local"
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62247381
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Primeros pasos antes de empezar a migrar usuarios de Lync Online a Lync local

 

_**Última modificación del tema:** 2016-12-08_

Antes de empezar a mover usuarios de Lync Online a su entorno local, compruebe que se cumplan las condiciones siguientes:

  - Su entorno de Lync Server local debe estar completamente implementado y validado. Para obtener más información, vea [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Su inquilino de Lync Online debe estar configurado para ofrecer acceso remoto a PowerShell.
    
    Para ello, primero instale el módulo Skype Empresarial Online para Windows PowerShell, que puede obtener aquí: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).
    
    Después de instalar el módulo, puede establecer una sesión remota escribiendo los siguientes cmdlets en Shell de administración de Lync Server:
    
    ```
    Import-Module LyncOnlineConnector
    ```
    ```
    $cred = Get-Credential
    ```
    ```
    $CSSession = New-CsOnlineSession -Credential $cred
    ```
    ```
    Import-PSSession $CSSession -AllowClobber
    ```
  Si desea más información sobre cómo establecer una sesión PowerShell remota con Skype Empresarial Online, consulte [Conectar con Lync Online mediante Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
  Si desea más información sobre el uso del módulo de PowerShell Skype Empresarial Online, consulte [Administrar Lync Online con Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Su Lync Online debe estar configurado para un espacio de direcciones SIP compartido. Para hacerlo, primero inicie una sesión de PowerShell remota con Lync Online. A continuación, ejecute el cmdlet siguiente:
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

Cuando haya realizado estos pasos, podrá empezar a mover usuarios a [Migrar usuarios de Lync Online a Lync local](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

