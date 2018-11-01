---
title: "Supp. d’une coll. existante de par. de conf. de l’enr. des détails des appels"
TOCTitle: "Supp. d’une coll. existante de par. de conf. de l’enr. des détails des appels"
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49889372
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un conjunto existente de opciones de configuración de CDR

 

_**Última modificación del tema:** 2013-02-23_

El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.

Al instalar Microsoft Lync Server 2013, se crea automáticamente una colección única y global de opciones de configuración de CDR. Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales. Por diseño, las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Si elimina la configuración con ámbito en el sitio, el CDR se puede administrar en dicho sitio utilizando la configuración global.

Recuerde que también puede "eliminar" la configuración global. Sin embargo, esta no se quitará realmente. En su lugar, todas las propiedades de dicha colección se restablecerán a sus valores predeterminados. Por ejemplo, la purga está habilitada de forma predeterminada en una colección de opciones de configuración de CDR. Supongamos que modifica la colección global y la purga se deshabilita. Si más adelante elimina la configuración global, todas las propiedades se restablecerán a sus valores predeterminados. En este caso, eso significa que la purga volverá a estar habilitada.

Para quitar las opciones de configuración de CDR, puede usar el Panel de control de Lync Server o el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration).

## Para quitar las opciones de configuración de CDR mediante el Panel de control de Lync Server

1.  En Panel de control de Lync Server, haga clic en **Archivado y supervisión**.

2.  En la pestaña **Registro detallado de llamadas**, seleccione la colección o colecciones de opciones de CDR que se van a quitar. Para seleccionar varias colecciones, haga clic en la primera colección, mantenga presionada la tecla Ctrl y haga clic en otras colecciones.

3.  Haga clic en **Editar** y, a continuación, en **Eliminar**.

4.  En el cuadro de diálogo Panel de control de Lync Server, haga clic en **Aceptar**.

## Para quitar las opciones de configuración de CDR mediante los cmdlets de Shell de administración de Lync Server

Puede eliminar las opciones de configuración del registro detallado de llamadas mediante Windows PowerShell y el cmdlet **Remove-CsCdrConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una colección especificada de opciones de configuración de CDR

  - Este comando quita las opciones de configuración de CDR que se aplican al sitio Redmond:
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

## Para quitar todas las opciones de configuración de CDR que se aplican al ámbito del sitio

  - Este comando quita todas las opciones de configuración de CDR que se aplican al ámbito del sitio:
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

## Para quitar todas las opciones de configuración de CDR que deshabilitan el registro detallado de llamadas

  - Este comando quita todas las opciones de configuración de CDR en las que se ha deshabilitado el registro detallado de llamadas:
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

Para obtener más información, consulte el tema sobre el cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration).

