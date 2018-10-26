---
title: Copia de seguridad de la configuración y los datos básicos
TOCTitle: Copia de seguridad de la configuración y los datos básicos
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202170(v=OCS.15)
ms:contentKeyID: 52061621
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Copia de seguridad de la configuración y los datos básicos

 

_**Última modificación del tema:** 2014-04-23_

Los siguientes procedimientos utilizan cmdlets de Shell de administración de Lync Server a fin de crear archivos de copia de seguridad para la configuración y los datos de los servicios principales. Para obtener información detallada sobre las herramientas usadas en esta sección, incluida su ubicación, consulte [Requisitos de copia de seguridad y restauracion: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Para obtener más información sobre la copia de seguridad de datos de archivado y supervisión, consulte [Copia de seguridad de las bases de datos de archivado y supervisión](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).


> [!NOTE]
> El paso de esta sección para crear una copia de seguridad del Almacén de administración central incluye los valores y la configuración para el archivado y la supervisión.



Puede ejecutar los cmdlets descritos en esta sección de manera local o remota.

## Para crear copias de seguridad de datos y configuración principales

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en cualquier equipo de la implementación interna.

2.  Para almacenar las copias de seguridad creadas en los pasos siguientes, cree una nueva carpeta compartida y actualice la ruta de acceso a la que hace referencia **$Backup** con la nueva carpeta compartida.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

4.  Cree una copia de seguridad del archivo de configuración del Almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Por ejemplo:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    

    > [!NOTE]
    > Con este paso, se exporta la topología, las directivas y los valores de configuración de Lync Server a un archivo. No es necesario realizar ningún otro paso para crear una copia de seguridad de los datos de la topología.



5.  Copie el archivo de configuración del Almacén de administración central del que se realizó la copia de seguridad en $Backup\\.

6.  Cree una copia de seguridad de los datos del servicio de información de ubicaciones. En la línea de comandos, escriba lo siguiente:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Por ejemplo:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copie el archivo de configuración del servicio de información de ubicaciones del que se realizó la copia de seguridad en $Backup\\.

8.  Cree una copia de seguridad de los datos de usuario en cada base de datos back-end de un Grupo de servidores front-end y cada Servidor Standard Edition. En la línea de comandos, escriba lo siguiente:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Por ejemplo:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copie el archivo de usuario del que se realizó la copia de seguridad en $Backup\\.

10. En cada grupo de servidores que ejecuta la Aplicación de grupo de respuesta, cree una copia de seguridad de la configuración del Grupo de respuesta. Haga lo siguiente:
    
    1.  En la línea de comandos, escriba:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Por ejemplo:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copie el archivo de configuración del Grupo de respuesta del que se realizó la copia de seguridad en $Backup\\.

