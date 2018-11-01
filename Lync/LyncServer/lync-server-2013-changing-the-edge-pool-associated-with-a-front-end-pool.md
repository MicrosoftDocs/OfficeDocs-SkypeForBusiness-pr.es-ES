---
title: "Lync Server 2013: Cambio del grupo perimetrale asociado a servidores front-end"
TOCTitle: Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49889045
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Si se produce un error en un grupo perimetral pero el grupo de front-end del mismo sitio sigue en ejecución, deberá establecer el grupo de servidores front-end para que use un grupo perimetral de otro sitio hasta que se restablezca el grupo perimetral en el que se ha producido el error.

## Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end

1.  En el Generador de topologías, navegue hasta el nombre del grupo de servidores front-end que desea cambiar.

2.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **Asociaciones**, en **Asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.

4.  Haga clic en **Aceptar**.

## Vea también

#### Conceptos

[Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

