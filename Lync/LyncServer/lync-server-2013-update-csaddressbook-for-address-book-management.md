---
title: Update-CsAddressBook para la administración de la libreta de direcciones
TOCTitle: Update-CsAddressBook para la administración de la libreta de direcciones
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48274456
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Update-CsAddressBook para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar el cmdlet Update-CsAddressBook de forma local: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

El cmdlet Update-CsAddressBook sustituye al comando **abserver.exe –syncNow** de Office Communications Server. El objetivo del cmdlet es iniciar una sincronización inmediata, en lugar de esperar a la hora programada. El primer comando de ejemplo actualiza todas las libretas de direcciones de la organización. El segundo actualiza solo la libreta de direcciones asociada con el servidor definido.


> [!NOTE]
> En Lync Server 2013, el Replicador de usuarios de Lync Server tomará los cambios de Active Directory y actualizará la base de datos de usuario de Lync Server en función de un intervalo configurado. El Replicador de usuarios de Lync Server también propagará los cambios a la base de datos RTCab rápidamente sin que el administrador deba ejecutar Update-CSAddressBook. Los administradores solamente necesitarán ejecutar Update -CSAddressBook si la descarga del archivo Libreta de direcciones se encuentra habilitado.



Por ejemplo:

```
Update-CsAddressBook
```
```
Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
```

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook)

