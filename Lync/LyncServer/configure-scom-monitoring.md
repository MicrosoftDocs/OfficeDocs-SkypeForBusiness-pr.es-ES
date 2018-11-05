---
title: Configurar la supervisión SCOM
TOCTitle: Configurar la supervisión SCOM
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49889056
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la supervisión SCOM

 

_**Última modificación del tema:** 2012-10-04_

Después de migrar a Microsoft Lync Server 2013, debe completar unas pocas tareas para configurar Lync Server 2013 para trabajar con System Center Operations Manager.

  - Aplique las actualizaciones Lync Server 2010 a un servidor elegido para administrar la lógica de detección central.

  - Actualice la clave de registro del servidor candidato de detección central.

  - Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de detección central candidato.

A continuación se proporcionan instrucciones para realizar cada una de estas tareas.

**Aplique las actualizaciones Lync Server 2010 a un servidor elegido para administrar la lógica de detección central.**

1.  Elija un servidor que tenga los archivos del agente System Center Operations Manager instalados y esté configurado como un nodo de detección candidato.

2.  Aplique las actualizaciones Lync Server 2010 a este servidor. Vea el tema [Aplicar actualizaciones de Lync Server 2010](apply-lync-server-2010-updates.md).

**Actualice la clave de registro del servidor candidato de detección central.**

1.  En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.

2.  En la línea de comandos, escriba:
    
    ```
    New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
    ```
    ```
    New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
    ```

    > [!NOTE]
    > Al cambiar el registro, puede recibir un error que indica que el comando ha fallado si la clave de registro ya existe. Si le pasa esto, puede ignorar el error de forma segura.



**Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de monitor de detección central candidato.**

1.  En un PC donde se haya instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y luego seleccione **Detecciones de objetos**.

2.  Haga clic en **Cambiar ámbito...**

3.  En la página **Objetos de módulo de administración de ámbito**, seleccione **Candidato de detección de LS**.

4.  Reemplace el **Valor efectivo de Candidato de detección de LS** con el nombre del servidor candidato elegido en el procedimiento anterior.

Por último, para finalizar los cambios, reinicie el servicio de estado en el Servidor de administración raíz de System Center Operations Manager.

