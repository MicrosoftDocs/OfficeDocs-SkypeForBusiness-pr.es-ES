---
title: Quitar un grupo de servidores front-end o un servidor Standard Edition
TOCTitle: Quitar un grupo de servidores front-end o un servidor Standard Edition
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49889357
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar un grupo de servidores front-end o un servidor Standard Edition

 

_**Última modificación del tema:** 2012-10-04_

Este tema lo guiará por el proceso de eliminar un Grupo de servidores front-end o un Servidor front-end Standard Edition. Cuando elimina un Grupo de servidores front-end, elimina los Servidor front-end que pertenece al grupo como parte del proceso de eliminación de grupo. Cuando elimina un Servidor front-end Standard Edition, debe eliminar la definición del almacén SQL de Generador de topologías.

## Para eliminar un grupo de servidores Front End

1.  Abra Generador de topologías.

2.  Desplácese hasta el nodo de Lync Server 2010.

3.  Amplíe **Grupos de servidores front-end Enterprise Edition** , amplíe el Grupo de servidores front-end, haga clic con el botón secundario en el Grupo de servidores front-end que desea eliminar y luego haga clic en **Eliminar** .

4.  Publique la topología, compruebe el estado de replicación y después ejecute el Asistente para la implementación de Lync Server según sea necesario.

## Para eliminar un servidor Front End Standard Edition

1.  Abra Generador de topologías.

2.  Desplácese hasta el nodo de Lync Server 2010.

3.  Amplíe **Servidores front-end Standard Edition** , haga clic con el botón secundario en el Servidor front-end que desea eliminar y luego haga clic en **Eliminar** .

4.  Amplíe **Almacenes SQL** , haga clic con el botón secundario en la base de datos SQL Server asociada con el Servidor front-end Standard Edition y luego haga clic en **Eliminar** .
    
    > [!IMPORTANT]  
    > Debe eliminar la definición de las bases de datos SQL Server colocadas del Servidor front-end Standard Edition.
    


5.  Publique la topología, compruebe el estado de replicación y después ejecute el Asistente para la implementación de Lync Server según sea necesario.

