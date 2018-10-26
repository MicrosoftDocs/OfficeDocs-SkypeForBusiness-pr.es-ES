---
title: 'Lync Server 2013: Configurar un servidor de administración central existente'
TOCTitle: Configurar un servidor de administración central existente
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48276823
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar un servidor de administración central existente en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Si reutiliza un Servidor de administración central de una implementación existente de Lync Server 2013, debe ejecutar el procedimiento que se describe más abajo para garantizar que Panel de control de Lync Server y Windows PowerShell funciona correctamente.

## Para configurar un Servidor de administración centralexistente

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Utilice el cmdlet **Update-CsAdminRole** para actualizar los roles de control de acceso basados en roles (RBAC) almacenados en Servidor de administración central.
    

    > [!NOTE]
    > No se espera ningún resultado a no ser que ocurra un error.


