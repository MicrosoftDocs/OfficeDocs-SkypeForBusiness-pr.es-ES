---
title: "Configuración de un nodo de monitor para participar en la detección en System Center"
TOCTitle: "Conf. nœud observateur pour la participation à la découverte de System Center"
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48274533
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de un nodo de monitor para participar en la detección en System Center

 

_**Última modificación del tema:** 2012-10-22_

Para asegurarse de que su nodo de observador participa en el proceso de detección para System Center Operations Manager, debe completar el siguiente procedimiento en un equipo donde se ha instalado la consola de System Center Operations Manager:

1.  En la pestaña **Administración**, haga clic en **Agente administrado**.

2.  Haga clic con el botón secundario en el nombre del equipo del nodo de observador y, a continuación, haga clic en **Propiedades**. En el cuadro de diálogo **Propiedades**, en la pestaña **Seguridad**, seleccione **Permitir que este agente actúe como proxy y detectar objetos administrados en otros equipos** y, a continuación, haga clic en **Aceptar**.

Tras configurar el nodo de observador para que actúe como proxy, reinicie el equipo del nodo de observador. Una vez se ha reiniciado el equipo, compruebe que no se están registrando eventos de error en el registro de eventos de Operations Manager en ese equipo. Una vez el equipo se ha estado ejecutando durante unos 15 minutos, use la consola de Operations Manager para comprobar que se muestran sus equipos de Lync Server bajo la categoría de **Lync**.

