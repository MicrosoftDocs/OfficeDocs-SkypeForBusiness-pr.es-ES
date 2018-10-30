---
title: Instalación de los archivos del agente Operations Manager
TOCTitle: Instalación de los archivos del agente Operations Manager
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48276970
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación de los archivos del agente Operations Manager

 

_**Última modificación del tema:** 2012-10-20_

Para instalar los archivos de agente de Operations Manager en el PC, ejecute los pasos siguientes.

1.  En el medio de instalación de System Center, haga doble clic en **SetupOM.exe**.

2.  En la instalación de System Center Operation Manager, haga clic en **Instalar el agente Operations Manager**.

3.  En el Asistente para la instalación de System Center, en la página del Asistente de **Bienvenida a la instalación de System Center Operations Manager**, haga clic en **Siguiente**.

4.  En la página **Carpeta de destino**, seleccione la carpeta en la que se instalarán los archivos agente de Operations Manager y después haga clic en **Siguiente**.

5.  En la página **Configuración del grupo de administración**, seleccione **Especificar información del grupo de administración** y después haga clic en **Siguiente**.

6.  En la página **Configuración del grupo de administración**, escriba el nombre del grupo de administración de Operations Manager en el cuadro **Nombre del grupo de administración** y después escriba el nombre del host del servidor de Operations Manager (por ejemplo, atl-scom-001) en el cuadro **Servidor de administración**. Si ha cambiado el número de puerto que Operations Manager usa, escriba el nuevo número en el cuadro del puerto del servidor de administración. De lo contrario, deje el puerto en el valor predeterminado 5723 y haga clic en **Siguiente**.

7.  En la página **Cuenta de acción del agente**, seleccione **Sistema local** y haga clic en **Siguiente**.

8.  En la página **Microsoft Update**, seleccione **No quiero usar Microsoft Update** y haga clic en **Siguiente**.

9.  En la página **Preparado para instalar**, haga clic en **Instalar**.

10. En la página **Completar el Asistente para instalar System Center Operations Manager**, haga clic en **Finalizar**.

11. Haga clic en **Salir**.

Si usa System Center 2007 R2, compruebe que se haya creado el agente, haciendo clic sucesivamente en **Inicio**, **Todos los programas**, **System Center Operations Manager 2007 R2** y **Shell de Operations Manager**. En el Shell de Operations Manager, escriba el comando de Windows PowerShell siguiente y presione ENTRAR:

    Get-Agent 

Aparecerá en pantalla una lista de todos los agentes de Operations Manager.

Si usa System Center 2012, ejecute este comando desde el shell de Operations Manager 2012:

    Get-SCOMAgent

