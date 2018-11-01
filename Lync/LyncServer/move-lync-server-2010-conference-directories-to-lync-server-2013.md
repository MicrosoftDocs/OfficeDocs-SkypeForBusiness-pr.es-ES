---
title: "Déplacement des annuaires de conf. Lync Server 2010 vers Lync Server 2013"
TOCTitle: Mover directorios de conferencia
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62388670
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover directorios de conferencia

 

_**Última modificación del tema:** 2016-12-08_

Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia en su grupo de Lync Server 2010.

## Para mover un directorio de conferencia a Lync Server 2013

1.  Abra Shell de administración de Lync Server.

2.  Para obtener la identidad de los directorios de conferencia de la organización, ejecute el siguiente comando:
    
        Get-CsConferenceDirectory
    
    El comando anterior devuelve todos los directorios de conferencia de la organización. Por eso, es posible que desee limitar los resultados al grupo de servidores que se está retirando. Por ejemplo, si está retirando el grupo de servidores con el nombre de dominio completo (FQDN) pool01.contoso.net, utilice este comando para limitar los datos devueltos a los directorios de conferencia del grupo de servidores:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Ese comando solo devuelve los directorios de conferencia donde la propiedad ServiceID contiene el FQDN pool01.contoso.net.

3.  Para mover directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia del grupo:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por ejemplo, para mover el directorio de conferencia 3, utilice este comando especificando un grupo de Lync Server 2013 como TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Si desea mover todos los directorios de conferencia a un grupo, utilice un comando similar al siguiente:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Vea el documento "Desinstalación de Microsoft Lync Server 2010 y eliminación de roles de servidor (Uninstalling Microsoft Lync Server 2010 and Removing Server Roles)" (que puede descargarse en [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) para obtener instrucciones globales paso a paso sobre cómo retirar grupos de servidores de Lync 2010.

Al mover directorios de conferencia puede encontrar el siguiente error:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Normalmente, este error se produce cuando Shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory para completar una tarea. Para resolver el problema, cierre la instancia actual de la Shell de administración, luego abra una nueva instancia de la shell y vuelva a ejecutar el comando para mover el directorio de conferencia.

