---
title: Restaurar un servidor miembro de Enterprise Edition
TOCTitle: Restaurar un servidor miembro de Enterprise Edition
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202191(v=OCS.15)
ms:contentKeyID: 52061776
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar un servidor miembro de Enterprise Edition

 

_**Última modificación del tema:** 2013-02-18_

Si se produce un error en un servidor que ejecuta uno de los siguientes roles de servidor, siga el procedimiento que se describe en este tema para restaurarlo.

  - Servidor front-end

  - Servidor de mediación

  - Director

  - Servidor de chat persistente

  - Servidor perimetral

> [!TIP]  
> Se recomienda realizar una copia de la imagen del sistema antes de iniciar la restauración, de forma que pueda usar esta imagen como punto de reversión en caso de que haya errores durante la restauración. Es posible que desee realizar la copia de la imagen después de instalar el sistema operativo y SQL Server y restaurar o volver a inscribir los certificados.



## Para restaurar un servidor miembro

1.  Comience con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el servidor con el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    

    > [!NOTE]
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.



2.  Inicie sesión en el servidor que está restaurando con una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins.

3.  Busque la carpeta o medios de instalación de Lync Server e inicie el Asistente para la instalación de Lync Server ubicado en \\setup\\amd64\\Setup.exe.

4.  Siga el Asistente para la instalación para realizar lo siguiente:
    
    1.  Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **Paso 2: Instalar o desinstalar componentes de Lync Server** para instalar el rol de servidor de Lync Server.
    
    3.  Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.
    
    Para obtener información detallada sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación correspondiente al rol de servidor que esté restaurando.

