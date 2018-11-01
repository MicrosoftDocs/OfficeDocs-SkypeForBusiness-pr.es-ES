---
title: "Actualización o mejora de servidor back-end o Standard Edition en Lync Server 2013"
TOCTitle: "Màn ou màj serv. princ. ou serveur Standard Edition Server dans LS 2013"
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49889823
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Actualización o mejora de un servidor back-end o un servidor Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

En este tema se explica cómo instalar una actualización en un Servidor back-end de Enterprise Edition o en un servidor Standard Edition.

Si un servidor back-end está inactivo al menos 30 minutos mientras se actualiza, los usuarios podrían entrar en modo de resistencia. Cuando termine la actualización y los servidores back-end se conecten de nuevo a los servidores front-end del grupo, los usuarios volverán al modo de funcionalidad total. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.

## Para actualizar un servidor back-end o un servidor Standard Edition

1.  Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.

2.  Descargue la actualización extráigala en el disco duro local.

3.  Inicie el Shell de administración de Lync Server: Haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, a continuación, en **Shell de administración de Lync Server**.

4.  Detenga los servicios de Lync Server. En la línea de comandos, escriba:
    
        Stop-CsWindowsService

5.  Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
        net stop w3svc

6.  Cierre todas las ventanas de el Shell de administración de Lync Server.

7.  Instale la actualización.

8.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

9.  Vuelva a detener los servicios de Lync Server para capturar ensamblados -d de la caché global de ensamblados (GAC). En la línea de comandos, escriba:
    
        Stop-CsWindowsService

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
        net start w3svc

11. Aplique los cambios realizados por LyncServerUpdateInstaller.exe a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:
    
      - Si este es un Enterprise EditionServidor back-end y las bases de datos no se combinan en este servidor, como las bases de datos de archivado o de supervisión, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Si este es un Enterprise EditionServidor back-end y hay bases de datos combinadas en este servidor, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Si este es un servidor Standard Edition, escriba lo siguiente en la línea de comandos:
        
            Install-CsDatabase -Update -LocalDatabases

