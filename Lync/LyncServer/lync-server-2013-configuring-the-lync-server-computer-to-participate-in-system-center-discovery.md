---
title: "Configurar equipo de Lync Server para participar de la detección en System Center"
TOCTitle: "Conf. de l’ordinateur Lync Server pour la particip. à la déc. de System Center"
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48274813
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del equipo de Lync Server para participar de la detección en System Center

 

_**Última modificación del tema:** 2012-10-20_

Para asegurarse de que su nuevo agente Lync Server participa en el proceso de detección de System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en que se haya instalado la consola System Center Operations Manager:

1.  En la pestaña **Administración**, haga clic en **Agente administrado**.

2.  Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en **Propiedades**. En el cuadro de diálogo **Propiedades**, en la pestaña **Seguridad**, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y luego haga clic en **Aceptar**.

Luego de completar el paso 2, reinicie el servicio Agente de estado. (Reiniciar el servicio “obligará” a que se detecte la nueva máquina. Si no reinicia el servicio, podría demorar hasta 4 horas la detección de la nueva máquina por parte de System Center Operations Manager). Una vez que se haya reiniciado el servicio, verifique que no se registra ningún evento de error en el registro de eventos de Operations Manager en ese equipo.

