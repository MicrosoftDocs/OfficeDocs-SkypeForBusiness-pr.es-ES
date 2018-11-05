---
title: "Instalación de archivos principales de Lync Server 2013 y la base de datos RTCLocal"
TOCTitle: "Inst. des fich. Lync Server 2013 princ. et de la base de données RTCLocal"
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48274632
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación de los archivos principales de Lync Server 2013 y la base de datos RTCLocal

 

_**Última modificación del tema:** 2012-10-20_

Para instalar los archivos principales de Lync Server 2013 en un equipo, lleve a cabo el procedimiento siguiente. La base de datos RTCLocal se instalará automáticamente cuando se instalen los archivos principales. Tenga en cuenta que no necesita instalar SQL Server en los nodos de supervisor. En su lugar, SQL Server Express se instala automáticamente.

Para instalar los archivos principales de Lync Server 2013 y la base de datos RTCLocal:

1.  En el equipo nodo de supervisor, haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  En la ventana de la consola, escriba el siguiente comando, presione ENTRAR y use la ruta de acceso que corresponda a sus archivos de instalación de Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Para comprobar que los componentes principales de Lync Server se han instalado correctamente, haga clic en **Inicio**, **Todos los programas**, **Lync Server 2013** y, a continuación, haga clic en **Shell de administración de Lync Server**. En el Shell de administración de Lync Server 2013, escriba el comando siguiente de Windows PowerShell y presione ENTRAR:

    Get-CsWatcherNodeConfiguration

La primera vez que ejecute este comando, no se devolverá ningún dato porque todavía no se han configurado equipos de nodo de supervisor. Siempre que el comando se ejecute sin error, puede suponer que la instalación de Lync Server se ha llevado a cabo correctamente.

Si el equipo de nodo de supervisor se encuentra dentro del perímetro de su red, ejecute el comando siguiente para comprobar la instalación de Lync Server 2013:

    Get-CsPinPolicy

Recibirá una información similar a la siguiente, en función de las directivas de número de identificación personal (PIN) configuradas para usar en su organización:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Si aparece información sobre las directivas PIN, quiere decir que los componentes principales se han instalado correctamente.

