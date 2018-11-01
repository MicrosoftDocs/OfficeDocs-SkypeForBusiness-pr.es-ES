---
title: Mover directorios de conferencia
TOCTitle: Mover directorios de conferencia
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48275626
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover directorios de conferencia

 

_**Última modificación del tema:** 2012-10-04_

Antes de retirar un grupo de servidores, necesita realizar el siguiente procedimiento para cada directorio de conferencia en su grupo de Office Communications Server 2007 R2.

## Para mover un directorio de conferencia a Lync Server 2013

1.  Abra Shell de administración de Lync Server.

2.  Para obtener la identidad de los directorios de conferencia de su organización, ejecute los comandos siguientes:
    
        Get-CsConferenceDirectory
    
    Debido a que este cmdlet devuelve todos los directorios de conferencia de su organización, es posible que desee limitar los resultados solo a los grupos que desea retirar. Por ejemplo, si desea retirar un grupo con el nombre de dominio completo (FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Este cmdlet devuelve todos los directorios de conferencia en los que el identificador de servicio contiene el FQDN pool01.contoso.net.

3.  Para mover directorios de conferencia, ejecute lo siguiente para cada directorio de conferencia del grupo:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por ejemplo:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net


> [!NOTE]
> Es posible que se produzca un error, como se muestra abajo, porque el Shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory. Para solucionarlo, cierre la ventana actual, abra un Shell de administración de Lync Server nuevo y vuelva a ejecutar el comando.



![Resultado de error de Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Resultado de error de Move-CsConferenceDirectory")

