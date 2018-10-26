---
title: "Aff. des info. de configuration de l’enregistrement des détails des appels"
TOCTitle: "Aff. des info. de configuration de l’enregistrement des détails des appels"
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49889234
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de configuración de CDR

 

_**Última modificación del tema:** 2013-02-23_

El registro detallado de llamadas (CDR) permite realizar un seguimiento de uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.

Cuando se instala Microsoft Lync Server 2013, se crea una colección única y global de opciones de configuración de CDR. Los administradores también tienen la opción de crear colecciones de configuración personalizadas que se pueden aplicar a sitios individuales. Puede ver las opciones de configuración de CDR que se está usando en su organización desde el Panel de control de Lync Server o con el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration).

## Para ver la información de configuración de CDR utilizando el Panel de control de Lync Server

1.  En el Panel de control de Lync Server, haga clic en **Supervisión y archivado**.

2.  En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.

## Para ver la información de configuración de CDR utilizando los cmdlets del Shell de administración de Lync Server

También puede ver las opciones de configuración de CDR con Shell de administración de Lync Server y el cmdlet Get-CsCdrConfiguration. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de configuración de CDR

  - Para ver la información sobre todas las opciones de configuración de CDR, escriba el comando siguiente en el Shell de administración de Lync Server y presione Entrar:
    
        Get-CsCdrConfiguration
    
    La información que aparecerá se asemejará a esto:
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

Para más información, vea el tema de ayuda sobre el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration).

