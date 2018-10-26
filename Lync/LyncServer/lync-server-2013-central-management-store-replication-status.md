---
title: "Skype Entreprise Server 2015 : statut de réplic. du magasin central de gest."
TOCTitle: Estado de replicación del almacén de administración central
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn720926(v=OCS.15)
ms:contentKeyID: 62246717
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Estado de replicación del almacén de administración central en Lync Server 2013

 

_**Última modificación del tema:** 2015-01-26_

Cuando un administrador hace un cambio de algún tipo en Lync Server (por ejemplo, si crea una nueva directiva de voz o cambia la configuración del servidor de libreta de direcciones), dicho cambio se registra en el Almacén de administración central. A su vez, el cambio debe replicarse en todos los equipos que ejecutan servicios o roles de servidor de Lync Server.

Para replicar datos, el replicador maestro (que se ejecuta en el servidor de administración central) crea una instantánea de los datos de configuración cambiados. Una copia de esta instantánea se envía a cada equipo que ejecuta servicios o roles de servidor de Lync Server. En estos equipos, un agente de replicación recibe la instantánea y carga los datos cambiados. Después, el agente envía un mensaje al replicador maestro para informar del estado de replicación más reciente.

El cmdlet Get-CsManagementStoreReplicationStatus permite verificar el estado de replicación de cualquiera de los equipos Lync Server de la organización.

¿Quién puede ejecutar este cmdlet? De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar localmente el cmdlet Get-CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Para obtener la lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluido cualquier rol RBAC personalizado que usted haya creado), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

## Vea también

#### Otros recursos

[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsManagementStoreReplicationStatus)

